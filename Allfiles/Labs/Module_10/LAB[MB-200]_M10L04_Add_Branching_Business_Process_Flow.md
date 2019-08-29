Module 10: Business Process Flows
================================

Lesson 4: Practice Lab – Adding branching to business process flow

Scenario
--------

You have created several automations to support your client’s knowledge
assessments process and now it is time to bring the final pieces together. In
this lab, you will update the business process flow and add a business rule.

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
    .

Exercise 2 – Update Process 
----------------------------

### Task 1 – Update Business Process Flow

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment.

3.  Select **Solutions**.

4.  Click to open the **Knowledge Assessment Solution**.

5.  Click on the **…** button located on the command bar and select **Switch to
    Classic**.

6.  Select **Processes** and open the **Assessment Process** you created.

7.  Select the **Components** tab, drag **Condition** and drop it in between the
    two existing stages.

8.  Select the **Condition**, select the **Properties** tab, and enter **Check
    Notification** for **Display Name**.

9.  Go to **Rule 1,** select **Notify Manager** for **Field**, select **Value**
    for **Type**, select **Yes** for **Value**, and click **Apply**.

10. Select the **Condition**, click **Connector** and select **Disconnect**.

11. Click **Update**.

12. Close the process editor.

13. Close the solution explorer.

### Task 2 – Add Business Lock Unlock Rule

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment.

3.  Select **Solutions** and open the **Knowledge Assessment Solution**.

4.  Click to open the **Knowledge Assessment** entity.

5.  Select the **Business Rules** tab and click **Add Business Rule**.

6.  Click on the **Show Details** chevron button next to the Business Rule name.

7.  Enter **Lock/Unlock Status** and click **Hide Details**.

8.  Select the **Condition**, go to the **Properties** tab, and enter **Check
    Notification** for **Display Name**.

9.  Go to **Rule 1**, select **Notify Manager** for **Field**, select **Equals**
    for **Operator**, select **Value** for **Type**, select **Yes** for
    **Value**, and click **Apply**.

10. Add new **Rule** by clicking **+ New**.

11. Go to **Rule 2**, select **Approval Status** for **Field**, select **Does
    not Equal** for **Operator**, select **Value** for **Type**, and select
    **Approved** for **Value**.

12. Make sure **And** is select for **Rule Logic** and click **Apply**.

13. Select the **Components** tab, drag **Lock/Unlock** action and drop it on
    the **True** side of the condition (the checkmark side).

14. Select the **Lock/Unlock** action, got to the **Properties** tab, enter
    **Lock Status** for **Display Name**, select **Assessment Status** for
    **Field**, select **Lock** for **Status**, and click **Apply**.

15. Select the **Components** tab, drag **Lock/Unlock** action and drop it on
    the **False** side of the condition (the x side).

16. Select the second **Lock/Unlock** action, got to the **Properties** tab,
    enter **Unlock Status** for **Display Name**, select **Assessment Status**
    for **Field**, select **Unlock** for **Status**, and click **Apply**.

17. Click **Save**.

18. Click **Activate**.

19. Confirm activation.

20. Close the process editor.

21. Click **Done**.

### Task 3 – Test the Updated Business process Flow

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment.

3.  Select **Apps** and click to open the **Knowledge Admin** application.

4.  Select **Assessments**.

5.  Click **New**.

6.  Enter **BPF Assessment Two** for **Title** and click **Save**.

7.  Select the **Questions** tab and click **New Knowledge Question.**

8.  Select **Simple** for **Question Type**.

9.  Enter **Process Test Question** for **Question**.

10. Enter **Answer One** for **Answer 1**, **100** for **Answer 1 Points**.

11. Enter **Answer Two** for **Answer 2**, **0** for **Answer 2 Points**.

12. Enter **Answer Three** for **Answer 3**, **0** for **Answer 3 Points**.

13. Enter **Answer Four** for **Answer 4**, **65** for **Answer 4 Points**.

14. Click **Save**.

15. Click on the browser back button.

16. Your Business Process Flow should have just one stage.

17. Click on the **Assessment** stage of then Business Process Flow. The steps
    for this stage will come to view.

18. Enter **80** for **Passing Score**.

19. Click on the **Total Points** calculator icon.

20. Click **Recalculate**.

21. The **Total Points** should get recalculated.

22. Select **Yes** for **Notify Manager**.

23. The Activate Stage should now be added to the Business Process Flow.

24. Select **Complete** for **Create Questions** and click **Next Stage**.

25. The process should move to the **Activate** stage.

26. The Approval Flow should run and set the **Approval Status** to **Waiting**.

27. The Business Rule should run and **Lock** the **Assessment Status**. Do not
    close this page.

28. Start a new browser window and navigate to
    [https://flow.microsoft.com](https://flow.microsoft.com/)

29. Select **Approvals**.

30. You should have one approval waiting for you. Click on the approval.

31. The Approval pane will open. Click **Approve**.

32. Provide **Comments** and click **Confirm**.

33. Go back to **Knowledge Admin** application and click on the **Refresh**
    button.

34. Click on the **Activate** stage of the Business Process Flow.

35. The Approval Flow should complete the approval and set the **Approval
    Status** to **Approved**.

36. The Business Rule should **Unlock** the **Assessment Status** field.

37. Select **Published** for **Assessment Status** and click **Finish**.
