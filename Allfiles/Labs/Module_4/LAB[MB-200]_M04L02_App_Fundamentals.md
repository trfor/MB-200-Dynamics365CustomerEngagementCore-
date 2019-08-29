Module 4: Building Canvas Applications
======================================

Lesson 2: Practice Lab – App fundamentals

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You have been assigned to
continue work on the Fabrikam Knowledge canvas app that we started creating in
the prior module. In this practice you will be starting to build out the screens
and connecting to the data in CDS.

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

Exercise 2 – Setup the Data Sources from CDS
--------------------------------------------

In this exercise, you will be associating the data sources needed with the
application.

### Task 1 – Setup data sources 

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created. You can find
    the environment selector in the upper right corner.

3.  Select **Solutions**.

4.  Select **Common Data Services Default Solution.**

5.  Select the **Fabrikam Assessment** Canvas application.

6.  Click on the **Edit** button located on the command bar.

7.  The app designer should open. There are 5 tabs on top of the app designer
    File, Home, Insert, View, and Action. Select the **View** tab.

8.  Click on the **Data Sources** button.

9.  The **Data** pane will open. Click **Add Data Source**.

10. Select **Common Data Service**.

11. You will be presented with a list of entities. Select the **Feedback**,
    **Knowledge Assessments**, **Knowledge Questions**, **Knowledge Test
    Results**, and **Users**, entities. You can use the Search feature to make
    it quicker to find the entities.

12. Click **Connect**. If a warning screen appears regarding user licensing,
    click **Got It**.

13. The data from the entities you selected will now be available for your
    application. Close the **Data** pane.

14. Click on the **File** tab and click **Save**. Saving your work periodically
    is always a good idea.

15. To go back to the app designer, click on the **Back** button located on the
    top left of the page.

16. Do not close the App designer.

Exercise 3 – Setup screens for Knowledge Assessment and Taking Assessment
-------------------------------------------------------------------------

In this exercise, you will be adding a list of Knowledge Assessment available to
the main screen, and then adding navigation to drill down to allow employees to
take the assessment.

### Task 1 – Setup Knowledge Assessment screen 

1.  Click on the **...** button of **mainScreen** and select **Duplicate
    Screen**.

2.  Click on the **…** button of the new screen and click **Rename**.

3.  Rename the Screen **takeAssessmentScreen.** Note: It is always good to give
    components a good name so when you reference them later there will not be
    confusion.

4.  Select the **mainScreen**.

5.  Make sure the **Insert** tab is selected. Click **Gallery** and select
    **Horizontal**.

6.  The **Data** pane will come to view. In the Gallery pane just to the right
    of it Select **Knowledge Assessments** for **Data Source** under the
    Properties tab of the Gallery pane.

7.  Select **Days Remaining** for the subtitle.

8.  Close the **Data** pane.

9.  In the left-hand control tree, locate the gallery, right click and select
    rename. Rename the Gallery **knowledgeAssessmentList**

10. Resize the **Gallery** so it takes all the space below the header by
    clicking on the gallery and dragging the image area to fit the space.

11. Select the first item of the **KnowledgeAssessmentList** gallery. Make sure
    you are selecting the item in the designer.

12. Click on the **subtitle** control by clicking **Subtitle1**.

13. Select the **Text** property in the designer function list (fx) and paste
    the snippet below. This snippet will add the text “ Days remaining” to the
    end of the number. If you have issues with the formula, try typing it out
    manually instead of copying and pasting.

    ThisItem.'Days Remaining ' & " Days remaining"

1.  Depending on your test data you may have some items that currently just say
    Days remaining and some that have a number e.g. 6 Days remaining. That is
    ok.

2.  With **Subtitle1** on the **knowledgeAssessmentList** still selected, go to
    the **Insert** tab and click **Icons**.

3.  Select the **Next** icon.

4.  Move the icon to below the **Days Remaining** subtitle by dragging it with
    your mouse.

5.  Select the icon, select the **OnSelect** property and set it the snippet
    below. This snippet will let the user navigate to the Take Assessments
    screen when they click on the icon. If you have issues with the formula, try
    typing it out manually instead of copying and pasting.

    Navigate(takeAssessmentScreen, ScreenTransition.None)

**Note:** If the designer shows a red line under your function it could be due to
the name of the screen being different. If that happens adjust the name used to
be the same as your second screen.

### Task 2 – Setup Taking Assessment screen 

In this task we will be setting up the display of the questions, in subsequent
practices you will be scoring and storing the results.

1.  Select the **takeAssessmentScreen**.

2.  With the **takeAssessmentScreen** still selected, go to the **Insert** tab,
    click **Gallery,** and select **Blank Horizontal**.

3.  The **Data** pane will come to view. Close the **Data** pane.

4.  Rename the Gallery **assessmentQuestionList**.

5.  Select the **assessmentQuestionList** gallery.

6.  Select the **Items** property and set it to the snippet below. This snippet
    will filter the Knowledge Questions for the select Knowledge Assessment. If
    you have issues with the formula, try typing it out manually instead of
    copying and pasting.

    Filter('Knowledge Questions', 'Knowledge Assessment'.'Knowledge Assessment' =
    knowledgeAssessmentList.Selected.'Knowledge Assessment' )

7. Resize the **assessmentQuestionList** until takes all the space below the
    header.

8.  Select the **assessmentQuestionList.**

9.  Click **Add and item from the Insert Tab** of the **assessmentQuestionList**
    gallery.

10.  From the **Insert** tab click **Label**.

11. Select the **Label** you just added and set the **Text** property to
    **Question**.

    ThisItem.Question

12.  If you don’t see any questions display in your app preview, click on
    mainScreen, while holding the alt key, use the mouse to click on the next
    icon on one of the assessment records. You should then navigate to the
    takeAssessment screen. If you still don’t see questions show up check in the
    model-driven app that you have created some test data.

13. With the label still selected, set the **X** property to **0**.

14. Select the **Y** property to **0**.

15. Select **Width** property and set it to **300**.

16. Select the **Height** property to **100**.

17.  From the **Insert** tab click **Controls** and **Check Box**.

18. Move the new checkbox below the Question label.

19. Select the **Text** property of the new checkbox and set it to **Answer 1**.

    ThisItem.'Answer 1'

20. By using the ThisItem. syntax you are referencing a data field from the
    current record.

21. Set the **Width** property to **300** or drag it to expand the width of the
    control.

22. With the CheckBox contro selected, in the property panel on the right side
    of the screen. Select the Advanced tab and set the **OnCheck** property to
    the snippet below. This snippet will add the points of the check answer to a
    Collection name UserAnswers.

    Collect(UserAnswers, {Question:GUID(ThisItem.'Knowledge Question'),
    Points:ThisItem.'Answer 1 Points'})

23. Set the **OnUnCheck** property to the snippet below. This snippet will
    remove the points of the uncheck answer form the Collection when the user
    unchecks the answer.

    Remove(UserAnswers, LookUp(UserAnswers, Question = GUID(ThisItem.'Knowledge
    Question')))

24. Select **takeAssessmentScreen**.

25. Select the **OnVisible** property and paste the snippet below. This will
    clear the prior answers each time they select another question.

    Clear(UserAnswers)

26. In the left control tree, select the checkBox and rename the checkbox
    **answer1Selected**.

27. With **answer1Selected** still selected, go to the **Insert** tab, click
    **Controls** and select **Check Box**. We are going to add the additional
    answer checkboxes and do a similar setup of the options for each of them.

28. Move the new checkbox below the **answer1Selected** checkbox.

29. Select the **Text** property of the new checkbox and set it to **Answer 2**.

    ThisItem.'Answer 2'

30. Set the **Width** property to **300**.

31. Set the **OnCheck** property to the snippet below. This snippet will add the
    points of the check answer to the Collection.
    
    Collect(UserAnswers, {Question:GUID(ThisItem.'Knowledge Question'),
    Points:ThisItem.'Answer 2 Points'})

32. Set the **OnUnCheck** property to the snippet below. This snippet will
    remove the points of the uncheck answer form the Collection.

    Remove(UserAnswers, LookUp(UserAnswers, Question = GUID(ThisItem.'Knowledge
    Question')))

33.  Rename the checkbox **answer2Selected**.

34. With **answer2Selected** still selected, go to the **Insert** tab, click
    **Controls**, and select **Check Box**.

35. Move the new checkbox below the **answer2Selected** checkbox.

36. Select the **Text** property of the new checkbox and set it to **Answer 3**.

    ThisItem.'Answer 3'

37.  Set the **Width** property to **300**.

38.  Set the **OnCheck** property to the snippet below. This snippet will add the
    points of the check answer to the Collection.

    Collect(UserAnswers, {Question:GUID(ThisItem.'Knowledge Question'),
    Points:ThisItem.'Answer 3 Points'})
    
39.  Set the **OnUnCheck** property to the snippet below. This snippet will
    remove the points of the uncheck answer form the Collection.

    Remove(UserAnswers, LookUp(UserAnswers, Question = GUID(ThisItem.'Knowledge
    Question')))

40.  Rename the checkbox **answer3Selected**.

41.  With **answer3Selected** still selected, go to the **Insert** tab, click
    **Controls** and select **Check Box**.

42.  Move the new checkbox below the **answer3Selected** checkbox.

43.  Select the **Text** property of the new checkbox and set it to **Answer 4**.

    ThisItem.'Answer 4'

44.  Set the **Width** property to **300**.

45.  Set the **OnCheck** property to the snippet below. This snippet will add the
    points of the check answer to the Collection.
    
    Collect(UserAnswers, {Question:GUID(ThisItem.'Knowledge Question'),
    Points:ThisItem.'Answer 4 Points'})

46.  Set the **OnUnCheck** property to the snippet below. This snippet will
    remove the points of the uncheck answer form the Collection.

    Remove(UserAnswers, LookUp(UserAnswers, Question = GUID(ThisItem.'Knowledge
    Question')))
    
47.  Rename the checkbox **answer4Selected**.

48.  Select **testAssessmentScreen**.

49.  Go to the **Insert** tab and click **Button**.

50.  Drag and place the button below the **assessmentQuestionList**.

51.  Select the button and set the **Text** property to **“Score Assessment”.**

52.  Make the button larger until the text doesn’t wrap.

53. Click **File** and **Save**.
