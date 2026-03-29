# Creating Users & Groups in Active Directory

This section covers the creation of user accounts and security groups in Active Directory.

Users are created with different roles and permissions, then organised into groups to simplify access management. Instead of assigning permissions to individual users, permissions are assigned to groups, and users inherit access based on group membership.\
\
for this this lab my admin account will be `Luffy` and my individual account will be `Gojo` .

## 1- Creating Users

Open Server Manager Dashboard click on **tools** ⇒ **Active Directory Users and Computers**&#x20;

<figure><img src="../../.gitbook/assets/image (144).png" alt=""><figcaption></figcaption></figure>

&#x20;Then click right on Users ⇒ New ⇒ User

<figure><img src="../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

Chose a name and user name and set password and write it store it somewhere

<div><figure><img src="../../.gitbook/assets/image (134).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure></div>

We need to create another user with the option “User must change password at next logon”.

<div><figure><img src="../../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (138).png" alt=""><figcaption></figcaption></figure></div>

### Testing Login After Creating Users

Click on “Log in with another account” and ensure that the domain is specified.\
If it is not displayed, manually enter it using the following format:

DomainName\Username

<div><figure><img src="../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure></div>

### 2- Creating Groups

&#x20;Right on Users ⇒ New ⇒ Group

<div><figure><img src="../../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure></div>

### adding members in the Group

you have 2 way to add member in group:

first way:\
&#x20; Double click on the group ⇒ Members ⇒ Add&#x20;

<div><figure><img src="../../.gitbook/assets/image (22) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure></div>

Write the user name then click on "Check Names"<br>

<div><figure><img src="../../.gitbook/assets/image (23) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (24) (1).png" alt=""><figcaption></figcaption></figure></div>

Second way : \
\
&#x20;Double click on your user ⇒ Members of ⇒ Add&#x20;

&#x20; Enter the group name then click on "Check Names"<br>

<div><figure><img src="../../.gitbook/assets/image (25) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (26) (1).png" alt=""><figcaption></figcaption></figure></div>



### In addition your admin account should be member of these groups

\
Administrators\
Domain Admins\
Domain Users\
Schema Admins

<div align="left"><figure><img src="../../.gitbook/assets/image (146).png" alt=""><figcaption></figcaption></figure></div>
