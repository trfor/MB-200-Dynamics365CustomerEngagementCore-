Module 3: Building Model-Driven Applications
============================================

Lesson 10: Practice Lab – Building dashboards

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You will be continuing your work
on the model-driven Knowledge Admin app. In this practice, you will be creating
a dashboard and modifying the app to include it.

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

Exercise 2 – Create a dashboard 
--------------------------------

In this exercise, you will create a dashboard using existing charts and views.

### Task 1 – Create the dashboard

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open the **Common Data Service Default Solution**.

5.  Click + New and select **Dashboard** \| **2-Column Overview**. Note: Always
    pick the template that best fits what you plan to build you can always
    remove some of the cells you are not using as well as adjust the size of
    them.

6.  Enter **Results Overview** for Name.

7.  Click **Insert Chart** for the left top section.

8.  Select **Knowledge Test Result** for **Record Type**.

9.  Select **Active Knowledge Test Results** for **View**.

10. Select **Leader Board** for **Chart**.

11. Click **Add**.

12. Click **Insert List** for the right top sections.

13. Select **Knowledge Assessments** for **Record Type**.

14. Select **Active Knowledge Assessments** for **View**.

15. Click **Add**.

16. Click **Save** to save the dashboard.

17. Click **Close**.

18. Click **Done**.

### Task 2 – Edit the Knowledge Admin App

For your dashboard to show up in the model-driven app you must edit the app
module and added to the definition

1.  Make sure you are still in <https://web.powerapps.com> and you have the
    **Practice** environment selected.

2.  Open **Common Data Service Default Solution**.

3.  Click on the **Knowledge Admin Model-Driven** application. The app designer
    should open.

4.  Select **Dashboards**.

5.  Uncheck the **All** checkbox.

6.  Check the **Results Overview** checkbox.

7.  Uncheck the **Innovation Challenge** checkbox.

8.  Go to the **Entity View** area and see if Challenge and Idea were added. If
    yes, select each and click **Remove**.

9.  Click **Save**.

10.  Click **Edit Site Map**.

11.  Select the **Assessments** area.

12.  Select the **Configuration**.

13.  Click **+ Add** and select **Subarea**.

14.  Select **Dashboard** for **Type**.

15.  Select **Results Overview** for **Default Dashboard**.

16. Drag the **Dashboards** subarea you just added and drop it above the
    **Assessments** subarea.

17. Drag the **Assessments** area and drop it to the left of the
    **Administration** area.

18. Click **Save**.

19. Click **Publish** to publish the sitemap.

20. Click **Save and Close** to close the sitemap designer.

21. Click **Validate** to validate your changes.

22. **Publish** to publish the application.

23. Click **Save and Close** to close the close the app designer.

24. Click **Done**.

25. Click **Publish All Customizations**.

### Task 3 – Test Your Changes

1.  Make sure you are still in <https://web.powerapps.com> and you have the
    **Practice** environment selected.

2.  Select **Apps**.

3.  Select the **Knowledge Admin Model-Drive** application and click **Play**.

4.  Click on the **Administration** area and selected the **Assessments**.

5.  The Dashboard will load and **Results Overview** will be selected by
    default.
