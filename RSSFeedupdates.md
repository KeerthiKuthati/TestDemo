# Set-Up guide

Below are the steps to send RSS Feed updates in kaizala work groups

1. Download the action package
2. Download the latest version of [KAS client]
3. Unzip action package, inlcude the latest version of KAS client and Zip it back
4. Change the action ID in Package.json file or the version in incremental manner by +1
5. Upload the folder in [Management portal]
6. Download the Flow package
7. Import the flow in MS FLow portal (First change the settings to FLow old default)
8. Edit the flow-
                 Enter the following details in the last block of the Flow and save
		* Group- Select/Map the group name/group ID where you want to send the card
		* Action- By default is set to "kaizala"
		* Action package- Select Action package ID that you have given in package.json file

RSS Feeds will be sent to the chosen Kaizala group, ecah time flow is triggered by RSS Updates
		
Learn how this custom action works [here](https://github.com/KeerthiKuthati/TestDemo/blob/master/FeedUpdatesDetails.txt)
