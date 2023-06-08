# What is auth0 and oath2.0

Auth0 is an authentication and authorization platform that provides services to secure their applications. It simplifies the process of adding authentication and authorization to applications.
With Auth0, you don’t need to build authentication infrastructure yourself.  You can quickly integrate Auth0 into applications. 
OAuth 2.0 is an open protocol that enables secure authorization and access to protected resources. It is used by developers and companies to allow users to grant access to their data without sharing their information, like passwords with third-party applications.
In my individual project I use auth0 for my authentication and then auth2.0 to secure the credentials.

- when using oauth2.0 there are 4 actors involved:
 - Resources are protected data that require OAuth to access them.
 - Resource Owner: Owns the data in the resource server. An entity capable of granting access to protected data. For example, a user Google Drive account.
 - Resource Server: The API which stores the data (Google Drive.)
 - Client: It is a third-party application that wants to access your data


The flow of oauth2.0
1.	The resource owner wants to make a change to his photo you go to your application, tell the application that the photo is google drive (resource owner).

2.	The application sends a request to the authorization server to access the photo. The oath2.0server asks the user to grant permissions.
3.	Once the user allows third-party access and logs into the website using any log in method, the authorization server sends a short-lived authorization code to the application.
4.	application exchange auth codes for access tokens, which define the duration and what kind of access.
5.	The Authorization Server validates the access token, and the application fetches the image that the user wants to edit from their Google Drive account.

![oath2 0](https://github.com/ArthurBrouwersSemester3/Documentation/assets/95029345/59971466-4658-4abc-a9ad-c835ae74d279)

