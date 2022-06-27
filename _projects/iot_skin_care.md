---
title: "IoT-connected Skin Care Product"
---

**Date:** 2019 to 2022

**Summary:** This project added IoT wireless functionality to a new consumer skin-care technology product for P&G Ventures. The IoT feature allowed the user to connect the product to their home WiFi, monitor usage data and receive tips and rewards from an app connected to the cloud, and to receive over-the-air product firmware updates. It was one of the first major IoT integrations for this company, and we successfully accelerated their design and deployment to market.

[diagram]

**Outcome:** The IoT functionality was implemented successfully, and the product was launched into market. 

**My Role:** I was the Technical Program Manager managing the wireless integration, and in communication with developers, core product designeers, product team, cloud team, and QA.

**What Happened**

- P&G Ventures approached our company MMB Networks to help them accelerate the development of the IoT feature for a new skin-care technology product. 
- We designed and developed the firmware for the IoT wireless chip, which acted as a bridge between other chips in the product and the cloud infrastructure. We designed the communication protocol that transfers data and commands between the IoT wireless chip and other chips within the product. We worked with the cloud team to refine the MQTT messages to the cloud. 
- We solve security issues based on feedback from a Security Audit
- We designed and developed the over-the-air firmware updates for all the chips in the product that can be issued from the cloud.
- We ran integration tests for all IoT features using different phones, browsers, and routers.
- The onboarding was initially done from the browser in a progressive web app (PWA). Later a mobile app was developed.
- Provided continual support as the product was launched into market.
- How the project was managed:
  - It was developed in phases. The features and goals of each phase was done per request and discussion with the client. The client would have ideas, and we would bring forth our perspective on how to refine the ideas. 
  - Each phase supported the aim for further learning about the product, until we reached a phase where it could be ready for launch. The launch dates kept on being delayed, as it usually goes for these kinds of projects. 
  - I translated business requirement into clear technical requirements that are understandable to both developers and QA (so QA can create test cases)
  - I managed a team of developers and QA. There were weekly internal technical meetings, meetings with client product team, with external tester, with customer support (as device launched), with app UI designer, and occasional support meetings with the cloud and data team
  - Development and support tasks were planned using Jira. 
  - How was risk managed? P&G was good at approaching product development through phases of learning. It was very focused on ever larger user trials to gather feedback and support. The risk was enormous for a completely novel product like this. It is creating a new product category on the market that most users have never seen before. It utilizes and integrates technology for a user case that is completely novel. So the risk was huge. Therefore, investment in every step is protected with user trials and panels. There are also extensive testing with external tester labs to test it against hundreds of different smart phones. We try to anticipate every user scenario that could break the device. And we do extensive regression testing on all the edge cases. A lot of effort was to analyze every reported bug or unexpected behavior from testing. I would triage the cases to determine the severity, and whether to feed it into the next development cycle. So the behaviour was carefully checked and pruned. The product wasn't perfect and it had limitations, we tried to push forward while managing the imperfections and limitations. This is where it helps to have both technical knowledge and business acumen. A technical person would want to make it perfect, but having business knowledge as well helps you to know when to push forward while having acceptable risks and limitations. 
  - How was budget managed? Each phase was allocated a fixed amount. As the program manager, I had to check regularly the progress of the project versus the estimate to make sure we are not in danger of running over the budget. To minimize the risk of running over, I took a developer's estimate and add buffers. Because usually the development takes longer. There will be likely extra iterations and also to account for unexpected issues from integration testing. Later as the product was launched into the market, we had SLA support contract, where again, I managed the hours, because we had a maximum number of support hours we provide per month. So I had to make decisions on how much time we can spend on an issue, depending on the criticality of the issue. A developer or QA may want to drill down deep into an issue, but I had to make a call on whether the issue is worth the time. 
  - What were the systems and processes? Regular communications within technical team and product team. 

**Challenges Encountered:**

- Global market
  - Need to maintain firmware differences for China and North America. Different language and wireless settings.
  - Differences in cloud also. MQTT kept on resetting in China
  - China could not access google time server. Had to point to a different time server in China
  - Chinese users also different expectations, different usage habits
  - Different device certificates for different regions. But must load device certificates for all regions. 
- Time out of sync. Product was not designed with IoT in mind, the product's core chip could not keep time correctly, causing issues with data accuracy later on. 
- Lack of BLE support. Would be good to deploy with chips that support as many wireless standards, then would have flexibility to include different software designs without altering the underlying hardware. 
- Oops issue: channel switching. When joining a router on a channel that is different from the channel of the product's SoftAP, it temporarily disbands the SoftAP, causing the phone to drop and having need to rejoin. And phones don't allow the app to automatically control the WiFi switching. 
- Constant changes to phone and browser ecosystem. Browser becoming more strict with security, no more mixed mode. Phone becoming more restrictive when joining WiFi networks that do not have internet access. 
- We tried to fake internet access, with mixed results.
- Market diversity of phones, browsers, and routers. Different behaviors depending on the home router, browser, and phone type. Hired a testing company specifically to test all the different combinations
- Over-the-air firmware issues. Initially, erased settings on F4. Had to develop procedures to rigorously check OTA before releasing. Check upgrade and downgrade.
- OTA issue of signature verification. 
- OTA issue of order of upgrade
- Develop different levels of testing: regression, pre-release, integration. It is particularly easy to overlook integration testing. 
- How to keep the OTA firmware signing key secure. 

**Lessons Learned**

- Design with IoT from the beginning. Know what data you want to collect, what user feature you want to support. 
- Similarly, security must be thought of from the beginning. 
- As IoT market matures, it is important to understand user expectations of how the features work. And these expectations may differ depending on the region. 
- Integration testing must not be neglected. IoT is complex, involving multiple teams developing different components of the system (firmware, wireless, cloud, app). Each team tends to only oversee the quality of its own component. It is critical for there to be ownership over integration testing that involves end-to-end testing. This also needs to be tested and monitored regularly, because there can be regular changes to cloud and phone operations that can affect the user experience. 
- Because of the complexity of an IoT product, with many components that need to be integrated. It does take time to iterate to get it right. Integrate testing often. Stay engaged with all the different team, to be aware of the changes they are making to other parts of the product, so you can stay ahead of how it can impact your part. 
- Launch the product in stages with trial users to gather feedback and evaluate the value.
- It takes time for IoT value to show. As more data are collected, then it can help to improve business decision and user experience. 
