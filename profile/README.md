![CaberLogo.png](/profile/CaberLogo.png)


# Fine-Grained Data Security for Generative AI 

Caber is delivering a radically new architecture for ensuring enterprise data used with RAG is delivered only to users authorized to received it.  Caber uses existing enterprise permissions on data.

![Screen Shot](/profile/RAG_SideBySide.png)
*<p align="center">Authorization failure incident and associated API call-graph in Caber</p>*

## Generative AI Security Challenges

- **Chunked Data**: Data in GenAI and RAG systems is chunked and, because of enterprise data duplication, it is common to see 60% to 90% of chunks duplicated in multiple documents that can have conflicting permissions.
- **Per-Customer Policies**: Individual customer mandates on how their data may be used with AI make compliance-oriented classifications (PII, PHI, etc.) overly-broad for securing GenAI use cases.
- **Lack of Visibility**: Frameworks like LangChain for building GenAI apps pull data from many sources on-demand but lack the ability to show the source, ownership, or permissions that belong to that data.
- **Scalable Automated Deployment**: Caber deploys automatically into your AWS account and requires no agents or code changes. Only two observation points in the application, log ingest and an API gateway plug-in, are required for it to work. 

## How Caber is Different:
- **Deterministic Authorization**: Caber identifies data by tracing its lineage back to the sources it comes from.  Where there are multiple possible sources with different permissions, Caber determines which set of permissions to use by precedence, policy, or prevalence.
- **Fine-Grained Control**: Caber is agnostic to the authorization scheme used.  RBAC, ABAC, and ReBAC are supported.
- **Byte-level Data Tracing**: Trace the individual API calls that move data bytes from source to your AI systems to determine where and how data security incidents occurred.
- **Remediation Options**: Get application aware remediation options that account for non-incident data flows to avoid application breakage.

## See Caber in Action - No email or Sign-up needed
Caber is using [Haggle](https://www.gohaggle.io/buyer) to anonymously provide live answers to your questions and show you how Caber works.  Register your interest and get your questions answered by clicking [https://app.gohaggle.io/pitch/?domain=https://caber.com]()

## About
Caber is backed by data and security industry veterans from Cisco, Akamai, Riverbed, Netskope, Meta, and Oracle.

Caber is Copyright 2024, Caber Systems, Inc.

Terms of use are available at https://www.caber.com/legal/terms-of-service
