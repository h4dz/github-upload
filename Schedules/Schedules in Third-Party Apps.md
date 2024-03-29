---
title: "Schedules in Third-Party Apps"
excerpt: ""
---
[block:api-header]
{
  "title": "Confluence"
}
[/block]
PagerDuty schedules in Confluence allow Confluence users access to their on-call shifts without having to login to multiple interfaces.

##In PagerDuty
1. Go to the **Configuration → Schedules**.
2. Navigate to the schedule you would like to export to Confluence. Click **Export → iCal feed → Everyone → (right click) Copy Link Address**. Keep that link copied to your clipboard.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0337489-copylinkaddress.png",
        "copylinkaddress.png",
        566,
        574,
        "#3b744e"
      ]
    }
  ]
}
[/block]
##In Confluence
1. Click **Create** in the top navigation menu.
2. Select the **Blank page** option, and name the page.
3. Once you name your page, click the **+** icon from the toolbar, and select **[Team Calendars](https://confluence.atlassian.com/teamcalcloud/team-calendars-for-confluence-cloud-documentation-909903153.html)** from the dropdown menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f86200f-selectteamcalendar.png",
        "selectteamcalendar.png",
        386,
        455,
        "#e4e7e9"
      ]
    }
  ]
}
[/block]
4. Click **Subscribe by URL**. Then enter the name of the schedule, the iCal URL you copied to your clipboard, and your PagerDuty username and password. Then click **Subscribe**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f4cc7b-iCal_URL.png",
        "iCal_URL.png",
        531,
        466,
        "#efefef"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Atlassian expects the name of your schedule in PagerDuty to be 28 characters or fewer. If the name of your PagerDuty schedule has 29 or more characters, then you will see the following error in Confluence: `Specified calendar does not seem like iCalendar`. Note that this refers to the schedule's name and not the iCal URL.\n\nThe same error message will appear if one or more of your users in PagerDuty has a name that is 29 or more characters long.",
  "title": "Note"
}
[/block]
5. You may see an incomplete calendar at first. Click **Save** in the bottom right corner of the page, and then your full calendar will be appear.
[block:api-header]
{
  "title": "Calendar Apps"
}
[/block]
You can integrate your on-call schedule with calendar software (Apple Calendar, Google Calendar, Microsoft Outlook, etc.) using iCal or WebCal.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "iCal and WebCal feeds will display historical data over a 1 month period. Up to 6 months of on-call schedules can be exported in the feed."
}
[/block]
- [Export All Schedules](#section-export-all-schedules)
- [Export a Single Schedule](#section-export-a-single-schedule)
- [Making Changes to Schedules](#section-making-changes-to-schedules)
- [Troubleshooting WebCal Exports](#section-troubleshooting-webcal-exports)

##Export All Schedules
You can export **all** of your personal on-call schedules at once on your profile page.
1. Go to **My Profile** in the drop-down menu in the top right hand corner of the screen and select the **User Settings** tab.
2. Under **Calendar** settings, right click **WebCal feed** and copy the link (alternatively, you can download the ".ics" file by clicking on **iCalendar file**).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07218cf-5e675b2-Webcal_img1.png",
        "5e675b2-Webcal_img1.png",
        1135,
        643,
        "#dfdada"
      ]
    }
  ]
}
[/block]
3. Open [Google Calendar](https://calendar.google.com/calendar/render#main_7) or iCal — in this example, we will add the schedules to Google calendars.
4. Under **Other Calendars**, select **Add by URL** from the drop-down list.
5. Paste the URL and click **Add Calendar**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6b41dc7-82bf84b-Add_calendar.png",
        "82bf84b-Add_calendar.png",
        548,
        238,
        "#e4dde0"
      ]
    }
  ]
}
[/block]
##Export a Single Schedule
If you do not want to export all your on-call schedules, you can also choose to export schedules individually.

The iCal or WebCal link for a specific schedule can be found by clicking on the specific schedule and selecting **Export**. You can export only your on-call shifts, or the entire schedule (everyone's shifts). When exporting the calendar feed from the on-call schedules page, it will export **only the selected** on-call schedule.

###Export only your on-call shifts 
1. Go to the **Configuration → Schedules**.
2. Next to a calendar click **Export  → Just My Calendar** to launch your calendar application. You will be prompted to subscribe to the calendar URL.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d84866f-2adeaef-WebCal_img2.png",
        "2adeaef-WebCal_img2.png",
        1122,
        327,
        "#edecec"
      ]
    }
  ]
}
[/block]
3. In this example we're using Apple Calendar, and need to click **Subscribe** to finish importing your personal schedule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e7a27a1-1e37dcd-sing2.png",
        "1e37dcd-sing2.png",
        466,
        167,
        "#e3e3e3"
      ]
    }
  ]
}
[/block]
###Export the Entire Schedule (everyone's shifts)
1. Go to the **Configuration → Schedules**.
2. In the On-Call Schedules Tab, select **Export → Everyone** to launch your calendar application. You will be prompted to subscribe to the calendar URL.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d848f1b-fb3f1a3-webcal_img3.png",
        "fb3f1a3-webcal_img3.png",
        1118,
        326,
        "#eeeded"
      ]
    }
  ]
}
[/block]
3. Click **Subscribe** to complete the import of the entire schedule.

##Making Changes to Schedules
Once an on-call schedule is exported into Google Calendar, Google Calendar will **automatically** update when you make a change to the on-call schedule in the web application. Therefore, once an on-call schedule has been exported, you will not need to edit it when you make changes to the schedule in PagerDuty.
[block:callout]
{
  "type": "info",
  "body": "Google Calendar can take up to 24 hours to refresh the on-call schedule when modified as Google Calendar caches the data every time it refreshes.",
  "title": "Note"
}
[/block]
##Troubleshooting WebCal Exports
###Export Errors
If you experience any of the following issues when exporting your PagerDuty schedule WebCal feeds to Google Calendar:
- A "could not fetch URL" error displays in Google Calendar
- A "loading" message appears in Google Calendar, but events are not imported
These issues are due to a Google Calendar issue with syncing and caching when fetching a calendar feed after adding by URL. There are several threads on this topic in [Google Product Forums](https://productforums.google.com/forum/#!searchin/calendar/$3Fnocache/calendar/ixQnzHmWDSk/yHm7YGuBbvwJ), however, none of these reflect a concrete resolution.

If you do experience this issue, please test the following fixes when initially subscribing to the calendar via URL:
- Add `?nocache` to the end of the feed URL. For example:

`webcal://yoursubdomain.pagerduty.com/private/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/feed/XXXXXXX`

turns into

`webcal://yoursubdomain.pagerduty.com/private/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/feed/XXXXXXX?nocache`
- Change `webcal://` to `http://` or `https://` at the beginning of the URL. For example:

`http://yoursubdomain.pagerduty.com/private/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/feed/XXXXXXX`

## Reset Your Personal Calendar Feed URLs
If you would like to reset the calendar feed URLs, please follow these instructions.  Please note, these URLs are different than the calendar feed URLs associated with an on-call schedule. This will update all on-call schedules.

1. Login to your PagerDuty account.
2. Go to **My Profile**, select the **User Settings** tab, then click **Regenerate feed URLs**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48b2cbb-b3e6c11-webcal_img4.png",
        "b3e6c11-webcal_img4.png",
        1135,
        665,
        "#dedbdb"
      ]
    }
  ]
}
[/block]
3. Use the links for the WebCal or iCalendar feed to update your calendar application.

## Delete an Imported Schedule
Sometimes when you export the wrong calendar to Google Calendar and attempt to export a different calendar it does not work. Unsubscribing to the wrong calendar in Google Calendar before exporting the new calendar should resolve this issue.

To unsubscribe from a PagerDuty calendar:

- In Google Calendar, go to the **Settings** page.
- Go to the Calendars tab, then click **Unsubscribe** next the PagerDuty calendar. You may need to scroll to see the calendar.
- Import your PagerDuty calendar again.