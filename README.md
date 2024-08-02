***Google Apps Script for Processing ClickUp Webhooks***

This Google Apps Script project handles incoming POST requests from ClickUp webhooks, processes the payload, logs relevant data to a Google Sheet, and updates tasks in ClickUp.

**Setup Instructions**

**Prerequisites**

* Google Account: Ensure you have a Google account.
* ClickUp API Token: Obtain your ClickUp API token from your ClickUp account.
* Google Spreadsheet: Create a Google Spreadsheet and note its ID.

**Steps**

1. Create Google Spreadsheet:

* Create a Google Spreadsheet.
* Note the Spreadsheet ID from the URL (the long string after /d/ and before /edit).

2. Google Apps Script:

* Open the Google Spreadsheet.
* Go to Extensions > Apps Script.
* Delete any code in the script editor and paste the code in this repo
* Replace the ClickUp API key, SpreSheet ID, and Sheet name with your values
* Save the code

3. Deploy as a Web App:

* Click on Deploy > New Deployment.
* Select Web app.
* Set Execute as to Me and Who has access to Anyone.
* Click Deploy.
* Note the Web App URL.

4. Set up ClickUp Webhook:

* In your ClickUp workspace, go to Settings > Integrations > Webhooks.
* Create a new webhook with the Web App URL you noted in the previous step.
* Configure the webhook to send the necessary events.

5. Functions
   
* doPost(e): Handles incoming POST requests, parses the JSON payload, logs data, and updates the task in ClickUp.
* getCustomFieldValue(payload, fieldName): Retrieves the value of a custom field from the payload.
* updateTask(taskId, assigneeName, issueId): Updates the task in ClickUp with new data.
* addTagToTask(taskId, tagName): Adds a tag to the task in ClickUp.
* appendLogToSheet(logDetails): Appends log details to the last row in Column H of the Google Sheet.
