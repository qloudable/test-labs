# Hello A2019 Bot Getting Started With Building Bots

## Table of Contents

[Overview](#overview)

[Pre-Requisites](#Pre-requisites)

[Introduction](#Introduction)

[Register your device](#register-your-device)

[Create and structure the task bot](#create-and-structure-the-task-bot)

[Step 1: Extract data from a web portal into a CSV file](#step-1-Extract-data-from-a-web-portal-into-a-CSV-file)

[Step 2: Open the CSV file and launch the CRM](#step-2-Open-the-CSV-file-and-launch-the-CRM)

[Step 3: Populate the CRM webform ](#step-3-Populate-the-CRM-webform)

[Step 4: Save and send the CSV file to the Relationship Manager](#step-4-Save-and-send-the-CSV-file-to-the-Relationship-Manager)



## Overview

This course provides the steps to automate a process using a software bot. This is done using Automation Anywhere Enterprise A2019, a premium Robotic Process Automation (RPA) platform from Automation Anywhere, which allows enterprises to deploy a digital workforce comprised of software bots that will automate business processes end to end.

## Introduction
In this use case, you will learn to use Recorder and other actions to 

Extract the data from a web portal into a CSV file. 

Open the CSV file and launch the CRM website.Populate the CRM webform.

Save and send the CSV file to the relationship manager. 

Run the task bot.

## Pre-Requisites

Non-required

## Register your device

**Login to RDP**

1.Click Apps icon in the toolbar and select Remote Desktop Client to open a terminal window.

2.RDP login in details below.


 <p class="accessDetails-container"> 
 RDP-Public-IP: {{RDP-Public-IP}}  <br>
 RDP-USERNAME: {{RDP-username}} <br>
 RDP-PASSWORD: {{RDP-Password}} <br>
</p>


3.Click on Accept in default window opened. Close all opened browsers.

**Log into the Automation Anywhere portal**

1.Open below url from Chrome Browser.

* **Automation Anywhere webportal:** [https://aa-aaudev.my.automationanywhere.digital](https://aa-aaudev.my.automationanywhere.digital)

2.Login details below:

 <p class="accessDetails-container"> 
 AA-User-Name: {{AA-User-Name}}  <br>
 AA-User-Password: {{AA-User-Password}} <br>
 </p>

**Register your devices**

1.From the Features panel of the Automation Anywhere Enterprise A2019 Control Room, navigate to DEVICES → My devices.

2.In the top-right toolbar, click the Add local device icon. click on connect to my computer in opened window.

3.Wait until the Bot Agent downloads and Install the agent by clicking the downloaded exe (AutomationAnywhereBotAgent_v1_0) file. 

![alt text](https://previews.dropbox.com/p/orig/AAuJ_szQs6R7ue1ez_K_OE6kRdiO890CLbHIrQ5RQ0Po_XUDhU7SR1yz700pOTIQIskWkv1kf81wQ7kgnPh6Bgl5D2Yo93pm_2a5SkbtWfdf1PEFmabNnTatciH6gBD313z15IgkTdm6X-WJwnXI8p3tTmV-rQKRBsYmr72043Wz9_JQp-vwHCaxiKaeqVQObLfPKFzP3_8URk-cIxITJgFUkiX18K5gtXNVil7lVOeLBkg8jbIbtZ0gaDQRg9mR5m0IcYLxMnzXaGEf_yNk2Tx2mNPrSRBcTw5Zc_FPV-4FqeXdjbs1GwvUOwNwwFmp0vMajobh6ZnUX8481RbyfeJYav-_Zfy5KZ_2CDZyNtksta51n74svdDOzajafjuSTMw/p.gif?fv_content=true&size_mode=5)

4.To enable the bot extention in the chrome browser, click the warning icon on the browser address toolbar at right corner and click the new extention added (Automation Anywhere) option. Click the  enable extention button on new window opened.

5.To open the Device login credentials section, click computer icon at top right corner of the browser beside the username. From the dropdown window you should see green tick mark and ready to run bot! message.

## Create and structure the task bot

**Create a task bot**

1.In the Getting started section of the Dashboard, click the Create a bot link.

2.In the Create Task Bot dialog box, enter a name for the bot, and then click Create & edit.

## Step 1:Extract data from a web portal into a CSV file

**Launch the source webportal**

1.From the Actions panel, drag and drop the Launch website action to the first step.

2.In the Action details panel, enter the below URL and then select Internet Explorer as the browser.

* **Static-app-Fqdn:** http://{{Static-app-Fqdn}}

<p class="note-container"> 
 Note: For the purpose of this activity, we will use Internet Explorer.<br>
</p>

3.Click Apply.

**Open webportal in Internet Explorer Browser in another window**

1.Click on start button -> Type IE and select Internet Explore browser. Maximise the browser and close all default windows in browser.


* **Static-app-Fqdn** : http://{{Static-app-Fqdn}} 


**Capture the data from the web table**

1.In the Control Room on the Variables panel, Click the + button and Enter the name Table and Type table. Click Create button.

2.Navigate back in the Control Room and From the Actions panel, drag and drop the Recorder: Capture action to the first step.

3.In the Object detail section of the Action details panel, click Window and from the drop-down list, select the appropriate window (Home Page - New User List - AA Static App - Internet Explore).

 **Note: You must click the Refresh windows icon to populate the drop-down list.**

4.Click the Capture object button.

5.Navigate to the web portal, hover your mouse over the table until a red outline appears , and then click to capture it.

6.Navigate back in the Control Room and from the Action drop-down list, select the Get table action.

7.In the Assign the output to variable (optional) field, select the variable Table-string and assign it to the output.

8.Click Apply.

**Write the captured table to a CSV file**

1.From the Actions panel, drag and drop the Write to file action at the end of the first step.

2.In the Data table name field in the Action details panel, select the variable to which you assigned the captured table.

3.In the Enter file name field, enter the file location of the CSV file.

4.Select the Create folders/files if it doesn’t exist checkbox and then click the Override existing file option.

5.From the Encoding list, select the ANSI encoding option. Note: Select the encoding option as per the encoding scheme of your system.

6.Click Apply.

**Close the web portal window**

1.From the Actions panel, drag and drop the Window: Close action to the workbench.

2.In the Action details panel, click Window and from the drop-down list, select the appropriate window (Home Page - New User List - AA Static App - Internet Explore).

3.Click Apply.


**Note:** You must click the Refresh windows icon to populate the drop-down list. 


Great! You have completed the first step.

<question id="24dbdc53-94b7-4655-a807-a3c3b39e3ef6" retry=5 required=false input=true time=5></question>

## Step 2: Open the CSV file and launch the CRM

**Open the CSV file**

1.From the Actions panel, drag and drop the Excel advanced: Open action to the second step.

2.In the Action details panel, click Desktop file and enter the file path with name. (Example: C:\test.csv)

3.Open the file in a read-write mode and select the Sheet contains a header checkbox.

4.Click Apply. 

**Position the cursor in the required cell to update the status**

1.From the Actions panel, drag and drop the Excel advanced: Go to cell action to the second step.

2.In the Cell option section of the Action details panel, select the Specific cell option and enter the cell address. (Example: G2) 

3.Click Apply. 

**Launch the CRM web page**

1.From the Actions panel, drag and drop the Launch website action at the end of the second step. 
2.In the Action details panel, enter the below URL  ) and then select a browser.
 
* **CRM-app-fqdn:** http://{{CRM-app-fqdn}} 

3.Click Apply. 

Now, you have opened the CSV file and launched the CRM website. 

## Step 3: Populate the CRM webform

**Retrieve data from the CSV file**

1.From the Actions panel, drag and drop the Excel advanced: Get multiple cells action to the third step.
2.In the Select range of cells to be returned list of the Action details panel, specify that you want to get all rows.
3.In the Assign value to the variable list, select the same variable to which you assigned the output.
4.Click Apply.

**Loop through the rows of the CSV file and assign each row to a variable**

1.From the Actions panel, drag and drop the Loop action to the workbench.

2.In the Iterator list, select For each row in table.

3.From the Table variable list, select the same variable used earlier.

4.In the Assign the current row to this variable field, select a variable.

**Note:** Make sure that the variable is already created with the variable type as Record.
 

5.Click Apply. 

**Update each field in the CRM webform with the data from the CSV file**

1.From the Actions panel, drag and drop the Recorder: Capture action within the Loop action.

2.In the Object detail section of the Action details panel, click Window and from the drop-down list, select the appropriate window (Create - AA CRM - Internet Explore)

3.Click the Capture object button.

4.Navigate to the CRM web page and capture the First Name field.

5.Navigate back in the Control Room and from the Action drop-down list, select Set text.

6.In the Keystrokes section, use the Insert a variable icon to insert the First Name field.

7.Click Apply.

8.Repeat steps i to vii for each field in the CSV file. 

**Capture the create button**

1.From the Actions panel, drag and drop the Recorder: Capture action within the Loop action.

2.In the Object detail section of the Action details panel, click Window and from the drop-down list, select the appropriate window (Create - AA CRM - Internet Explore).

3.Click the Capture object button.

4.Navigate to the CRM web page and capture the 'create' button.

5.Navigate back in the Control Room and from the Action drop-down list, select Click.

6.Click Apply.

**Capture the create new button**

1.From the Actions panel, drag and drop the Recorder: Capture action within the Loop action.

2.In the Object detail section of the Action details panel, click Window and from the drop-down list, select the appropriate window (Home Page - AA CRM - Internet Explore)

3.Click the Capture object button.

4.Navigate to the CRM web page and capture the 'create new' button at the top.

5.Navigate back in the Control Room and from the Action drop-down list, select Click.

6.Open the below url in the Internet Explore browser.


   **CRM-app-fqdn:** http://{{CRM-app-fqdn}}  


7.Navigate back in the Control Room. In the Object detail section of the Action details panel, click refresh windows and from the drop-down list, select the appropriate window (Create - AA CRM - Internet Explore).

8.Click Apply.

**Move the cursor one cell below**

1.To move the cursor, from the Actions pane, drag and drop the Excel advanced: Go to cell action at the end of the loop.

2.In the Active Cell list, select One cell below.

3.Click Apply.

Great! You have now completed the third step and populated all the customer details in the CRM webform.

<question id="6012f14c-49fd-449a-b13b-0657a757d035" retry=5 required=false input=true time=5></question>

## Step 4: Save and send the CSV file to the Relationship Manager

**Close the web portal window**

1.From the Actions panel, drag and drop the Window: Close action to the workbench.

2.In the Action details panel, click Window and from the drop-down list, select the appropriate window (Create - AA CRM - Internet Explore).

3.Click Apply.

**Close the CSV file**

1.From the Actions panel, drag and drop the Excel advanced: Close action to the fourth step.

**Send an email to the Relationship Manager**

1.From the Actions panel, drag and drop the Email: Send action to the step.

2.In the To address field of the Action details panel, enter the Relationship Manager’s email ID.

3.In the Subject field, update the text.

4.In the Attachment (optional) section, click Desktop file, and enter the file path and name of the CSV file.

5.In the Message field, enter the suitable message to be included in the body of the email.

6.In the Send email via list, select the application for sending the email.

7.Click Apply. 

8.Your bot is now ready! 

9.Close all open Internet Explorer windows and Excel spreadsheets.

10.To run the bot, click Run.

**Conclusion:**

Congratulations! You have now successfully created the bot that would extract data from a web portal, capture it in an excel sheet, and also notify the email recipients. 

Summary: In this course, you learned the steps to build a bot in a few clicks to automate the process.
