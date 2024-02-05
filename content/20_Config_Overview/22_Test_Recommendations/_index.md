+++
title = "TE Test Recommendations"
chapter = false
weight = 2
+++

## Introduction

In this section, you will learn how to integrate ThousandEyes and AppDynamics to generate network tests from the recommendations that ThousandEyes has created using the services already discovered in AppDynamics.

## Configure Test Recommendations &nbsp;<span style="color: #ff9900;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;Reference Only&nbsp;<span style="color: #ff9900;"><i class='fas fa-cog fa-spin fa-sm'></i></span>

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Configure bi-directional integration with **Test Recommendations** in the ThousandEyes platform.

1. In the left menu, select **Integrations** and click on **+ New Integration**
    - Select **AppDynamics** integration when prompted
2. Provide the integration details, and make sure you select **Test Recommendations** radio button
    - You can use basic authentication or API client from AppDynamics
3. Click the **Test** button to ensure that communication works with the specified credentials
4. You should see the confirmation that the test was successful
5. Save the integration
    - Note that this integration does not only apply to one account group, but is visible for all account groups in your organization

![image](/images/20_config_overview/test_recommendations_1.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Next, create the recommended tests in Cisco ThousandEyes that are suggested as part of the bidirectional integration with Cisco AppDynamics.

1. In the left menu, under **Cloud & Enterprise Agents**, select **Test Settings**
2. Click the dropdown next to **Add New Test**
3. Select **Add From Recommendations**

![image](/images/20_config_overview/test_recommendations_2.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; There may be several business applications that ThousandEyes has included through bidirectional integration with AppDynamics. These are the applications that are currently monitored by the AppDynamics controller, and seen by the user or API token used for the integration.

1. Select the application for which you want to create the tests

![image](/images/20_config_overview/test_recommendations_3.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; The connection between AppDynamics and ThousandEyes brings information about the services you monitor with AppDynamics into ThousandEyes. Based on this information, the ThousandEyes platform recommends tests and test configurations to bring you full visibility into these services.

1. From the list of dependent services, select the ones you want to monitor with ThousandEyes
2. To configure tests for the selected services, click **Configure Tests**

![image](/images/20_config_overview/test_recommendations_4.png)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Once you have selected the services, you need to configure the tests. When creating tests based on the recommendations, the <a href="https://docs.thousandeyes.com/product-documentation/internet-and-wan-monitoring/tests/working-with-test-settings#network-layer-tests" target="_blank">**Agent to Server**</a> test is currently supported.

1. Select one or more agents from the list of available vantage points
2. Configure the time interval for test execution
3. Click **Review** for a final review of the test settings

![image](/images/20_config_overview/test_recommendations_5.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; The recommendations generate Agent to Server tests for the selected services and a dashboard showing the status of the tests and the health of business application, as provided by AppDynamics.

1. Click **Deploy Now** to deploy the tests

![image](/images/20_config_overview/test_recommendations_6.png)

You should see a **Setup Completed Successfully** window after the deployment.

![image](/images/20_config_overview/test_recommendations_7.png)

The tests should now be visible in the **Test Settings** menu, and you should be able to inspect the monitored data in the **Views**.

![image](/images/20_config_overview/test_recommendations_8.png)

In the following sections, you will learn how to use the tests to improve your monitoring strategy for full stack observability.


You can find more detail about configuring Test Recommendations <a href="https://docs.thousandeyes.com/product-documentation/integration-guides/appdynamics#creating-your-integration" target="_blank">**here**</a> and <a href="https://docs.thousandeyes.com/product-documentation/integration-guides/appdynamics#creating-recommended-tests" target="_blank">**here**</a>.

<br>


## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

You will learn how AppDynamics matches domains monitored by ThousandEyes, how to see ThousandEyes data in AppDynamics BRUM applications, and how to manually add ThousandEyes test results to the AppDynamics BRUM application.

<br>
