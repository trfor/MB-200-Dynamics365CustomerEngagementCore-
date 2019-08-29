Module 3: Building Model-Driven Applications
============================================

## Lesson 8: Practice Lab – Building charts

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. In this practice you will be
continuing your work on the model-driven Knowledge Admin app. In this practice,
you will be creating a chart to use as a leader board to show the top 5-point
earners based on the Knowledge Test Result data.

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

Exercise 2 – Create a chart 
----------------------------

In this exercise, you will create a chart using the Knowledge Test Result data.

### Task 1 – Edit the Knowledge Assessment active item view

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open the **Common Data Service Default Solution**.

5.  Click on the **Knowledge Test Result** entity.

6.  Select the **Charts** tab.

7.  Click **Add Chart**.

8.  Enter **Leader Board** for **Name**.

9.  Click **Bar Chart** and select **Bar**.

10. Click on the **Top X Rule** and select **Top 5 Items**.

11. Select **Total Points** for **Legend Entities (Series).**

12. Select **Owner** for **Horizontal (Category) Axis Label**.

13. Click **Save and Close**.

14. Click **Done**.

15. From the navigation breadcrumbs, click on the solution name **Common Data
    Service Default Solution**.

16. Click **Publish All Customizations** located in the command bar.

### Task 2 – Modify Knowledge Test Result form

In this task, you will be modifying the Knowledge Test Result form, so you can
input some data to test your chart.

1.  Make sure you are still on <https://web.powerapps.com> and you are in the
    **Practice** environment.

2.  Select **Solutions**.

3.  Open **Common Data Service Default Solution**.

4.  Click on the **Knowledge Test Result** entity.

5.  Select the **Forms** tab.

6.  Open the **Information Main** form.

7.  Select the **General** tab of the form.

8.  Go to the **Field Explorer** and double click on the **Knowledge
    Assessment** field. The Knowledge Assessment will be added to the form.

9.  From the **Field Explorer**, double click on the **Total Points** field.

10. Click **Save**.

11. Click **Publish** and wait for the publishing to complete.

12. Click **Save and Close** to close the form editor.

13. Click **Done**.

### Task 3 – Create Records and Test the Chart

1.  Make sure you are still on <https://web.powerapps.com> and you are in the
    **Practice** environment.

2.  Select **Apps**.

3.  Select the **Knowledge Admin Model-Driven** application and click **Play**.

4.  Click on the **Administration** area and selected the **Assessments**.

5.  Select **Knowledge Test Results**.

6.  Click **+ New**.

7.  Enter **Result One** for **Name**, **180** for **Total Points**, and click
    **Save**

8.  Click **+ New** again.

9.  Enter **Result Two** for **Name**, **250** for **Total Points** and click
    **Save**.

10. Add four more records, you can provide any name you want but make sure you
    enter random total points.

11. Select **Knowledge Test Results** again. The **Active Knowledge Test
    Results** view will load.

12. Click **Show Chart**.

13. The chart will show your user aggregated points. Later in the course when
    you add more users you can re-test to see multiple users show up on the
    leader board.
