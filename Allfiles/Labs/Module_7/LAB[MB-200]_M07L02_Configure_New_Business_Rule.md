Module 7: Business Rules
========================

## Lesson 2: Practice Lab – Configure a new business rule

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a model-driven Knowledge Admin app for your client Fabrikam. In this
lab, you will create fields and use business rules to control visibility of the
fields without needing custom code.

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

Exercise 2 – Create Environment and Import Solution 
----------------------------------------------------

In this exercise, you will create a new environment and import a solution

### Task 1 – Create Environment

1.  Navigate to <https://admin.powerapps.com>

2.  Click **+ New Environment**.

3.  Enter **Practice** for **Environment Name** and click **Create
    Environment**.

4.  Click **Create Database**.

5.  Select **USD** for **Currency**, select **English** for **Language**, and
    click **Create Database**.

6.  Wait for the environment to be created.

### Task 2 – Import Solution

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s and click **Import**.

4.  Click **Browse**.

5.  Select the **Starting Solution** zip file and click **Open**.

6.  Click **Next**.

7.  Click **Import**.

8.  Wait for the Import to complete, **Publish** the changes, and click
    **Close**.

Exercise 3 – Prepare the Solution 
----------------------------------

### Task 1 – Add Fields to Knowledge Question

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solutions**.

4.  Click to open the **Knowledge Assessment Solution** you imported.

5.  Click to open the **Knowledge Question** entity.

6.  Select the **Fields** tab and click **+ Add Field**.

7.  Enter **Question Type** for **Display Name** and select **Option Set** for
    **Data Type**.

8.  Click on the **Option Set** dropdown and click **+ New Option Set**.

9.  Enter **Simple** and click **Add New Item**.

10. Enter **Scenario** and click **Save**.

11. Check the **Required** checkbox and click **Done**.

12. Click **Save Entity**.

13. Click **+ Add Field**.

14. Enter **Scenario Description** for **Display Name**, select **Text Area**
    for **Data Type**, and click **Done**.

15. Click **Save Entity**.

### Task 2 – Add Fields to Knowledge Question Form

1.  Make sure you still have the **Knowledge Question** selected.

2.  Select the **Forms** tab and click to open the **Main** form.

3.  Drag the **Scenario Description** field from the fields explorer and drop it
    above the **Question** field on the form.

4.  Drag the **Question Type** field from the fields explorer and drop it above
    the **Scenario Description** field on the form.

5.  Double click on **Scenario Description** field.

6.  Uncheck the **Visible by Default** checkbox and click **OK**.

7.  Drag the **Knowledge Assessment** field from the fields explorer and drop it
    below the **Owner** field on the form.

8.  Click **Save**.

9.  Click **Publish**.

10. Click **Save and Close**.

11. Click **Done**.

12. Click on the solution name **Custom Data Service Solution** located in the
    navigation breadcrumbs.

Exercise 4 – Create Business Rule
---------------------------------

### Task 1 – Create Question Type Business Rule

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s.

4.  Click to open the **Knowledge Assessment Solution** you imported.

5.  Click to open the **Knowledge Question** entity.

6.  Select the **Business Rules** tab and click **Add Business Rule**.

7.  Click on the **Show Details** button next to the business rule name.

8.  Enter **Question Type Rule** for **Business Rule Name** and click on the
    **Hide Details** button.

9.  Select the **Condition** and enter **Check Question Type** for **Display
    Name.**

10. Go to the **Rule** section, select **Question Type** for **Field**, select
    **Equals** for **Operator**, select **Value** for **Type**, and select
    **Scenario** for **Value**.

11. Click **Apply**.

12. Select the **Components** tab.

13. Drag **Set Visibility** action and place it on the **True** side (on the
    right side) of the condition.

14. Enter **Show Scenario Description** for **Display Name**, select **Scenario
    Description** for **Field**, select **Yes** for **Visible** and click
    **Apply**.

15. Select the **Components** tab.

16. Drag **Set Business Required** action and place it after the **Show Scenario
    Description** action.

17. Select the new action, enter **Make Scenario Required** for **Display
    Name**, select **Scenario Description** for **Field**, select **Business
    Required** for **Status** and click **Apply**.

18. Drag **Set Visibility** action and place it on the **False** side (below) of
    the condition.

19. Enter **Hide Scenario Description** for **Display Name**, select **Scenario
    Description** for **Field**, select **No** for **Visible** and click
    **Apply**.

20. Select the **Components** tab.

21. Drag **Set Business Required** action and place it after the **Hide Scenario
    Description** action.

22. Select the new action, enter **Remove Scenario Requirement** for **Display
    Name**, select **Scenario Description** for **Field**, select **Not Business
    Required** for **Status** and click **Apply**.

23. Select the **Components** tab.

24. Drag **Set Field Value** action and place it after the **Remove Scenario
    Requirement** action.

25. Select the new action, enter **Clear Field** for **Display Name**, select
    **Scenario Description** for **Field**, select **Clear** for **Type** and
    click **Apply**.

26. Change the **Scope** to **All Forms**. You can find the Scope in the command
    bar.

27. Click **Save**.

28. Click **Activate**.

29. Confirm activation.

30. Close the business rule designer.

31. Click **Done**.

### Task 2 – Test Business Rule

1.  Navigate to <https://web.powerapps.com/> and select the **Practice**
    environment.

2.  Select **Apps** and click on the **Knowledge Admin** Model-Driven
    application.

3.  Select **Assessments** and click **+ New**.

4.  Enter **Test Assessment** for **Title**, select today’s date for **Start
    Date**, a month from today for **End Date**, and click **Save**.

5.  Select the **Questions** tab.

6.  Click **+ Add New Knowledge Question**.

7.  Select **Scenario** for **Question Type**. The **Scenario** field will come
    to view, and it will be required.

8.  Type **This is a test Scenario** in the **Scenario Description**.

9.  Change the **Question Type** to **Simple**. The Scenario field will
    disappear.

10. Change the **Question Type** back to **Scenario**. The **Scenario
    Description** will come to view again and the text you entered will no
    longer be there.

11. Type **This is a test Scenario** for **Scenario Description**.

12. Type **Test Question** for **Question**.

13. Scroll down to the **Answers** section, enter **Test Answer One** for
    **Answer 1**, enter **20** for **Answer 1 Points.**

14. Click **Save**.
