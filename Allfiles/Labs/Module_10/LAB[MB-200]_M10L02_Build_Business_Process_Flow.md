Module 10: Business Process Flows
================================

## Lesson 2: Practice Lab – Build a business process flow

Scenario
--------

You have been building automations to support your client Fabrikam’s knowledge
assessment process. The client is concerned that their users won’t be able to
create new knowledge assessments without your help. You need to create a guided
process to interact with the user and support their configuration of new
assessments. In this lab, you will enable the knowledge assessment entity for
business process flows and then build a business process flow.

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

### Task 1 – Add Field to Knowledge Assessment

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s.

4.  Click to open the **Knowledge Assessments Solution** you imported.

5.  Click to open the **Knowledge Assessment** entity.

6.  Click select the **Fields** tab and **+ Add Field**.

7.  Enter **Passing Score (%)** for **Display Name**, select **Whole Number**
    for **Data Type** and click **Done**.

8.  Click **Save Entity**.

9.  Click **+ Add Field**.

10. Enter **Create Questions** for **Display Name** and select **Two Options**
    for **Data Type**.

11. Click on the **Yes** option under **Items** and replace **Yes** with
    **Completed**.

12. Click on the **No** option under **Items** and replace **No** with **Mark
    Complete**.

13. Click **Done**.

14. Click **Save Entity**.

### Task 2 – Add Field to Knowledge Assessment Form

1.  Make sure you still have the **Knowledge Assessment** selected.

2.  Select the **Forms** tab and click on the Main form.

3.  Add the **Passing Score (%)** field to the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click **Save and Close**.

7.  Click **Done**.

8.  Click on the solution name **Custom Data Service Solution** located in the
    navigation breadcrumbs.

9.  Click **Publish All Customizations**. Do bot navigate away from this page.

Exercise 3 – Create Business Process Flow 
------------------------------------------

### Task 1 – Create Business Process Flow

1.  Select **Solutions**.

2.  Click to open the **Knowledge Assessment Solution**.

3.  Click on the **…** button located on the command bar and select **Switch to
    Classic**.

4.  Expand **Entities** and select the **Knowledge Assessment** entity.

5.  Locate the **Process** section and check the **Business Process Flow**
    checkbox.

6.  Click **Save**.

7.  Collapse **Entities** and select **Processes** and click **New**.

8.  Enter **Assessment Process** for **Process Name**, select **Business Process
    Flow** for **Category**, select **Knowledge Assessment** for entity, and
    click **OK**.

9.  Select the stage, select the **Properties** tab, enter **Assessment** for
    **Display Name** and click **Apply**.

10. Click the **Details** of the **Assessment** stage.

11. Select the **Data Step**.

12. Select **Passing Score (%)** for **Data Field** and click **Apply**.

13. Click **+ Add** and select **Add Data Step**.

14. Click on the **+** below the **Passing Score (%)** step.

15. Select the **New Step**, select **Total Points** for **Data Field**, and
    click **Apply**.

16. Select the **Components** tab, drag **Data Step** form the **Components**
    tab and drop it below the **Total Points** step.

17. Select **Notify Manager** for **Data Field** and click **Apply**.

18. Drag **Data Step** from the **Components** tab and place it below the
    **Notify Manager** step.

19. Select **Create Questions** for **Data Field**, check the **Required**
    checkbox, and click **Apply**.

20. Click **+ Add** and select **Add Stage**.

21. Add the new stage to the right of the **Assessment** stage.

22. Select the new stage, go to the **Properties** tab, enter **Activate** for
    **Display Name** and click **Apply**.

23. Click **Details** of the **Activate** stage.

24. Select the **Data Step** inside the **Activate** stage.

25. Select **Assessment Status** for **Data Field** and click **Apply**.

26. Select the Components tab, drag Data Step and place it below the Assessment
    Status step.

27. Select **Approval Status** for **Data Field** and click **Apply**.

28. Click **Save** to save the **Business Process Flow**.

29. Click **Activate**.

30. Confirm activation.

31. Close the process editor.

32. Click **Publish All Customizations**.

33. Close the solution explorer.

### Task 2 – Test Business Process Flow

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment.

3.  Select **Apps** and click to open the **Knowledge Admin** application.

4.  Select **Assessment** and click to open the **Test Assessment**.

5.  Existing records will not pick up the Business Process Flow you created.
    Click **Process** and select **Switch Process**.

6.  Select the **Assessment Process** you created and click **OK**.

7.  The **Assessment Process** should now be used.

8.  Click **New**.

9.  New records should pick up the new Business Process Flow.

10. Enter **BPF Test Assessment** for **Title** and click **Save**.

11. Select the **Questions** tab and click **Add New Knowledge Question**.

12. Select **Simple** for **Question Type**.

13. Enter **Process Test Question One** for **Question**.

14. Enter **Answer One** for **Answer 1**, **50** for **Answer 1 Points**.

15. Enter **Answer Two** for **Answer 2**, **80** for **Answer 2 Points**.

16. Enter **Answer Three** for **Answer 3**, **0** for **Answer 3 Points**.

17. Enter **Answer Four** for **Answer 4**, **0** for **Answer 4 Points**.

18. Click **Save**.

19. Click on the browser back button.

20. Click on the **Assessment** stage of then Business Process Flow. The steps
    for this stage will come to view.

21. Enter **80** for **Passing Score**.

22. Click on the **Total Points** calculator icon.

23. Click **Recalculate**.

24. The **Total Points** should get recalculated.

25. Select **Yes** for **Notify Manager**.

26. Select **Complete** for **Create Questions** and click **Next Stage**.

27. The process should move to the **Activate** stage.

28. The Approval Flow should run and set the **Approval Status** to **Waiting**.

29. Start a new browser window and navigate to <https://flow.microsoft.com>

30. Select **Approvals**.

31. You should have one approval waiting for you. Click on the approval.

32. The Approval pane will open. Click **Approve**.

33. Provide **Comments** and click **Confirm**.

34. Go back to **Knowledge Admin** application and click on the **Refresh**
    button.

35. Click on the **Activate** stage of the Business Process Flow.

36. The Approval Flow should complete the approval and set the **Approval
    Status** to **Approved**.

37. Select **Published** for **Assessment Status** and click **Finish**.
