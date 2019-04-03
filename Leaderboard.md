# Drive performance using Leaderboard
Leaderboard is a simple visual representation of participants to provide understanding of where they rank in comparison to peers. Leaderboards are the best way to inject competitive spirit among teams and also track individual/team performance against business targets. They provide instant feedback to course-correct and identify patterns in KPI's that could help employees imrprovise.

This generic solution is a great way to incentivise team and create an open culture. It can be used by any sales or service organization to track performance- Individual or Team and compare performance across multiple KPI's. 

Excel from your onedrive for business is consumed by Flow and leaderboard card is sent to Kaizala group in a recurrance pattern.This card has two views- Chat card view & immersive view. 

Chat card view 

<img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/2.jpg" width="250">


Immersive view

This view has two tabs, first being wall of fame for Top 10 performers , second is "My performance" which is different for each user.

<img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/1.png" width="250">

My Performance has 2 sections that displays KPI's and near by ranks. 


## Implementation steps
This can be broadly divided into 3 steps:
1. Upload Action Package
2. Format Excel Sheet
3. Configure Microsoft Flow

### Upload Action package
1. Download the “Leaderboard-SolutionPackage.zip”(*This* *contains* *"Leaderboard_ActionPackage.zip"* *and* *"Leaderboard_FlowPackage.zip"* *Package*)[PlaceholderforGithubLink]
2. Download the latest version of Kaizala ["ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK) (*This contains KASClient.js*)
3. Edit "Leaderboard_ActionPackage.zip"
    1. Unzip "Leaderboard_ActionPackage.zip" to a folder
   2. Change the action "id" and "provider name" in package.json
   3. Add KASClient.js to this folder 
   4. Zip all the contents in this folder (*This folder is your modified action package which should be imported to Kaizala Management Portal*)
   5. [Import](https://docs.microsoft.com/en-us/kaizala/actions/publish#import-kaizala-action) the edited action package to [kaizala Management Portal](https://manage.kaiza.la/)(*This card is sent by calling an API, so no need to add the card to a group*)

### Format Excel Sheet

1.Fill all mandatory fields-Name, PhoneNo and Score. Apart from these three mandatory fields, flow considers the rest as KPI's that are diaplyed in "My performance" tab.

<img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/3.jpg">

> Note: Columns can have Numeric or % values. If the column has percentages, apply [percent number](https://support.office.com/en-ie/article/format-numbers-as-percentages-de49167b-d603-4450-bcaa-31fba6c7b6b4) format to that column

>Note: If you wish to change the label from "score", change it in 


2. [Rename](https://support.office.com/en-us/article/rename-an-excel-table-fbf49a4f-82a3-43eb-8ba2-44d21233b114) excel table as "Leaderboardyyyymmdd" E.g, Leaderboard20190431 for the day 2019/04/31(yy/mm/dd)

> Note: Flow automatically picks up the excel data of that day based on the table name and sends the card.
> Note: Ensure phone number contains country code


### Configure Microsoft Flow

1. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "Leaderboard_FlowPackage.zip"[LinktoGithub] to your Microsoft Flow account

    > Note- If you have never used Sharepoint or Kaizala connections, first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)	
2. Edit details in Imported Flow (*See steps below*)

    1. In the second block, enter the card title in value field, that you want to show in the leaderboard. For E.g, "Sales Leaderboard" 

       <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/4.jpg" width="600">
    
    2. In the third block, set value as  true if the "score" is percentage, if not set it to false
        <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/6.JPG" width="600">

    3. In the seventh block
       1.Select Location as "OneDrive for Business" from dropdown
       2.Select Document library as "OneDrive" from dropdown
       3.Select excel file on clicking folder picker
     
       > Note: Table name that you have given in excel file earlier will automatically picked up by the flow. 
       
       <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/7.JPG" width="600">


    4. In the eighth block "Apply to each", 
        1. Edit KPI names as you have given in the excel table in Parse JSON block fFor E.g, Calls, Deals closed, Productivity, Revenue etc. (*as shown below*)

        <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/8.JPG" width="600">

        >Note: Card can display max of 6 KPI's 

        2. Edit KPI names as given in the excel table in Compose (*as shown below*)
        
        <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/9.png" width="600">

        
    5. In the last block

          1. Enter the group ID or select group name to where you want to send the card
          2. Click on Action to select "Action Package"      
          3. Click on Action package to enter action "id"
          4. Map body to "ActionBodyProperties
          5. Save the Flow

        <img src="https://github.com/KeerthiKuthati/TestDemo/blob/master/10.JPG">

Leaderboard card will be sent to the specified group as per the interval and frequency set in the Flow. 

