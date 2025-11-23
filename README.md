# FORTIGATE AZURE REST API PROJECT

This project shows how I deployed a FortiGate firewall in Microsoft Azure and used its REST API to retrieve configuration data through Postman. 
The goal was to understand how real network devices expose programmable interfaces and how automation tools can interact with them. 
This project demonstrates deployment, API authentication, and API calls to view live firewall policies.

## 1-Deploying the FortiGate in Azure

I started by deploying a licensed FortiGate VM in Microsoft Azure. After the deployment finished, I accessed the firewall through its public IP address.
Azure assigned me a public IP and placed the firewall inside a dedicated virtual network. The screenshot below shows the VM running in my Azure portal.

## 2-Creating a REST API Administrator

Inside the FortiGate, I created a REST API administrator account. This type of administrator does not log in through the graphical interface. 
Instead, it generates an API token that can be used by external automation tools.

A token works like a digital key. It identifies you to the device and proves that you are authorized to make API requests. 
Because of that, you do not need to send your username and password every time you call the API. It is safer and much more convenient for automation.

## 3-Understanding the Role of Postman

I used Postman to send API requests to the firewall. Postman is a tool that allows you to build, test, and repeat HTTP requests easily.
It lets you set headers, add tokens, choose methods such as GET or POST, and see the response from the server.
Because of that, Postman is perfect for learning how APIs work before writing automation code.

## 4-Calling the FortiGate API through the Public IP

I took the public IP address of the firewall and added it to Postman as the target API endpoint. 
Then I included my token inside the Authorization header. 
After that, I was able to successfully make a GET request to the policy endpoint.

##Summary

This project helped me understand how a FortiGate exposes its configuration through REST API endpoints.
I learned how to authenticate with a token, how to use Postman to test API requests, and how to read JSON responses that represent real firewall objects. 
This is an important skill for network automation, cloud architecture, and DevOps workflows.
