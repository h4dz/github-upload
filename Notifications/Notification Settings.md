---
title: "Notification Settings"
excerpt: ""
---
##Dialing Extensions and Introducing a Delay before Voicemail
If you want PagerDuty to notify you via a phone number that requires you to dial an extension, or you want to introduce a delay so that our voice message is timed correctly to speak after the beep, you can set this up by editing your contact methods.

Simply enter the phone number and then add comma(s), by itself for a delay or followed by a number for a direct extension. Each additional comma represents a 1-second pause (please see additional examples below).

###Setting your Contact Method to Dial a Phone Number with an Extension
- 415-555-5555,1234
    Dial 415-555-5555, wait **one** second, then dial 1234
- 415-555-5555,,,1234
   Dial 415-555-5555, wait **three** seconds, then dial 1234
- 415-555-5555,,1,,,2,987
    Dial 415-555-5555, wait **two** seconds, dial 1, wait **three** seconds, dial 2, wait **one** second, dial 987
[block:callout]
{
  "type": "info",
  "body": "In some cases you may need to add commas for pauses before **AND** after your direct extension depending on your phone system.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8beb00c-Phone_Ext_Example.png",
        "Phone Ext Example.png",
        530,
        70,
        "#dfe5e2"
      ]
    }
  ]
}
[/block]
###Setting your Contact Method to Dial a Phone Number and Wait for Voicemail
- 415-555-5555,,,,,,
    Dial 415-555-5555, wait **six** seconds (to account for the 'Please leave a message after the tone...' delay), then leave a message.