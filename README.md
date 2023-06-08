# Bema_Site_Products_Scraping

This code is a Python script that automates the process of retrieving product information from a webpage using the ***Selenium*** library and storing the information in a **CSV** file. Let's go through the code step by step:

The necessary modules and packages are imported at the beginning of the code:

**csv module for reading and writing CSV files.
selenium library for automating web browsers.
undetected_chromedriver library for using Chrome WebDriver without detection.
Various classes and modules from the selenium.webdriver package for browser automation.
The code sets up the Chrome WebDriver with the specified driver path (./chromedriver.exe), Chrome options, and service.

The code defines a function named **Products_links** that takes a URL as input and retrieves the links of products from that URL. It uses Selenium to navigate to the URL, wait for the presence of an element with class name **"list-wrapper,"** and then finds all the anchor elements (<a>) within that element. It extracts the href attribute from each anchor element and appends it to the All_Product list. Finally, it returns the All_Product list.

The code defines a function named **Product_details** that takes a file name and a list of links as input. This function retrieves various details of products from the given list of links and stores the information in a CSV file. It iterates over each link, navigates to the link using Selenium, and waits for elements to load. It uses various find_element methods to extract information such as title, product number, short description, price, image URL, and description. The extracted information is appended to their respective lists **(Title, Title_url, Product_number, etc.)**. After processing all the links, it writes the information to a CSV file using the csv.writer class. Finally, it returns the provided file name.

The code prompts the user to enter the URL of the page where the products are placed and stores it in the url variable.

The Products_links function is called with the provided URL, and the resulting links are stored in the links variable.

The code removes any duplicate links from the links list using an OrderedDict.

The total number of products (length of links) is printed.

The user is prompted to enter a file name and it is stored in the file_name variable.

The Product_details function is called with the file_name and links variables to retrieve the product details and store them in a CSV file.

**Data cleaning** is performed on the generated CSV file. The file is read into a DataFrame using pd.read_csv. Then, the image URLs are modified from base64 format to regular URLs using the base64 and requests modules. The modified DataFrame is saved as a new CSV file named "Modify.csv".

The "Modify.csv" file is read into a DataFrame and stored in the df1 variable.
