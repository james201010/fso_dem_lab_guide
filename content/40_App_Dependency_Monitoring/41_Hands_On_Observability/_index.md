+++
title = "Hands-On Observability"
chapter = false
weight = 2
+++

## Introduction

This use case examines an API that the application uses to process credit card payments with a third-party application.  

<!-- PER LITE VS FULL START -->

<!-- FULL -->
<!--
<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials used previously to <a href="https://www.fsolabs.net/20_lab_environment/23_finalize_setup.html#verify-appdynamics-agents" target="_blank">**login to the AppDynamics controller**</a> if you've been logged out.
-->
<!-- FULL -->


<br>

## Payment API Availability

Use the credentials as described in [**login to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}} "login to AppDynamics"), to access the AppDynamics controller.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Open your **TeaStore FSO Dashboard** using the steps below.

1. Click on the **Dashboards & Reports** tab on the top menu
2. Double-click on the dashboard you see in the list (there should be only one)

![image](/images/40_app_depend_mon/ADM_01.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll to the tiles below **Tiers and Node Transactions** and notice that the **AMEX API Availability** is 0 percent. This percentage means that any application component that uses this API cannot complete a transaction.

1. Double-click on the **AMEX API Availability** widget to delve into ThousandEyes and investigate the status of the dependency.

![image](/images/40_app_depend_mon/ADM_02.png)

If you need to login again to ThousandEyes, follow the process in [**login to ThousandEyes**]({{< ref "/10_lab_access.html#login-to-thousandeyes" >}} "login to ThousandEyes") guide.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; See the HTTP Server performance.

1. **Status by Phase** immediately suggest that there is a problem on the HTTP side.

![image](/images/40_app_depend_mon/ADM_03.png)

Before making final conclusions, make another check that it's not the network.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the **Network** layer.

1. Click the **Agent to Server** test view.
2. Review the graph and network metrics; you'll notice minimal TCP packet loss, and both latency and jitter appear not to be contributing factors to the issue.

![image](/images/40_app_depend_mon/ADM_04.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the **Web** layer again.

1. Click the **HTTP Server** test layer
2. Select the **Map** tab.
3. See the HTTP response code 403.

![image](/images/40_app_depend_mon/ADM_05.png)

This view indicates that there is a problem with request authorization to the payment gateway.

## Dependencies tested by Test Recommendations

The tests created using **Test Recommendations** provide users with a simple way to create them, based on what is AppDynamics's view of application dependencies. The tests created using this method are automatically tied to Cisco AppDynamics, and provide you with additional ThousandEyes dashboard widgets, where you can see the performance of the applications from AppDynamics perspective. See [**Test Recommendations**]({{< ref "/22_test_recommendations.html" >}}) for setup instructions.

If you need to login again to ThousandEyes, follow the process in [**login to ThousandEyes**]({{< ref "/10_lab_access.html#login-to-thousandeyes" >}} "login to ThousandEyes") guide.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Observe the test created from **Test Recommendations**.

1. In the left menu, select **Views**.
2. Select the **appd-teastore-fso-lab-**\* test.
   - The test naming is done automatically from the recommendations.

![image](/images/40_app_depend_mon/ADM_Rec_01.png)

The test layers in tests derived from recommendations are identical to those in any other ThousandEyes test. Currently, only **Agent to Server** tests are supported in the Test Recommendations feature.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; See the test **Dependent Applications**.

1. Select the **Dependent Applications** tab.
2. Inspect the list of all applications that use the dependency.

![image](/images/40_app_depend_mon/ADM_Rec_02.png)

Observe that multiple applications share the same payment gateway dependency.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Check the Dashboard made from the test recommendations.

1. In the left menu, navigate to **Dashboards**.
2. From the dropdown menu, select **App Dependency Dashboard**.
3. See the **Application Service Health** widget which is available only for tests created from the recommendations.

![image](/images/40_app_depend_mon/ADM_Rec_03.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Leverage the Application Service Health widget in ThousandEyes for a swift transition to Cisco AppDynamics..

1. Click the health status widget.
2. Under **Test Name**, click the name of the application.

![image](/images/40_app_depend_mon/ADM_Rec_04.png)

Clicking the link will direct you to the relevant application dashboard within Cisco AppDynamics. Should login be required at the AppDynamics controller, utilize the credentials provided in [**login to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}} "login to AppDynamics").

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the application dependency in Cisco AppDynamics.

1. Select the backend named **amex-fso-payment-gw-**\* on the application dashboard's Flow Map and examine its metrics.

![image](/images/40_app_depend_mon/ADM_Rec_05.png)

By leveraging the connection between application dependencies in Cisco ThousandEyes and AppDynamics, you can seamlessly transition from monitoring dependencies from a network perspective to evaluating them through application performance monitoring.

<br>


## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

Last step!

<br>