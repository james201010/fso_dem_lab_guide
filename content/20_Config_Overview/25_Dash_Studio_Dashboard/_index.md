+++
title = "Create Dash Studio Dashboard"
chapter = false
weight = 5
+++

## Introduction

In this section, you will walk through the steps to configure a dashboard with AppDynamics Dash Studio that includes the ThousandEyes data previously enabled through the integration.


<br>


## Create Dash Studio Dashboard &nbsp;<span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;Hands-On-Exercise&nbsp;<span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Open the Cisco AppDynamics controller. Use the steps you previously used to [**log in to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}}) if you were logged out.

1. Navigate to **Dashboards & Reports**
2. Click the **Dash Studio** tab
    - Dash Studio is a newer version of dashboard creator that aims to provide a simpler and more intuitive editor for your dashboards. It also allows ThousandEyes native widgets when integration is enabled
3. Click the plus sign (+) to create a new dashboard

![image](/images/20_config_overview/dash_studio_01.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; When you open the dashboard for the first time, you will enter the edit mode. Here you can add and edit various widgets, creating your own customized experience to keep track of the things that matter to you in a single window.

1. Use a unique name for your dashboard
2. Click the **Time Series** button to place a new time series widget on the canvas
3. When you select a widget in edit mode, the **Data** section appears at the bottom. From the drop-down menu, select **ThousandEyes** as the data source for the widget
    - The ThousandEyes data source is only enabled if the integration has been previously configured
4. Use the following values for the data source:
    -  Metric Category: **Network - Agent to Server**
    - Metric: **Latency**
    - Group by: **Tests**
    - Account Groups: Select the available account group
    - Tests: select 1 or more tests from ThousandEyes
        - In the example on the figure, two ThousandEyes tests are selected, which were created using the test recommendations
5. Use the **Widget Properties** and customize the widget according to your needs

![image](/images/20_config_overview/dash_studio_02.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Navigate to the ThousandEyes platform. You will include an Iframe widget in the Dash Studio dashboard. Iframe integration is another great way to incorporate data from other platforms into your dashboard. In this task, you will add a ThousandEyes widget to the Dash Studio dashboard.

1. Navigate to the **Dashboards** menu
2. Select the **appd-teastore-fso-lab-62-f6d9 Dashboard**
3. Select one of the widgets you want to include in the AppDynamics Dash Studio Dashboard, click the button with the three dots and select **Embed Widget**

![image](/images/20_config_overview/dash_studio_03.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; A new window opens with the preview of the widget, the iframe link and some basic settings.

1. Copy the URL within the **src** tag
    - Don't copy the entire string, only the HTTPS URL is required
2. Click **Save Changes**
    - If you do not save the widget embed, the URL will not work

![image](/images/20_config_overview/dash_studio_04.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Navigate back to your Dash Studio dashboard in Cisco AppDynamics. 

1. Click the **Iframe** button to place a new Iframe widget on the canvas
    - You may need to activate **Edit** mode by clicking on the pen icon in the upper right corner
    - To exit edit mode, click on the **View** button in the upper right corner
2. Paste the ThousandEyes widget URL you copied earlier
3. Disable the sandbox
4. Click **Embed**

![image](/images/20_config_overview/dash_studio_05.png)

The Iframe widget in AppDynamics Dash Studio is a great way to include data and visualizations from any platform. This allows you to bring monitored data closer together and provide a unified experience when monitoring your applications from the perspective of the entire stack.

You can find more detail about configuring a Dash Studio Dashboard With ThousandEyes data <a href="https://docs.appdynamics.com/appd/23.x/latest/en/appdynamics-essentials/dashboards-and-reports/dash-studio/thousandeyes-integration-with-appdynamics/configure-the-thousandeyes-dashboard" target="_blank">**here**</a>.

<br>


## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll walk through the ...

<br>
