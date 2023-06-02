# Own_Hosting_IOT
#exportData.php -for export sensorData table data to xls format to download
The provided code is written in PHP and is used to generate and download an Excel file (.xls) containing data fetched from a database table named "SensorData." Here's a breakdown of how the code works:

1. The code starts by including the "dbConfig.php" file, which presumably contains the necessary configuration for connecting to the database.

2. It defines a custom function called "filterData" that is used to sanitize and format the data before adding it to the Excel file. In this case, it replaces tabs and newlines with escape sequences and handles double quotes appropriately.

3. The code initializes the variable "$fileName" with a name for the Excel file. It includes the current date in the file name using the "date" function.

4. Next, an array called "$fields" is defined, which contains the column names that will be displayed as the first row in the Excel file.

5. The variable "$excelData" is initialized with the column names joined together using tabs ("\t") and a newline character ("\n").

6. A database query is executed to fetch records from the "SensorData" table, sorting them by the "id" column in ascending order.

7. If there are records returned from the query, the code enters a loop to process each row. The values from each row are stored in the "$lineData" array and passed through the "filterData" function to sanitize them. Then, the sanitized data is appended to the "$excelData" variable.

8. If no records are found in the query result, the code appends a "No records found..." message to the "$excelData" variable.

9. After the data retrieval and formatting is complete, the code sets the appropriate headers to indicate that the response should be treated as an Excel file attachment. The "Content-Type" header is set to "application/vnd.ms-excel," and the "Content-Disposition" header specifies the filename for the downloaded file.

10. Finally, the generated Excel data is echoed out, and the script exits.

Please note that the code uses the older Excel file format (.xls) rather than the newer one (.xlsx), which may cause compatibility issues with some versions of Microsoft

Excel.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------
