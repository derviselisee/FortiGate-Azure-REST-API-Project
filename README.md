## FORTIGATE AZURE REST API PROJECT

This project shows how I deployed a FortiGate firewall in Microsoft Azure and used its REST API to retrieve configuration data through Postman. 
The goal was to understand how real network devices expose programmable interfaces and how automation tools can interact with them. 
This project demonstrates deployment, API authentication, and API calls to view live firewall policies.

## Understanding APIs and REST APIs

First of all, an API is a way for two systems to communicate with each other through requests and responses. 
It allows one application to ask another application for information or to perform an action without needing to know how the internal code works.
Because of that, APIs create a clean bridge between programs and make automation possible.
There are different kinds of APIs, and each one follows its own rules for how data is exchanged and how requests must be sent.

In our case, we used a REST API, which is a very common style of API that relies on standard web methods such as GET, POST, PUT, and DELETE.
A REST API uses simple URLs and usually exchanges data in JSON, which makes it easy to read and easy to automate.
Because REST APIs follow predictable rules, they allow tools like Postman or Python scripts to interact with devices such as a FortiGate firewall in a very efficient way.

<img width="1600" height="900" alt="Figure_Real_world_Analogy_of_an_API_2f5cee9677" src="https://github.com/user-attachments/assets/734c53e8-3218-435a-85cf-9a4378569f22" />

## 1-Deploying the FortiGate in Azure

I started by deploying a licensed FortiGate VM in Microsoft Azure. After the deployment finished, I accessed the firewall through its public IP address.
Azure assigned me a public IP and placed the firewall inside a dedicated virtual network. The screenshot below shows the VM running in my Azure portal.

<img width="2878" height="1560" alt="FORTIGATE IN AZURE" src="https://github.com/user-attachments/assets/b0d42895-4678-4066-a768-5d18f7d46812" />

## 2-Creating a REST API Administrator

Inside the FortiGate, I created a REST API administrator account. This type of administrator does not log in through the graphical interface. 
Instead, it generates an API token that can be used by external automation tools.

<img width="2876" height="1468" alt="I created a REST API Admin on my FortiGate" src="https://github.com/user-attachments/assets/7cf4a4c3-00d1-439e-9761-936a75ed251c" />

A token works like a digital key. It identifies you to the device and proves that you are authorized to make API requests. 
Because of that, you do not need to send your username and password every time you call the API. It is safer and much more convenient for automation.

## 3-Understanding the Role of Postman

I used Postman to send API requests to the firewall. Postman is a tool that allows you to build, test, and repeat HTTP requests easily.
It lets you set headers, add tokens, choose methods such as GET or POST, and see the response from the server.
Because of that, Postman is perfect for learning how APIs work before writing automation code.

<img width="2880" height="1800" alt="I am using POSTMAN to call my FortiGate API" src="https://github.com/user-attachments/assets/3c1e23f2-f803-4c0f-bf40-74eb5f93a3ba" />

## 4-Calling the FortiGate API through the Public IP

To test the API remotely, I used the firewall’s public IP address as the target endpoint in Postman. 
I placed my API token inside the Authorization header and set the request type to GET.
Once everything was in place, Postman successfully reached the firewall and returned the firewall policy data, which confirmed that the API token, endpoint, and connectivity were all working correctly.

<img width="2880" height="1800" alt="I called an API to see my FGT firewall policy " src="https://github.com/user-attachments/assets/579b2242-edc6-4ab2-a229-43ee2bb5a9e7" />
<img width="2880" height="1464" alt="Firewall Policy in FGT GUI" src="https://github.com/user-attachments/assets/7d813f54-067c-4542-96c1-ecd334473849" />


## Summary

This project helped me understand how a FortiGate exposes its configuration through REST API endpoints.
I learned how to authenticate with a token, how to use Postman to test API requests, and how to read JSON responses that represent real firewall objects. 
This is an important skill for network automation, cloud architecture, and DevOps workflows.

## Taking API Automation Further with Python

The next step in my API journey will be using Python to interact with the FortiGate instead of relying only on Postman. 
Python will allow me to automate requests, apply configuration changes, and build scripts that can read or modify settings on the firewall in a repeatable way. 
Because Python supports powerful libraries for HTTP requests, I will be able to connect to the FortiGate API, send commands, process JSON data, and eventually create real automation tools that manage the device just like a network engineer would through the GUI.
