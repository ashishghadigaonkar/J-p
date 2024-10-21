To implement Role-Based Authorization in Jenkins with specific roles and restrictions, follow these steps:

1. Install the Role-Based Authorization Strategy Plugin
Open Jenkins in your browser.
Go to Manage Jenkins → Manage Plugins.
Select the Available tab.
Search for Role-Based Authorization Strategy.
Select the plugin, click on Install without restart or Download now and install after restart.
Once installed, go to Manage Jenkins → Configure Global Security.
Under Authorization, select Role-Based Strategy and click Save.
2. Create Roles for Developer, QA Engineer, and Project Manager
Go to Manage Jenkins → Manage and Assign Roles → Manage Roles.

Under the Roles section:

In the Global roles area, enter the role name (e.g., developer, qa, pm for Project Manager) and click Add Role.
For each role, assign specific permissions:

Developer Role:
Select the following permissions:
Job: Create, Delete, Build, Configure, Workspace
View: Read
QA Engineer Role:
Select the following permissions:
Job: Build, Read, Workspace
View: Read
Project Manager Role:
Select only these permissions:
Job: Read
View: Read
Click Save.

3. Assign Specific Users to Roles
Go to Manage Jenkins → Manage and Assign Roles → Assign Roles.
Under the Assign Roles section:
Add the specific usernames of the users and assign them to the roles created.
For example:
Assign the user dev_user to the developer role.
Assign the user qa_user to the qa role.
Assign the user pm_user to the pm role.
Click Save.
4. Restrict Project Manager Access
Make sure the pm (Project Manager) role has only Read permissions for both Job and View categories, as defined earlier.
This setup will allow the Project Manager to:
View job status and build history.
Restrict the Project Manager from triggering builds, modifying jobs, or configuring settings.
5. Test Role Assignments
Log out from the admin account.
Log in as dev_user (Developer):
Verify that the Developer can create, configure, and build jobs.
Log in as qa_user (QA Engineer):
Verify that the QA Engineer can only trigger builds and read job configurations.
Log in as pm_user (Project Manager):
Verify that the Project Manager can only view job status and build history without the ability to modify or trigger any job actions.
