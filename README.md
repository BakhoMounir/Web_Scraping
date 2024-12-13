Main Goal:
The script extracts various types of data from an HTML page (https://www.baraasallout.com/test.html) and stores the results in different formats:

Table Data
Text Data
Product Information
Form Data
Links and Multimedia
Tools:
-Python
Requests: Used to make HTTP requests and retrieve HTML content.
BeautifulSoup (bs4): Used for parsing and navigating HTML.
csv Module: For storing tabular data in CSV files.
json Module: For saving data in JSON format.
re (Regular Expressions): For cleaning text.
Approach
1. Fetching HTML Content
Used the requests library to make an HTTP GET request to the given URL (https://www.baraasallout.com/test.html).
Parsed the HTML content with BeautifulSoup to navigate and search through different HTML elements.
2. Extracting Table Data
Located <tr> tags to find table rows.
Extracted cell contents (<td> and <th> tags) and wrote the row data into a CSV file named Extract_Table_Data.csv.
3. Extracting Text Data
Found all <p> and <li> elements to gather text data.
Stored these elements into a CSV file, distinguishing between:
Paragraphs (<p> tags)
List Items (<li> tags).
4. Extracting Book/Product Information
Located each div with the class product-card.
Extracted product details:
Product ID from the data-id attribute.
Product Name, Hidden Price, and Available Colors from their respective HTML tags.
Stored these details into a JSON file extracted_products_data.json.
5. Extracting Form Input Data
Identified all <form> elements and extracted <input> fields.
Recorded information about each input field’s:
Field Name
Input Type
Default Value
Saved this information in Form_Input_Data.json.
6. Extracting Links and Multimedia
Found all <a> tags to gather hyperlinks (text + href value).
Located the <iframe> tag to extract video sources.
Saved the extracted data into extracted_links_data.json.
 Challenges Faced
HTML Structure Complexity:
Websites often have inconsistent HTML structures, requiring careful parsing to locate tags accurately. specifically in the third task

Hidden Data Extraction:
Extracting hidden prices and text inside the <span> with inline styles required understanding inline HTML rendering intricacies.

Text Cleaning:
Removing unwanted characters and formatting using re.sub proved essential to clean text effectively.

Conclusion
The script utilizes Python, BeautifulSoup, Requests, CSV, and JSON modules to efficiently gather data from various HTML sections of a web page. It successfully extracts tables, product information, hyperlinks, multimedia links, and form input fields while ensuring data integrity across different output files.