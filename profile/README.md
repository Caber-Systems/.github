![CaberLogo.png](/profile/CaberLogo.png)


# Caber CA/CO 
**Continuous Authorization and Continuous Observability**

Caber is addressing one of the most important questions in web application and API security: 

*<p align="center">How can we find the scary exploits happening inside modern applications<br>without having to sift through a fog of false positive alerts?</p>*

Security tools today are based on __probabalistic__ detection.  They alert on anomalies and potential threats, yet most of these are false alarms[^1]. True incidents of data breaches, such as those described in the OWASP Web Application Top10[^2] and API Security Top10[^3], are burried under thousands of these false positives and go unnoticed or even undetected. 

Caber complements today's security tools by making incident detection __deterministic__ rather than probabalistic.  Using permissions and policies that already exist on protected data, Caber looks at the bytes in egress and internal API payloads inside cloud applications to detect unauthorized use of that data.  As a result, the true/false detection ratio is flipped: true incident detections outweigh false detections by orders of magnitude.

Caber then uses AI to analyze the data collected across the APIs in the application to show the sequence of events leading up to an authorization failure, and generate options to remediate it.  

![Screen Shot](/profile/cytoscape_1280_900.png)

## How it Works

False positives are a result of the probabalistic approach taken by today's security tools.  They hunt for anomalies when change is constant in modern cloud apps due to CI/CD.  Every new API is a new risk regardless of the data it may carry.  Policies that authorize access to data-in-transit and data-in-use are based upon API header and request parameters rather than on permissions associated with the data itself.  Because of growing application complexity, correlation between an anomaly, an API, or request paramters and true incidents where data confidentiality is compromised, is dwindling[^4].

Caber's Continuous Authorization and Continuous Observability platform, Caber CA/CO for short, is based on deterministic detection of incidents using an authorization-centric architecture that targets the most common vulnerabilities in modern cloud-based applications.

Using scalable technologies, Caber CA/CO tracks byte sequences in API payloads, similar to how delivery companies simultanneously track every package from sender to receiver.  From the data collected in this process, Caber CA/CO build API call graphs of how byte sequences move, like the path each package would take, and connect them to their source objects and permissions.  

By combining these call-graphs, Caber CA/CO builds a model of application behavior that fuels AI-backed analysis of each incident and generation of remediation options such as policy updates, resource tagging, and configuration changes.  This analysis is based on well-known black-box testing techniques[^5] and completes in minutes, versus today's Mean Time To Identify (MTTI) an incident of almost 7 months[^6].  The analysis:
1. Does not impact, or rely on information from, development engineers since it is independent of the code making up each service or API 
2. Is effective for large and complex applications
3. Provides an application-wide model of how data is moved in APIs and affected by each service 

## Why This is So Important

Because the microservices are built in isolation[^7], developers have intimate knowledge of, and are responsible for, only the individual services making up the complete application.  The application-wide model Caber CA/CO builds represents how all of these services interract _functionally_ from the perspective of the actual bytes moving between them.  

The importance if this is evident when you consider that, incidents related to interractions between services fall outside the normal responsibilities of the development teams.  Hence it's security engineers that must essentially debug the application to understand how these incidents happened.  

Consider the utility a software debugging tool that cannot show the values of the variables passed in each function call, versus one that can.  Which would win?If you are a software engineer, the answer is obvious.  This is not to say network-oriented tools, or observability tools like those related to OpenTelemetry, that are analogous to that first choice, are not valuable.  However, for the express purpose of debugging an incident, they are no substitute for a tool that can show the actual bytes being passed between functions.  That's the utility Caber's approach brings to incident analysis.

## Key Features:
- **Authorize with Existing Permission**: Scalably track and authorize API payload access, using existing metadata and permissions in object stores, databases, and streaming sources.
- **Incident Identification**: Get an exact call graph for each incident, showing the path bytes took through the application with full detiails of the API calls and their parameters.
- **AI Analysis and Policy Generation**: Combining calls graphs with AI, Caber models application behavior giving it the abiity to pinpoint vulnerabilities, generate configuration updates, and policy changes that can be used to remediate incidents on existing controls.
- **Scalable Automated Deployment**: Caber deploys automatically into your AWS account and requires no agents or code changes. Only two observation points in the application, log ingest and an API gateway plug-in, are required for it to work. 


## Demo Caber CA/CO
A self-service live demo of Caber CA/CO is available. Go to https://caber.com and click 'Try Demo' at the top.

You can also see video walkthrough of the demo at https://vimeo.com/923537694?share=copy

## Questions and Support
We've set up GitHub disccusions for reporting issues and to answer your questions.  We welcome your thoughts and feedback on what we are building.  

To add a comment or ask a question, please head to https://github.com/orgs/Caber-Systems/discussions 

## Status

The core functionality of Caber CA/CO is complete.  However, the repo remains closed as we are still working on configuration, integrations, and reporting functionality.  

Caber CA/CO is Copyright 2023, Caber Systems, Inc.

Terms of use are available at https://www.caber.com/legal/terms-of-service

---
[^1]: [The False Positive Problem in Cybersecurity, CSO Online](https://www.csoonline.com/article/3513898/the-false-positive-problem-in-cybersecurity.html)

[^2]: [OWASP Top 10 - 2021](https://owasp.org/www-project-top-ten/)

[^3]: [OWASP API Security Top 10 - 2023](https://owasp.org/API-Security/editions/2023/en/0x00-header/)

[^4]: [Why API Attacks are Increasing and How to Avoid Them, CSO Online](https://www.csoonline.com/article/646557/why-api-attacks-are-increasing-and-how-to-avoid-them.html)

[^5]: [Black Box Testing: An In-Depth Tutorial With Examples And Techniques](https://www.softwaretestinghelp.com/black-box-testing/)

[^6]: [Cost of a Data Breach Report 2023, IBM](https://www.ibm.com/reports/data-breach)

[^7]: [Microservices and Isolation](https://www.westerndevs.com/_/Microservices-and-isolation/)
