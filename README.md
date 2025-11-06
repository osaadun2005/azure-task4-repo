# azure-task4-repo
Detailed Research, Documentation, Roles And The Uses  Of  Azure Container App Features



1.**Task Overview**

- To Document The Various Features of The Azure Container App

- Owner: Intern/ Osa Adun

- Instructor: Gabriel Mekuleyi

- Start Date: November 5, 2025

- End Date: Novemberr 6, 2025

- Status Completed



2.**Perequisite**

- Microsoft Azure Platform

- Azure subscription

- Resource Group


3. **Steps to Deploy**
  
   - Overview

     The Essentials features are displayed on the **Overview** page as can be seen bekow

      - Resource Group                                    
      - Status                                            
      - Location                                          
      - Subscription                                      
      - Application Url
      - Container App Environment 
      - Environmental Type
      - Get Started
      - Properties
      - Monitoring
      - Log Analytics




     ![WhatsApp Image 2025-11-05 at 9 55 51 PM](https://github.com/user-attachments/assets/1f5ff0b2-d84d-48e9-a55a-fe51563c3b61), 


   - Activity Log
  
     The Activity Log is helpful in the search and monitoring of performance, diagnostic, health logs and so many more as seen below
     
     These logs help you monitor
     
     Troubleshoot

     Analyze the behavior of your app.
  
     
     
     <img width="1008" height="548" alt="image" src="https://github.com/user-attachments/assets/a64dd6e9-9417-41ce-81ac-a6d9b41e5e4d" />

   - Access Control (IAM)
  
     Azure Container Apps use  Access Control to manage access permissions. You can assign built-in or custom roles to users, groups, or service principals to control who can view, deploy, or manage container         apps.
     Access is granted by assigning roles at the subscription, resource group, or resource level.
     
     - Role	Permissions
     - Owner	Full access to manage everything, including access control
     - Contributor	Can create and manage resources but not assign roles
     - Reader	Can view resources but not make changes
     - Container App Contributor	Can manage container apps but not environments or access control



     <img width="912" height="624" alt="image" src="https://github.com/user-attachments/assets/c4dbcdce-021b-4dda-8dcc-689470b1c157" />

   - Tag

     Azure Container Apps support tagging at the resource level, allowing you to organize, manage, and track costs across your cloud environment. Tags are key-value pairs that help categorize resources.
     Tags in Azure Container App are metadata elements you attach to resources. Each tag consists of a name (key) and a value, such as below,
     
     - Container App resources
       
     - Container App environments
       
     - Resource organization
       
     - Billing and cost management
     
     - Automation and policy enforcement




     <img width="976" height="511" alt="image" src="https://github.com/user-attachments/assets/a1686e80-d3ec-4e62-ac09-7edd587c1981" />



   - Diagnose And Solve Problem
  
     Azure Container Apps includes a built-in “Diagnose and solve problems” tool in the Azure Portal that helps you troubleshoot common issues like deployment failures, scaling delays, and connectivity problems.
     This tool provides guided diagnostics for your container app. It automatically checks for common issues and offers actionable insights based on your app’s configuration and runtime behavior.Some                  troubleshooting Tips:View Console Logs, Check Revision Status, Verify Image Accessibility, and Use Azure Monitor.
  
     - Error deploying new revision
     - Provisioning delays
     - Ingress issues
     - Scaling problems
     - Container crashes or restarts



     <img width="935" height="477" alt="image" src="https://github.com/user-attachments/assets/bec93350-15db-467e-9b07-54ea483ad0ce" />


   - Resource Visualizer
  
     Azure Container Apps can be visualized using the Azure Resource Visualizer, a tool in the Azure Portal that automatically generates interactive diagrams of your cloud resources and their relationships.
     Azure Resource Visualizer is a built-in feature that helps you understand the architecture of your deployed resources—including Azure Container Apps—by showing how they connect to other services like             environments, registries, secrets, and monitoring tools. Some benefit for Container App Users below,
  


      - Architecture clarity: See how your app fits into the broader cloud environment.
  
     - Troubleshooting: Identify misconfigured or missing dependencies.
    
     - Security reviews: Visualize access paths and network boundaries
    
     - Documentation: Export diagrams for team sharing or compliance.
  
     - Interactive diagrams: Clickable nodes representing resources and their dependencies.
    
     - Real-time mapping: Reflects the current state of your Azure environment.
    
     - No setup required: Automatically available in the Azure Portal.



     <img width="960" height="425" alt="image" src="https://github.com/user-attachments/assets/08d6045f-768a-4f99-916d-2a224981fa9a" />


 
   - Application

     There several features under  **Application** in the Container App Deployment, several features are shown below
  


      <img width="1094" height="1280" alt="image" src="https://github.com/user-attachments/assets/cac2c4f7-9416-4e2f-9998-4bc1db76f71d" />



     1. Revision and Replicas
      
        Azure Container Apps use revisions to manage deployments, and replicas to scale workloads dynamically. Each new revision starts with its own replica settings, which may differ from previous ones
        
        - Revisions in Azure Container Apps
          - Immutable snapshots: Every deployment creates a new revision that captures the app's configuration at that point in time. Once created, a revision cannot be changed
          - Version control: Revisions allow you to roll back to previous versions easily if needed
          - Scoped changes: Changes like environment variables or container image updates trigger new revisions. App-wide settings (e.g., secrets or scaling rules) can affect all revisions
          - Multiple revisions: You can run multiple revisions concurrently, enabling gradual rollouts or A/B testing

        - Replicas in Azure Container Apps
          - Replicas represent the number of active instances of a revision handling traffic.
          - Azure Container Apps scale replicas automatically based on traffic or custom metrics. You can configure min/max replica counts per revision
          - New revision behavior: When a new revision is deployed, it starts with the initial scale settings (often 1 replica). It does not inherit the replica count from the previous revision
         
          <img width="1280" height="598" alt="image" src="https://github.com/user-attachments/assets/7ea9211c-dec7-497e-ad8f-c7a0c1e030db" />

           
     2 .Containers
              
        In Azure Container Apps, a container is the core unit that runs your application code, packaged with its dependencies. You define it using a template configuration that includes the image, resources,             and environment settings.

        - Container Basics
           - Runtime flexibility: You can use any Linux-based x86-64 container image, built with any language or framework
           - Image sources: Containers can be pulled from public or private registries like Docker Hub or Azure Container Registry.
           - Crash recovery: If a container crashes, Azure automatically restarts it to maintain availability

              <img width="1280" height="558" alt="image" src="https://github.com/user-attachments/assets/01cb8159-0ea4-4bde-98ec-639e60b157fe" />


      3. Scale
    
         Azure Container Apps scale automatically using KEDA-based rules that respond to traffic and events. You can also set manual min/max replica counts to control scaling behavior.

           - How Scaling Works
        
             - Horizontal scaling: Azure Container Apps scale out by creating more replicas of a revision. Each replica is an instance of your container running independently.
             - Autoscaling engine: Powered by KEDA (Kubernetes Event-driven Autoscaling), which monitors metrics and triggers scaling actions based on thresholds
             - Autoscaling: Azure Container Apps scale replicas automatically based on traffic or custom metrics. You can configure min/max replica counts per revision.

              <img width="1280" height="547" alt="image" src="https://github.com/user-attachments/assets/f5beb8f5-fc98-4ac9-a426-00ffcfde1af6" />



      4. Volume

         Azure Container Apps support multiple types of volumes, including ephemeral and persistent storage, to manage data across containers and replicas.
         
          - Volume names must not include special characters like dots (.), or deployment will fail
          - Ephemeral volumes are lost on shutdown—don’t use them for critical data.
          - Azure Files volumes require proper authentication (via secrets or managed identity).
        
           <img width="1280" height="689" alt="image" src="https://github.com/user-attachments/assets/4aaaf2f7-0e42-4bb8-b8da-f3b9813e2300" />







   - Setting

     Azure Container Apps settings include configuration options for deployment, deployment stacks, Dpar, service connector , locks, and resiliency. These settings define how your app runs, scales, and interacts      with other services.

    1 . Deployment Github, Registry, Azure Access, and Artifacts
   
        Set up GitHub Actions to automatically build and deploy your code to your Container App. Note that every deployment will create a new revision.With every deployment, you'll get a new image tag that will          be stored in the registry of your choice. Upload an artifact from your computer, and Azure Container Apps will build it into a container image and deploy it to your Container App.Configure environment
        variables for building a container image from your code. For Java applications, JDK 17 is used for build by default

    <img width="1280" height="697" alt="image" src="https://github.com/user-attachments/assets/b10ad078-330a-4d6c-9039-9856eb7cc3da" />




    2 . Development stack: It helps Azure apply optimized settings for telemetry, diagnostics, and performance monitoring.

        A deployment stack defines the runtime environment and monitoring configuration for your container app. Azure Container Apps support multiple deployment stacks, including Generic, Java, and .NET, which           influence monitoring and runtime behavior. The default is Generic, but you can set a specific stack to enable enhanced telemetry and diagnostics.
        
      <img width="1280" height="684" alt="image" src="https://github.com/user-attachments/assets/7d3aebcc-347e-4898-be94-b94d9a513960" />




    3 . Dapr

       Azure Container Apps natively support Dapr (Distributed Application Runtime), enabling you to build resilient, event-driven microservices with minimal infrastructure management and offers a                       fully managed version of the Dapr APIs in your applications. Enable Dapr and right away you'll get reliable service-to-service calls for your new revision. Select more Dapr components for                         capabilities like state management, message publish/subscribe, and more.
   
       - Dapr settings
          - Enabled
          - Disabled

      <img width="1280" height="662" alt="image" src="https://github.com/user-attachments/assets/4f63927d-71d3-4a4a-a15b-3e15e00b0df9" />





    4 .Service Connector Preview

       Azure Container Apps support Service Connector to simplify secure connections to other Azure services and Use Service Connector to connect your Azure Compute and target backing services. It is a tool that        automates the setup of secure connections between Azure services. It handles:

         - Network configuration
         - Authentication setup
         - Connection string management

      <img width="1280" height="644" alt="image" src="https://github.com/user-attachments/assets/2d1290a9-da22-4696-b83b-ae40f6fd55f4" />







    5 . Resiliency preview

      Azure Container Apps offer built-in resiliency features like zone redundancy, autoscaling, and retry policies to help your applications recover gracefully from failures and maintain high availability.
      Resiliency policies allow your container apps to recover from failures by adding retries, timeouts, circuit breakers, and connection pools on service-to-service calls. Check and configure the resiliency          policies you want to establish for your container app


      <img width="1280" height="551" alt="image" src="https://github.com/user-attachments/assets/94c80557-f710-4096-a6c7-e6d64c6aa791" />





  
    6 . Locks

        Azure Container Apps support resource locks through Azure Resource Manager to prevent accidental deletion or modification. You can apply locks at the resource, resource group, or subscription level.There         are types of locks, scope of lock, Notes attached to lock. These locks override user permissions—even if someone has full access, they can’t delete or modify a locked resource unless the lock is removed

        - ReadOnly: Prevents updates and deletions. Users can only view the resource.
        - CanNotDelete: Allows updates but blocks deletion.

      <img width="1280" height="667" alt="image" src="https://github.com/user-attachments/assets/2d2460da-4c72-46fd-a4dd-f4ab8adb3bab" />





   - Networking
  
     
     Azure Container Apps support flexible networking options, including public ingress, internal-only access, and integration with virtual networks (VNets) for secure communication with other Azure resources.It      operate within a Container App Environment, which defines the networking scope. There are two main environment types:

     - Consumption/Serverless
     - Dedicated/App Service Plan
    
       
     1 . Ingress

     Azure Container Apps support three ingress modes—external, internal, and disabled—allowing you to control how your app is accessed over the network. Ingress is an app-wide setting and affects all revisions       simultaneously.


     <img width="945" height="469" alt="image" src="https://github.com/user-attachments/assets/c8a4971a-3edf-4f5e-b47a-5be4388ad22d" />

     
    2 . Custom Domain

    Azure Container Apps support custom domains, allowing you to map a personalized web address to your app and secure it with SSL/TLS certificates. You can use either a free managed certificate or upload            your own.
   
      - Custom Domain Setup Overview

      - Ingress Required: Your container app must have ingress enabled (external or internal) to support custom domains.

      - TLS/SSL Certificate: Every custom domain must be bound to a certificate. You can:Use a free managed certificate from Azure / Upload your own certificate (e.g., from Let's Encrypt or DigiCert).

      - SNI Certificates: Azure Container Apps require Server Name Indication (SNI) certificates for domain binding.
     
   
     
           ![WhatsApp Image 2025-11-06 at 4 40 36 PM](https://github.com/user-attachments/assets/2ae5f25b-3fc2-489c-bb60-2dd65e70e7cf)




   3 . CORS

   Cross-Origin Resource Sharing (CORS) allows JavaScript code running in a browser on an external host to interact with your backend. Specify the origins that should be allowed to make cross-origin calls           (for example: http://example.com:12345). To allow all, use "*" and remove all other origins from the list. Slashes are not allowed as part of domain or after TLD

     - CORS is a browser security feature that restricts web apps from making requests to a different domain than the one that served the web page.

     - Azure Container Apps allow you to configure CORS to permit specific domains to access your app.


        <img width="982" height="475" alt="image" src="https://github.com/user-attachments/assets/2d920813-94bc-4267-a51f-bf3b1a1dbca3" />








   - Security
  
     Azure Container Apps offer a robust security model that includes managed identities, secrets management, network isolation, and built-in authentication to help you build secure, scalable applications.

     1 . Secrets
  
         Azure Container Apps allow you to securely store and manage secrets at the application level, making them accessible to container revisions without embedding sensitive data in your code.
         Secrets are key/value pairs that can be used to protect sensitive data like passwords and connection strings. Secrets that you store here will be valid across all your revisions. Note that changing               secrets will not create a new revision.

        <img width="905" height="427" alt="image" src="https://github.com/user-attachments/assets/c325c47e-f245-4011-a749-ab8d2315a9e0" />


    2.  Authenrication
  
        Azure Container Apps support built-in authentication and authorization (often called “Easy Auth”) to secure your app with identity providers like Microsoft Entra ID, GitHub, Google, and Facebook. You can         enable it with minimal configuration and no code changes.

      <img width="905" height="427" alt="image" src="https://github.com/user-attachments/assets/e7a637b9-dfb5-492e-afe5-608691a1f0ac" />


   3 . Identity

     Azure Container Apps support managed identities—both system-assigned and user-assigned—allowing your app to securely access other Azure resources without storing credentials.

      - System-assigned : Tied to a single container app

      - User-assigned : Standalone Azure resource
  


        <img width="986" height="508" alt="image" src="https://github.com/user-attachments/assets/da299a83-8912-4cab-adac-a626f35d0224" />




   - Monitoring
  
   Azure Container Apps offer built-in monitoring features including log streaming, metrics, console access, and integration with Azure Monitor and Application Insights to help you track performance, diagnose       issues, and optimize your app.

   1. Log Streams

      Azure Container Apps support real-time log streaming for both system logs and container console logs, accessible via the Azure Portal or CLI. This helps you monitor and troubleshoot your app as it runs.
      Log Streaming: View real-time system and console logs directly from your container. Useful for debugging and tracking runtime behavior
   
      <img width="1080" height="528" alt="image" src="https://github.com/user-attachments/assets/7184a936-ddcb-4875-b414-ed50e0c585f1" />

  2. Log

     Azure Container Apps provide two main types of logs—console logs and system logs—that help you monitor, troubleshoot, and optimize your applications. You can stream logs in real time or integrate with Azure      Monitor for deeper insights Azure Monitor Log Analytics is a tool used to produce insights from Azure Monitor logs.

     <img width="1080" height="534" alt="image" src="https://github.com/user-attachments/assets/03127542-91ac-482f-9418-477451b35de2" />


  3.  Console

      Azure Container Apps provide interactive console access to running containers, allowing you to troubleshoot and inspect your app directly from the Azure Portal or CLI. The featurs ae as follows:

      - It lets you connect to a running container’s shell (e.g., bash or sh) to inspect logs, environment variables, file system, or running processes.
      - Useful for debugging startup issues, checking runtime behavior, or validating configuration.


       <img width="1080" height="533" alt="image" src="https://github.com/user-attachments/assets/97c7a1b4-4a16-4e9b-a560-732f28c8a1da" />



     4.  Alets

         Azure Container Apps support alerts through Azure Monitor, allowing you to track performance, detect issues, and respond quickly to critical events using metric and log-based rules.

         There are different types of aleart on the Azure container app :

        - Metric Alerts: Triggered by thresholds on metrics like CPU usage, memory consumption, replica count, or request latency.

        - Log Alerts: Based on queries in Log Analytics (e.g., error rates, failed requests, or custom logs)


   <img width="1080" height="536" alt="image" src="https://github.com/user-attachments/assets/71902ac5-5d07-4869-8271-6dc17de6ea85" />





 5 . Metric

    Azure Container Apps provide built-in metrics through Azure Monitor, allowing you to track performance, resource usage, and scaling behavior across your containerized workloads.
    

   <img width="1080" height="536" alt="image" src="https://github.com/user-attachments/assets/a58d1742-96ae-4f70-87ab-024a1b3312dd" />



    
  6 . Dashboards with Grafana (Preview) 

     Azure Container Apps now support built-in Grafana dashboards (preview), offering preconfigured visualizations for monitoring app performance, resource usage, and environment health—all accessible directly        from the Azure Portal.

     - Container App View : Shows metrics for a single app: CPU, memory, request rates, replica count, restarts
     - Environment View :Aggregates metrics across all apps in an environment: revisions, scaling, traffic

   <img width="1080" height="561" alt="image" src="https://github.com/user-attachments/assets/8571be00-9363-4ff6-a18e-b379fad07bd2" />



 7 . Advisor recommendations

     Azure Advisor provides recommendations for Azure Container Apps across key areas like reliability, security, cost optimization, and operational excellence to help you build resilient and efficient cloud-         native applications.

     <img width="1280" height="711" alt="image" src="https://github.com/user-attachments/assets/6552073d-c749-45ce-85df-ba6be672d222" />

    
   - Automation


  1 . CLI/PS

      Azure Container Apps can be managed using both Azure CLI and PowerShell, giving you flexibility to automate deployments, configure settings, and monitor your apps from the command line.
      The Azure CLI provides the most complete support for managing Container Apps. You’ll need the, While PowerShell support is more limited and typically wraps Azure CLI commands using az or uses ARM templates

     <img width="1280" height="574" alt="image" src="https://github.com/user-attachments/assets/880bf36c-07d0-41b9-a320-b30196ee24ff" />

      
  2 . Export template

      You can export an Azure Container App as an ARM or Bicep template using Azure CLI or PowerShell to replicate or automate deployments. This helps you capture the app’s configuration for reuse or version           control.

   <img width="1280" height="626" alt="image" src="https://github.com/user-attachments/assets/f5f526d5-ca47-4438-a2dd-a4331bf91916" />


   - Help

     How can we help you?

 1.| Support + Troubleshooting

     Azure Container Apps offer built-in support and troubleshooting tools to help you diagnose issues like failed deployments, scaling problems, or image accessibility errors. You can use log streaming, console      access, and the “Diagnose and solve problems” tool in the Azure Portal.


  <img width="1080" height="483" alt="image" src="https://github.com/user-attachments/assets/d7daa5a8-7a9b-4351-aa1a-b5a522a49959" />














  




