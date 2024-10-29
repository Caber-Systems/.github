![CaberLogo.png](/profile/CaberLogo.png)


# Fine-Grained Access Control on Generative AI RAG

Caber is making it easy for enterprises to build RAG-based applications with the same granularity of access control to data they store in RAG as they have on that data in Sharepoint, Confluent, Jira, and other systems.  Without these controls, companies risk violating compliance requirements as users can access knowledge from sensitive data they don't have permission to view. 

![Screen Shot](/profile/RAG_SideBySide.png)
*<p align="center">Caber ensures users are only able to retreive chunks from RAG they are allowed to see</p>*
*<p align="center">(Click to enlarge)</p>*

## Challenges Putting Permissions of RAG Data

- **Chunked Data**: Data in GenAI and RAG systems is chunked and, because of enterprise data duplication, it is common to see 60% to 90% of chunks duplicated in multiple documents that can have conflicting permissions.  
- **User Experience**: Redacting data in LLM reponses, removing or redacting information the user shouldn't see, solves a security problem at the expense of user experience. With significant chunks of data removed, users can be left looking at a response from the LLM that makes little sense.  Perceived value of the app, in the eyes of the users drop, and lead to dissatisfaction or defection to unsanctioned chat applications.
- **Service Accounts**: While the user is authenticated through the chat agent, retreival of data from the vector database is done by the chat agent's service account.  Thus the chat agent has to be tightly integrated with the authorization of user access to the data.   

## How Caber is Different:
- **Permissions Resolution**: Caber identifies chunks in RAG by tracing the chunk's lineage back to the sources it comes from.  Where there are multiple possible sources with different permissions, Caber determines which set of permissions to use by precedence, policy, or prevalence.
- **Authoriation Accross API Calls**: Traces data lineage of data gives Caber the ability to determine the user service account API calls are being made for, even across multiple hops.  
- **Granularity and User Experience**: Caber is agnostic to the authorization scheme used (RBAC, ABAC, and ReBAC..) and redacts RAG chunks the user is not allowed to see before they are sent to the LLM.  Thus, the LLM response is coherent and relevant to just the data the user has access to.
- **Observability**: When things go wrong, Caber provides deep observability for authorization failures and incidents -- including data movement leading up to the incident -- so you have the tools to fix them.

## About
Caber is backed by data and security industry veterans from Cisco, Akamai, Riverbed, Netskope, Meta, and Oracle.

Caber is Copyright 2024, Caber Systems, Inc.

Terms of use are available at https://www.caber.com/legal/terms-of-service
