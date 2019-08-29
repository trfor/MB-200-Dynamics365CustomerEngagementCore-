Module 3: Building Model-Driven Applications
============================================

## Lesson 4: Practice Lab – Modifying Forms

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. In this practice you will be
continuing your work on the model-driven Knowledge Admin app. In this practice,
you will be modifying the auto generated forms to add the new fields you added
in the data-modeling practice.

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

Exercise 2 – Edit the Knowledge Assessment Form 
------------------------------------------------

In this exercise, you will edit the form for the Knowledge Assessment entity.
There are two places you can edit this from, either from the Solutions > Entity > Forms list, or via the App Designer. If you are already in App
Designer start, there.

### Task 1 – Enable Notes on the Knowledge Assessment entity

Initially when the entity was created notes were not enabled. Since then the
client Fabrikam has determined that they like to be able to track notes against
the knowledge assessments. We are going to make this change before getting into
the form editor because it is the easier way to do so. The same is true, for
example, if you need to add any fields: you should always try to add the fields
before jumping into the editor.

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open the **Common Data Service Default Solution**.

5.  Click on the **Knowledge Assessment** entity.

6.  Click **Settings** in the command bar

7.  Check the **Enable Attachments** checkbox, this enables notes and files for
    the entity.

8.  Click **Done**.

9.  Click **Save Entity**.

### Task 2 – Edit the Knowledge Assessment form

In this task, you will perform the following changes to the form: 

- Put fields in the header 
- Insert the Timeline control
- Add a tab that contains a list of related assessment questions

To customize your form:

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open the **Common Data Service Default Solution**.

5.  Select the **Knowledge Admin Model – Driven App**.

6.  Click **Edit**.

7.  Locate the **Knowledge Assessment** entity and select **Forms**.

8.  Go to the **Components** tab, hover over the **Main Information** form and
    click **Edit**.

9.  Double click on the **Header** section of the form.

10. In the **Field Explorer**, uncheck the **Only Show Unused Fields** checkbox.

11. Drag the **Owner** field for the **Field Explorer** and place it in the
    right column of the **Header**.

12. Drag the **Days Remaining** filed to the left column of the **Header**.

13. Select the **General** tab by double clicking on it.

14. Double click on the **General** tab again.

15. Select the **Formatting** tab.

16. Select **Two Columns 50% Column 1 - 50% Column** and click **OK**.

17. Select the new section of the **General** tab.

18. Select the **Insert** tab.

19. Click **Timeline**. Timeline is located below the IFRAME.

20. Select the **Owner** field located in the General section.

21. Select the **Home** tab.

22. Click **Remove**. We are removing this field because we added a duplicate
    field to the header.

23. Add the **Start Date** field to the **General** section and place it below
    the **Title** field. You can add fields to the form by selecting the section
    you want to add the field to and double clicking on the filed you want to
    add, or you can drag the field from the field explorer and drop it in the
    section you want to add the field to.

24. Add the **End Date** to the **General** section and place it below the
    **Start Date** field.

25. Add the **Difficulty** field to the **General** section and place it below
    the **End Date** field.

26. Select the **Insert** tab.

27. Click **One Column** tab. A new tab will be added to the form.

28. Double click on the new tab.

29. Change the **Label** to **Questions** and click **OK**.

30. Select the **Questions** tab.

31. Select the **Insert** tab.

32. Click **Sub-Grid**.

33. Enter **KnowledgeQuestions** for **Name**.

34. Select **Only Related Records** for **Records**.

35. Select **Knowledge Questions** for **Entity**.

36. Click **OK**.

37. Select the **Home** tab and click **Save**.

38. Click **Publish** and wait for the publish to complete.

39. Close the form by clicking **Save and Close**.

40. **DON’T** close the app designer.

Exercise 3 – Edit the Knowledge Question Form 
----------------------------------------------

In this exercise, you will edit the form for the Knowledge Question entity.

### Task 1 – Edit the main form

1.  Make sure you are on the app designer.

2.  Click **+ Add** and select **Entities**.

3.  Locate the **Knowledge Question** entity and select it.

4.  After the **Knowledge Question** entity is added to the application, select
    **Forms**.

5.  Hover over the **Main Form** and click **Edit**.

6.  Select the **Header** by double clicking on it.

7.  Add the **Knowledge Assessment** field to **Header** and place it on the
    left column.

8.  Select the **General** tab by double clicking.

9.  Select the **Insert** tab.

10. Click **Section** and select **One Columns**.

11. Double click on the new section.

12. Enter **Answers** for Label and check the **Show Label** checkbox.

13. Click **OK**.

14. Add **Answer 1** field to the **Answers** section.

15. Add **Answer 1 Points** after the **Answer 1**.

16. Repeat the two steps above for each Answer and Points.

17. Select the **Home** tab.

18. Click **Save**.

19. Click **Publish** and wait for the publish to complete.

20. Click **Save and Close** to close the form editor.

21. Click **Save** to save the changes to the application.

22. Click **Validate** and make sure there are no errors. You can ignore the
    warnings.

23. Click **Publish** to publish your changes.

24. **DON’T** close the app designer.

### Task 2 – Test Your Work

1.  Click **Play**.

2.  Click on the **Administration** area located in bottom-left of the page and
    select the **Assessments** area.

3.  Select the **Assessment** entity and click **+ New**.

4.  The form should have two tabs **General** and **Questions**.

5.  The General tab should have two sections **General** and **Timeline**.

6.  Enter **Assessment Three** for **Title**.

7.  Select today’s date for **Start Date** and select ten days into the future
    for **End Date**.

8.  Select **Beginner** for **Difficulty**.

9.  Click **Save**.

10. Make sure the **Days Remaining** value was calculated correctly.

11. Select the **Questions** tab

12. Click **Add New Knowledge Question**.

13. Close the application without creating **Knowledge Question** record.

14. You should back on the app designer. Click **Save and Close** to close it.
