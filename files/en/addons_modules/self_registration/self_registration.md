Self Registration
=================

**Self Registration** (formerly called **Social registration**) is a Splynx add-on that allows customers to register themselves in the Splynx portal using their e-mail address or cell phone number. Customers can also register and log in using their Google, Facebook or Twitter accounts.

If you want to use this add-on with social network platforms - it is necessary to have the API applications. If you don't have such apps - below you can find how to create them.

**How to create and enable API-apps in Google, Facebook, and Twitter**

### **Google API**

You need a Google API Console project to integrate Google Sign-In into your Splynx-site. To create a Google API Console project and client ID, follow these steps:

* Go to the Google API Console ([https://console.developers.google.com/projectselector/apis/library](https://console.developers.google.com/projectselector/apis/library))
* Select an existing project, or create a new one
    ![4.png](4.png)

* Click on navigation menu, choose **APIs & Services**, select **Credentials**, then select the **OAuth consent screen** tab. In **OAuth consent screen** choose how you want to configure and register your app.
    ![5.png](5.png)
    ![5.1.png](5.1.png)

During app registration steps you should specify the app name, its logo, user support email, authorized domain, developer contact info, add the necessary scopes etc. If you want to continue testing your app (internal app type), you can specify test users as well, only such users will be able to access the app. Otherwise, for production (external app type), publish your app. If you change your app's configuration in the future, like adding more than 10 domains, uploading a logo, or requesting sensitive or restricted scopes, you will need to [submit for verification](https://support.google.com/cloud/answer/9110914).
    ![6.png](6.png)
    ![6.1.png](6.1.png)

* In the **Credentials** tab, select **Create credentials** drop-down list, and choose **OAuth client ID**
    ![7.png](7.png)

* Under **Application type**, select **Web application**;
    **Authorized JavaScript origins** - URL of your Splynx-server;
    **Authorized redirect URIs** - enter these values:
    1) `https://splynx.youdomain.com/register/site/auth?authclient=google`
    2) `https://splynx.youdomain.com/register/login/auth?authclient=google`

    ![selfreg_create-google-api-auth.png](selfreg_create-google-api-auth.png)

* Click **Create**

**NOTICE:** If the customer receives this error message during registration or sign-in process, then the _wrong_ URI has been added to **Authorized redirect URIs** list.

![10.png](10.png)

* From the resulting OAuth client dialog box, copy **Client ID** and **Client secret** to Splynx.
    ![selfreg_oauth-credentials.png](selfreg_oauth-credentials.png)

* And, finally, turn on the Google+ API ([https://console.developers.google.com/apis/library/plus.googleapis.com](https://console.developers.google.com/apis/library/plus.googleapis.com))  
    ![12.png](12.png)

Reference: [Google documentation](https://developers.google.com/identity/sign-in/web/devconsole-project)

### **Facebook API**

To integrate Facebook Logins into your Splynx-site, you must have a Facebook API.

**Notice:** Splynx-site must use HTTPS. It is required by Facebook.

* Go to developers portal [https://developers.facebook.com/apps](https://developers.facebook.com/apps)
* Create App and specify its name, app contact email, app purpose etc. Pay particular attention to complete the security check (Google reCaptcha), some adblock extensions can block it.
    ![13.png](13.png)
    ![13.1.png](13.1.png)

More about facebook app [types](https://developers.facebook.com/docs/development/create-an-app/app-dashboard/app-types).

* From **Add Products to Your App** select **Facebook Login** (click **Set Up**)  
    ![14.png](14.png)

* Do not use **Quickstart**, use **Settings**.
    ![selfreg_fb-use-settings.png](selfreg_fb-use-settings.png)
By default facebook app has standard access to public_profile and email, it should be changed to advanced access.
The **public_profile** permission allows apps to read the Default Public Profile Fields on a User node. The allowed usage for this permission is to authenticate app users and provide them with a personalized in-app experience.
The **email** permission allows your app to read a person's primary email address. The allowed usage for this permission is to let end users log into your app with the email address associated with their Facebook profile.
In order to change permission settings, open _App Review > Permissions and Features_
![public_profile1](public_profile1.png)
![public_profile2](public_profile2.png)

* Open facebook login settings and enter **Valid Oauth redirect URIs**:
    1) `https://splynx.youdomain.com/register/site/auth?authclient=facebook`
    2) `https://splynx.youdomain.com/register/login/auth?authclient=facebook`
    ![15.png](15.png)

* Click **Save Changes**

* Go to App _Settings / Basic_, copy **App ID**  and **App Secret** to Splynx
    ![selfreg_fb-AppID_Secret-mix.png](selfreg_fb-AppID_Secret-mix.png)

Reference: [Facebook documentation](https://developers.facebook.com/docs/facebook-login)

### **Twitter API**

For Twitter integration, go to the Application Management page - [https://apps.twitter.com/](https://apps.twitter.com/)

* Create a New App
    ![18.png](18.png)

* Enter application **Name** and copy your **API key (consumer key)** and **API secret key (consumer secret)** to Splynx (_Config → Integrations → Modules list → Splynx Social Registration Add-on_).
After that click on **App settings** button.
![19.png](19.png)

* In **App settings** you can specify app description and its icon. Also, it's necessary to change **App permissions** to _Read and Write_.
![19.1.png](19.1.png)

* In **Authentication settings** enable **_3-legged OAuth_** and **_Request email address from users_** options, after that add info to required fields:
**Callback URLs**: 1) `https://splynx.youdomain.com/register/login/auth` 2) `https://splynx.youdomain.com/register/site/auth`;
**Website URL**: `https://splynx.youdomain.com` ;
**Terms of service** and **Privacy policy**:`https://splynx.youdomain.com/privacy_policy` .
![19.2.png](19.2.png)

## Installing the Add-on

The add-on can be installed in two methods, via CLI or the Web UI.

To install the "Self Registration" add-on via CLI, the following commands can be used:

```bash
sudo apt update
sudo apt install splynx-social-registration
```
To install it via the Web UI:

Navigate to *Config -> Integrations -> Add-ons:*

![1.png](1.png)

Locate or search for the "splynx-social-registration" addon and click on the install icon in the *Actions* column

![2.png](2.png)

Click on the "OK, confirm" button to begin the installation process

![3.png](3.png)

After the installation has completed, you have to configure the add-on under _Config / Integrations / Modules List_.

![Modules_list1.png](Modules_list1.png)

Locate or search for the "splynx-social-registration" addon and click on the edit icon in the *Actions* column

![Module_edit.png](Module_edit.png)

You need to enable the **Entry points status for portal** in the **Main information** section

![Module_edit1.png](Module_edit1.png)

You may enable or disable **Entry Points** here as well. There are two entry points in the configuration.

![Edit_entry.png](Edit_entry.png)

The first one provides the ability to sign-in to the Splynx-portal using social networks:

![Entry_point_one.png](Entry_point_one.png)

The second one provides the ability of registration via social networks:

![Entry_point_two.png](Entry_point_two.png)

Edit the URL of your server:

![Splynx_url.png](Splynx_url.png)

Enable social networks that you want to use:

![Social_networks_enable-disable.png](Social_networks_enable-disable.png)

Also, you can enable [TowerCoverage](addons_modules/towercoverage/towercoverage.md) integration (optional):

![selfreg_towercoverage.png](selfreg_towercoverage.png)

[TowerCoverage Integration](addons_modules/towercoverage/towercoverage.md)

Once all settings have been configured click on **Save**.

* * *

**Registration**

![28.png](28.png)

Customer will need to Enter the required information, and click on the **Sign In** button. Confirmation code will be send to the mentioned mail box.

![29.png](29.png)

* * *

## **Login customer to Splynx-portal**

* Login with Facebook  
    If the customer is not logged into Facebook, they will be prompted to log into Facebook and then redirected to Splynx-portal.
    ![21.png](21.png)

* Login with Google
    If the customer is not logged in Google, they will be prompted to log into Google and then redirected to Splynx-portal.
    ![22.png](22.png)

* Login with Twitter  
    If the customer is not logged in Twitter, they will be prompted to log into Twitter and then redirected to Splynx-portal.
    ![23.png](23.png)

Information about social-network is stored in _Customer / Information / Additional information_ in the **Social ID** field.

![24.png](24.png)
