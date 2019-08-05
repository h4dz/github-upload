---
title: "Mobile Notification Settings"
excerpt: ""
---
[block:api-header]
{
  "title": "Enabling Sound for PagerDuty Notifications"
}
[/block]
To enable sound for your PagerDuty notifications, you will need to assign both High and Low Urgency notifications a ringtone. In the PagerDuty app, you can do this from the **Settings** menu as shown below. **By default, low urgency notifications will be silent**. With the notification sounds set and no other settings enabled, the PagerDuty notifications will also be muted when your phone is set to Do Not Disturb or when your volume is muted.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/95888ec-Screenshot_1552516793_copy.png",
        "Screenshot_1552516793 copy.png",
        1080,
        1920,
        "#282c39"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Do Not Disturb and System Volume Settings in Android 9"
}
[/block]
In Android 9 if you'd like to bypass Do Not Disturb, you can enable **High-Urgency Override Do Not Disturb**. 

If your phone does not have Do Not Disturb turned on, but your volume slider is set to 0, PagerDuty notifications will be silent. To change this, you can enable **High- Urgency Override System Volume** on the same page. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c690e7-Screenshot_1552519311.png",
        "Screenshot_1552519311.png",
        1080,
        1920,
        "#262c3a"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Bypassing Do Not Disturb on Android 8"
}
[/block]
As of Android 8, bypassing Do Not Disturb can be less intuitive since there may be additional steps to set it up successfully. 

1. Ensure that you have **Override System Volume** enabled in the app. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f13919-Screenshot_1545326236.png",
        "Screenshot_1545326236.png",
        1080,
        1920,
        "#262c3a"
      ]
    }
  ]
}
[/block]
2. Selecting this option will take you to the **Do Not Disturb access** page. From here, enable **PagerDuty** and accept the prompt. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a37d6e9-Screenshot_1545412645.png",
        "Screenshot_1545412645.png",
        1080,
        1920,
        "#f4f5f5"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac88619-Screenshot_1545412652.png",
        "Screenshot_1545412652.png",
        1080,
        1920,
        "#828282"
      ]
    }
  ]
}
[/block]
3. At this point, we recommend that you test to see if your High Urgency notifications are able to bypass Do Not Disturb. 

If you're still having an issue, you may have to configure this option manually as we have shown below. 

1. Select **Settings** and then select **Apps & notifications**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a598ee-Screenshot_1545325927.png",
        "Screenshot_1545325927.png",
        1080,
        1920,
        "#f2f3f1"
      ]
    }
  ]
}
[/block]
2. Click **App info** and select **PagerDuty** in the app list. Then select **Notifications**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2f629c8-Screenshot_1545325968.png",
        "Screenshot_1545325968.png",
        1080,
        1920,
        "#f3f2f1"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Don't see this option when you select Notifications?",
  "body": "If you select Notifications and don't see the menu below, you'll need to send a test notification or trigger an incident in order to receive a push notification. Once you've received your first push notification, the menus will populate."
}
[/block]
3. Ensure that the **High-Urgency** and **Low-Urgency** toggles are both set to **on**. Next, **tap the text** for **High Urgency Notifications**. This will take you to a different menu. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/67f4ea9-Screenshot_1545325957.png",
        "Screenshot_1545325957.png",
        1080,
        1920,
        "#e2ebea"
      ]
    }
  ]
}
[/block]
4. On this menu, **Override Do Not Disturb** will be an option at the bottom of the screen. Make sure to toggle this **on**. Keep in mind, if you'd like your Low Urgency Notifications to override Do Not Disturb, you'll need to go back to the previous menu and select the text for Low Urgency Notifications. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b03ede1-Screenshot_1545325982.png",
        "Screenshot_1545325982.png",
        1080,
        1920,
        "#e0e9e8"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Why Can't I Bypass Do Not Disturb on my iPhone?",
  "body": "Apple has enforced limitations on what notifications can bypass their Do Not Disturb setting. As of December 2018, the only notifications that can bypass this setting are medical and health related notifications, home and security notifications, and public safety notifications. You can  provide Apple with your feedback [here](https://www.apple.com/feedback/iphone.html)."
}
[/block]

[block:api-header]
{
  "title": "MIUI and EMUI (Huawei and Xiaomi devices)"
}
[/block]
For these particular forks of Android, you may not be able to set sounds from the respective High and Low Urgency Notification Settings. Instead, you may need to navigate to:
- System Notification Settings
- Make sure High and Low Urgency Notifications are enabled
- From here, tap either High or Low Urgency to choose your sound.