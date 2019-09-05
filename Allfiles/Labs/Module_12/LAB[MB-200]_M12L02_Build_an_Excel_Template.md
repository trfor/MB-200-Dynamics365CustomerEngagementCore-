Module 12: Integration with Office
=================================

### Lesson 2: Practice Lab – Build an Excel template

Scenario
--------

You are a functional consultant for Contoso building a knowledge assessment
application for you client Fabrikam. You need to configure a template so that
managers without much experience in Excel or the knowledge assessment
application can generate an Excel report of test scores. In this lab, you will
create an Excel template from a view, upload the template and use it against
data about knowledge test results.

**Important Note:** This lab will provide you with an actual Office 365 tenant
and licenses for the Power platform applications you will be using in this
course. You will only be provided with one tenant for the practice labs in this
course. The settings and actions you take within this tenant do not roll-back or
reset. Whereas the virtual machine you are provided with does reset each time
you close the lab session. What’s more, Office 365 is evolving all the time. The
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

Exercise 2 – Build an Excel template
------------------------------------

In this exercise, you will build an Excel template for the Knowledge Test Result
entity.

### Task 1 – Create View

In this task, you will create a new view for the Knowledge Test Result entity.

1.  Navigate to <https://web.powerapps.com/environments>

2.  Check the Environment selector in the upper right corner to make sure you
    are NOT in the Default environment. You should be in an environment that is
    named like Contoso(crm200) and not Contoso(Default).

3.  Expand **Solutions** on the left navigation

4.  Click to open the **Knowledge Management Solution.**

5.  Locate and click to open the **Knowledge Test Results**.

6.  Select the **Views** tab and click **Add View**.

7.  Enter **Excel Template View** for Name and click **Create**.

8.  Change the **Fields** pane to show **All** fields.

9.  Select the fields listed below:
	- Knowledge Assessment
	- Total Points
	- Created On
	- Owner

10. Click **Save**.

11. Click **Publish**.

12. Close the view editor browser tab.

13. Click **Done**.

### Task 2 – Create the Excel Template

In this task, you will be creating an Excel worksheet with a Pivot Chart on
Knowledge Test Results.

1.  Select **Apps**.

2.  Locate and click on the **Knowledge Admin** application.

3.  Click on the **Site Map** button and select **Knowledge Test Results**.

4.  Click on the **Excel Template** button locate on the command bar and select
    **Download Template**.

5.  Make sure **Knowledge Test Result** is selected for **Entity** and select
    **Excel Template View** for **View**.

6.  Click **Download**.

7.  Wait for the template to be downloaded and click then click **Open**.

8.  Click **Enable Editing**.

9.  Select the **Insert** tab and click **Pivot Table**.

10. Click **OK**.

11. Click **Pivot Chart**.

12. Select **Column** and click **OK**.

13. Go to the **Pivot Fields** pane and select **Total Points** and **Owner**.

14. Right click on the Pivot table and select **Pivot Table Options**.

15. Select the **Data** tab.

16. Check the **Refresh Data**… checkbox and click **OK**.

17. Click **File** and click **Save As**.

18. Save the file on your machine and name it **Knowledge Test Result
    Template**.

19. Close the Excel file.

Exercise 3 – Upload and Use Excel Template
------------------------------------------

In this exercise, you will upload the template you created and test it

### Task 1 – Upload Template

In this task, you will upload the template you created

1.  Go to your **Knowledge Admin** Model-Driven application (web.powerapps.com
    -\>Apps).

2.  Click on the **Site Map** button and select **Knowledge Test Results**.

3.  Click on the **Excel Template** button located on the command bar and select
    **Upload Template**.

4.  Click **Browse**.

5.  Select the template you created and click **Open**.

6.  Click **Upload**.

### Task 2 – Use Excel Template

In this task, you will create a new Knowledge Test Result record and test the
template you created

1.  Click **+ New**.

2.  Enter **New Test Result** for **Primary Name**, select one of the available
    **Knowledge Test Result** for **Knowledge Assessment**, enter **980** for
    **Total Points** and click **Save and Close**.

3.  Click on the **Excel Template** button located on the command bar and select
    the **Knowledge Test Result Template** you uploaded.

4.  Click **Download a Copy**.

5.  Wait for the download to complete and click **Open**.

6.  Select **Sheet1** and make sure the new record is in the table.
