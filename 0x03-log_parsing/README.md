Log parsing is the process of converting log data into a common format to make them machine-readable. You might start with ingested logs spanning several different formats; but once they have been parsed, you can use your log management system to search and analyze their events as if they were a single unit.
A log management system must first parse the files to extract meaningful information from logs. Log parsing translates structured or unstructured log files so your log management system can read, index, and store their data. This way, you can easily filter, analyze, and manipulate the key-value information.
One of the most commonly used structured data formats is JSON. It’s the first choice for many application developers because its Unicode encoding makes it universally accessible and readable by humans and machines alike. The snippet below shows a simple JSON document with key-value pairs as elements
{      
 "userAccess":  {
        "timestamp":  "2022-01-31 17:55.50”,
        "client_ip": "10.2.31.21", 
        "username": "bob",         
        "status": "Error",         
        "message": "File not found"     
 }
}
Usually, log parsers are built into the log management software’s engine. This means each log manager will have its proprietary method for parsing logs.

Most log management solutions have built-in parsers for common data types like Windows Event Logs, JSON, CSV, or W3C. Parsers are configured to recognize these log types based on the source data structure and file extensions.

Once a log file is ingested, the parser applies its built-in rules to extract useful field names and their values. Sometimes, a parser can store the extracted data in a hierarchical structure. With this approach, the user can search on any field and drill down through the returned result set to fine-tune the query.

For non-standard log types, users can provide custom log parsing rules. Typically this is done using regular expressions or the logging solution’s proprietary language. Some log management solutions make it even easier by letting users build the parsing rule from a graphical interface. Users can highlight the field names they are interested in; meanwhile, behind the scenes, the log management solution builds the parsing rule.

Once logs are parsed, the logging system will ingest the data so users can query, analyze, and visualize it.