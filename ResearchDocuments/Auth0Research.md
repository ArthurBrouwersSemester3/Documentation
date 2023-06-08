## Research Document: Auth0 and OAuth 2.0
![oath2 0](https://github.com/ArthurBrouwersSemester3/Documentation/assets/95029345/59971466-4658-4abc-a9ad-c835ae74d279)
### Definition
Auth0 is an authentication and authorization platform that simplifies the process of adding authentication to applications. OAuth 2.0 is an open protocol that enables secure authorization and access to protected resources.

### Overview
In our individual project, we utilize Auth0 for authentication and OAuth 2.0 for securing user credentials and accessing resources. Let's explore the concepts of Auth0 and OAuth 2.0 and their roles in software development.

### Description
**Auth0**: Auth0 is an authentication and authorization platform that provides pre-built solutions for securing applications. By integrating Auth0, developers can save time and effort in building authentication infrastructure. It enhances security and user experience in applications.

**OAuth 2.0**: OAuth 2.0 is an open protocol used by developers and organizations to enable secure authorization and access to protected resources. It allows users to grant access to their data without sharing sensitive information, such as passwords, with third-party applications.

### Roles in OAuth 2.0
OAuth 2.0 involves four key actors:
1. **Resource**: The protected data that requires OAuth 2.0 for access. For example, user files stored in a resource server like Google Drive.
2. **Resource Owner**: The entity that owns the data in the resource server and can grant access to it. In our case, the user who owns a Google Drive account.
3. **Resource Server**: The API that stores the protected data and serves it to authorized clients. In our example, Google Drive acts as the resource server.
4. **Client**: A third-party application that wants to access the protected resources on behalf of the resource owner. The client interacts with the authorization server to obtain permissions for accessing the resources.

### Flow of OAuth 2.0
The OAuth 2.0 flow consists of the following steps:
1. **Resource Owner Authorization**: The resource owner initiates the process by accessing the client application and specifying the location of the desired resource.
2. **Authorization Request**: The client application sends a request to the authorization server, requesting access to the resource. The authorization server prompts the user to grant permissions.
3. **Authorization Code Exchange**: Upon granting permission and logging in, the authorization server generates a short-lived authorization code and sends it to the client application.
4. **Access Token Acquisition**: The client application exchanges the authorization code for an access token that defines the duration and scope of access granted.
5. **Resource Access**: With the access token, the client application can access the requested resource from the resource server and perform authorized operations.

### Conclusion
By utilizing Auth0 and OAuth 2.0 in our project, we ensure secure authentication and authorization processes. Auth0 simplifies the implementation of authentication mechanisms, while OAuth 2.0 enables secure access to protected resources. This approach enhances the software development process and reinforces security measures in our project.

