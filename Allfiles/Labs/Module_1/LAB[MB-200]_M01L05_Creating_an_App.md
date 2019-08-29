Module 1: Power Platform Overview
=================================

## Lesson 5: Practice Lab – Creating an app

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. Fabrikam would like to encourage
their employees to continuously learn.  They want to build an application that
allow a small set of employees to create knowledge assessments and then make
them available to all employees to test their knowledge.  The employees need to
be able to pick an assessment and quickly complete it in just a few minutes. In
this practice, you will be creating the apps necessary to support this effort.

Working with the solution architect on the project you have determined that you
will create two apps.

**Fabrikam Knowledge Admin** – this will be a model-driven application that you
can quickly enable creation of the knowledge assessments by the users.

**Fabrikam Knowledge** – this will be a PowerApps canvas app that will be a
custom user experience making it easy to find the assessments and take them

In this practice, you will be starting the creation of these applications and
will build them out as you progress through the course. You will also create one
of the template applications so you can see how easy it is to get started using
a “Make from data” template.

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

Exercise 2 – Review Templates and Create App from Data
------------------------------------------------------

In this exercise, you will review the template and sample apps that are
available on the maker portal. You will also create an app using the Create from
data templates to see how quickly that can get a basic canvas app started.

### Task 1 – Review + Create templates/samples

If you have time, you can choose any of these and select Make It and explore on
your own.

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **+ Create** from the left-hand navigation.

4.  Review the different apps that are available to use as both samples and
    starting templates

5.  If you have time choose any of these and select make it, when you are done
    proceed to Task 2

### Task 2 – Create an App over data for Account

Starting a canvas app from data is a quick way to start a canvas app when the
goal is to have a list of data from an entity. 

1.  Select **Home**.

2.  Click **Start from Data**. If it is not on the home screen, select it from
    **Create.**

3.  Click **Make this App**.

4.  Select your **Region** and click **Get Started**.

5.  From the **Start with Data** section, locate the **Common Data Service**
    tile.

6.  Click **Phone Layout**.

7.  Click **Create**.

8.  Select **Accounts** and click **Connect**.

9.  Your app should open in the designer. Click **Play** (Preview the App).

10.  The application will load list of the accounts. View one of the
    **Accounts**.

11.  A detail view of the selected account will load. Click **Edit**.

12.  An editable form of the selected account will load. Enter **Test Account**
    in the **Description** field.

13.  Click **Submit Item** checkbox.

14.  Your changes will be saved, and the detail view will show your changes.
    Click on the **Back** button.

15.  The application will go back to the list of accounts. Close the preview.

16.  Click **File** and select **Save**.

17.  Select the **Cloud** and enter **Fabrikam Accounts** for in the **Name**
    box.

18.  Click **Save**.

19. Explore the app as much as you want and then proceed to the next exercise.
    This app will be saved, and you can always revisit it later to review how
    things are done.

20. Close the **App Designer**.

Exercise 3 – Create the model-driven app
----------------------------------------

In this exercise, you will be creating the Knowledge Admin model-driven app. In
the data modeling module, you will be creating all the entities, so getting this
started will be easy.

### Task 1 – Create a model-driven app

1.  Go back to <https://web.powerapps.com> and make sure you are in the
    **Practice** environment.

2.  Select **Solutions** and open **Common Data Service Default Solution**.

3.  Click in the upper right-hand area for **New \| App \| Model-Driven App**.

4.  Enter **Knowledge Admin** for Name and click **Done**.

5.  Click **Edit Site Map**. Note: When you start a new app, you must edit the
    site map before you can run it otherwise you will get an error. You need to
    add at least one item to the navigation.

6.  Click on the **New Area**.

7.  Enter **Administration** for **Title**.

8.  Select the **New Group**.

9.  Enter **User Admin** for **Title**.

10. Select the New **Subarea**.

11. Select **Entity** for **Type**.

12. Select **User** for **Entity**

13. Click **Save**.

14. Click **Publish**.

15. Close the sitemap editor by clicking **Save and Close**.

16. Close the app designer by clicking **Save and Close** again.

17. Click **Done**.

18. Click **Publish All Customizations** and wait for the publishing to
    complete.

19. Select **Apps**.

20. The **Knowledge Admin** application you created should be listed. Open the
    **Knowledge Admin** application.

21. The **Model-Driven** application **Knowledge Admin** will load.

22. Open one of the **Users**.

23. The User form of the selected record will load.

24. Close the application.

Exercise 4 – Create the Knowledge canvas App
--------------------------------------------

In this exercise, you will be creating the Fabrikam Knowledge canvas app. This
will be just to setup the basic app, we will build out the user experience in
the canvas app module.

### Task 1 – Create a canvas app

1.  Go back to <https://web.powerapps.com> and make sure you are in the
    **Practice** environment.

2.  Select **Solutions** and open **Common Data Service Default Solution**.

3.  Click **New \| App \| Canvas App \| Tablet Form Factor**.

4.  Click **Skip** if you see a prompt before the designer loads.

5.  The Canvas App Designer will load. Hover over **Screen1** and click on the
    **…** button.

6.  Select **Rename**.

7.  Enter **mainScreen** and press the [Enter] key. Note: It is always a good
    idea to give components meaningful names, it makes them easier to use as
    your application gets more complex.

### Task 2 – Add Header to the App

Part of making a good app is giving it a personality, we are going to keep
things simple here and just add a basic header to the app.

1.  Select the **Insert** tab.

2.  Click **Label**.

3.  A label will be added to the screen. Select the Label.

4.  Rename the label **headerLabel** by clicking the … Rename in the control
    tree on the left side of the screen

5.  Select the **Home** tab.

6.  Change the **Font Size** to **28.**

7.  Click **Color** and change the **Font Color** to **White**.

8.  Click **Align** and select **Center**.

9.  Click **Fill** and change the **Fill Color** to **Blue**.

10. Make sure that the **headerLabel tab is selected and g**o to the
    **Properties** window located on the right. Locate the **Position** section.

11. Enter **0** for **Y** and **0** for **X**.

12. Locate the **Size** section.

13. Enter **1365** for **Width** and **60** for **Height**.

14. Double click on the **Text** of the **label**.

15. Replace **Text** with **Fabrikam Assessment**.

### Task 3 – Add User Name to the Header

In this task, you are going to leverage the User() information to add the name
of the current user to the header.

1.  Select the **MainScreen**.

2.  Select the **Insert** tab and click **Label**.

3.  Rename the label **userLabel**.

4.  Make sure text **Text** property is select and the function value is now
    **“Text”.**

5.  Replace **“Text”** with *User().FullName*

6.  The user’s Full Name will now be displayed on the label. Select the **Home**
    tab.

7.  Change the **Font Size** to **14**.

8.  Change the Font **Color** to White.

9.  Click **Align** and select **Right**.

10.  Click **Align Control** and select **Align Right**.

11.  Go to **Properties** and set **Position Y** to **0**.

12.  Locate **Size** and set the Height to **60**.

13.  Locate **Padding** and enter **10** for **Right**.

14.  Click **File** and select **Save**.

15. Select **Cloud** and enter **Fabrikam Assessment** for **Name**.

16. Click **Save**.

17. Click on the **Back** button.

18. Click **Play** (Preview the App).

19. Your application will load.

20. Close the preview.

21. Close the Canvas App Designer.

22. Click **Done**.
