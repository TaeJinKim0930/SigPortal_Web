TJK Sig Portal Readme
# SIG Portal

For Special Interest Group(SIG), it is a community within a larger organization with a shared interest in advancing a specific area of knowledge, learning or technology where members cooperate to affect or to produce solutions within their particular field, and may communicate, meet, and organize conferences.


# Sig Portal Website Design Overview

Page Directory Layout

We have a controller for the Homepage created, has handlers for
- MyPortal
    - log in required
    - Created by users and prints out annoucements and forums from users and owner(user who created the portal) of the portal
        - Annoucement
            - has Photo of user, Title of announcement, ID, Content of announcement, Link, Edit, and Delete 
        - Forum
            - has Photo of user, Title of announcement, ID, Content of announcement, Link, Edit, and Delete
        - menu of the page
        - Add button
            - accept input of Title and Content and Link and Photo if user checks the checkbox to add.
            - Link and Photo can be empty input(can be null).
        - Edit button
            - ability to announce Forum into Announcement, but only by the portal owner
            - ability to make Announcement into Forum, but only by the portal owner
            - takes input of Title, Content, Link, and Photo.
        - Link and Phto requires a specified format as input as indicated in Add
            - Link
                -  (ex: https://link.com)
            - Photo
                - (ex: ~/image/FileName.jpg)
- Requests
    - log in required
    - Every users requires to request access of the portal to the owner who created the portal
    - menu of the page
    - List of users who required to have access of owner's portal
        ID, Portal Name, User Name, User Email, Status(T/F), Accept button
        - Depends on status of user who requested, users are idenfided as allowed and not allowed.
            - Accept button updates the status of user for the portal
- About
    - Any information about SIG Portal
    - menu of the page
- Contact
    - Contact info about team
- Default
    - Homepage of the SIG Portal where has list of portals and ability to make a new portal, but log in required to see the list of portal
    - For guests who did not log in are not able to see anything except for menu of the page but future work can be added for the guests
    - list of portals has ID, Name, and Owner information in list
- Login
    - log in page
    - a button that redirects to register page for new user
- Register
    - sign up page
    - email and password required and confirm password
    - a button that redirects to log in page for existing user
- Users
    - list of users email of portal
    - menu of the page


- Sig Portal User Pages/ Windows:
    - A portal will have a few additionnal windows or pages for the creation of adding a forum/ annoucement/ paper or addiotnal content. 
    - The window focuses on the content that is being edited.

- Sig Portal control visibility will be a later added function where if a feature is not desired, forums, annoucements, etc..., they may be made unavailable. 

# Domain Control of Portals

- User Portals will be saved to a database called sig-portal
- We do not believe users can have database control over user's information

# How to create DB
1. Create DB called "sig-portal"
2. run the line 88 - 153 from sig-portalDB.sql file to generate tables

# How to Connect database (https://www.entityframeworktutorial.net/entityframework6/create-entity-data-model.aspx)
0. copy the SQL server name that you want to store the DB.
1. Right click BL
2. Add New item
3. type "Data" in search
4. ado.net entity data model -> name it as sigEntities -> EF designer from database
5. new connection
6. data connection
7. In Data source -> sql server
8. In server Name, SQL server name
9. db name -> sig-portal
10. add connection settings in app.config as "sigEntities"
    - 10-1. check Web.config to make sure the coonectionstring name is "sigEntities"
11. Tables check -> dbo check
12. Done

* If app.config has multiple of connectionstring because somehow you did multiple process of connecting db, it will cause error, so keep the connectionstring string as one.
* SIG-Model.edmx ==> chart of my DB
* In Homepage after connection, 
    - ID: test1@gmail.com
    - PW : 123456
