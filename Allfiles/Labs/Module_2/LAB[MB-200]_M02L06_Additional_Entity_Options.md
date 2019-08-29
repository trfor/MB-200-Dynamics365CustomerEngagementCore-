Module 2: Data Model
====================

## Lesson 6: Practice Lab – Additional entity options

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You are working on the data model
you started in the prior practice. In this practice you are enabling some entity
options that can only be done using the classic solution explorer.

To view the data model you are building, **view  Image[MB-200]_M02L02_Creating_Entities_Fields.png in the Lab Resources**.

In this practice, you will be performing the following tasks.

1.  Enabling the Feedback option on Knowledge Assessment. This will cause the
    system to create the relationship between Knowledge Assessment and the CDM
    Feedback entity.

2.  You will enable auditing on the Knowledge Assessment entity.

3.  You will be updating the icon on the Knowledge Assessment entity, so it is
    not using the default icon.

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

Exercise 2 – Enable Entity Options
----------------------------------

In this exercise, you will enable the Feedback option on Knowledge Assessment as
well as enable auditing. You will then update the icon on the Knowledge
Assessment entity.

### Task 1 – Enable Feedback and Auditing Options for Knowledge Assessment

1.  Navigate to <https://web.powerapps.com/> and make sure you are in the
    **Practice** environment.

2.  Select **Solutions**.

3.  Click to open **Common Data Service Default Solutions**.

4.  Click on the **…** button and select **Switch to Classic**.

5.  Expand **Entities**.

6.  Select the **Knowledge Assessment** entity.

7.  Scroll down to the to the **Communication and Collaboration** section.

8.  Select the **Feedback** checkbox.  
    Note: Enabling any option with a + can not be undone, so always confirm
    before you enable any of those features that you are on the right entity and
    need the feature.

9.  Scroll down to the **Data Services** section.

10. Check the **Auditing** checkbox.

    Note: Remember auditing must be turned on at the environment settings,
    entity and field to produce any audit data. By default, fields are enabled
    for auditing.

11. Click **Save**.

### Task 2 – Replace Default Entity Icon 

The entity icon is used in the user experience to identify the entity in the
navigation. There are two icons that can be used; one for the legacy web client
and the other for the new Unified Interface. You will be updating the Unified
Interface icon. In order to reference the icon for the entity you will fist
upload a web resource containing the SVG icon.

1.  With the **Knowledge Assessment** entity still selected, click **Update
    Icons**.

2.  Select the **Unified Interface** tab.

3.  Click on the **New Icon** lookup.

4.  Scroll down and click **Look Up More Records**.

5.  Click **New**.

6.  Enter **assessmenticon** for Name.

7.  Enter **Assessment Icon** for **Display Name**.

8.  Select **Vector Format (SVG)** for **Type**.

9.  Select **English** for **Language** and click **Browse**.

10. Locate the **Knowledge Assessment Icon.svg** image located in the course
    resources and click **Open**.

11. Click **Save**.

12. Click **Publish** and **close.**

13. Select the **Assessment Icon** and click **Add**.

14. Click **OK**.

15. **Save** the solution.

16. Select **Entities** and click **Publish All Customizations**.

17. Close the solution explorer.


