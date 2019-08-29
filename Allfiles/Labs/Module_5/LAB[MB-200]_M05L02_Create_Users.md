Module 5: Security
==================

## Lesson 2: Practice Lab – Create users

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a project for your client Fabrikam. You will be continuing your work
on the model-driven Knowledge Admin app. In this practice, you will be creating
a dashboard and modifying the app to include it.

We need to add additional users to be able to use the application we have built.
You will be adding three users to the tenant; one manager and two additional
users. For this practice you will be adding them and assigning their licenses.
In future practices we will add security roles and organize the team members.

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


Exercise 2 – Add users and assign license to user
-------------------------------------------------

### Task 1 – Create Users

In this task, you create users and assign licenses to them.

1.  Navigate to https://admin.microsoft.com

2.  Login with your admin users, if prompted.

3.  Expand **Users** and select **Active Users**.

4.  Click **+ Add a User**.

5.  Enter **User** for **First Name** and **One** for **Last Name**.

6.  The **Display Name** will be populated for you.

7.  Enter **UserOne** for **User Name**.

8.  Click on the **Password**. This action will expand the password section.

9.  Select the **Let me Create the Password** radio button

10. Enter **practice\@1** for **Password**.

11. **Uncheck** the **Make this User Change Their Password…** checkbox.

12. Click on the **Product Licenses**. This action will expand the product
    licenses section.

13. Turn on the **Microsoft 365 Customer Engagement Plan**, if not already on.

14. Click **Add**.

15. Uncheck the **Send Password in Email** checkbox.

16. Click **Add Another User**.

17. Enter **User** for **First Name** and **Two** for **Last Name.**

18. Enter **UserTwo** for **User Name**.

19. Click **Password**.

20. Select **Let me Create the Password**.

21. Enter **practice\@1** for **Password** again.

22. Uncheck the **Make this User Change Their Password…** checkbox

23. Click on the **Product Licenses**.

24. Make sure the **Dynamics 365 Customer Engagement Plan** is turned on.

25. Click **Add**.

26. Uncheck the **Send Password in Email** checkbox.

27. Click **Add Another User**.

28. Enter **Manager** for **First Name** and **User** for **Last Name**.

29. Enter **ManagerUser** for **User Name**.

30. Click **Password**.

31. Select **Let me Create the Password**, if not already selected.

32. Enter **practice\@1** for **Password**.

33. Uncheck the **Make this User Change their Password ….** checkbox, if not
    already unchecked.

34. Click **Product Licenses**.

35. Make sure the **Dynamics 365 Customer Engagement Plan** is turned on.

36. Click **Add**.

37. Uncheck the **Send Password in Email** checkbox, if not already unchecked.

38. Click **Close**.

39. Your new users should now be on the list of active users in Office.
