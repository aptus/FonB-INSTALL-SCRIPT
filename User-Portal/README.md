FonB User Portal
===
### Table of Contents
1. [Getting Started](#gettingstarted)

2. [CRM Integration](#crmintegration)

   2.1. [Salesforce CRM](#salesforcecrm)
___
<a name="gettingstarted"/>
### 1. Getting Started
1.1. Assuming that you installed your backend on the system with IP 10.0.8.10 and configured port 8080 for access while installation, you can now access the User Portal by accessing 10.0.8.10:8889. Here you will see the License Inventory available in your FonB. The inventory is empty for the newly installed systems.

1.2. If you are on the license page after the fresh installation, you will have to visit Aptus FonB Download Page and register for a 30 days trial license.

1.3. Fill in and submit the registration form, to receive an email providing all the necessary information along with the license activation key.

1.4. Copy this license key and paste it in FonB License Inventory Page you are seeing everytime you try to access 10.0.8.10:8889.

1.5. Press the Activate License button to activate your product and start your 30 days trial period.

1.6. You will be redirected to the Login Screen. Use the credentials as following:
* username: admin
* password: you can obtain it by running this command from your PBX CLI: 
```
grep AdminPassword /etc/phoneb/phoneb.cfg
```

1.7. Start using FonB User Portal.

<a name="crmintegration">
### 2. CRM Integration
The current Release of FonB support three CRM Platforms:
<a name="salesforcecrm">
### 2.1. Salesforce CRM
To integrate FonB with Salesforce CRM, first you need to perform some configuration on Salesforce to allow FonB to connect to it.
First Create new application, give it any common name like FonB_Integration, set these permissions on your app you created:
* Access and manage your data (api)
* Full access (full)
* Perform requests on your behalf at any time (refresh_token, offline_access)

After that you need to set the redirect URL, please use the following: https://FonBserverIP:7717/salesforce/oauth_callback.php
Please note that FonB on HTTPS (PORT 7717) runs only to support salesforce.
After you perform all the above steps, please login to FonB using one of your extensions, navigate to Settings>Contacts page and enter the required information on salesforce Section then press Verify and Sync. a pop-up window will appear asking you to login to your salesforce account, please do so and the window will automatically close after the verification complete.
For further operational details, please use FonB Technical Guide.

