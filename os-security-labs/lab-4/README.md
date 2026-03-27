# Lab 4

This Lab about setup Windows server and Domain Controller and Install Active Directory

### **Requirements :**&#x20;

**1- VirtualBox Or VMware**

**2-** [**Windows Server 2012 or Newest**](pre-installation-preparation.md#id-1-windows-server-2012-and-product-keys)



### Configuring the Virtual Machine Network:

<details>

<summary>How to create Nat Network in VirtualBox: </summary>

<div align="left"><figure><img src="../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure></div>

You can change the Nat Network settings if you want

<figure><img src="../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

</details>

<details>

<summary>How to create Nat Network in VMware:</summary>

After open the VMware press Edit then "Virtal Network Editor"

<figure><img src="../../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

<div><figure><img src="../../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure></div>

You can chose any Network number you want put only one can be the Nat

<figure><img src="../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

Select Nat then edit the "Subnet IP" and "Subnet mask"

<figure><img src="../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

then go to Nat Settings and edit the Gateway IP to Fit your Subnet IP

<figure><img src="../../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

Then press Apply ✅

{% hint style="info" %}
note: the same way if you going to create it for Host-only
{% endhint %}

After Finishing go to your VM and enter **"Edit virtual machine settings"**

<figure><img src="../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

Then go to Network Adapter -> Select Custom and choose the same network number you configured

<figure><img src="../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>



</details>

