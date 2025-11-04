# Article CMS (FlaskWebProject)

This project is a Python web application built using Flask. The user can log in and out and create/edit articles. An article consists of a title, author, and body of text stored in an Azure SQL Server along with an image that is stored in Azure Blob Storage. You will also implement OAuth2 with Sign in with Microsoft using the `msal` library, along with app logging.

![app_demo](https://github.com/user-attachments/assets/fa469950-90bb-40fa-8f35-10bd2967bc7a)

## Log In Credentials for FlaskWebProject

- Username: admin
- Password: pass

Or, once the MS Login button is implemented, it will automatically log into the `admin` account.
<img width="653" height="377" alt="image" src="https://github.com/user-attachments/assets/5411f24a-573d-4f9f-8b5d-bd43df2f4e06" />





## Project Instructions (For Student)

You are expected to do the following to complete this project:
1. Create a Resource Group in Azure.
2. Create an SQL Database in Azure that contains a user table, an article table, and data in each table (populated with the scripts provided in the SQL Scripts folder).
    - Provide a screenshot of the populated tables as detailed further below.
3. Create a Storage Container in Azure for `images` to be stored in a container.
    - Provide a screenshot of the storage endpoint URL as detailed further below.
4. Add functionality to the Sign In With Microsoft button. 
    - This will require completing TODOs in `views.py` with the `msal` library, along with appropriate registration in Azure Active Directory.
5. Choose to use either a VM or App Service to deploy the FlaskWebProject to Azure. Complete the analysis template in `WRITEUP.md` (or include in the README) to compare the two options, as well as detail your reasoning behind choosing one or the other. Once you have made your choice, go through with deployment.
6. Add logging for whether users successfully or unsuccessfully logged in.
    - This will require completing TODOs in `__init__.py`, as well as adding logging where desired in `views.py`.
7. To prove that the application in on Azure and working, go to the URL of your deployed app, log in using the credentials in this README, click the Create button, and create an article with the following data:
	- Title: "Hello World!"
	- Author: "Jane Doe"
	- Body: "My name is Jane Doe and this is my first article!"
	- Upload an image of your choice. Must be either a .png or .jpg.
   After saving, click back on the article you created and provide a screenshot proving that it was created successfully. Please also make sure the URL is present in the screenshot.
8. Log into the Azure Portal, go to your Resource Group, and provide a screenshot including all of the resources that were created to complete this project. (see sample screenshot in "example_images" folder)
9. Take a screenshot of the Redirect URIs entered for your registered app, related to the MS Login button.
10. Take a screenshot of your logs (can be from the Log stream in Azure) showing logging from an attempt to sign in with an invalid login, as well as a valid login.


## example_images Folder

This folder contains sample screenshots that students are required to submit in order to prove they completed various tasks throughout the project.

1. The file article-cms-solution.png displays a screenshot of the deployed application.
   <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/5a2c4ba3-bea5-473f-9fea-4c67ee05a1d5" />

2.resource-group.png is a screenshot from the Azure Portal showing all of the contents of the Resource Group I have created. 
 <img width="1366" height="768" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/2cece3a0-c1a1-455f-9b4b-1e6a25738d42" />

3.sql-database.png shows tables and one query of data
<img width="1366" height="768" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/c30fe7d9-0e29-4245-9dc3-e5030cf48297" />

3. storage-container.png is a screenshot showing container is created
<img width="1366" height="768" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/03c4ca58-3a25-433f-9b7a-74b95fc3c6ee" />

4. blob-solution.png is a screenshot showing an  blob endpoints for where images are sent for storage.
<img width="1365" height="660" alt="image" src="https://github.com/user-attachments/assets/43cac583-96c0-411b-b03f-d57a541f2da9" />

5. uri-redirects-solution.png is a screenshot of the redirect URIs related to Microsoft authentication.
   <img width="1365" height="660" alt="image" src="https://github.com/user-attachments/assets/bb6db788-c99b-40b7-bd98-3bda15e2c18a" />

6. log-solution.png is a screenshot showing one potential form of logging with an "Invalid login attempt" and "admin logged in successfully", taken from the app's Log stream.
<img width="1365" height="660" alt="image" src="https://github.com/user-attachments/assets/dfa42f5d-4e41-49c6-88af-9fe4c4221e2b" />


  

## Dependencies

1. A free Azure account
2. A GitHub account
3. Python 3.10
4. Visual Studio 2019 Community Edition (Free)
5. The latest Azure CLI (helpful; not required - all actions can be done in the portal)

All Python dependencies are stored in the requirements.txt file. To install them, using Visual Studio 2019 Community Edition:
1. In the Solution Explorer, expand "Python Environments"
2. Right-click on "Python 3.10 (64-bit) (global default)" and select "Install from requirements.txt"

## Troubleshooting

- Mac users may need to install `unixodbc` as well as related drivers as shown below:
    ```bash
    brew install unixodbc
    ```
- Check [here](https://docs.microsoft.com/en-us/sql/connect/odbc/linux-mac/install-microsoft-odbc-driver-sql-server-macos?view=sql-server-ver15) to add SQL Server drivers for Mac.
