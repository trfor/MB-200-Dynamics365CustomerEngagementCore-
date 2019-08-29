Module 3: Building Model-Driven Applications
============================================

## Lesson 2: Practice Lab – App designer

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. In this practice you will be
continuing your work on the model-driven Knowledge Admin app. Previously, all
you have done is set up the basic app. Now that you have the data model defined
you can add the other entities to the app navigation.

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

Exercise 2 – Edit the site map 
-------------------------------

In this exercise, you will use the site map designer to add the other entities
to the app navigation.

### Task 1 – Edit the site map

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open **Common Data Service Default Solution**.

5.  Select the **Knowledge Admin**, make sure you are selecting the
    **Model-Driven Application** and click **Edit**.

6.  Click **Open Site Map Designer**.

7.  Drag **Area** from the **Components** tab and place it after the
    **Administration** area.

8.  Select the new area and enter **Assessments** for **Title**.

9.  Make sure the **Assessment** group you created is selected.

10. Select the **Components** tab.

11. Drag **Group** and place it in the **Assessments** area.

12. Enter **Configuration** for **Title**.

13. Select the **Configuration** group you just added.

14. Select the **Components** tab.

15. Drag **Subarea** to the **Configuration** group.

16. Select the **New Subarea**.

17. Select **Entity** for **Type**.

18. Select **Knowledge Assessment** for **Entity**

19. Enter **Assessments** for **Title**.

20. Click **Advanced**.

21. Click **More Titles**.

22. Select **German – Germany (1031)** for **Local (LCID).**

23. Enter **Bewertung** for **Tile**.

24. Click **Client**.

25. Study at the options available to you.

26. Click on the **SKUs** and examine the options available.

27. Examine the options available in **More Options** and **Privileges**.

28. Select the **Configuration** group.

29. Select the **Components** tab.

30. Drag **Subarea** to the **Configuration** group.

31. Select **Entity** for **Type** and **Knowledge Test Result** for **Entity**.

32. Click **Save**.

33. Click **Publish**.

34. Click **Save and Close**.

35. The entities you added to the sitemap are now referenced in the app
    designer.

36. **DON’T** close the app designer.

Exercise 3 – Other app designer changes
---------------------------------------

In this exercise, you will use the app designer to filter what is visible.

### Task 1 – Add and Remove components

Components can easily be added and removed from an app. Remember an app is just
a view into the entities that exist in your environment. Removing them from an
app does not physically remove the entity.

1.  With the app designer still open, click **+ Add**.

2.  Select **Entities**.

3.  Select the **Account** entity. The Account will be added to the Application

4.  Uncheck the **Account** entity. The Account entity will be removed from the
    application.

### Task 2 – Validate and Adjust what forms and views show

Validating your app will alert you if you are missing any dependencies or other
issues. We will also adjust what forms and views are available to the app. By
limiting them now we won’t be surprised if somebody adds a view in CDS later. We
can then specifically choose which forms and views will show in our app you can
do this for the other components as well.

1.  Select **Forms** for the **Knowledge Assessment** entity.

2.  By default, all available components are selected. Uncheck the **All**
    checkbox.

3.  All but the Main form will be unchecked. You required to select at least one
    form.

4.  Check the **All** checkbox. Both forms will be selected.

5.  Select the **Views** of the **Knowledge Test Result**.

6.  All the **Views** are currently selected. Uncheck the **All** checkbox.

7.  All but one Public View will be unchecked. You are required to have at least
    one view.

8.  Check the All checkbox. All the views will be selected.

9.  You don’t have Dashboards or Charts yet. Click **Save**.

10. Click **Validate**.

11. You will get a warning letting you know you that application users will see
    all forms and views.

12. Click **Publish**.

13. Click **Save and Close**.

### Task 3 – Run the Application

1.  Make sure you still have the **Knowledge Admin Model – Driver App**
    selected.

2.  Click **Play**.

3.  The application will load. The current area is shown on the bottom-left of
    the page (**Administration**).

4.  Click on the **Administration** area and switch to the **Assessments** area.

5.  The **Assessments** active view will load.

6.  Click **+ New**.

7.  Enter **Test Assessment One** for **Title** and click **Save.**

8.  Click **+ New** Again.

9.  Enter Test **Assessment Two** for **Title** and click **Save and Close.**

10. Select on the **Assessments**.

11. The two records you created will be visible in the view.

12. Select the **Knowledge Test Results**.

13. The view will load but you don’t have any records.

14. Click on the **Assessments** area and switch to the **Administration** area.

15. The **User** will be selected, and the **Enabled Users** view will load.
