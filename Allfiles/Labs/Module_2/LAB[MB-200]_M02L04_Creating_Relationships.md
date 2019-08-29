Module 2: Data Model
====================

## Lesson 4: Practice Lab – Creating relationships

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You are working on the data model
you started in the prior practice. In this practice you will be adding the
relationships to what you created in the prior practice. If you haven’t
completed that practice you should pause this practice and complete that first.

The following is the data model you are building. At this point all the entities
are created and you are ready to create the relationships. **Please refer to the file labeled Image[MB-200]_M02L02_Creating_Entities_Fields.png in the Lab Resources to view the entity relationship diagram.**

The following relationships need to be created.

1.  Knowledge Assessment to Knowledge Question changing the relationship
    behavior to be parental.

2.  Knowledge Assessment to Knowledge Test Result changing the relationship
    behavior to be parental.

3.  User to Knowledge Test Result we don’t need to create because we will assign
    the user who took the test as the owner of the record. An alternative design
    could have left owner to track who is working on the record and create
    another relationship to track who took the assessment. For our purposes we
    are going to keep it simple and use record owner.

4.  The relationship to Feedback is handled via an entity option you will be
    doing in a future practice.

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

Exercise 2 – Create the Knowledge Assessment Relationships
----------------------------------------------------------

In this exercise, you will be creating the relationships for Knowledge
Assessment entity.

### Task 1 – Knowledge Assessment to Knowledge Question Relationship

In this task, you will create a One-to-Many relationship between the Knowledge
Assessment and Knowledge Question entities.

1.  Navigate to <https://web.powerapps.com> and make sure you are in the
    **Practice** environment.

2.  Select **Solutions** and open the **Common Data Service Default Solution.**

3.  Click to open the **Knowledge Assessment** entity.

4.  Select the **Relationship** tab.

5.  Click **Add Relationship** and select **One-to-Many**.

6.  Select **Knowledge Question** for **Primary Entity** and click **Done**.

7.  Click **Save Entity**. It is a good idea to save your changes as you make
    them.

### Task 2 – Knowledge Assessment to Knowledge Test Result Relationship

In this task, you will create a One-to-Many relationship between the Knowledge
Assessment and Knowledge Test Result entities.

1.  Make sure you have the **Relationship** tab selected.

2.  Click **Add Relationship** and select **One-to-Many**.

3.  Select **Knowledge Test Result** for **Primary Entity** and click **More
    Options**.

4.  The relationship names must be unique. Change the **Relationship Name** to
    **KnowledgeAssessment_KnowledgeResult**.

5.  Click **Done**.

6.  Click **Save Entity**.

7.  From the navigation breadcrumbs, click **Common Data Service Default
    Solution**.

8.  Click **Publish All Customizations**.

Exercise 3 – Adjust relationship behaviors
------------------------------------------

In this exercise, you will be changing the relationship behaviors to be
parental. You will be performing this change in the classic Solution Explorer.

### Task 1 – Change the relationship behavior

1.  Make sure you still have the **Common Data Service Default Solution** open.

2.  Click on the **…** button located next to **Publish All Customizations** and
    select **Switch to Classic**.

3.  Expand **Entities**.

4.  Expand the **Knowledge Assessment** entity.

5.  Select **1:N Relationships**.

6.  Double click to open the relationship with the **Knowledge Question**
    Related Entity.

7.  Scroll down to the **Relationship Behavior** section and locate the **Type
    of Behavior** field.

8.  Select **Parental** for **Type of Behavior**.

9.  Click **Save and Close**.

10. Open the relationship with the **Knowledge Test Result** related entity.

11. Change the **Type of Behavior** to **Parental**.

12. Click **Save and Close**.

13. Click **Publish All Customizations**.

14. Close the solution explorer.
