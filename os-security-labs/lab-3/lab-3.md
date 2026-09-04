# Lab 3

### Opening the Local Policy Tools

1. Open Run by Win+ R or Search bar and search for Run
2. Type gpedit.msc ⇒ press Enter ⇒ Local Group Policy Editor opens.
3. Repeat the same way ⇒ type secpol.msc ⇒ press Enter ⇒ Local Security Policy opens.
4. Open Search bar ⇒ search for Event Viewer ⇒ open it.

<figure><img src="../../.gitbook/assets/image (227).png" alt=""><figcaption></figcaption></figure>

### 3. Password and Account Lockout Policies

Set the required password and lockout values.

In Local Group Policy Editor, go to **Computer Configuration ⇒ Windows Settings ⇒ Security Settings ⇒ Account Policies.**

#### 3.1 Configure Password Policy

1. Click Password Policy.
2. For each setting below, double-click it ⇒ select Define this policy setting (if shown) ⇒ enter the value ⇒ click Apply ⇒ click OK.

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top">Policy</td><td valign="top">Value</td></tr><tr><td valign="top">Enforce password history</td><td valign="top">5 passwords</td></tr><tr><td valign="top">Maximum password age</td><td valign="top">42 days</td></tr><tr><td valign="top">Minimum password length</td><td valign="top">8 characters</td></tr><tr><td valign="top">Password must meet complexity requirements</td><td valign="top">Enabled</td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/image (276).png" alt=""><figcaption></figcaption></figure>

#### 3.2 Configure Account Lockout Policy

1. Click Account Lockout Policy.
2. &#x20;Account lockout threshold ⇒ enter 3 invalid logon attempts.
3. &#x20;Account lockout duration ⇒ enter 30 minutes.
4. &#x20;Reset account lockout counter after ⇒ enter 30 minutes.

<figure><img src="../../.gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

#### 3.3 Verify the Policies

**To create a new user:**\
1\. open Search bar ⇒ search for **Computer Management**

&#x20;2\. Click **Local Users and Groups ⇒ Users ⇒ right-click an empty area ⇒ New User.**

{% hint style="info" %}
For efficiency, I recommend creating two test users. If the first account becomes locked, you can continue working with the second one.
{% endhint %}

<div><figure><img src="../../.gitbook/assets/image (290).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (307).png" alt=""><figcaption></figcaption></figure></div>

3\. Sign out of the Administrator account ⇒ sign in as LabUser ⇒ try a password shorter than 8 characters or without complexity ⇒ confirm Windows rejects it.

<div><figure><img src="../../.gitbook/assets/image (348).png" alt="New password with 7 charachers instead of 8"><figcaption><p><mark style="color:$danger;"><strong>New password with 7 charachers instead of 8</strong></mark></p></figcaption></figure> <figure><img src="../../.gitbook/assets/image (347).png" alt=""><figcaption></figcaption></figure></div>

4\. Sign out again ⇒ enter the wrong LabUser password three times ⇒ confirm that the account is locked.

<figure><img src="../../.gitbook/assets/image (349).png" alt=""><figcaption></figcaption></figure>

## 4. Local Policies: Audit, User Rights, and Security Options

Path: Computer Configuration > Windows Settings > Security Settings > Local Policies

### 4.1 Enable Account Logon Auditing

1\.     Open Audit Policy.

2\.     Double-click Audit account logon events.

3\.     Select Define these policy settings, enable Success and Failure, and click OK.

<figure><img src="../../.gitbook/assets/image (350).png" alt=""><figcaption></figcaption></figure>

### 4.2 Restrict the Shutdown Right

1. Open User Rights Assignment.
2. Double-click Shut down the system.
3. Ensure that only the approved administrative group is listed. For this lab, remove the Users group if it is present.

<figure><img src="../../.gitbook/assets/image (351).png" alt=""><figcaption></figcaption></figure>

### 4.3 Disable the Guest Account

1\.     Open Security Options.

2\.     Double-click Accounts: Guest account status, select Disabled, and click OK.

<figure><img src="../../.gitbook/assets/image (352).png" alt=""><figcaption></figcaption></figure>

### 4.4 Verify Logon Auditing

1\.     Sign out and attempt to sign in to the test account using an incorrect password.

2\.     Open **Event Viewer** and go to **Windows Logs > Security**.

3\.     Use Filter Current Log and search for Event ID 4625, which records a failed logon.

<div><figure><img src="../../.gitbook/assets/image (353).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (355).png" alt=""><figcaption></figcaption></figure></div>

## 5. Configuring Object Access Auditing

Enable object access auditing and configure the folder SACL.

### 5.1 Enable the Audit Policies

1. Open Search bar ⇒ search for secpol.msc ⇒ press Enter.
2. Click Security Settings ⇒ Local Policies ⇒ Audit Policy.
3. Double-click Audit object access ⇒ enable Success and Failure ⇒ click Apply ⇒ click OK.

<figure><img src="../../.gitbook/assets/image (357).png" alt=""><figcaption></figcaption></figure>

4. Repeat the same path ⇒ Audit logon events ⇒ check Success and Failure ⇒ click Apply ⇒ click OK.

<figure><img src="../../.gitbook/assets/image (358).png" alt=""><figcaption></figcaption></figure>

### 5.2 Create and Configure an Audited Folder

1\.     Open File Explorer ⇒ go to Local Disk (C) ⇒ create New Folder name it SecretData

2\.     Right-click SecretData ⇒ Properties ⇒ Security.

3\.     Click Advanced ⇒ Auditing ⇒ Continue if asked ⇒ Add.

4\.     Select a principal... ⇒ enter LabUser or Everyone ⇒ Check Names ⇒ OK \
⇒ Type: Failure ⇒ Show advance permissions ⇒ select Create files / write data and Delete.

<figure><img src="../../.gitbook/assets/image (359).png" alt=""><figcaption></figcaption></figure>

6. Go back to permissions Select the user ⇒ Type: Deny \
   ⇒ Show advance permissions ⇒ select Create files / write data and Delete.

<figure><img src="../../.gitbook/assets/image (366).png" alt=""><figcaption></figcaption></figure>

### 5.3 Generate and Verify Audit Events

1. Sign in as LabUser (or another account without Write/Delete permission) ⇒ open SecretData ⇒ try to modify or delete a test file

<figure><img src="../../.gitbook/assets/image (365).png" alt=""><figcaption></figcaption></figure>

2. Open Event Viewer ⇒ Windows Logs ⇒ Security ⇒ Filter Current Log... ⇒ enter 4656 and 4663 in Event IDs ⇒ click OK.

<figure><img src="../../.gitbook/assets/image (364).png" alt=""><figcaption></figcaption></figure>

## 6. Modifying User Rights Assignments

### 6.1 Create a Test User and Record the Baseline

1. Use the LabUser account created in Section 3.
2. Sign in as LabUser ⇒ click Start ⇒ Power ⇒ confirm that Shut down is available before changing the policy.

<div><figure><img src="../../.gitbook/assets/image (367).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (368).png" alt=""><figcaption></figcaption></figure></div>

### 6.2 Remove the Shutdown Right

1. Sign back in with the Administrator account ⇒ open Search bar ⇒ search for secpol.msc ⇒ press Enter.
2. Click Local Policies ⇒ User Rights Assignment.
3. Double-click Shut down the system ⇒ select Users ⇒ click Remove ⇒ Apply

<figure><img src="../../.gitbook/assets/image (369).png" alt=""><figcaption></figcaption></figure>

4. Sign out and sign in as LabUser again.\
   &#x20;If the old permissions remain, run gpupdate /force as administrator or restart the VM.
5. Confirm that LabUser can no longer shut down the computer from the normal interface

<figure><img src="../../.gitbook/assets/image (370).png" alt=""><figcaption></figcaption></figure>

### 6.3 Review Policy Change Events

1. Open Event Viewer ⇒ Windows Logs ⇒ Security ⇒ review events created at the time of the policy change.
2. Filter Current Log... ⇒ Event IDs: 4717, 4718&#x20;

<figure><img src="../../.gitbook/assets/image (371).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (372).png" alt=""><figcaption></figcaption></figure>

### 6.4 Grant Perform Volume Maintenance Tasks

1. Return to Local Security Policy ⇒ Local Policies ⇒ User Rights Assignment ⇒ double-click Perform volume maintenance tasks.
2. Add User or Group... ⇒ enter LabUser ⇒ Check Names ⇒ OK ⇒ Apply ⇒ OK. Take a screenshot, then remove LabUser after testing.

<figure><img src="../../.gitbook/assets/image (373).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="warning" %}
The “Perform volume maintenance tasks” user right allows a user to perform disk maintenance operations, such as volume defragmentation. Because this privilege may allow access beyond normal file permissions, it should only be assigned to trusted users and removed after testing.
{% endhint %}

## 7. Security Event Log Settings

Set the Security log size and overwrite behavior.

Open Search bar ⇒ search for gpedit.msc ⇒ press Enter ⇒ go to Computer Configuration ⇒ Administrative Templates ⇒ Windows Components ⇒ Event Log Service ⇒ Security.

1. Double-click Specify the maximum log file size (KB).
2. Select Enabled ⇒ enter 131072 KB (128 MB) ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (374).png" alt=""><figcaption></figcaption></figure>

3. Double-click Retain old events ⇒ select Disabled ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (375).png" alt=""><figcaption></figcaption></figure>

### 7.1 Verify the Event Log Settings

1. Open Search bar ⇒ search for Command Prompt ⇒ Run as administrator ⇒ type gpupdate /force ⇒ press Enter. Restart the VM if needed.
2. Open Event Viewer ⇒ Windows Logs ⇒ Security ⇒ right-click Security ⇒ Properties.
3. Check that Maximum log size is about 128 MB and that events are overwritten when the log is full.

## 8. Configuring Security Options

Open Search bar ⇒ search for secpol.msc ⇒ press Enter ⇒ click Local Policies ⇒ Security Options.

### 8.1 Configure an Interactive Logon Message

1. Double-click Interactive logon: Message title for users attempting to log on.
2. Enter Authorized Access Only ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (376).png" alt=""><figcaption></figcaption></figure>

3. Double-click Interactive logon: Message text for users attempting to log on.
4. Enter Your activity is monitored. This system is for business use only. ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (377).png" alt=""><figcaption></figcaption></figure>

### 8.2 Rename the Built-in Administrator Account

1\.     Double-click Accounts: Rename administrator account.

2\.     Enter SecAdmin (or another non-obvious name) ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (378).png" alt=""><figcaption></figcaption></figure>

### 8.3 Configure Cached Domain Logons

1\.     Double-click Interactive logon: Number of previous logons to cache (in case domain controller is not available).

2\.     Enter 0 ⇒ click Apply ⇒ OK.

<figure><img src="../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note: This setting affects cached domain logons, not local accounts.

This setting applies to cached domain credentials when a domain controller is unavailable; it does not disable ordinary local-account logons. A value of 0 can prevent domain users from signing in while disconnected, so evaluate availability needs before using it in production.
{% endhint %}

### 8.4 Verify the Security Options

1\.     Sign out or restart the VM.

2\.     Check that the Authorized Access Only message appears before the sign-in screen.

<figure><img src="../../.gitbook/assets/image (380).png" alt=""><figcaption></figcaption></figure>

3. Try the old Administrator username. It should not work; sign in with SecAdmin or another account.

<figure><img src="../../.gitbook/assets/image (381).png" alt=""><figcaption></figcaption></figure>

## 9. Software Restriction Policies (SRP)

Block cmd.exe with a path rule.

Open Search bar ⇒ search for gpedit.msc ⇒ press Enter ⇒ go to Computer Configuration ⇒ Windows Settings ⇒ Security Settings ⇒ Software Restriction Policies.

1. If Software Restriction Policies is empty, right-click it ⇒ New Software Restriction Policies.
2. Click Additional Rules ⇒ right-click an empty area ⇒ New Path Rule.
3. In Path, enter C:\Windows\System32\cmd.exe.
4. Set Security level to Disallowed ⇒ add a description such as Block Command Prompt ⇒ Apply

<figure><img src="../../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

### 9.1 Verify the Restriction

5. Open Search bar ⇒ search for Command Prompt ⇒ Run as administrator ⇒ type gpupdate /force ⇒ press Enter, or restart the VM.
6. Open Search bar ⇒ search for Command Prompt and try to open it. You can also press Win + R ⇒ type cmd ⇒ press Enter.
7. Confirm that Windows shows a message saying that the application was blocked by policy.

<figure><img src="../../.gitbook/assets/image (383).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Recovery: Administrator ⇒ Additional Rules ⇒ remove or change the cmd.exe rule.
{% endhint %}
