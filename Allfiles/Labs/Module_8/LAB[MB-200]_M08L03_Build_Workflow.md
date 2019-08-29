Module 8: Workflows
===================

Lesson 3: Practice Lab – Build a workflow

Scenario
--------

As a functional consultant at Contoso, you are you continuing to work on a
model-driven Knowledge Admin app for your client Fabrikam. Your client has
requested an automated way to track the highest scoring knowledge assessment
record. You need to create a process that will continue to update as new scores
enter the system. In this lab, you will create a relationship between the
knowledge assessment and the high score entity and create a real-time workflow
to compare the current high score with the knowledge assessment to determine if
it is the new highest scoring assessment.

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

Exercise 2 – Prepare the Solution 
----------------------------------

### Task 1 – Add Fields to Knowledge Assessment

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s.

4.  Click to open the **Knowledge Assessment Solution** you imported.

5.  Click on the **Knowledge Assessment** entity.

6.  Click select the **Fields** tab and **+ Add Field**.

7.  Enter **High Score** for **Display Name**, select **Whole Number** for
    **Data Type** and click **Done**.

8.  Click **Save Entity**.

9.  Select the **Relationships** tab.

10. Click **+ Add Relationship** and select **Many-to-One**.

11. Select User for Entity, enter **High Score User** for Display Name, and
    click **Done**.

12. Click **Save Entity**.

### Task 2 – Add Fields to Knowledge Assessment Form

1.  Make sure you still have the **Knowledge Assessment** selected.

2.  Select the **Forms** tab and click on the Main form.

3.  Drag the **High Score User** field from the fields explorer and drop it
    below the **Total Points** field on the form.

4.  Drag the **High Score** field from the fields explorer and drop it below the
    **High Score User** field on the form.

5.  Click **Save**.

6.  Click **Publish**.

7.  Click **Save and Close**.

8.  Click **Done**.

9.  Click on the solution name **Knowledge Assessment Solution** located in the
    navigation breadcrumbs.

10. Click **Publish All Customizations**.

Exercise 3 – Create Workflow 
-----------------------------

In this exercise, you will create a real-time workflow that will run when a
knowledge test result record is created, this workflow will check the current
high score of the related knowledge assessment and updated it if it is lower
than the current knowledge test result.

### Task 1 – Add Fields to Knowledge Question

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s.

4.  Click to open the **Knowledge Assessment Solution** you imported.

5.  Click on the **…** button located on the command bar and select **Switch to
    Classic**.

6.  Select **Processes** and click **New**.

7.  Enter **Update High Score** for **Process Name**, select **Workflow** for
    **Category**, select **Knowledge Test Result** for **Entity**, uncheck the
    **Run this Workflow in the Background** checkbox, and click **OK**.

8.  Select **Organization** for **Scope** and **The Owner of the Workflow** for
    **Execute as**.

9.  Click **Add Step** and select **Check Condition**.

10. Enter **Check current high score** for **Description** and click
    **Configure**.

11. Click on the **Select** dropdown and select **Knowledge Assessment
    (Knowledge Assessment)**.

12. Select **High Score** from the second dropdown and **Does Not Contain Data**
    from the third dropdown.

13. Go to the second row, click **Select** and select **Knowledge Assessment
    (Knowledge Assessment)**.

14. Select **High Score** from the second dropdown and select **Is Less Than**
    from the third dropdown.

15. Click on the **Enter Value** field.

16. Make sure **Knowledge Test Result** is select from the **Look For** dropdown
    of the **Form Assist**.

17. Click **Total Points** located in the **Form Assist**.

18. Go to the first condition and click on the chevron button located on the
    left of the first field and click **Select Row**.

19. Go to the second condition and click on the chevron button located on the
    left of the first field and click **Select Row** again.

20. Click **Group Or**. The condition will now evaluate to True if the High
    Score is empty/null or is less than the Total Points of the new Knowledge
    Test Result.

21. Click **Save and Close**.

22. Select below the condition, click **Add Step** and select **Update Record**.

23. Enter **Update High Score** for **Description**.

24. Select **Knowledge Assessment** for **Update** and click **Set Properties**.

25. Click on the **High Score User** field, go to the **Form Assist**, make sure
    **Knowledge Test Result** is selected from the **Look For** dropdown, select
    **Owner** and click **Add**.

26. Click **OK**.

27. Select on the **High Score** field, go to the **Form Assist**, make sure
    **Knowledge Test Result** is selected from the **Look For** dropdown, select
    **Total Points** and click **Add**.

28. Click **OK**.

29. Click **Save and Close**.

30. Click **Add Step** and select **Stop Workflow**.

31. Enter **Stop after update** for **Description** and select **Succeeded**.

32. Select the **If** step, click **Add Step** and select **Default Action**.

33. Select the text below **Otherwise**, click **Add Step** and select **Stop
    Workflow**.

34. Enter **Stop without update** for **Description** and select **Succeeded**.

35. Click **Save**.

36. Click **Activate**.

37. Confirm activation.

38. Close the workflow editor.

39. Click **Publish All Customizations**.

40. Close the solution explorer.

### Task 2 – Test Workflow

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Apps** and click to open the **Knowledge Admin** Model-Driven
    application.

4.  Select Knowledge **Test Results** and click **+ New**.

5.  Enter **Test Result One** for **Primary Name**, select **Test Assessment**
    for **Knowledge Assessment**, enter **85** for **Total Points** and click
    **Save**.

6.  Select Assessments and click on the Test Assessment.

7.  Locate the **High Score User** and **Hight Score** fields. These fields will
    now have values.
