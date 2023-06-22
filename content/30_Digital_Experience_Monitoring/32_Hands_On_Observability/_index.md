+++
title = "Hands-On Observability"
chapter = false
weight = 2
+++

## Introduction

This use case covers the integration with ThousandEyes to illustrate how you can assess the application as experienced by end-users located around the world.


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


<br>

## HTTP Server View

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to open the **HTTP Server View**.

1. Click on the **Cloud & Enterprise Agents** and then **Views** on the left menu
2. Select the **Tea-Store-AMEX-Transaction** test from the drop-down 
3. Click on the **HTTP Server** view
4. Look at the **Map** area below for each metric in the **Metric** drop-down to see if there are any obvious issues

![image](/images/30_digital_exp_mon/te_observability_01.png)

<br>

## Transactions View

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to explore the **Transactions View**.

1. Click on the **Transactions** view
2. Ensure that **Transaction Time** is the **selected metric**
3. Hover over the **red circle** in the northeast region of the USA on the map
4. Click on **Chicago, IL** to select that agent

If you hover on each of the circles in the map, you will see a list of transactions and the completion time from the geographic location. ThousandEyes provides cloud agents in locations throughout the world on multiple provider networks for instant use by customers.

![image](/images/30_digital_exp_mon/te_observability_02.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next click on **Waterfall**.

This display represents what the user in Chicago sees in terms of the response time for the transactions of the application. You can see the steps the user goes through and all the components involved in the transactions and the amount of time it takes to complete any of the responses by scrolling down the page.

![image](/images/30_digital_exp_mon/te_observability_03.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next, under **Views** click **Path Visualizations** to display the routes the user takes from the WAN.

![image](/images/30_digital_exp_mon/te_observability_04.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll down the page to see the actual paths taken.

Looking through the paths there appears to be no issues, so you can assume that the network is not contributing to any problems accessing the front-end of the application. 

![image](/images/30_digital_exp_mon/te_observability_05.png)


<br>

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll take a look at the application from an operations viewpoint in the Application Dependency Monitoring use case.

<br>