# Display RSS Feed updates in Kaizala using custom Action
This is a two step process
* Develop a custom action
* Configure MS flow 

## Develop a Custom Action
This is a simple card that has no creation view and no response view. This is an announcemnet in the form of a card, directed to kaizala group using MS Flow.

### Chat Card view
This card has 3 fields in chat view- Card title(Ex- Tech Trends), Image, Feed title ( title of the News feed and summary). Tapping this card on chat cavas opens white-listed URLS's within kaizala.

#Chat card view Pic

### White-list the hosts in Package.json

Only the hosts whitelisted will be accesible within the card, if not, the content will be directed to a browser.

#Screenshot to Whitelist

## Configure MS Flow
MS Flow should be configured to direct the card created above to a specific group in kaizala. In MS Flow you can only set one feed URL. To direct different feeds to same group, different flows have to be created.

# Implementation steps
* **Create a group** -  This card works in Managed groups and Flat groups
    * To set up flat group-
        *  Login to the Kaizala Management Portal (http://manage.kaiza.la) and navigate to Groups on the left menu and click on “Create Group” button at top right of the Groups page
        ○ Add one or more members to the group
    * To set up Managed public group- 
        *  Login to the Kaizala Management Portal (http://manage.kaiza.la) and navigate to Public Groups on the left menu and click on “Create Group” button at top right of the Public Groups page
        ○ Add one or more subscribers to the group once the group is created
*  **Edit the custom action**
    *  Download the RSS Feed zip file
    *  Extract the files. Go to "RSSFeed Package" and  open package.json file. It is mandatory to change the "id" to different name, in the demo you would see com.kaizala.rssfeedtitleweb.t3 , which can be modified as you wish or you can change the version in incremental manner by +1
    * You could also change the display name, Icon and description to give a suitable title . In this demo you would see
        *  Display name- "RSS feed"
        * Icon - "AppIcon.png"
        * Description- "Tech Trends"
    *  Select all the files in the folder, zip them together and upload on the portal
* **Upload custom action**
    *  Go to Kaizala Management Portal and navigate to the Actions menu option and click on Import Action option to import action package
    *  Change the status of action package from draft to stage and activate. 
    * **Important note**- The card is made to send content by calling an API, so there is no need to add the card to action palette. The card would be directed to Kaizala group by MS Flow
* **Configure MS Flow**
    *  Navigate to http://flow.microsoft.com and click on “My Flows” menu option at the top. In the next screen select the Import button
    * Go to Profile button and search for Microsoft (old default) and click on it
    *  Choose the "RSSFeedsFlow" .zip file and Import the flow– if importing for the first time change it from “Update” to “Create as new”
    *  Setup Microsoft Kaizala connection and RSS Feed connection with Flow from the resources, these are general purpose connections and can be reused with other Flows in your environment
    *  If you are setting up for the first time, Create new-->New connection-->Search for Microsoft Kaizala connection--> Create-->Save. Follow same procedure to add RSS connection. Import the setup. Below is the screenshot after importing Flow package and setting up
    * Click on Import to complete importing the Flow
    * Once import is complete navigate to My Flows, open the imported Flow and click on Edit Flow
    * Enter the details in the first block based on your requirements, these include    
        *  RSS feed link- In this demo we use http://feeds.feedburner.com/TechCrunch
        *  Card title- Tech Trends
    
#Insert FirstBlock Pic 
            
* **Send the card to a Kaizala group** 
    * Enter the following details in the last block and save
        *  Group- Select/Map the group name/group ID where you want to send the card ; Ex- Demo Test group
        * Action- By default is set to "kaizala"
        * Action package- Select Action package ID that you have given in package.json file
        * Body- By default, the variable actionBody is mapped to Body, if not, select it from dynamic content.
        * Save the flow
    
#Insert Lastbloack Pic

### A card is sent to group each time flow is triggered by RSS feed updates

#Insert Final Pic 

