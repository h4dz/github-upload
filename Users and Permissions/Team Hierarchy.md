---
title: "Team Hierarchy"
excerpt: ""
---
Team Hierarchy is currently in Early Access, please work with your Customer Success Manager or your Account Manager to have this enabled. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f78ed44-Screen_Shot_2018-03-28_at_2.21.24_PM.png",
        "Screen Shot 2018-03-28 at 2.21.24 PM.png",
        1036,
        457,
        "#cbdcf5"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Creating and Managing a Team Hierarchy"
}
[/block]
Team Hierarchies are built using existing Teams. To prepare for configuring a hierarchy, make sure you have created the Teams that will be involved, and have decided upon a structure for your Team Hierarchy.

The following considerations should be made:

- Which Teams will act as parent Teams (more inclusive), and which will be Subteams (more granular)?
- How close will your hierarchy map to the directory system or your existing organizational structure?
- How do you want to configure permissions? (For more information, see [Access and Permissions Management](https://support.pagerduty.com/docs/team-hierarchy#section-access-and-permissions-management-in-hierarchies)).

Once you have decided on a structure, you can assign a Team as a parent to a given other team to start building the structure. Depending on how openly you distribute and how open lines of communication are between Teams and your organization, you may want to consider utilizing public or private Teams.

##Assigning a Parent Team

This action will assign your current Team to be a Subteam of another Team.

1. Navigate to a Team's view page
2. Click **Edit Team** 
3. In the **Parent Team** field, select a Team to designate as the current Team's parent. There can only be one.
4. Click **Save**

##Deleting a Parent Team

To delete a Team, any other Teams of which it is a parent must first be dissociated. In other words, all Teams that have the Team to be deleted as their parent must get a new Team selected to be the parent, or have no parent Team set for it.
[block:api-header]
{
  "title": "Access and Permissions Management in Hierarchies"
}
[/block]
Users and their roles in a given parent Team of a hierarchy will have hierarchical access to all its Subteams, with the role they have in their parent Team applying to objects and actions in the Subteams. 

Any role explicitly granted to a user in a Subteam will take precedence over the role they have in a parent Team, and any role inherited by a user in a Subteam will be derived from the nearest parent in the hierarchy in which a role is explicitly granted to them.

To give a few examples, let us consider the diagram at the beginning of this page, and assume all Teams' visibility are set to **Public**:

* A user with a Team-specific *Manager* role in the *Software Division* Team will have manager access to all objects within the *Software Division* Team as well as manager access to all the Subteams: *ABC Software*, *Acme Software* and the two Subteams of the former.
* If the user has an account-level **Responder** role, they will have responder access to all the same Teams in the hierarchy
* Let us assume a user has the **Observer** role in the *Support Division* Team, and has been granted the **Responder** role in the *ABC Software Support Team.* They will then have the Responder role in the Subteams of that Team, and observer role in the *Acme Support Software* Team and its one Subteam.

##Team Visibility

Teams can be set to public or private. Making a Team private will make it invisible to anyone who does not belong to it. However, when a Team is part of a hierarchy, this has additional implications.

In effect, making a Team private will essentially override all inherited access, and access will need to be granted to the Team explicitly. Furthermore, setting a parent Team's visibility as private thus effectively (to those not on the Team) sets the Subteams to private as well, but does not affect that Team member's access to its tree of Subteams.

Using the same example as before (see diagram), let's say we set the *ABC Software* Team to private, and leave its Subteams as public. This affects visibility and permissions in the following ways: 

* **Setting a Team to private will override and prevent hierarchical access to it from the parent Team(s).** So, no one in the *Software Division* Team will have access to the *ABC Software* Team.
* **Users not assigned to the private Team will not be able to see that Team or any of its Subteams**. This also applies to further descendant Subteams. So, members of the *Software Division* Team will not be able to view or access the *Database Team*, nor see that it is a Subteam of *ABC Software*.
* **Users will always be able to see Teams they are assigned to, and all their Subteams,** provided the Subteams are not individually set to private. So, a user assigned to *ABC Software* as the Manager role will have manager access to that Team, as well as manager access to *Database Team* and *Foo Team*, even if *ABC Software* is set to private.

##Navigating to Teams and Sub-Teams

To navigate through a Team hierarchy:

1. Go to **Configuration → Teams**
2. View all the Teams to which currently have access
3. You can click into each Team to navigate down into the existing Team to view all associated objects, and make edits, if permitted.
[block:callout]
{
  "type": "info",
  "body": "Access to view each Team will depend on your base role, your Team role, and whether a Team is public or private"
}
[/block]