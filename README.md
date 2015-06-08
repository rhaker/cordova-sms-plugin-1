PLUGIN: CORDOVA SMS WITH ATTACHMENTS (ios only)

This plugin was forked from https://github.com/hazems/cordova-sms-plugin. For basic usage without attachments, see that repo.

This plugin is for ios only. For android sms with attachments, see my other github repo.

The javascript uses the cordova file plugin (https://github.com/apache/cordova-plugin-file) to set the attachment path.

Notice
====================
This plugin is one of the examples of the ["JavaScript Mobile Application Development"](https://www.packtpub.com/web-development/javascript-native-mobile-apps-development) book which can be reached at: <br> 
[http://www.amazon.com/JavaScript-Native-Mobile-Apps-Development/dp/1783554177/](http://www.amazon.com/JavaScript-Native-Mobile-Apps-Development/dp/1783554177/) <br>
[https://www.packtpub.com/web-development/javascript-native-mobile-apps-development](http://www.amazon.com/JavaScript-Native-Mobile-Apps-Development/dp/1783554177/) 

Sms Custom Cordova Plugin:
====================
This plugin allows you to send SMS message for ios with attachments. Here is an example below:

	// use ios plugin with attachment					
	var audioPath = cordova.file.tempDirectory + "fileAudio.wav";					
	var contactPhoneNumber = "12221231234";
	var messageInfo = {
				phoneNumber: contactPhoneNumber,
				textMessage: "I recorded a message for you.",
				audioFilePath: audioPath // set audioPath to "noFile" to skip attachment
	};

	sms.sendMessage(messageInfo, function(message) {
						
			// on text view dismissal, back to screen)					
						
	}, function(error) {
						
			// try to send email if text fails
			alert("success");
	});
	
As you notice you just need to call *sms.sendMessage(messageInfo, successCallback, failureCallback)*:

 * *messageInfo* is a JSON object which contains phoneNumber and textMessage attributes.
 * *sucessCallback* is a callback function which will be called if the send SMS operation succeeds.
 * *errorCallback* is a callback function which will be called if the send SMS operation fails.

Installing the plugin
---
In order to install the plugin you can simply use the following Cordova CLI command: 
	
	cordova plugin add https://github.com/rhaker/cordova-sms-plugin-1.git

Important Note
---
For iOS and Windows Phone platforms, it is not possible to send SMS directly without opening the default device SMS application. This means that the API will only open and track the SMS application events (cancel, successful sending, un-successful sending, ...etc) in iOS platform. For Windows Phone 8, the plugin will only open the SMS application without tracking its events because tracking SMS application events is not currently applicable in Windows 8 platform.

Test Client
---
You can reach the test client of this plugin here:
 [https://github.com/hazems/cordova-sms-plugin-test/ ](https://github.com/hazems/cordova-sms-plugin-test/)

Used Resources
---
Special Thanks to [appcoda.com]() for helping me in implementing the iOS part of this plugin:

[http://www.appcoda.com/ios-programming-send-sms-text-message/ ](http://www.appcoda.com/ios-programming-send-sms-text-message/)

Licence
---
It is Apache License, Version 2.0. Feel free to fork the project and send pull requests if you have any.
 
