# Employee Help Desk

 In an Organization,helpdesk team looks into the issues raised by employees, assigns it to the right field agent and updates back the resolution status to the employee. All the queries are logged in as tickets by organizations for easy tracking and resolution. A ticketing systems enables help desk agents to systematically capture, categorize, resolve and collect feedback. This enables an organization to be effective in issue resolution and has a multiplier effect on employee satisfaction scores.

This solution uses Kaizala as the front-end, SharePoint as the backend and Flow as a means to interact with Kaizala and SharePoint. User creates the ticket by submitting a form in Kaizala, the data submitted in the card is captured and stored in the sharepoint using Flow.
On submission, User gets notified, either when-
1. Help desk agent updates the status of the ticket in sharepoint (New, Assigned or Resolved) or
2. Help desk agents comments on the ticket in sharepoint or 
3. Both, help desk agent updates status and adds comments

If user is satisfied with the proposed resolution, user has the ability to close the ticket and submit feedback. If the user is not satisfied with the resolution, user can re-open the ticket. Based on user Feedback (rating and comments) and status is updated to Reopened or closed in sharepoint.


> Note: This card works only in Hub and spoke groups

Creation view

Chat card view ( Status updates- Assigned, resolved, closed)

Immersive view (with timeline & Share Feedback)

## Implementation Steps:
This is broadly divided into 3 steps:
1. Upload action packages
2. Set up a SharePoint list
3. Configure Microsoft Flow

### Upload Action Packages
1. Download the ["EmployeeHelpDesk-SolutionPackage.zip"](Placeholder for Github link) (*This contains 2 action packages and 3 Flows*)
2. Download the latest version of Kaizala ["ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK) (*This contains KASClient.js*)
3. Set up the "CreateTicket-ActionPackage.Zip"
   1. Unzip "CreateTicket-ActionPackage.Zip" to a folder
   2. Change the action "id" and "provider name" in package.json
   3. Add KASClient.js to this folder 
   4. Zip all the contents in this folder (*This folder is your modified action package which should be imported to Kaizala Management Portal*)
   5. [Import](https://docs.microsoft.com/en-us/kaizala/actions/publish#import-kaizala-action) the edited action package to [kaizala Management Portal](https://manage.kaiza.la/)
   6. [Publish](https://docs.microsoft.com/en-us/kaizala/actions/publish) the action and add the action to a group where you want to add the card
   7. Select user roles as admin and member
4. Set up "StatusUpdateFromHelpDesk-ActionPackage.Zip"
   1.  Unzip "ReplyFromHelpDesk-ActionPackage.Zip" to a folder
   2. Change the action "id" and "provider name" in package.json
   3. Add KASClient.js to this folder 
   4. Zip all the contents in this folder (*This folder is your modified action package which should be imported to kaizala management portal*)
   5. [Import](https://docs.microsoft.com/en-us/kaizala/actions/publish#import-kaizala-action) the edited action package to [kaizala management portal](https://manage.kaiza.la/)
   6. [Publish](https://docs.microsoft.com/en-us/kaizala/actions/publish) the action and add the action to a group where you want to add the card
   7. Select user role as admin

 > Note: "CreateTicket-ActionPackage.Zip" is the card that is used to raise a ticket and should be made available to admin and Subscribers."StatusUpdateFromHelpDesk-ActionPackage.Zip" show helpdesk comments and status updates. Subscribers do not have to see this card in action palette, hence this is only made visible to admin.

### Set up a SharePoint List

1. [Create](https://support.office.com/en-us/article/create-a-list-in-sharepoint-0d397414-d95f-41eb-addd-5e6eff41b083) a new list in SharePoint

2. [Add] columns (https://support.office.com/en-us/article/create-a-column-in-a-sharepoint-list-or-library-2b0361ae-1bd3-41a3-8329-269e5f81cfa2) and [Edit]column settings for this list](https://support.office.com/en-us/article/Edit-list-settings-in-SharePoint-Online-4d35793b-246e-42a3-990c-563a83795b7f)(*as below in the same order and format*)

Column
Recomended settings
-------- |---
Department|Single line of text
Location|Single line of text
Category|Single line of text
Description |Multiple lines of text
Photos|Multiple lines of text
CreatorName|Single line of text
CreatorContact|Single line of text
ReportedAt|Single line of text
AssignedTo|Single line of text
AssignedBy|Single line of text
Status|Choice with options as New, Assigned, Resolved, Closed and Reopened (*These ticket stages are mandatory*)
HelpdeskComments|Multiple lines of text
UserFeedback|Multiple lines of text
ReasonsToReopen|Multiple lines of text
CreatorKaizalaName|Single line of text
CreatorKaizalaContact|Single line of text
UserRating|Single line of text

4. [Edit list view](https://support.office.com/en-gb/article/edit-a-list-view-in-sharepoint-online-15916903-e79a-423f-b4e2-02d37e1ff372)to position ID in first place.This is the unique ticket ID that will be diaplyed in the card, once the ticket is assigned.

     >Note: Download excel sheet for reference

### Import and Set up Flows

This solution has 3 Flows, namely
1. Flow to collect ticket information and store it in SharePoint

    1. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "TicketCreationFlow.Zip" to your Microsoft Flow account

          > Note- If you have never used Sharepoint or Kaizala connections, first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)	

    2. Edit details in Imported Flow (*See steps below*) 

          1. In the First block 

               1. Enter the Group ID or Select the Group name where you want to add the card

	           2. Click on Action Package field to enter action id that you have given for "CreateTicket-ActionPackage.zip"

               3. Map action to "All"

                  <img src="EmployeeHelpDesk-Images/5.JPG" width="600">

          2. In the Last block

               1. Enter the SharePoint Site address

	           2. Enter List Name
                  
                  <img src="EmployeeHelpDesk-Images/6.JPG" width="600">

                   > Note: All the columns in the SharePoint list will be displayed in Flow on entering Sharepoint Site address & List Name. Verify the mapping of sharepoint list fields in Flow. 

           3.  Save the Flow
           

2. Flow to send status updates to user, as and when updated by Help desk

    1. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "TicketStatusUpdatesFlow.Zip" to your Microsoft Flow account

	2. Edit details in Imported Flow (*See steps below*) 

          1. In the first block

               1.  Enter the SharePoint Site address

	           2. Enter List Name

                  <img src="EmployeeHelpDesk-Images/6.5.JPG" width="600">

          2. In the last block

               1. Enter the group ID or select group name to where you want to send the status updates

               2. Click on Action to select "Action Package" 

               3. Click on Action package to enter action id that you have given for "StatusUpdateFromHelpDesk-ActionPackage.Zip"

			   4. Map body to "ActionBody"

                  <img src="EmployeeHelpDesk-Images/7.JPG" width="600">

        3.  Save the Flow
    
3. Flow to allow user to Close or Re-open the ticket and share feedback with Help desk
 
    1. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "TicketReopenFlow.Zip" to your Microsoft Flow account

	2. Edit details in Imported Flow (*See steps below*) 

        1. In the First block 

             1. Select group name or enter the group ID

	         2. Click on action package to enter action id that you have given for "StatusUpdateFromHelpDesk-ActionPackage.Zip"

             3. Map action to "All"

                <img src="EmployeeHelpDesk-Images/8.JPG" width="600">

        2. In the second block

			 1. Enter the site address

             2. Enter the list name 

                <img src="EmployeeHelpDesk-Images/9.JPG" width="600">

        3. In the Last block

             1. Enter the site address

             2. Enter the list name

                <img src="EmployeeHelpDesk-Images/10.JPG" width="600">

        4.  Save the Flow