+++
title = "Manually Match TE Tests"
chapter = false
weight = 3
+++

## Introduction

In this section, you will go through the configuration steps to manually find existing ThousandEyes tests and assign them to a browser RUM application within the AppDynamics controller. This process allows you to add the ThousandEyes tests you want to the Browser App Dashboard in AppDynamics, so you can see more data with fewer tools.


## Manually Match TE Tests &nbsp;<span style="color: #ff9900;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;Reference Only&nbsp;<span style="color: #ff9900;"><i class='fas fa-cog fa-spin fa-sm'></i></span>


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Open the Cisco AppDynamics controller. Use the steps you previously used to [**log in to AppDynamics**]({{< ref "/10_lab_access.html#login-to-appdynamics" >}}) if you were logged out.

1. Navigate to **User Experience** menu
2. A Browser Real User Monitoring (BRUM) application is used to monitor the interaction of real users with the teastore web application. If network tests are configured in ThousandEyes, you can click the **Sync with ThousandEyes** button. This will attempt to automatically match domains monitored by both AppDynamics and ThousandEyes and transfer the test results from ThousandEyes to AppDynamics
    - Before synchronization, you need to ensure that AppDynamics and ThousandEyes are integrated via a token, as you see in the [**Configure the OAuth Bearer Token**]({{ < ref "/21_oauth_token_config.html" > }})
3. The integration with ThousandEyes that you see in the following figure covers 3 application domains with the ThousandEyes tests, but they may not all be automatically detected. For some domains, you can manually match the tests you want to bring to AppDynamics, as you will see in the next steps

![image](/images/20_config_overview/manually_match_tests_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Double-click the BRUM application to open the **Browser App Dashboard**
1. The **ThousandEyes Network Insights** widget is included in the dashboard so teams can see ThousandEyes test results in the same view without leaving the AppDynamics controller
2. Click the **View test** link

![image](/images/20_config_overview/manually_match_tests_03.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; A new pop-up window shows you the ThosusandEyes tests associated with the BRUM application. If you click on one of the tests, you will be redirected to the ThousandEyes platform where you can view the test details.

![image](/images/20_config_overview/manually_match_tests_04.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; In addition to the automatic synchronization of tests by AppDynamics, you can also synchronize the desired tests manually.

1. In the **Browser App Dashboard**, select the **Network Monitoring** tab
    - A list of current ThousandEyes tests with basic network metrics is displayed
2. Click the **Manually Match ThousandEyes Tests** button

![image](/images/20_config_overview/manually_match_tests_05.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; A list of all available ThousandEyes tests appears for selection.

1. Select the ThousandEyes tests that you want to match with the current Browser app that you are monitoring in AppDynamics
    - Instead of the test names, the list shows the test target domains
2. Click **Match and ingest data** to start the process of synchronizing the tests with AppDynamics

![image](/images/20_config_overview/manually_match_tests_06.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; All tests, whether automatically synchronized or manually matched, can now be viewed in the **ThousandEyes Network Insights** widget.

1. Filter the ThousandEyes test metrics by selecting the monitored domains for which you want to view the data and the agent locations you are interested in
    - You can also view the average of all tests and all sites

![image](/images/20_config_overview/manually_match_tests_07.png)

By manually reconciling the test domains, you have successfully brought in the associated ThousandEyes test data so that teams can quickly see network performance for the monitored domains without leaving the AppDynamics Controller and Browser App Dashboard. This gives you more time to focus on solving the digital experience issues, not on which tool to use.

You can find more detail about Manually Matching TE Tests <a href="https://docs.appdynamics.com/appd/23.x/latest/en/end-user-monitoring/thousandeyes-integration-with-browser-real-user-monitoring/thousandeyes-network-metrics-in-browser-rum#id-.ThousandEyesNetworkMetricsinBrowserRUMv23.6-MatchThousandEyesTestsManually" target="_blank">**here**</a>.


<br>


## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

You will walk through the setup of ThosuandEyes Alert Notifications.

<br>
