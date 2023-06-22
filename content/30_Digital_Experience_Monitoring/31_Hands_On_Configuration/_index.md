+++
title = "Hands-On Configuration"
chapter = false
weight = 1
hidden = true
+++

<!-- PER LITE VS FULL START -->

<!-- 

FULL: hidden = false

LITE: hidden = true

-->

<!-- PER LITE VS FULL END -->

## Introduction

In this section we’ll walk through the following deployment and configuration tasks for ThousandEyes.

- Deploy a ThousandEyes Enterprise Agent in AWS
- Create a ThousandEyes Web HTTP Server Test
- Configure a Dashboard in ThousandEyes

<!--
- Install ThousandEyes Browser Agent (Optional)
-->

## Deploy ThousandEyes Agent

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the URL below to **navigate to okta** in your browser.

```bash
https://cisco-one.okta.com/
```

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Enter the Cisco User email (**email ending in @cisco-one.com**) provided by your instructor for the **Username** and the associated Cisco Password for the **Password** and click on the **Sign in** button.

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now click on the **ThousandEyes** tile to login to ThousandEyes.

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_02.png)

<!--
<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Enter your username again and the associated password that was provided to you

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_03.png)
-->

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to begin the creation of a new enterprise agent

1. Click on the **Cloud & Enterprise Agents** tab to expand the menu on the left
2. Click on the **Agent Settings** menu option 
3. Click on the **Add New Enterprise Agent** button on the right

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_04.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to obtain your Account Group Token and open AWS to complete the CloudFormation template

1. Click on **IaaS Marketplaces**
2. Click on the **eyeball icon** to display the Account Group Token 
3. Click on the **Copy** button to copy the Account Group Token and then save it for later
4. Click the **Launch in AWS** button (this will open another window with the AWS console login)

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_05.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now you should see the **Create Stack** screen

1. Change the region to **N. Califronia** if it did not default to that region
2. Click on the **Next** button

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_06.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the command below in your Cloud9 terminal to obtain the EKS cluster name you'll need in the next step

```bash
echo $aws_eks_cluster_name
```

The output should look like the image below.

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_07.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to complete the second page of the CloudFormation template

1. Enter your **EKS cluster name** with **-Stack** at the end for your stack name
2. Paste the **Account Token** you copied earlier 
3. Enter your **EKS cluster name** with **-EA** at the end for your Hostname
4. Select **FSO-Lab-Dev-Ops** for your KeyName
5. For Subnet ID type your lab # (for example – Lab-01) to filter your subnets and select one of your **public** subnets
6. For VPC type your lab # (for example – Lab-01) to filter your VPC and select your VPC ID
7. Click the **Next** button

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_08.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Click on the **Next** button

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_09.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Click on the **Create stack** button

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_10.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Wait for the the stack to show **CREAT_COMPLETE** on the left hand side

- The stack will take approximately 2-3 minutes to be created
- You can click the refresh button at the top left next to Stacks to see the status

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_11.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; The agent you just created should appear in the Agent Settings page within about 5 minutes

![image](/images/30_digital_exp_mon/te_ent_agent_deploy_12.png)


<br>


## Create ThousandEyes Test

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to begin the creation of a new Web HTTP Server test

1. Click on the **Cloud & Enterprise Agents** tab to expand the menu on the left
2. Click on the **Test Settings** menu option 
3. Click on the **Add New Test** button

![image](/images/30_digital_exp_mon/te_create_test_01.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to configure the new Web HTTP Server test

1. The Layer should be **Web**
2. Test Type should be **HTTP Server**
3. Test Name should be **TeaStore-API-Call-** followed by your **EKS cluster name**
4. Enter **https://fso-payment-gw-sim.azurewebsites.net/api/payment** in the URL field
5. Interval should be **2 minutes**
6. Click on the **Agents** Field 
7. Select **Enterprise** in the **Built-in Labels** column
8. Select your agent you just created
9. Click the **Create New Test** button

![image](/images/30_digital_exp_mon/te_create_test_02.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now click on the Web HTTP Server test you just created.

![image](/images/30_digital_exp_mon/te_create_test_03.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now click on the **Run Once** button to run the test on-demand.

![image](/images/30_digital_exp_mon/te_create_test_04.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; The test should run and the Views Display should appear after a couple minutes where you can look at the **Availability** and the **Status by Phase**

![image](/images/30_digital_exp_mon/te_create_test_05.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; You can also select the **Response Time** from the **Metric** pull-down menu

![image](/images/30_digital_exp_mon/te_create_test_06.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; You can also select the **Path Visualization** view

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; In the upper right of the path visualization section, you can get additional path detail by increasing the path hops by **sliding the hop bar**

![image](/images/30_digital_exp_mon/te_create_test_07.png)


<br>



## Copy ThousandEyes Dashboard

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to start the copy of the shared ThousandEyes dashboard

1. Click on the **Dashboards** tab on the left menu
2. Click on the drop-down menu 
3. Select the **Tea Store** shared dashboard
4. Click on the **three ellipses** to the right of **Add Widget** button
5. Select **Duplicate Dashboard**

![image](/images/30_digital_exp_mon/te_copy_dashboard_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Now use the steps below to complete the copy of the shared ThousandEyes dashboard

1. Name the dashboard **Tea Store -** and the **name of your EKS cluster**
2. Leave the **Account Group Visibility** set to **Only current account group** 
3. Check the **Set as my default** checkbox
4. Click on the **Duplicate Dashboard** button

![image](/images/30_digital_exp_mon/te_copy_dashboard_02.png)



<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Scroll down the dashboard and explore the different metrics

![image](/images/30_digital_exp_mon/te_copy_dashboard_03.png)



<!--


<br>


## Install ThousandEyes Endpoint Agent (Optional)

<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Use the steps below to start the **download of the Endpoint Agent**.

1. Click on **Endpoint Agents** and then **Agent Settings**
2. Click on the **Download** button

![image](/images/30_digital_exp_mon/te_browser_agent_01.png)


<span style="color: #143c76;"><i class='fas fa-circle fa-sm'></i></span>&nbsp; Choose the **Endpoint Agent** for your OS **(Windows or Mac OS)**. Then click on the **Installation Guide link** for your OS and keep it **open in a separate browser window**.

![image](/images/30_digital_exp_mon/te_browser_agent_02.png)


-->



<br>

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We’ll look at the results of your configuration with specific observability scenarios.

<br>