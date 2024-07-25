What Is a UTF8 Validator?

With this tool you can easily find all errors in UTF8-encoded text. Valid UTF8 has a specific binary format. If it's a single byte UTF8 character, then it is always of form '0xxxxxxx', where 'x' is any binary digit. If it's a two byte UTF8 character, then it's always of form '110xxxxx10xxxxxx'. Similarly for three and four byte UTF8 characters it starts with '1110xxxx' and '11110xxx' followed by '10xxxxxx' one less times as there are bytes. This tool will locate mistakes in the encoding and tell you where they occured.

