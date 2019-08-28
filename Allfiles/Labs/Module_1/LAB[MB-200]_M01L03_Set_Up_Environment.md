Module 1: Power Platform Overview
=================================
## Practice Lab – Set up environment

Scenario
--------

You are a functional consultant for your organization Contoso. You have been
asked to prepare an environment for a proof of concept your company is building
for Fabrikam. You will be preparing two environments; one that has only Common
Data Model core entities and another that has the Dynamics 365 for Sales
application installed.

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
might pick up where you left off and you will not need to log in again.  In that
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

Exercise 2 – Create a Power platform environment
------------------------------------------------

In this exercise, you will be creating a new environment with just the “core”
Common Data Model entities configured.

### Task 1 – Create an environment

1.  Click either **Show Al**l or **Admin Centers** to expand **Admin Centers**
    and select **PowerApps**.

2.  Click **New Environment** in the upper right corner.

3.  Enter **Practice** for **Name**, select your **Region**, select **Trial**,
    and click **Create Environment**.

4.  Click **Create Database**.

5.  Select **USD** for **Currency**, select **English** for **Language**, check
    the **Include Sample Apps and Data** checkbox, and click **Create
    Database**.

    It will take few minutes to create the environment. You may proceed to
    exercise three while the environment is being created.

Exercise 3 – Configure a Dynamics 365 Application
-------------------------------------------------

In this exercise, you will be making another new environment, one that has the
Dynamics 365 for Sales app installed.

### Task 1 – Create a Dynamics 365 environment

1.  Go back to <https://admin.Powerplatform.microsoft.com>

2.  Expand **Admin Centers** and select **Dynamics 365**.

3.  Select **Sales** and enter **SalesPractice** for **URL** if available or
    enter a different **URL**.

4.  Click **Configure**.  
      
    It will take few minutes to create the environment. You may proceed to
    exercise four while the environment is being created.

Exercise 4 – Review Settings and Configure
------------------------------------------

In this exercise, you will be reviewing settings, enabling an additional
currency, and auditing.

### Task 1 – Verify CDS has finished provisioning

1.  Go to [https://admin.Power
    platform.microsoft.com](https://admin.powerplatform.microsoft.com) expand
    **Admin Center** and select **PowerApps**.

2.  Locate the **Practice** environment you created previously.

3.  Your environment was successfully created if you see (orgxxxxxx) added to
    the end of your environment name, if not wait for the environment to be
    created.

### Task 2 – Explore the settings

1.  Go back to <https://admin.Powerplatform.microsoft.com> and select
    **Environments**.

2.  Select the **Practice** environment by clicking on its name when it is
    underlined and click **Settings** in the upper right-hand corner.

3.  Explore the different areas in **Settings** that you are interested in but
    **do not make any changes.**

### Task 3 – Enable an additional currency

1.  Locate the **Business** section of the **Settings** and click
    **Currencies**.

2.  Click **New**.

3.  Click on the **Currency Code** lookup.

4.  Select **Germany Euro** and click **Add**.

5.  Enter **0.88** for **Currency Conversion** and click **Save and Close**.

6.  You should see both **USD** and **EUR** listed in your **Currencies**.

7.  Close the currencies tab. Do not close the Settings tab.

### Task 4 – Enable auditing 

1.  Locate the **Product** section of the **Settings** and click **Features**.

2.  Locate the **Auditing** section and turn on **Audit Entities**.

3.  Click **Save**.


Exercise 5 – Explore the environments
-------------------------------------

In this exercise, you will be exploring the environments you created and explore
them.

### Task 1 – Explore the Practice environment

1.  Navigate to <https://web.powerapps.com/>

2.  Make sure you are in the **Practice** environment.

3.  Select **Apps**.

4.  You should see the sample applications.

5.  Click the **Asset Checkout** sample application.

6.  The **Asset Checkout** application will load.

7.  Explore and familiarize yourself with the application.

### Task 2 – Explore the Dynamics 365 environment

1.  Go back to <https://web.powerapps.com/>

2.  Make sure you are not in the default or practice environments.

3.  Select the gear icon in the upper menu. In the dropdown menu, select
    **Advanced Settings.**

4.  Your Business Settings will open (usually in a new window). Click the drop
    down menu by **Settings** in the top menu to expand the entire Settings
    options.

5.  Open **Data Management.**

6.  Click **Sample Data**.

7.  You can confirm that sample data is already installed if you have the option
    to **Remove Sample Data.** If sample data is not installed, click **Install
    Sample Data**.

8.  Wait for the installation to start and click **Close**.

9.  Close the Sales application.

10.  Click to open the **Sales Hub** application.

11.  The **Sales Hub** application will load.

12.  Explore and familiarize yourself with the application.
