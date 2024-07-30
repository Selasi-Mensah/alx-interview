What is N Queen Problem?
In N-Queen problem, we are given an NxN chessboard and we have to place N number of queens on the board in such a way that no two queens attack each other. A queen will attack another queen if it is placed in horizontal, vertical or diagonal points in its way. The most popular approach for solving the N Queen puzzle is Backtracking.

Input Output Scenario
Suppose the given chessboard is of size 4x4 and we have to arrange exactly 4 queens in it.
Backtracking Approach to solve N Queens Problem
In the naive method to solve n queen problem, the algorithm generates all possible solutions. Then, it explores all of the solutions one by one. If a generated solution satisfies the constraint of the problem, it prints that solution.

Follow the below steps to solve n queen problem using the backtracking approach −

Place the first queen in the top-left cell of the chessboard.

After placing a queen in the first cell, mark the position as a part of the solution and then recursively check if this will lead to a solution.

Now, if placing the queen doesn’t lead to a solution. Then go to the first step and place queens in other cells. Repeat until all cells are tried.

If placing queen returns a lead to solution return TRUE.

If all queens are placed return TRUE.

If all rows are tried and no solution is found, return FALSE.

Example
The following example illustrates how to solve the n-queen problem with 5 queens in various programming languages.

C
C++
Java
Python
Open Compiler
#include<stdio.h>
#define BOARD_SIZE 5
void displayChess(int chBoard[BOARD_SIZE][BOARD_SIZE]) {
   for (int row = 0; row < BOARD_SIZE; row++) {
      for (int col = 0; col < BOARD_SIZE; col++)
         printf("%d ", chBoard[row][col]);
      printf("\n");
   }
}
int isQueenPlaceValid(int chBoard[BOARD_SIZE][BOARD_SIZE], int crntRow, int crntCol) {
   // checking if queen is in the left or not    
   for (int i = 0; i < crntCol; i++)    
      if (chBoard[crntRow][i])
         return 0;
   for (int i = crntRow, j = crntCol; i >= 0 && j >= 0; i--, j--)
      //checking if queen is in the left upper diagonal or not
      if (chBoard[i][j])       
         return 0;
   for (int i = crntRow, j = crntCol; j >= 0 && i < BOARD_SIZE; i++, j--)
      //checking if queen is in the left lower diagonal or not
      if (chBoard[i][j])      
         return 0;
   return 1;
}
int solveProblem(int chBoard[BOARD_SIZE][BOARD_SIZE], int crntCol) {
   //when N queens are placed successfully
   if (crntCol >= BOARD_SIZE)           
      return 1;
   // checking placement of queen is possible or not
   for (int i = 0; i < BOARD_SIZE; i++) {     
      if (isQueenPlaceValid(chBoard, i, crntCol)) {
         //if validate, place the queen at place (i, col)
         chBoard[i][crntCol] = 1;     
         //Go for the other columns recursively
         if (solveProblem(chBoard, crntCol + 1))    
            return 1;          
         //When no place is vacant remove that queen   
         chBoard[i][crntCol] = 0;        
      }
   }
   return 0;      
}
int displaySolution() {
   int chBoard[BOARD_SIZE][BOARD_SIZE];
   for(int i = 0; i < BOARD_SIZE; i++)
      for(int j = 0; j < BOARD_SIZE; j++)
         //set all elements to 0
         chBoard[i][j] = 0;      
   //starting from 0th column
   if (solveProblem(chBoard, 0) == 0) {     
      printf("Solution does not exist");
      return 0;
   }
   displayChess(chBoard);
   return 1;
}
int main() {
   displaySolution();
   return 0;
}
Output
1 0 0 0 0 
0 0 0 1 0 
0 1 0 0 0 
0 0 0 0 1 
0 0 1 0 0