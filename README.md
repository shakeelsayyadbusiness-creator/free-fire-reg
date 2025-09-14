Overview
--------
This project provides a complete, serverless solution for a "Free Fire Tournament" registration form. It features a cinematic, war-themed HTML form that captures user data and seamlessly sends it to a Google Sheet for easy management. The entire process is handled using only front-end technologies (HTML, CSS, JavaScript) and Google Apps Script, eliminating the need for a dedicated backend or database.

Upon successful submission, the form displays a personalized "good luck" message to the registered team.

Features
--------
- Cinematic Design: A visually appealing form with a war-themed background, custom fonts, and responsive layout.
- Serverless Data Submission: Connects directly to a Google Sheet using Google Apps Script, no backend required.
- Dynamic Success Message: Displays a personalized message to the user upon successful registration (e.g., "Wish you all the best team <Team Name>!").
- Responsive Layout: The form is fully functional and looks great on desktops, tablets, and mobile devices.
- Form Validation: Basic client-side validation ensures all fields are filled before submission.
- Easy to Deploy: Can be hosted for free on static site platforms like GitHub Pages, Netlify, or Vercel.

How It Works
------------
The project consists of two main parts:

1. The HTML Form (`index.html`): This is the front-end part that users interact with. It's built with HTML for structure, CSS for styling, and JavaScript to handle form submission.
2. The Google Apps Script: This script acts as the bridge between the HTML form and the Google Sheet. It receives the form data via a POST request and appends it as a new row in the designated Google Sheet.

Setup and Installation
----------------------
Follow these steps to get your registration form up and running.

Step 1: Create the Google Sheet
- Go to Google Sheets and create a new blank spreadsheet.
- Rename the sheet to "Registrations" (or a name of your choice).
- In the first row, add the following headers. The names must match exactly:
  Timestamp
  TEAM NAME
  CAPTAIN NAME
  CONTACT NUMBER
  PLAYER 1 NAME
  PLAYER 1 CONTACT
  PLAYER 2 NAME
  PLAYER 2 CONTACT
  PLAYER 3 NAME
  PLAYER 3 CONTACT

Step 2: Create the Google Apps Script
- In your Google Sheet, navigate to Extensions > Apps Script.
- Delete any existing code in the editor and paste the code from the google-apps-script.gs file provided in this project.
- Save the script and give the project a name (e.g., "Free Fire Form Handler").

Step 3: Deploy the Web App
- In the Apps Script editor, click Deploy > New deployment.
- Click the gear icon and select Web app as the deployment type.
- Configure the settings as follows:
  Description: Free Fire Tournament Form
  Execute as: Me
  Who has access: Anyone
- Click Deploy.
- Authorize the script by granting it permission to access your Google account.
- Copy the Web app URL provided upon successful deployment. You will need this for the next step.

Step 4: Configure the HTML Form
- Open the index.html file.
- Find the following line in the <script> section at the bottom:
    const scriptURL = 'YOUR_WEB_APP_URL_HERE';
- Replace YOUR_WEB_APP_URL_HERE with the Web app URL you copied in the previous step.
- Save the file.

Step 5: Host the Form
- Upload the index.html file to a static hosting provider like GitHub Pages, Netlify, or Vercel. Once deployed, the provider will give you a public URL for your form.

Usage
-----
Share the public URL of your hosted form with participants. When they fill out and submit the form:
1. The data will automatically appear as a new row in your Google Sheet.
2. The participant will see an alert with a personalized success message.

Customization
-------------
Adding New Fields

To add a new field (e.g., "Player 4 Name"):
- HTML: Add the new input field to your index.html file.
- Google Sheet: Add a corresponding header for the new field in your spreadsheet.
- Apps Script: Update the rowData array in your Google Apps Script to include the new form parameter.

License
-------
This project is licensed under the MIT License. See the LICENSE file for more details.
