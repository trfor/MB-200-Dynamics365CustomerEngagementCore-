Module 4: Building Canvas Applications
======================================

Lesson 4: Practice Lab – Working with data and services

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You have been assigned to
continue work on the Fabrikam Knowledge canvas app that we started creating in
the prior module. In this practice you will be working with the CDS connector to
filter the list, save the results of the assessment in CDS and add support for
submitting feedback using the EditForm.

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

Exercise 2 – Filtering Data
---------------------------

### Task 1 – Filter Knowledge Assessments 

In this task, you will filter the Knowledge Assessment to show only Active
records that have Start Date in the past and End Date is in the future.

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Select **Common Data Service Default Solution**

5.  Select the **Fabrikam Assessment** Canvas application.

6.  Click on the **Edit** button located on the command bar.

7.  Wait for the app designer to load.

8.  Select the **knowledgeAssessmentList** gallery.

9.  Set the **Items** Property to the snippet below. This snippet will filter
    the Knowledge Assessment records and the list will show only the active
    records with Start Date in the past and End Date in the future. Note: if you
    type this instead of pasting it you will see how the editor helps you build
    expressions.

    Filter('Knowledge Assessments', (Status = 'Status (Knowledge Assessments)'.Active && 'Start Date' <= Today() && 'End Date' >= Today()))

10.  Click **File** and **Save** your changes.

11.  Click on the **Back** button.

12.  Do not close the app designer.

### Task 2 – Get Current User 

In this task, you will get the current User and save it in a global variable. We
are doing this during OnStart so that it only happens once, and the data is
available for use elsewhere in the app. We will be using this to retrieve a
filtered list of test results submitted by this user.

1.  Select the **mainScreen**.

2.  Select the **OnStart** property and set it to snippet below. This snippet
    will create a global variable **UserPrimaryEmail** that will hold the
    current user’s email.

    Set(UserPrimaryEmail, User().Email)

3.  Add the snippet below to the **OnStart** property. This snippet will first
    terminate the first function with semicolon, get the current User and save
    it in a global variable name **CurrentUser**.

    ;Set(CurrentUser, LookUp(Users, 'Primary Email' = UserPrimaryEmail))

4.  Add the following function to work around an existing bug that does not
    properly load the metadata for related properties. In the future this
    workaround will not be required. Select the **mainScreen** and select the
    **OnStart** property.

5.  Add the below snippet after the functions that are already there.

    ;Set(FirstKABugWorkaround,First('Knowledge Test Results').'Knowledge
    Assessment')

6.  For the variable to be available, we will have to save the changes, close
    the designer and re-open it again. The reason for this is the OnStart is
    only executed during the initial application start.

7.  Click **File** and **Save**.

8.  Click **Close**.

9.  Select **Open**.

10.  Select **PowerApps** and open the **Fabrikam Assessment** application again.

### Task 3 – Save Total Points 

In this task, you will create a Patch that will create a Knowledge Test Result
record. Using the Patch function allows us to on demand create a record with
just specific properties being passed. In this case, we will be using the sum
function to get a total of our points that are stored in our in-memory
collection based on the answers the user provided.

1.  Expand the **takeAssessmentScreen**.

2.  Locate the button and rename it **scoreButton**.

3.  While you still have the **scoreButton** selected, set the **OnSelect**
    property to snippet below. This snippet will create a new Knowledge Test
    Result record.
    
    Patch('Knowledge Test Results', Defaults('Knowledge Test Results'), {'Knowledge
    Assessment': knowledgeAssessmentList.Selected, 'Primary Name':
    knowledgeAssessmentList.Selected.Title, 'Total Points':Sum(UserAnswers.Points,
    Points)} )

### Task 4 – Add Feedback Screen 

In this task, you will add a new screen to the applications, this screen will
let the user submit feedback. This tasks demonstrates how to use the EditForm to
create a new record.

1.  Click on the **… More** button of the **takeAssessmentScreen** and click
    **Duplicate Screen**. We are creating a duplicate screen because we want all
    our screens to look the same, but we don’t want to recreate the header every
    time we add a new screen.

2.  Rename the duplicate screen **addFeedbackScreen**.

3.  Rename the Button on the **addFeedbackScreen** to **submitFeedbackButton**

4.  Change the **Text** property of the **submitFeebackButton** to **"Submit
    Feedback"**

5.  Click on the **… More** button of the **assessmentQuestionList** inside the
    **addFeedbackScreen** and click **Delete**.

6.  Select the **addFeedbackScreen**.

7.  From **Insert** tab click **Forms** and select **Edit**.

8.  In the property panel on the right. Select **Feedback** for **Data Source**.

9.  Rename the form **feedbackForm**.

10. Resize and reposition the **feedbackForm** to your liking.

11. Go to the tree view and expand the **feedbackForm**.

12. Select the **Title** field.

13. Select the **Default** property and set it to the **Title** of the selected
    **Knowledge assessment**.

    knowledgeAssessmentList.Selected.Title

14.  With the **Title** data card still selected

15.  Select the **DisplayMode** property and set it to **View**.

    DisplayMode.View

16.  Right click on Comments_DataCard1 and select Rename to change the
    **Comments_DataCard** field to **userComments**.

17.  Expand the **userComments** data card and rename the **DataCardValue1** to
    **userCommentsText**.

18.  Select the **submitFeedbackButton**.

19.  Replace the **OnSelect** property value with the snippet below. This snippet
    will submit the form, reset the form, and navigate back to the previous
    page.

    SubmitForm(feedbackForm);ResetForm(feedbackForm);Back(ScreenTransition.None)

20.  With the **submitFeedbackButton** still selected, select the **DisplayMode**
    property.

21.  Replace the **DisplayMode** property value with snippet below. This snippet
    will enable the button if the comments filed has value and disable it if the
    comments field is blank.

    If(IsBlank(userCommentsText), DisplayMode.Disabled, DisplayMode.Edit)

22.  Select the **takeAssessmentScreen**.

23.  Go to the **Insert** tab, click **Icons**, and select the **Left** icon.

24.  Place the icon on the left side of the header.

25.  Set the **Color** property of the icon to **White**.

26.  Set the **OnSelect** property of the icon to the snippet below. This snippet
    will navigate back to the previous page.
    
    Back(ScreenTransition.None)

27.  Select the **takeAssessmentScreen**.

28.  Click **Icons** and select the **Emoji - Smile** icon.

29.  Place the icon in the right side of the header and to the right of the User
    Name.
30.  Set the **Color** property of the icon to **White**.

31.  Set the **OnSelect** property of the **Information** icon to the snippet
    below.

    NewForm(feedbackForm);Navigate(addFeedbackScreen, ScreenTransition.None)
