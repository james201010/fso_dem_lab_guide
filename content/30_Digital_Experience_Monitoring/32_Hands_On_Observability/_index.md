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

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials used previously to [**login to ThousandEyes**]({{< ref "/10_lab_access.html#login-to-thousandeyes" >}} "login to ThousandEyes") if you've been logged out.

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

## Troubleshoot Latency Issues

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Latency issues are a common problem, and without a tool like Cisco ThousandEyes you are usually blind and need a lot of time and effort to identify the problem and find the root cause. You will use the new **Views 2.0** to monitor the status of the transaction and the underlying network state.

1. Navigate to the **Views** menu
2. Click the dropdown and select **Tea-Store-Transaction-LT**
3. Switch to **Views 2.0**
    - It may be that you are already using Views 2.0. In this case you can skip this step
4. Note the **Transaction** chart. It shows the average transaction time for 14 different agents
5. Hover over the **Ohio Enterprise Agent** on the map, which is highlighted in red
    - The response time for this agent is about 10 seconds higher than that of the others


![image](/images/30_digital_exp_mon/te_observability_06_LT.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; While transaction tests tell you how long a particular user transaction takes to finish, they do not tell you much about possible underlying errors that caused a delay in a transaction. With ThousandEyes, you can quickly jump into the network layer and examine side by side what is going on in the network.

1. Switch to the **Agent to Server** network layer
2. In Views 2.0, you can select multiple metrics to show them side by side. Select **Loss**, **Latency**, and **Jitter**.
    - **Loss** should already be selected.
3. Adjust the timeline to visually see if there are anomalies in any of the network metrics
    - Use the sliders in the top timeline view to select start and end times. If you want to select a point in time, click on the metrics chart


![image](/images/30_digital_exp_mon/te_observability_07_LT.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; The average value for all sites can sometimes be somewhat misleading. In turn, the map can be used to identify sites that have a somewhat poorer network experience.

1. Observe the average loss, latency, and jitter between all sites
2. Hover your mouse cursor over the **Ohio Office Enterprise** location on the map. You should notice that the packet loss is much higher than the average
3. Click **Filter by this agent** to restrict the view to this particular site
    - Note that packet loss, latency, and jitter are higher than the previously observed average


![image](/images/30_digital_exp_mon/te_observability_08_LT.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Path visualization can in turn be used to identify possible bottlenecks in the network.

1. Select the **Path Visualization** tab
    - The view should already be limited to a single agent. If this is not the case, use the **Show** dropdown menu
2. Click the **Link Delay** dropdown, and click **Select X matching links**
    - Since this is a live demo, the state of your lab may vary. You may have more links or none at all. If there are no links to choose from, use the slider to decrease the link delay threshold
3. Inspect the source and destination on the highlighted delayed link(s)

From transaction time to network metrics to paths across network nodes you do not own, ThousandEyes was able to pinpoint issues down to a link between two network nodes that could be the cause of increased latency, packet loss and effectively slower user transactions that affect the user's digital experience.

![image](/images/30_digital_exp_mon/te_observability_09_LT.png)

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll take a look at the application from an operations viewpoint in the Application Dependency Monitoring use case.

<br>