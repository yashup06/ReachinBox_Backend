# ReachInBox Backend Assignment

The assignment is to build a tool that will parse and check the emails in a Google and Outlook email ID, and
respond to the e-mails based on the context using AI. Use BullMQ as the tasks scheduler.

# To get the google_client_id,secret,uri,token

Step 1: Set Up a Google Cloud Project
Go to the Google Cloud Console:

Navigate to Google Cloud Console.
Create a New Project:

Click on the project dropdown at the top of the page.
Click on "New Project."
Enter a name for your project and select an organization and billing account if prompted.
Click "Create."
Step 2: Enable the Necessary APIs
Enable APIs:
In the Cloud Console, go to the "APIs & Services" > "Library."
Search for the API you need (e.g., Google Calendar API, Google Drive API).
Click on the API, then click "Enable."
Step 3: Configure OAuth Consent Screen
OAuth Consent Screen:
Go to "APIs & Services" > "OAuth consent screen."
Choose "External" or "Internal" based on your application's audience.
Fill in the required fields (app name, user support email, etc.).
Add any necessary scopes your app requires.
Save and continue.
Step 4: Create OAuth Credentials
Create OAuth 2.0 Client ID:

Go to "APIs & Services" > "Credentials."
Click on "Create Credentials" > "OAuth 2.0 Client ID."
Select the application type (e.g., Web application).
Enter a name for your OAuth client.
Set the "Authorized redirect URIs" (e.g., http://localhost:8000/oauth2callback for testing locally).
Click "Create."
Obtain Client ID and Secret:

After creation, you will see a pop-up with your Client ID and Client Secret.
Save these credentials securely.
Step 5: Configure Your Application
Set Up Redirect URI:
Ensure that the redirect_uri in your application matches the one configured in the Google Cloud Console.
Update your application settings with the GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET, and GOOGLE_REDIRECT_URI.
Step 6: Get the Refresh Token
Obtain Authorization Code:

Direct users to the Google authorization URL, including the client ID, redirect URI, and scopes.
Example URL:
bash
https://accounts.google.com/o/oauth2/auth?client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_REDIRECT_URI&response_type=code&scope=SCOPE
Exchange Authorization Code for Access and Refresh Tokens:

After the user authorizes the application, they will be redirected to the redirect URI with a code parameter.
Use this code to request access and refresh tokens from Google's token endpoint:
bash

POST https://oauth2.googleapis.com/token
Include the following parameters:
makefile

code=AUTHORIZATION_CODE
client_id=YOUR_CLIENT_ID
client_secret=YOUR_CLIENT_SECRET
redirect_uri=YOUR_REDIRECT_URI
grant_type=authorization_code
Receive and Save Tokens:

Google will respond with a JSON object containing the access_token and refresh_token.
Save the refresh_token securely for future use.

# to obation open_api_key

Step 1: Create an OpenAI Account
Sign Up or Log In:
Go to OpenAI's website.
Sign up for an account if you don’t have one, or log in if you already have an account.
Step 2: Access the API
Navigate to the API Section:
Once logged in, go to the API section of your account. This can typically be found in the dashboard or under a specific section related to API usage.
Step 3: Generate an API Key
Create a New API Key:

In the API section, look for an option to create a new API key.
Click on the button or link to generate a new key.
You may be prompted to give the key a name or description for your reference.
Save Your API Key:

Once the key is generated, it will be displayed on the screen.
Copy the key and store it securely. This key is your secret key and should not be shared publicly.
Step 4: Secure Your API Key
Store Securely:
Keep the API key in a secure place, such as an environment variable or a secrets management service.
Avoid hardcoding the API key directly into your application's source code.

# technologies used 

Node.js
Express.js
OpenAI
Google APIs
Microsoft Graph API

# To run this application

-Clone the repo first

-By clicking right on backend you will get open with integrated terminal

-After getting into the intergrated terminal run "npm install" 

-Then Run the server by writing the command "npm start"

