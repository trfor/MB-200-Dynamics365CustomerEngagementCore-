Module 5: Security
==================
## Practice Lab - Create security role

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You will be continuing your work
on the model-driven Knowledge Admin app. In this practice, you will be working
with security roles.

Our users need to have security roles assigned so they can use the application
we have built. Let’s evaluate the default role to see if it’s a good fit. We
notice there’s nothing for our custom entities. After we determine what changes
should be made we will copy from an existing role and create a new role for
users. Once created, we will assign the new role to our users. We will then
create and assign an application manager role.

**Important Note:** This lab will provide you with an actual Office 365 tenant
and licenses for the Power Platform applications you will be using in this
course. You will only be provided with one tenant for the practice labs in this
course. The settings and actions you take within this tenant do not roll-back or
reset, whereas the virtual machine you are provided with does reset each time
you close the lab session. Please be aware that Office 365 is evolving all the time. The
instructions in this document may be different from what you experience in your
actual Office 365 tenant. It is also possible to experience a delay of several
minutes before the virtual machine has network connectivity to begin the labs.

Exercise 1 - Acquire Tenant Information and Connect
---------------------------------------------------

**Note:** If you have already completed a practice recently, the virtual machine
might pick up where you left off and you will not need to login again.  In that
case you can skip ahead to exercise two and resume.

### Task 1 – Connect to the Power platform administration portal

1.  On Virtual machine MB200-Dynamics_Lab, sign in as Admin with the password
    Pa55w.rd if you are not already logged in.

2.  Outside the VM in the online lab interface click Files and choose D365
    Credentials. This will allocate an Office 365 tenant for you to use in these
    labs.  It will display the admin email and password for your tenant.  You
    should copy this information to notepad or similar for your reference.

3.  In MB200-Dynamics_Lab launch Microsoft Edge from the taskbar. By default,
    the browser opens Office 365. Use the O365 credentials you just acquired in
    the previous step to login.

4.  Navigate in the browser to the Power platform admin portal at
    [https://admin.Powerplatform.microsoft.com](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fadmin.Powerplatform.microsoft.com&data=02%7C01%7Cv-juya%40microsoft.com%7C4be5a28c6f1e41eefee808d687ae2dc7%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636845580068684293&sdata=cLrD%2FhTDb5sRbajtFR9RrztfyTDCo0xGS4k8FSxTaIc%3D&reserved=0)

Exercise 2 – Evaluate and Create Security Roles
-----------------------------------------------

### Task 1 – Evaluate Security Role

In this task, you will evaluate the Common Data Service User security role.

1.  Navigate to https://admin.powerplatform.microsoft.com/

2.  Select the **Environments**.

3.  Select the **Practice** environment and click **Settings**

4.  Locate the **Users + Permissions** section and click **Security Roles.**

5.  Click to open the **Common Data Service User** security role.

6.  Select the **Core Records** tab.

7.  Scroll down and see the privileges the **Common Data Service User** security
    role has to the **Core Records**.

8.  Select the **Custom Entities** tab.

9.  You will find that the **Common Data Service User** security role doesn’t
    have access to any of the **Custom Entities**.

### Task 2 – Copy from Existing Security Role

In this task, you will create a new security role by copying from the Common
Data Service User security role.

1.  Click on the **Actions** button and select **Copy Role…**

2.  Enter **Knowledge Assessment User** for **Name** and click **OK**.

3.  The new security role will open. Select the **Custom Entities** tab.

4.  Locate the **Knowledge Assessment** entity and click on the Read access
    circle. The security role will get **User** access to the **Knowledge
    Assessment** entity, this means users with this security role will have
    **Read** privilege to the records owned by the user or are shared with the
    user.

5.  Click on the **Read** access circle again. The security role will now get
    **Business Unit** access, this means the users with this security role will
    get **Read** access to all records owned by the business unit the user
    belongs to.

6.  Click the **Read** access circle again. The security role will now get
    **Parent: Child Business Units access**, this means users with this security
    role will get **Read** access to all records owned by the business unit the
    user belongs to and all its child business units.

7.  Click on the **Read** access circle one more time. The security role will
    now get **Organization** access, this means users with this security role
    will get **Read** access to all records owned by the organization.

8.  Locate the **Knowledge Question** entity and click on the **Read** access
    circle four times. This action will give the security role **Organization**
    wide Read access to the **Knowledge Question** entity.

9.  Locate the **Knowledge Test Result** entity and click on the **Create**
    circle one time.

10. Locate the **Read** circle of the **Knowledge Test Result** entity and click
    Four times.

11. Locate the **Write** circle of the **Knowledge Test Result** entity and
    click one time.

    The security role will get organization wide level Read privilege and user
    level Create/Write privileges to the Knowledge Test Result entity.

12. Select the **Core Records** tab.

13. Locate the **Feedback** entity and click on the **Create** circle one time
    and click on the **Write** circle one time.

14. Click **Save and Close**.

15. Close the Common Data Service User security role. Do not close the security
    roles window.

### Task 3 – Create Security Role

In this task, you will create a new security role for the application manager.

1.  Make sure you are still on the **Roles** window and click **New**.

2.  Enter **Knowledge Application Manager** for **Role Name**.

3.  Select the **Custom Entities** tab.

4.  Locate the **Knowledge Assessment** entity and click on the entity name four
    times. The security role will get organization level of all privileges.

5.  Locate the **Knowledge Question** entity and click on the entity name four
    times. The security role will get organization level of all privileges.

6.  Locate the **Knowledge Test Result** entity and click on the entity name
    four times. The security role will get organization level of all privileges.

7.  Select the **Core Records** tab.

8.  Locate the **Feedback** entity and click on the entity name four times. The
    security role will get organization level of all privileges.

9.  Click **Save and Close**.

10. Close the Roles window.

### Task 4 – Assign Roles

In this task, you will assign the security roles you created. You will first
assign the Knowledge Assessment User role to all the users you created and then
assign the Application Manager role to the Manager user.

1.  Navigate to https://admin.powerplatform.microsoft.com/

2.  Select the **Environments**.

3.  Select your **Production** environment and click **Settings**

4.  Locate the **Users + Permissions** section and click **Users.**

5.  Select all the users you create **Manager User**, **User One,** and **User
    Two**.

6.  Click **Manage Roles**.

7.  Select the **Knowledge Assessment User** role and click **OK**.

8.  Select only the **Manager User** and click **Manage Roles**.

9.  Select the **Knowledge Application Manager** role and click **OK**. The
    Manager User will get both the Knowledge Assessment User and Application
    Manager security roles.

10. Close the security roles list.
