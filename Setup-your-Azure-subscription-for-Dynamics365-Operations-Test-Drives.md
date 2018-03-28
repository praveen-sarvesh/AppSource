# Setup your Azure subscription and Dynamics 365 for Operations environment for Test Drives

1.	Login to your Azure management portal
2.	Create a new tenant in AAD (if not available already)
      *    Navigate to https://portal.azure.com
      *    Click on + New ->  (Search for Azure Active Directory)

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub1.jpg)

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub2.jpg)

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub3.jpg)

3. 	Register an application in azure. We will use this application to perform operations on your Dynamics 365 instance including adding and removing users etc. 

      *    Navigate to the newly created directory or already existing directory and select Azure Active directory in the filter pane.
      *    Search “App registrations” and click on “Add”
      *    Provide an application name.
      *    Select the Type of as “Web application”
      *    Click create.
      *    After the application has been created, go to  Properties -> Set the application as multi-tenant and hit Save.
      *    Under keys, add a Key Description, set the duration to two years or as appropriate. Do remember to update this before the key expires, else your test drives will be broken. 
      *    Click Save. This should generate the ClientSecret. 
      *    Keep this ClientSecret handy.

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub4.jpg)

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub5.jpg)

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/SetupSub6.jpg)

4. Now we need to add the above app to Dynamics 365 for operations in order to enable the app to manage users
      *    Navigate to your Dynamics 365 for Operations instance.
      *    Click on the Hamburger menu at the left top corner.
      *    Click on System Administration.
      *    Click on Azure Active Directory applications.
      *    Click on + New
      *    Enter in the Client Id of the Azure AD app that is going to perform the on-behalf-of actions.
      *    The user Id on whose behalf the actions will be performed (typically the System Admin of the instance or a user who has privileges to add other users).

![](https://github.com/Azure/AzureTestDrive/blob/master/AzureTestDriveImages/Dynamics365OperationsAddApp.png)
