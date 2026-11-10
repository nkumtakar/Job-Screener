# Linkedin-Job-Listings
This two part Flow illustrates the process by how you can automate and screen recurrent jobs listings from Linkedin using UiPath, Power Automate, Gmail and Linkedin Job Alerts, and ChatGpt

Please refer to Job Screener.pdf for complete documentation on triggers, flow schematics, etc.


How to Create the UIPath Workflow 

<img width="877" height="492" alt="image" src="https://github.com/user-attachments/assets/c37e5aa1-f985-4641-9cc2-fec2ac9349f1" />

1. Use  Email Received as the trigger.  Define the specified folder, otherwise leave as blank.  Would reccomend creating a folder as the trigger will definitely run every single time, an email hits the inbox.  Definining a folder will prevent any false positive runs from happening

2. Use the *Assign* action. Define a variable called **EmailBody**.  Assign that variable the value of **Email.Body**

3. Use the *Write File* Action.  In the Write to File field, put **emailBody.txt**, and for the text put **EmailBody**.  What you are saying to UiPath is "create a textfile called **emailBody** and use the value from the variable **EmailBody**.
   
4. Lastly, use the Upload File Google Drive action.  For connection, select your own gmail account.  Under files, just put **{output}** , and then select the Google Drive folder you want the file to be uploaded to. Under Show Properties, Select **Replace** in the files already exist field.

5. Deploy the solution

   

**Creating the GPT Project**

1. Go to the Projects Tab
2. Click the (+) to add a project 
3. Put in a description of specifics of your job, such as specific job responsibilities, salary, location and things that you do not want. The more details
   you give GPT the better the screener will be at giving you recommendations of whether to apply or rject the jobs that were selected.   Put this description here in the instructions field of the project settings.  (Click the three ellipsis in a project to pull up the project settings pane).
4. Call this project, *Job Opportunity Screener*





**Chatgpt scheduled task**: 

Go to the *Scheduled* Tab in the GPT interface.

Use a message similar to this in the GPT Prompt. 

<img width="665" height="207" alt="image" src="https://github.com/user-attachments/assets/c69c23bf-22b6-44a0-9a5f-37667e7b5a8c" />

make sure your GPT subscription has Google Drive integration. 








