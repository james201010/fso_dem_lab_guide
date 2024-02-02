+++
title = "Hands-On Observability"
chapter = false
weight = 2
+++

## Introduction

The Customer Digital Experience use case covers the functionalities of Cisco ThousandEyes and integration with Cisco AppDynamics to illustrate how you can assess the application as experienced by end-users located around the world.


<!-- PER LITE VS FULL START -->

<!-- FULL -->
<!--
<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the credentials for ThousandEyes provided by your instructor to <a href="https://performance.fsolabs.net/30_digital_experience_monitoring/31_hands_on_configuration.html#deploy-thousandeyes-agent" target="_blank">**login to ThousandEyes**</a> if you’ve been logged out.
-->
<!-- FULL -->


<!-- LITE -->

<!-- LITE -->

<!-- PER LITE VS FULL END -->


<br>

## Troubleshooting Customer Digital Experience

Cisco ThousandEyes enhances troubleshooting of customer digital experiences through synthetic testing, path visualization, and the correlation of metrics for comprehensive performance analysis.

Follow the process in [**login to ThousandEyes**]({{< ref "/10_lab_access.html#login-to-thousandeyes" >}} "login to ThousandEyes") to access the ThousandEyes platform.

### Transaction View
ThousandEyes transaction (synthetic) tests simulate user interactions with web applications, like online Tea shopping, through scripted sequences.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to open the **Transaction** view in Cisco ThousandEyes.

1. Click on the **Cloud & Enterprise Agents** and then **Views** on the left menu
2. Select the **Tea-Store-Transaction-LT** test from the drop-down 
3. If not already selected, click the **Transaction** view

![image](/images/30_digital_exp_mon/TE_LT_1.png)

> **Note**: For details on configuring the transaction test and the Selenium script utilized, navigate to **Test Settings**.

The **Transaction Time** view provides the average completion time for the transaction test across all selected agents.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Adjust the view by selecting the metrics you want to compare with.

1. Click the **Metrics** drop-down
2. Select the metrics you want to compare Transaction time with, e.g. Network **Loss, Latency, Jitter**.
3. You can expand or shrink the time range you're examining and then compare the metrics.

![image](/images/30_digital_exp_mon/TE_LT_2.png)

Are there any noticeable increases or unusual patterns in the data during this period?

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll down and inspect the Map view.

1. Click the **Metrics** drop-down
2. Select the metrics you want to compare Transaction time with, e.g. Network **Loss, Latency, Jitter**.
3. You can expand or shrink the time range you're examining and then compare the metrics.

![image](/images/30_digital_exp_mon/TE_LT_2.png)

Are there any noticeable increases or unusual patterns in the data during this period?

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll down and inspect the Map view.

1. On the map, hover over agent locations near Chicago area.
2. The **Ohio Office Enterprise Agent** shows significantly longer transaction times relative to other locations. To isolate this data, click on **Filter by this Agent** next to the specified agent.

![image](/images/30_digital_exp_mon/TE_LT_3.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll upwards to view the metric data now filtered to highlight the problematic location.

1. Note the selected agent.
2. Move your cursor over the metrics display. You'll observe a notably increased transaction time, alongside a significant loss of TCP packets.

![image](/images/30_digital_exp_mon/TE_LT_4.png)

Lets continue our investigation down the layers.

<br>

### HTTP Server View
The HTTP Server View in ThousandEyes provides a detailed analysis of server response times and performance metrics for web applications, enabling precise monitoring of HTTP services.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the **HTTP Server** view.

1. Click **HTTP Server** view.
2. Inspect the response times within the selected timeframe, alongside response timing into DNS lookup connect, wait, and SSL negotiation times. 
    - If you hover over the chart, individual timing averages are displayed.

![image](/images/30_digital_exp_mon/TE_LT_5.png)

Are there any noticeable increases or unusual patterns in the data during this period?

Next, lets look into the Network layer.

<br>

### Agent to Server View
The Agent to Server View in ThousandEyes provides a visual analysis of the network path and performance metrics between testing agents and target servers, facilitating in-depth network troubleshooting.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the **Agent to Server** view.

1. Click **Agent to Server** view.
2. Inspect the network metrics such as Loss, Latency, and Jitter

![image](/images/30_digital_exp_mon/TE_LT_6.png)

Does any of these metrics stand out?

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Inspect the Path Visualization.

1. Click **Path Visualization** tab.
2. Lower the **Link Delay** until you see some issues on the path.
3. Select one of the problematic (red) links and inspect the details.
    - Also see the source and destination nodes.

![image](/images/30_digital_exp_mon/TE_LT_7.png)

You have identified an increased delay between two network nodes, which could be a potential source of the issue.

Next, you will see how ThousandEyes and AppDynamics share data to combine troubleshooting powers.

## Unified view with ThousandEyes and AppDynamics

The unified view and integration between Cisco ThousandEyes and AppDynamics offer a cohesive platform for monitoring and diagnosing digital experiences across networks and applications.

Use the credentials as described in [**login to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}} "login to AppDynamics"), to access the AppDynamics controller.

### Browser Real User Monitoring (BRUM) with Network Insights
The integration of Browser Real User Monitoring (BRUM) in AppDynamics with ThousandEyes Network Insights brings together the power of real-time user experience tracking with deep network performance analysis. This collaboration enables organizations to gain a comprehensive understanding of the digital experience from the browser to the backend, identifying issues and optimizing the end-to-end path for superior user satisfaction.

The integration between Cisco ThousandEyes and AppDynamics is already configured. See the steps for integrating AppDynamics with ThousandEyes [**here**]({{< ref "/21_OAuth_Token_Config.html" >}})

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Navigate to the **User Experience** menu in Cisco AppDynamics.

1. Click the **User Experience** menu.
2. Make sure that **Browser Apps** tab is selected.
3. Filter your view to a single browser app by searching for *appd-teastore*.
4. See the **Sync with ThousandEyes** button.
    - As a read-only user, you cannot perform the Sync.
5. Double-click the browser app in the list to open the browser application dashboard.

![image](/images/30_digital_exp_mon/AppD_BRUM_1.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Explore the Browser App Dashboard.

1. Make sure you are in the **Overview** tab within the dashboard menu.
2. Inspect the real-user response times.
3. The ThousandEyes network insights widget is available for viewing the network performance.

![image](/images/30_digital_exp_mon/AppD_BRUM_2.png)

Browser Real User Monitoring (BRUM) in AppDynamics delivers insights into actual user interactions with your website, offering a glimpse into their digital experience, unlike synthetic tests. However, it doesn't cover network performance details. Integrating with ThousandEyes fills this gap by providing additional Network Insights, allowing you to access network test data without having to exit the platform.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Explore the Geo Dashboard.

1. Click the **Geo Dashboard** tab.
2. Inspect the map and see where the application users are coming from.

![image](/images/30_digital_exp_mon/AppD_BRUM_3.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Explore Browser Snapshots.

1. Click the **Browser Snapshots** tab.
2. Find a snapshot that has some **Resource Timing** data in the 4th column.
    - You can click the 4th column header to sort the data.
3. Select one of the snapshots and click **Details**
    - Or double-click the snapshot.

![image](/images/30_digital_exp_mon/AppD_BRUM_4.png)

Browser snapshots in Cisco AppDynamics capture specific user session details, providing real-time insights into user experience and website performance issues.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Observe the Browser Snapshot.

1. Inspect the **Waterfall Graph** of the overall transaction timing for the page. You can hover over each of the metrics to see a popup definition for that metric.
2. Under **Business Transactions**, an associated Business Transaction is listed, indicating a connection to the Application Performance Management (APM) aspect of AppDynamics.
    - If you don't see a Business Transaction snapshot, go back and try selecting another Browser Snapshot.
3. Double click the **Business Transaction Snapshot**.

![image](/images/30_digital_exp_mon/AppD_BRUM_5.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Observe the Business Tranasction Snapshot.

1. Inspect the Business Transaction Snapshot Overview. You can see the association between the Browser Application, and an application backend service, in this case **teastore-webui** service.
2. Under **Potential Issues**, you can see that there was a HTTP 500 error, indicating a problem with the server.

![image](/images/30_digital_exp_mon/AppD_BRUM_6.png)

Correlating browser monitoring data with APM within AppDynamics enhances diagnostic precision and efficiency by integrating user experience insights with application performance analysis on a single platform.

> **Note:** During an actual troubleshooting process, you would delve further into the application level to identify the root cause. However, for brevity in this scenario, we'll conclude here, encouraging you to explore the options independently.

### AppDynamics Dash Studio with ThousandEyes Network Insights
AppDynamics Dash Studio, integrated with ThousandEyes Network Insights, offers a dynamic visualization platform for merging application performance and network diagnostics in one comprehensive view.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Navigate to AppDynamics Dash Studio.

1. Click **Dashboards & Reports**.
2. Select **Dash Studio** tab.
3. Double-click the **teastore-fso** dashboard.

![image](/images/30_digital_exp_mon/AppD_BRUM_7.png)

> **Note:** This dashboard is shared among students, so it may already contain some data.

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Enter the edit mode.

1. Switch between **View** and **Edit** mode with a button on the top-right of the dash studio.
    - You are in the edit mode if you see the dashboard widget options and properties.

![image](/images/30_digital_exp_mon/AppD_BRUM_8.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Add a new **Time Series** graph.

1. Click the first icon to add a new **Time Series** graph.
2. Change the name of the widget heading.

![image](/images/30_digital_exp_mon/AppD_BRUM_9.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Configure the **Time Series** graph with ThousandEyes data.

1. From the drop-down menu, select **ThousandEyes** as the data source for the widget. Use the following values for the data source:
   -  Metric Category: **Web - Transactions**
    - Metric: **Transaction Time**
    - Group by: **Agents**
    - Account Groups: **Cisco-One**
    - Tests: **Tea-Store-Transaction-LT**
2. Observe the ThousandEyes widget. Which location is experiencing the slowest transaction times?

![image](/images/30_digital_exp_mon/AppD_BRUM_10.png)


## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll take a look at the application from an operations viewpoint in the Application Dependency Monitoring use case.

<br>