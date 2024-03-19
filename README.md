![CaberLogo.png](images/CaberLogo.png)


# Welcome to Caber Systems!

Caber is addressing the toughest question in web application and API security: _How do we get rid of false positive alerts?_

Security tools today generate a lot of alerts, and most of them are false positives[^1]. True incidents of data breaches, such as those described in the OWASP Web Application Top10[^2] and API Security Top10[^3], are burried under thousands of these false positives and go unnoticed. 

Caber has drawn from scalable technologies across multiple disciplines to rearchitect indicent detection and analysis in a way that makes false positives as rare as a hash collision. 

![cytoscape_1200_800.png](images/cytoscape_1200_800.png)

## How it Works

False positives are a result of the probabalistic approach taken by today's security tools that hunt for Indicators of Compromise (IoC) and Indicators of Attack (IoA), and authorize access to data-in-transit and data-in-use based upon API header and request parameters rather than on permissions associated with the data itself.

Caber's Continuous Authorization and Continuous Observability platform, Caber CA/CO for short, is based on deterministic detection of incidents using an authorization-centric architecture that targets the most common vulnerabilities in modern cloud-based applications.

Caber CA/CO traces bytes sequences in API payloads like packages on delivery trucks, and connect them through API call graphs to their original objects and permissions.  

By combining these call-graphs Caber CA/CO builds a model application behavior that fuels AI-backed analysis of each incident and generation of remediation options such as policy updates, resource tagging, and configuration changes.

## Key Features:
- **Continuous Authorization & Observation**: Scalably track and authorize API payload access, using existing metadata and permissions
- **Incident Detection and Analysis**: Get an exact call graph for each incident, showing the path bytes took through the application with full detiails of the API calls and their parameters.
- **AI Incident Analysis and Policy Generation**: Combining calls graphs with AI, Caber CA/CO can generate policy updates, resource tagging, and configuration changes to remediate incidents.
- **Scalable Automated Deployment**: Caber deploys automatically into your AWS account and requires no agents or code changes. Only two observation points in the application, log ingest and a gateway plug-in, are required for it to work. 


## Demo Caber CA/CO
A self-service live demo of Caber CA/CO is available at https://caber.com.

You can also see video walkthrough of the demo at https://vimeo.com/923537694?share=copy


---
[^1]: [The False Positive Problem in Cybersecurity, CSO Online](https://www.csoonline.com/article/3513898/the-false-positive-problem-in-cybersecurity.html)

[^2]: [OWASP Top 10 - 2021](https://owasp.org/www-project-top-ten/)

[^3]: [OWASP API Security Top 10 - 2023](https://owasp.org/API-Security/editions/2023/en/0x00-header/)
