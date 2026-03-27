# Lab 1 Exercise

### 1- VM Configuration

If you using VirtualBox and going to use **your personal internet** make sure you use **'Nat Network'** to make isolate network for the server and clients

You can also use **'Host-only Adapter'** if you going to use **university internet**

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

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

### Lab Exercise :&#x20;



