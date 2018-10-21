# Display RSS Feeds in work groups

To send RSS feeds to wok groups through custom actions follow the below steps. The secation is divided into two. Section 1- Set up guide. Section 2- Detailed explanation of how this custom action works.

## Section 1

1. Download the action package
2. Download the latest version of KAS client
3. Unzip Action package folder and inlcude the latest version of KAS client and Zip it back
4. Chnage the action ID in Package.json file
5. Upload the folder in Management portal
6. Download the Flow package
7. Import the flow in FLow portal ( First change the settings to FLow old default)
8. Edit the flow-
                 Enter the following details in the last block and save
		* Group- Select/Map the group name/group ID where you want to send the card
		* Action- By default is set to "kaizala"
		* Action package- Select Action package ID that you have given in package.json file
## Section 2

### How this works?

