Module 4: Building Canvas Applications
======================================

## Lesson 6: Practice Lab – User experience

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You have been assigned to
continue work on the Fabrikam Knowledge canvas app that we started creating in
the prior module. In this practice you will be providing the user with visual
feedback of which questions they got right and wrong. You will also be enabling
the score button only if the user has provided some answers.

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

Exercise 2 – Customizing the User Experience
--------------------------------------------

### Task 1 – Show the Assessment Result 

In this task, you will show the assessment result to the user. In this task you
will use a local variable ShowResults to indicate if the results should show. It
will be updated upon the user clicking the score button. Each item will then use
an expression to highlight if the answer is right or wrong, only when
ShowResults is true.

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Select **Common Data Service Default Solution.**

5.  Select the **Fabrikam Assessment** Canvas application.

6.  Click on the **Edit** button located on the command bar.

7.  Wait for the app designer to load.

8.  Select the **takeAssessmentScreen.**

9.  Select the **OnVisible** property of the **takeAssessmentScreen** and
    replace the value with the snippet below. This snippet will re-add the Clear
    function and add a new function that will initialize a variable
    **ShowResults** and set it to **false**.

    Clear(UserAnswers);UpdateContext({ShowResults:false})

10.  Select the **OnSelect** property of the **scoreButton**.

11.  Add the snippet below to the content you currently have. This snippet will
    add a function that will set the **ShowResults** value to **true**.

    ;UpdateContext({ShowResults:true})

12.  Select **Answer4Selected** checkbox of the **assessmentQuestionList**.

13.  Select the **Fill** property of **Answer4Selected** and set it to the
    snippet below. This snippet will

14.  Set the Fill Color to White if ShowResults is false.

15.  Set the Fill Color to Red id ShowResults is true, the checkbox is check, and
    the Points value is less than 0.

16.  Set the Fill Color to Green id ShowResults is true, the checkbox is check,
    and the Points value is more than 0.

    If(ShowResults, If(answer4Selected.Value = true && ThisItem.'Answer 4 Points' \>
    0, Green, If(answer4Selected.Value = false, White, Red)), White)

17.  Select the **Fill** property of **Answer3Selected** checkbox and set to the
    snippet below.

    If(ShowResults, If(answer3Selected.Value = true && ThisItem.'Answer 3 Points' \>
    0, Green, If(answer3Selected.Value = false, White, Red)), White)

18.  Select the **Fill** property of **Answer2Selected** checkbox and set to the
    snippet below.

    If(ShowResults, If(answer2Selected.Value = true && ThisItem.'Answer 2 Points' \>
    0, Green, If(answer2Selected.Value = false, White, Red)), White)

19.  Select the **Fill** property of **Answer1Selected** checkbox and set to the
    snippet below.

    If(ShowResults, If(answer1Selected.Value = true && ThisItem.'Answer 1 Points' \>
    0, Green, If(answer1Selected.Value = false, White, Red)), White)

### Task 2 – Disable/Enable Button 

In this task, you will disable the score button if there are no answers selected
and enable it when there is at least one answer selected.

1.  Select the **scoreButton**.

2.  With the **scoreButton** selected, set the **DisplayMode** property to the
    snippet below. This snippet will disable the button if there are no answers
    selected and enable it if there is at least one answer selected.

    >   If(CountRows(UserAnswers) \> 0, DisplayMode.Edit, DisplayMode.Disabled)

### Task 3 – Add Button for Results Screen 

In this task, you will add a button to the Main Screen, this button will
navigate to the Results page.

1.  Select the **mainScreen**.

2.  Go to the **Insert** tab and click **Icons**.

3.  Select the **… More** Icon.

4.  Place the icon in the left side of the header

5.  Select the **Home** tab and change the **Color** of the icon to **White**.

6.  Select the **OnSelect** property of the icon and provide the function below.
    This function will run when the icon is clicked and navigate to the Results
    Screen.

    Refresh(Users);Navigate(resultsScreen, ScreenTransition.None)

### Task 4 – Test Your Work 

In this task, you will run and test the applications.

1.  Select the **mainScreen**.

2.  Click **Play**.

3.  Click on the **… More** icon.

4.  You should navigate to the **Results Screen**. This page might be empty
    because you didn’t take any tests yet.

5.  Click on the **Back** button.

6.  You will be taken back to the **Main Screen.**

7.  Click on the take test icon of one of the **Assessments**.

8.  The questions should load, and the **Score Assessment** button should be
    **Disabled**. This is because you must select at least one answer before you
    can submit your answers. Note: If you do not see any data, you need to use
    the model-driven app to create some assessment questions with answers. Make
    sure to give some questions points with positive values (correct answers)
    and some with negative values (wrong answers)

9.  Select some answers.

10. The **Score Assessment** button will now be enabled.

11. Click on the **Score Assessment** button.

12. The answers that have more 0 points will become **Green** and the answers
    that have 0 zero points will become **Red**.

13. Click on the **Information** button.

14. You will be taken to the **Feedback Screen**.

15. The Submit Feedback button will be **Disabled**. This is because you must
    provide a comment before you can submit the feedback.

16. Provide a **Comment**.

17. The Submit Feedback will become **Enabled**.

18. Click **Submit Feedback**.

19. Your **Feedback** will be submitted, and you will navigate back to the
    **Assessment Screen**.

20. Click on the **Back** button.

21. You will go back to the **Main Screen**.

22. Click on the **… More** icon.

23. You will be taken to the **Results Screen**. You should see at least one
    result in the **Results** list.

24. Click on the **Back** button.

25. You will go back to the **Assessments Screen**.

26. Close the **Preview**.

27. Click **File** and **Save**.

28. Click **Close** to close the app designer.

### Task 5 – Other things you can try

Now that you have built a basic canvas app that interacts with the Common Data
Service, here are some things you can try on your own to make the app better.
**The following steps are optional and are more advanced to challenge your
learning. These are not expected or required to all be completed.**

1.  Try different ways of presenting the Test Results – for example you could
    try the Data Grid control

2.  Add an image control to the mainScreen and show the user’s profile image
    using User().Image. Note: You will need to setup a profile image for the
    user you are using for it to show more than the default image.

3.  You can add an image to the Knowledge Assessment entity and then change the
    mainScreen list of Assessments to show the image. Note: after you add the
    entity image in CDS, you will need to upload an image via the model-driven
    app. You will also need to go to View-Data Sources and refresh the Knowledge
    Assessment entity metadata.

4.  Think about how else you might improve the app using the knowledge you’ve
    gained during the practices. You can always Save As your app, and try any
    changes you want without impacting your completed work!
