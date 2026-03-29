# Connection Configuration & Domain Joining

Before starting, **make sure that both the server and the client are using the same network settings.** For example, if you choose NAT Network as shown in the previous lab, you should also configure the client to use the same NAT Network.

[**\[How to** Configuration a Nat Network?\]](../lab-4/#configuring-the-virtual-network)



### 1- Server Network Configuration

first you need to change the IP in the Server machine for automatically to static by going to&#x20;

control panel ⇒ View network status and tasks ⇒ Ethernet ⇒ Properties\
&#x20;⇒ Internet Protocol Version 4 (TCP/ IPv4) ⇒ Use the following IP address:



<div><figure><img src="../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure></div>

\
Open PowerShell or Command Prompt (CMD), then run the command **ipconfig** to display your IP information. After that, manually copy the IP address, Subnet Mask, and Default Gateway into the IPv4 settings.

<figure><img src="../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

**Make sure to set the DNS server to the same IP address as the server’s IPv4 address.**

{% hint style="info" %}
**Note**: According to the instructor’s instructions, the Default Gateway field on the server is intentionally left blank because the server is used as the primary gateway within the lab environment. Therefore, the client machines are configured with the Server IP address as both the Default Gateway and DNS server as part of the lab network setup.
{% endhint %}

### 2- Client Network Configuration and Domain Joining:&#x20;

<details>

<summary>Windows 10</summary>

#### 1- Network Configuration:

open search then search for "View network connections" ⇒ Click on Ethernet ⇒ Properties&#x20;

⇒ Internet Protocol Version 4 (TCP/IPv4) ⇒ Use the following IP address:

<div><figure><img src="../../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure></div>

**Search for Command Prompt (CMD) in the search bar, open it, and type `ipconfig`. Then, use the same IP information shown there to configure your network settings.**

<figure><img src="../../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note: don't forget that DNS server = your server IP address
{% endhint %}

**To make sure everything is working properly, in Command Prompt (CMD) use the `ping` command the to ping your server and check whether the connection is successful or not**

<figure><img src="../../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

#### 2- Joining the Domain:&#x20;

Open Search bar then search for **This Pc** ⇒ **Properties** ⇒ **Rename this Pc** ⇒ **Change**

<div><figure><img src="../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure></div>

Then, enter the same domain name that you configured on the server and press **OK**

<div><figure><img src="../../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure></div>

When prompted, provide the **server Administrator username** and password to allow the client machine to join the domain.

<figure><img src="../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

<div><figure><img src="../../.gitbook/assets/image (119).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure></div>

After success you should reboot the machine

</details>

<details>

<summary>Windows XP</summary>

#### 1- Network Configuration:

open start menu then go to Control Panel ⇒ Network and Internet Connection&#x20;

⇒ Network Connection ⇒ click on Local Area Connection and go to Properties&#x20;

⇒ Internet Protocol (TCP/IP) ⇒ Use the following IP address:

<div><figure><img src="../../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure></div>

<div><figure><img src="../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (98).png" alt=""><figcaption></figcaption></figure></div>

**Sometimes Windows XP cannot obtain an IP address automatically. In this case, set the IP address manually. Choose an address within your network range and make sure it is not assigned to another device.**

<figure><img src="../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note: don't forget that DNS server = your server IP address
{% endhint %}

**To make sure everything is working properly, open Command Prompt (CMD) and run the `ipconfig` command. Then, use the `ping` command to ping your server and check whether the connection is successful.**

<div><figure><img src="../../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure></div>

#### 2- Joining the Domain:&#x20;

Open start menu then right click on My Computer ⇒ Properties ⇒ Computer Name

<div><figure><img src="../../.gitbook/assets/image (104).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (105).png" alt=""><figcaption></figcaption></figure></div>

Then, enter the same domain name that you configured on the server and press **OK**

<div><figure><img src="../../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (108).png" alt=""><figcaption></figcaption></figure></div>



When prompted, provide the **server Administrator username** and password to allow the client machine to join the domain.

<figure><img src="../../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

then you should reboot the machine

</details>

<details>

<summary>Windows 7</summary>

#### 1- Network Configuration:

open start menu and search for "Network and Sharing Centre" ⇒ Click Local Area Connection ⇒ Properties ⇒ Internet Protocol Version 4 (TCP/IPv4) ⇒ Use the following IP address:



<div><figure><img src="../../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure></div>

<div><figure><img src="../../.gitbook/assets/image (123).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure></div>

**Search for Command Prompt (CMD) in the search bar, open it, and type `ipconfig`. Then, use the same IP information shown there to configure your network settings.**

{% hint style="info" %}
Note: don't forget that DNS server = your server IP address
{% endhint %}

If the your Ethernet adapter empty like this: you should do as we do In Windows XP and put an IP address from your own but make sure that the IP not taken by other Machine&#x20;

<figure><img src="../../.gitbook/assets/image (124).png" alt=""><figcaption></figcaption></figure>

**To make sure everything is working properly, open Command Prompt (CMD) and run the `ipconfig` command. Then, use the `ping` command to ping your server and check whether the connection is successful.**

<figure><img src="../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

**2- Joining the Domain:**\
Open the search bar and search for **Computer**. Then go to **Properties → Change settings** ⇒Change and write the domain name.

<div><figure><img src="../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure></div>

Then, enter the same domain name that you configured on the server and press **OK**

<div><figure><img src="../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure></div>



When prompted, provide the **server Administrator username** and password to allow the client machine to join the domain.

<div><figure><img src="../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure></div>

After success you should reboot the machine

</details>

### 3- Verification on the Server

After joining the domain with client go back to server and open Server Manager Dashboard click on **tools** ⇒ **Active Directory Users and Computers**

<figure><img src="../../.gitbook/assets/image (27) (1).png" alt=""><figcaption></figcaption></figure>

**Open the domain folder, then select&#x20;**_**Computers**_**. You should see the names of the devices that are joined to the domain.**

<figure><img src="../../.gitbook/assets/image (28) (1).png" alt=""><figcaption></figcaption></figure>

