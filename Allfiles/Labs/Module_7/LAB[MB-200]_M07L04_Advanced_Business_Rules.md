Module 7: Business Rules
========================

## Lesson 4: Practice Lab – Advanced business rules

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a model-driven Knowledge Admin app for your client Fabrikam and need
to add scoring functionality without code. In this lab, you will create a
calculated field, a rollup field, and a business rule.

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

Note: If you have already completed a practice recently, the virtual machine
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

### Task 1 – Add Field to Knowledge Question

1.  Navigate to <https://web.powerapps.com>

2.  Select the **Practice** environment you created.

3.  Select **Solution**s.

4.  Click to open the **Knowledge Assessment Solution** you imported.

5.  Click to open the **Knowledge Question** entity.

6.  Select the **Fields** tab and click **+ Add Field**.

7.  Enter **Question Points** for **Display Name** and select **Whole Number**
    for **Data Type**.

8.  Click **+ Add Calculation or Rollup** and select **Calculation**.

9.  Click **Save**.

10. On the **Set Question Points** popup, click **+ Add Action**.

11. Type **answer1points** and select the suggested field.

12. Type **+** , type **answer2points** and select the suggested field.

13. Repeat it for **answer3points** and **answer4points**. You action will look
    like the snippet below.

>   *cre7f_answer1points + cre7f_answer2points + cre7f_answer3points +
>   cre7f_answer4points*

1.  Save the action by clicking on the checkmark button.

2.  Click **Save and Close**.

3.  Click **Done**.

4.  Click **Save Entity**.

### Task 2 – Add Field to Knowledge Question Form

1.  Make sure you still have the **Knowledge Question** selected.

2.  Select the **Forms** tab and click to open the **Main** form.

3.  Drag the **Question Points** field from the fields explorer and drop it
    below the **Knowledge Assessment** field on the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click **Save and Close**.

7.  Click **Done**.

8.  Click on the solution name **Knowledge Assessment Solution** located in the
    navigation breadcrumbs.

### Task 3 – Add Field to Knowledge Assessment

1.  Click on the **…** button located in the command bar and click **Switch to
    Classic**.

2.  Expand **Entities**, expand the **Knowledge Assessment** entity, select
    **Fields**, and click **New**.

3.  Enter **Total Points** for **Display Name**, select **Whole Number** for
    **Date Type**, select **Rollup** for **Filed Type**, and click **Edit**.

4.  Click **+ Add Related Entity**.

5.  Select **Knowledge Questions** for **Related** and click **Tick**.

6.  Click **+ Add Aggregation**.

7.  Select Sum for **Aggregation Function**, select **Question Points** for
    **Aggregated Related Entity Filed**, and click **Tick**.

8.  Click **Save and Close**.

9.  Click **Save and Close** again.

10. Click **Publish All Customizations**.

11. Close the solution explorer.

### Task 4 – Add Field to Knowledge Assessment Form

1.  Make sure you still have the **Knowledge Assessment** selected.

2.  Select the **Forms** tab and click on the Main form.

3.  Drag the **Total Points** field from the fields explorer and drop it below
    the **Difficulty** field on the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click **Save and Close**.

7.  Click **Done**.

8.  Click on the solution name **Knowledge Assessment Solution** located in the
    navigation breadcrumbs.

9.  Click **Publish All Customizations**.

Exercise 3 – Create Business Rule
---------------------------------

### Task 1 – Create Question Points Business Rule

1.  Click to open the **Knowledge Question** entity.

2.  Select the **Business Rules** tab and click **Add Business Rule**.

3.  Click on the **Show Details** button next to the business rule name.

4.  Enter **Question Points Rule** for **Business Rule Name** and click on the
    **Hide Details** button.

5.  Select the **Condition** and enter **Check Question Points** for **Display
    Name.**

6.  Go to the **Rules** section, select **Answer 1 Points** for **Filed**,
    select **Is Less Than or Equals to** for **Operator**, select **Value** for
    **Type**, enter **0** for **Value**, and click **Apply**.

7.  Click **+ New** rule.

8.  Go to the **Rule 2**, select **Answer 2 Points** for **Filed**, select **Is
    Less Than or Equals to** for **Operator**, select **Value** for **Type**,
    enter **0** for **Value**, and click **Apply**.

9.  Click **+ New** rule.

10. Go to the **Rule 3**, select **Answer 3 Points** for **Filed**, select **Is
    Less Than or Equals to** for **Operator**, select **Value** for **Type**,
    enter **0** for **Value**. And click **Apply**.

11. Go to the **Rule 4**, select **Answer 4 Points** for **Filed**, select **Is
    Less Than or Equals to** for **Operator**, select **Value** for **Type**,
    enter **0** for **Value**, and click **Apply**.

12. Click **+ New** rule.

13. Select the **Components** tab.

14. Drag **Show Error Message** action and place it in **True** side of the
    Condition.

15. Select the action, enter **Show Points Error Message** for **Display Name**,
    select **Question** for **Field**, enter **At least one answer must have
    points more than zero**, and click **Apply**.

16. Click **Save**.

17. Click **Activate**.

18. Confirm the activation.

19. Close the business rule designer.

20. Click **Done**.

### Task 2 – Test Business Rule

1.  Navigate to <https://web.powerapps.com/> and select the **Practice**
    environment.

2.  Select **Apps** and click on the **Knowledge Admin** Model-Driven
    application.

3.  Select **Assessments** and click to open the **Test Assessment**.

4.  Select the **Questions** tab.

5.  Click **+ Add New Knowledge Question**.

6.  The error message for the points requirement will be displayed on the
    Question field.

7.  Select **Simple** for **Question Type**.

8.  Type **Test Two Question** for **Question**.

9.  Click **Save**. You will not be able to save because of the points
    requirement.

10. Scroll down to the **Answers** section, enter **Test Answer One** for
    **Answer 1**, enter **20** for **Answer 1 Points.** The points requirement
    error will go away.

11. Click Save. The record will now be saved.

12. Scroll down to the **Answers** section again, enter **Test Answer Two** for
    **Answer 2**, and **0** for **Answer 2 Points**.

13. Enter **Test Answer Three** for **Answer 3**, and **10** for **Answer 3
    Points**.

14. Enter **Test Answer Four** for **Answer 4**, and **50** for **Answer 4
    Points**.

15. Scroll up and locate the **Question Point** field. The calculated points
    should show in this field.

16. Click **+ New**.

17. Select **Test Assessment** for **Knowledge Assessment**, select **Simple**
    for **Question Type**, and enter **Test Three Question** for **Question**.

18. Scroll down to the Answers section.

19. Enter **Test Three Answer One** for **Answer 1**, and **25** for **Answer 1
    Points**.

20. Enter **Test Three Answer Two** for **Answer 2**, and **80** for **Answer 2
    Points**.

21. Enter **Test Three Answer Three** for **Answer 3**, and **10** for **Answer
    3 Points**.

22. Enter **Test Three Answer Four** for **Answer 4**, and **0** for **Answer 4
    Points**.

23. Click **Save and Close**.

24. Locate the **Knowledge Assessment** field and click **Test Assessment**.

25. Scroll down to locate the **Total Points** field and click on the calculator
    icon.

26. Click **Recalculate**.

27. The field show now show the total points of all the questions.

