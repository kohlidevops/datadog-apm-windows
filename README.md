# datadog-apm-windows

## Step -1: To Signup the Datadog account

To signup the Datadog account free trail with below link

    https://www.datadoghq.com/free-datadog-trial/

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/25e7a24d-2e34-4b29-802c-8979df7d1b8c)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/55d32190-9bcb-47b2-b206-9c2d35ca472e)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/66aff0fd-df00-4d58-afc7-4c08055545ca)

Then create an account.

After the Signup process, you will redirect to the link below

    https://us5.datadoghq.com/

You have to mention your stack. For my case, it is AWS and click Next.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/a5f305f5-6630-4927-a153-26041a0d452b)

## Step -2: Install Datadog Agent 

I'm going to install Datadog agent on Windows Server 2019 for Application Permonance monitoring to Continuous Profile for DotNet core application.

In order to configure, to download the Datadog agent and install it as Administrator and provide the Datadog API key.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/1b4429a8-1d46-4065-a84a-c3bc53d229b3)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/0833c25c-6513-43b8-9fab-61086e95c702)

Click Next -> Agree -> Select the location of Agent -> Next

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/80b6d2a7-5127-4660-812e-e6e1567d51d5)

Accept the License and provide the API key and Click Next.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/e4a788e2-71dd-4aa1-a648-9be7f688a87d)

Select the Datadog region -> Next -> Then enter the agent user account (I leave it as blank as testing instance)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/3a8e2dc5-a931-419f-ae08-2bb280fab7eb)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/e6ee10f0-b8ad-4b7d-866e-fbf6d56b4e6b)

To Click on Install to complete.

During installation you can see this loading icon in dashboard.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/2857d997-4094-4e71-ae5b-d4976a73ee62)

Now installation compled.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/0e091ac9-4c35-4e83-bca0-a86c6a2595e1)

After the installation. the Datadog agent manager will launch in local browser where you installed the agent.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/92f37a1a-2996-46b3-8349-7fbd9416fc61)

Now you can see the installation result in Datadog dashboard.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/52612f7f-0bd9-457e-833b-a61730cc41f2)

You can hit the Finish button in the same page.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/c44df684-aeaa-41a5-b293-84e27f538020)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/5b835d76-9f49-486b-8411-4bb5f31e8567)

If you click "System Overview Dashboard" then you will land here.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/abd34773-9f72-4f1b-a8f9-683894c692f3)

However, my Intention is to configure APM to Continuous profiler.

## step -3: Setup APM Tracer

Select the APM in main dashboard and choose the Profiles 

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/a08e0f3b-3979-477c-ad60-83e2926b20aa)

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/c9e69b17-b03e-4196-a906-e7e09d43d4d7)

Now, Select -> Add new service

I'm going to monitor the .Net based application in windows server. 

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/053a4f74-32fd-43c6-b0b2-d3aeca8a96e8)

You will see the ".Net profiler enable" section, Here I good to go with "Windows".

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/12336d48-61fe-4d87-84e7-30141be71035)

You can click on the link to downlad .Net agent or you can use below link to download.

        https://github.com/DataDog/dd-trace-dotnet/releases

Now run the installer with administrator privileges in windows server.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/ab02c887-b26d-4809-bb0a-bca249b6e3c1)

Accept the license term and setup the location path then click to Install.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/4defd244-223e-438b-8ef6-3c8c7904db84)

To enable the profiler

For my case, My application is standalone application in windows server. You can copy and paste the below PS code in windows server Powershell ISE to click execute.

        SET CORECLR_ENABLE_PROFILING=1
        SET CORECLR_PROFILER={111111-2222-3333-4444-55555555}
        SET DD_PROFILING_ENABLED=1
        SET DD_SERVICE=MyService
        SET DD_ENV=production
        SET DD_VERSION=1.2.3

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/e94495cc-8fa4-409b-8b6f-8cb20a0e0c3d)

To restart the application and reboot the windows server.

Now you can check the Datadog dashboard -> APM -> Traces.

![image](https://github.com/kohlidevops/datadog-apm-windows/assets/100069489/97dbdaf7-98e4-4db5-b7f3-f2811f8e9ce5)

Perfect! From this dashboard, you can see the API call and its response time and lot of things related to application performance monitoring.




        
