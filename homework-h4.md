# h4 Johnny Tables

## Broken Access Control
Broken Access Control is a security vulnerability that occurs when an application improperly enforces restrictions on user actions. It results to allowing unauthorized access to sensitive data or functions.
Hackers can take advantage of this to see, change or delete data. Furthermore, they can even act as admins without permission sometimes. 

### Vulnerabilites
* Violating the principle of least privilege or failing to deny access by default. These mistakes lead to the provision of access to unauthorized users
* Bypassing access controls by modifying URLs, internal application states, or HTML pages
* Allowing unauthorized viewing or editing of another user's account by manipulating unique identifiers
* Missing access controls for critical API Call methods (POST, PUT, DELETE)
* Privilege escalation, such as acting as a user without logging in or as an admin when logged in as a regular user
* Manipulation of metadata such as tampering with JSON Web Tokens (JWTs), cookies or hidden fields to elevate privileges
* Misconfiguring Cross-Origin Resource Sharing (CORS), allowing API access from unauthorized origins
* Forcefully browsing to authenticated or privileged pages without proper authorization

### Prevention
To stop it, apps should block access by default and make sure permissions are checked properly. There are also other ways to achieve that:
* Deny access by default if it is not for public resources
* Implement access control mechanisms centrally and use them throughout the application to minimize CORS usage
* Enforce record ownership in access controls to prevent unauthorized data manipulation
* Apply unique business limit requirements through the domain models
* Disable web server directory listings and ensure sensitive files are not within web roots
* Log access control failures and alert administrators when appropriate with monitoring tools
* Rate-limit API and controller access to reduce the impact of automated attacks
* Invalidate stateful session identifiers on the server after logout
* Use short-lived JWT tokens to minimize the windows of opportunity for attackers

### Example attack scenarios
#### Privilege Escalation via Role Manipulation
##### Scenario 1
A regular user intercepts a request and modifies their role from "user" to "admin" in a poorly protected application:
```json
{
   "username": "john_doe",
   "role": "admin"
}
```
If the system accepts this change the user gains admin privileges without authorization.

##### Scenario 2
A user changes the userID parameter in an API request to access another user's data:
```bash
GET /api/user/1234/profile
```
Changing 1234 to 5678 allows unauthorized access to another user’s profile if proper access controls aren’t enforced.

##### Scenario 3 
An application uses unverified data in a SQL query to access account information. An attacker modifies the 'acct' parameter in the browser to access another user's account:
```
https://example.com/app/accountInfo?acct=notmyacct
```

##### Scenario 4
An attacker forcefully browses to URLs requiring administrative rights:
```
https://example.com/app/getappInfo
```
```
https://example.com/app/admin_getappInfo
```
If a non-admin user can access the admin page, it's a security flaw.
