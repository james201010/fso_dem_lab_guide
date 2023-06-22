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


<!-- LITE -->

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials used previously to <a href="https://lt.fsolabs.net/20_lab_environment_lt/21_lab_login_steps.html#login-to-appdynamics" target="_blank">**login to the AppDynamics controller**</a> if you've been logged out.

<!-- LITE -->

<!-- PER LITE VS FULL END -->

<br>

## Payment API Availability

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Open your **TeaStore FSO Dashboard** using the steps below.

1. Click on the **Dashboards & Reports** tab on the top menu
2. Double-click on the dashboard you see in the list (there should be only one)

![image](/images/40_app_depend_mon/payment_api_01.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll to the tiles below **Tiers and Node Transactions** and notice that the **AMEX API Availability** is 0 percent.

This percentage means that any application component that uses this API cannot complete a transaction.

![image](/images/40_app_depend_mon/payment_api_02.png)


<br>



## Diagnose with AppDynamics

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to navigate to your TeaStore application.

1. Click on the **Applications** tab on the top menu
2. Find your TeaStore application with your lab number in the name and click on its name to open it

![image](/images/40_app_depend_mon/appd_diagnose_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now let's use AppDynamics deep diagnostic capabilities to understand if the issue with the AMEX API service stems from within the application iteslf.

1. Click on **Errors** under the **Transaction Scorecard**

![image](/images/40_app_depend_mon/appd_diagnose_02.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to open a **Transaction Snapshot** that involves a call to the AMEX API service.

1. Click on the column indicated to sort the snapshots so the call graphs are at the top of the list
   - Call graphs are indicated by the blue page icon
2. Double-click on the snapshot at the top of the list to open it

![image](/images/40_app_depend_mon/appd_diagnose_03.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Explore the details of the **Transaction Snapshot** to understand potential root cause of the issue with the AMEX API service.

1. Notice there was an error when the **teastore-webui** tier called the **AMEX API** service
2. Click on the **error** at the top of the **Potential Issues** list on the left
3. Now you see a **403 error** that is related to the AMEX payment processing

A list of possible reasons for the 403 error follows:

- The API may be unavailable
- Errors may be occurring in our network that prevents the call to the AMEX processing reaching that processing
- The infrastructure between our network and the target is experiencing problems, which require investigation with the ISPs between the TeaStore application and the target service

![image](/images/40_app_depend_mon/appd_diagnose_04.png)




<br>



## Diagnose with ThousandEyes

<!-- PER LITE VS FULL START -->

<!-- FULL -->
<!--
<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials for ThousandEyes provided by your instructor to <a href="https://performance.fsolabs.net/30_digital_experience_monitoring/31_hands_on_configuration.html#deploy-thousandeyes-agent" target="_blank">**login to ThousandEyes**</a> if you’ve been logged out.
-->
<!-- FULL -->


<!-- LITE -->

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials used previously to <a href="https://lt.fsolabs.net/20_lab_environment_lt/21_lab_login_steps.html#login-to-thousandeyes" target="_blank">**login to ThousandEyes**</a> if you've been logged out.

<!-- LITE -->

<!-- PER LITE VS FULL END -->

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below with ThousandEyes to verify if the network is a contributing factor with the AMEX service availability.


1. Click on the **Cloud & Enterprise Agents** and then **Views** on the left menu
2. Select the **Tea-Store-AMEX-API-Call** test from the drop-down 
3. Hover over the **red circle** on the map to inspect the details (**HTTP Server** view must be selected to see the map)
4. Next click on **Path Visualization** in the left part of the display under **Views** 

![image](/images/40_app_depend_mon/te_diagnose_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; You see that users can access the front end of the application without problems. 

The network on our end is fine.  The displayed paths indicate that the problem resides with the third-party application.  When the API becomes available again ThousandEyes updates the tile in the AppDynamics dashboard indicating the availability. 

The integration between ThousandEyes and AppDynamics provides you with a way to monitor whether any dependencies are meeting their service level agreements (SLA).

![image](/images/40_app_depend_mon/te_diagnose_02.png)




<br>

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

Let's find out **what's next!**

<br>