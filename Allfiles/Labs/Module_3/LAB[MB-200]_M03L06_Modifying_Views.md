Module 3: Building Model-Driven Applications
============================================

## Lesson 6: Practice Lab – Modifying views

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. In this practice you will be
continuing your work on the model-driven Knowledge Admin app. In this practice,
you will be modifying the auto generated views to add the new fields you added
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

Exercise 2 – Edit the Knowledge Assessment View 
------------------------------------------------

In this exercise, you will edit the view for the Knowledge Assessment entity. By
default, the auto generated views only show the primary attribute and created on
date.

### Task 1 – Edit the Knowledge Assessment active item view

1.  Navigate to <https://web.powerapps.com>

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Open the **Common Data Service Default Solution**.

5.  Open the **Knowledge Assessment** entity.

6.  Select the **View** tab.

7.  Click to open the **Active Knowledge Assessments.**

### Task 2 – Add and Remove Columns from View

1.  The **Active Knowledge Assessment** view currently has two columns.
    **Title** and **Created On**. Select **All**.

2.  Click on the **Status Reason** field.

3.  The **Status Reason** field will be added to view. Click on the **Owner**
    field.

4.  The **Owner** field will be added to the view. Click on the **Modified By**
    field.

5.  Click on the **Modified By** column header and select **Insert Column**.

6.  Select **Modified On**. The view should now have six columns.

7.  You will now remove the **Created On** field. Click on the **V** button of
    the **Created On** column.

8.  Click **Remove**.

9.  The **Created On** column will be removed from the view.

10. You will now add a field from a related entity to the view. From the
    **Fields** section select the **Related** tab.

11. All the entities the **Knowledge Assessments** has a **N:1** relationship
    will be listed here. Expand **Owning User (systemuser).**

12. Enter **Email** on the search box and enter.

13. Select **Primary Email**. The **Primary Email** will be added to the view.

14. Click **Save**.

### Task 3 – Reorder View Columns and Change Column Width

Generally, you will always want to have the order of the fields in view be the
highest value to lowest unless you have other specific needs

1.  You will now reorder the columns. Select the **Owner** column header and
    click **Move Left**.

2.  You can also reorder columns by drag/drop. Drag the **Primary Email** column
    header and drop it to the left of the **Status Reason** column.

3.  Move the **Modified On** column to right of the **Modified By** column.

4.  The columns order should now be **Title**, **Owner**, **Primary Email**,
    **Status Reason**, **Modified By**, **Modified On**.

5.  You will now make the **Title** and **Primary Email** columns wider. Select
    the **Title** column header and drag the right edge to the right. The
    **Title column** should get wider.

6.  Select the **Primary Email** column header and drag the right edge to the
    right until the emails are visible.

7.  Click **Save**.

### Task 4 – Sorting

The View is now sorted by the **Title (A-Z),** you will the sorting to be
Modified On and then Title.

1.  Locate the **Sort By..** area located in the view properties.

2.  Remove the **Title (Ascending)**. We want to sort **Modified On** then
    **Title**.

3.  Click **Sort By** and select **Modified On**.

4.  Click **Then Sort By** and select **Title**.

5.  Click **Save**.

### Task 5 – Use Save as to create a copy

In this task, you will use the Save As feature to create a template for new
views. An easy way to create views is to create the first one with all the
fields you want, then save as the view and change the filter to what the new
view needs.

1.  While still editing the Active view, click the **V** button next to the
    **Save** button.

2.  Select **Save As**.

3.  Enter **Created This Month** for Name and click **Save**.

4.  Locate the **Filter By**… section of the **View** property. You should have
    **Status is ‘Active’**. All records have a status field, if you don’t filter
    to only active you may have records showing in your list that are not
    editable or meant to be inactive. Inactive is used in CDS to mark records as
    soft deleted as an alternate to physically deleting the records.

5.  You will add the Created On filed back to the View. Click on the **+**
    button located on the top right of the view.

6.  Select All and then select **Created On**.

7.  Click on the **V** button of the **Created On** column header.

8.  Select **Filter By**.

9.  Click on the top dropdown and select **This Month**.

10. Click **Apply**.

11. Click **Save**.

12. Click **Publish**.

13. Close the view editor.

14. Click **Done**.

15. From the navigation breadcrumbs, click on the solution name **Common Data
    Service Default Solution**.

16. Click **Publish All Customizations**.

### Task 6 – Test the View

1.  While still on <https://web.powerapps.com> Select **Apps**.

2.  Click on the **Knowledge Admin Model-Driver** application.

3.  Click on the **Administration** area and select **Assessments**.

4.  The **Active Knowledge Assessment** view will be loaded. Make sure the
    columns you selected are there in the order you selected.

5.  Click **Select a View** and choose the **Created This Month** view.

6.  Make sure the column you select are showing in the order you selected.

7.  This view should show only the records that were created in this month.
