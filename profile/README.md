![CaberLogo.png](/profile/CaberLogo.png)


# AI Data Governance with Unprecedented Visibility and Control

Caber provides enterprises with unprecedented visibility and deterministic control over data use in AI applications, establishing predictable boundaries and audit trails to govern autonomous and inherently unpredictable AI agent actions. Unlike existing tools that rely on error-prone pattern-matching and similarity-based classification, Caber accurately identifies data by analyzing the sequences of ones and zeros it contains. By tracing the lineage of these sequences from their sources, through API calls on the network, and across business logic, Caber equips data and application owners with actionable intelligence to optimize performance, protect business-critical data, and ensure compliance.

![Screen Shot](/profile/Apple_RAG_for_Website.png)
*<p align="center">Caber ensures users can only access data they are allowed to see</p>*
*<p align="center">(Click to enlarge)</p>*

## Challenges Governing AI Data

- **Duplication of Data**: Data consumed in GenAI applications is often chunked and, because of enterprise data duplication, it is common to see 60% to 90% of chunks duplicated in multiple documents that can have conflicting permissions.  
- **User Experience**: Redacting data in LLM reponses, removing or redacting information the user shouldn't see, solves a security problem at the expense of user experience. With significant chunks of data removed, users can be left looking at a response from the LLM that makes little sense.  Perceived value of the app, in the eyes of the users drop, and lead to dissatisfaction or defection to unsanctioned chat applications.
- **Service Accounts**: While the user is authenticated through the chat agent, retreival of data from the vector database is done by the chat agent's service account.  Working around this by spoofing user credentials can lead to serious security problems.   

## How Caber is Different:
- **Permissions Resolution**: Caber identifies data in AI apps by tracing the data's lineage back to the sources it comes from.  Where there are multiple possible sources with different permissions, Caber determines which set of permissions to use by precedence, policy, or prevalence.
- **Authoriation Accross API Calls**: Tracing data lineage also gives Caber the ability to determine the user that service account API calls are being made on behalf of, even across multiple hops.  
- **Granularity and User Experience**: Caber is agnostic to the authorization scheme used (RBAC, ABAC, and ReBAC..) and redacts RAG chunks the user is not allowed to see before they are sent to the LLM.  Thus, the LLM response is coherent and relevant to just the data the user has access to.
- **Observability**: When things go wrong, Caber provides deep observability for authorization failures and incidents -- including data movement leading up to the incident -- so you have the tools to fix them.

**<p align="center">Get in touch with us now to get control of your AI data: dev@caber.com</p>**

Terms of use are available at https://www.caber.com/legal/terms-of-service

Copyright 2024, Caber Systems, Inc.
