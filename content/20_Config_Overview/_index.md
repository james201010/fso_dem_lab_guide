+++
title = "Configuration Overview"
chapter = false
weight = 2
+++

## Introduction

In this section, you will walk through the configuration steps for integrating AppDynamics and ThousandEyes. These steps are necessary if you are doing a greenfield integration of the two platforms, but your lab environment will have this preconfigured. The following sections are provided as a configuration reference, but the steps are not intended to be replicated in your lab environment. If the section title is preceded by *(Reference)*, the steps in that section have already been performed in the lab environment.


<br>


## *(Reference)* Configure the OAuth Bearer Token

The first step in integrating the Cisco AppDynamics and Cisco ThousandEyes platforms is to generate a **Bearer token**. The Bearer token is a type of access token used by client applications to authenticate themselves to a server and thereby gain permission to perform certain operations. In your case, the Bearer token is **generated in the Cisco ThousandEyes** platform and then configured in the integration menu in Cisco AppDynamics.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Navigate to the Cisco ThousandEyes platform. Use the steps you previously used to [**log in to ThousandEyes**]({{< ref "/10_lab_access.html#login-to-thousandeyes" >}}) if you were logged out.

1. In the left menu, under **Account Settings**, select **Users and Roles**
2. Create a new **OAuth Bearer Token** at the bottom of the page under **User API Tokens**.
    - If the **Basic Authentication Token** has not yet been generated, you must generate it first.
    - You can revoke the token at any time and generate a new token. However, you must ensure that all integrations then use the new token.
3. Copy the token somewhere, because you will need it in the integrations.

![image](/images/20_config_overview/config_overview_3.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next, open the Cisco AppDynamics controller. Use the steps you previously used to [**log in to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}}) if you were logged out.

1. Click the gear icon in the upper-right corner of the controller UI, and select **Administration**

![image](/images/20_config_overview/config_overview_1.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; In the administration area you can manage users, API clients, roles and various **integrations** to external platforms.

1. Navigate to the **Integrations** tab
2. Select **ThousandEyes** for configuring ThousandEyes integration
3. Enable the integration
4. Enter the ThousandEyes Bearer token you generated in one of the previous steps

![image](/images/20_config_overview/config_overview_2.png)

When you are done, make sure you save the changes

When you configure integration with ThousandEyes in AppDynamics Controller, you can use native ThousandEyes widgets in your Dash Studio dashboards and synchronize test domains to display ThousandEyes test results in AppDynamics Real User Montoring (RUM) applications. This also allows teams using AppDynamics primarily for monitoring to quickly observe the network health that ThousandEyes sees without leaving the controller UI.




## *(Reference)* Configure Test Recommmendations integration

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next, you will configure bi-directional integration with **Test Recommendations** in the ThousandEyes platform.

1. In the left menu, select **Integrations** and click on **+ New Integration**
2. Provide the integration details, and make sure you select **Test Recommendations** radio button
    - You can use basic authentication or API client from AppDynamics
3. Click the **Test** button to ensure that communication works with the specified credentials
4. You should see the confirmation that the test was successful
5. Save the integration
    - Note that this integration does not only apply to one account group, but is visible for all account groups in your organization

![image](/images/20_config_overview/config_overview_4.png)

## *(Reference)* Configure tests in ThousandEyes from the Recommendations

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next, create the recommended tests in Cisco ThousandEyes that are suggested as part of the bidirectional integration with Cisco AppDynamics.

1. In the left menu, under **Cloud & Enterprise Agents**, select **Test Settings**
2. Click the dropdown next to **Add New Test**
3. Select **Add From Recommendations**

![image](/images/20_config_overview/config_overview_5.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; There may be several business applications that ThousandEyes has included through bidirectional integration with AppDynamics. These are the applications that are currently monitored by the AppDynamics controller.

1. Select the application for which you want to create the tests

![image](/images/20_config_overview/config_overview_6.png)

<br>

## *(Reference)* Manually Match TE Tests 

Some text here ...

![image](/images/20_config_overview/example-image.png)


<br>

## *(Reference)* Configure Test Recommendations


Some text here ...

![image](/images/20_config_overview/example-image.png)



<br>

## **(Reference)** Configure Alert Notifications

Some text here ...

![image](/images/20_config_overview/example-image.png)


<br>

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll walk through the configuration for the **ThousandEyes** and **AppDynamics** integration.

<br>
