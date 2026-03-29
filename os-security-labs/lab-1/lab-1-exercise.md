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

before we start you should cheack if the two machine are in same network and have connecation:&#x20;

write command such as ip a or ifconfig to know the ip address for each machine and use ping from one of them to see if they can reach each other: <br>

<figure><img src="../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

1- Send a flag between two machines using Netcat :&#x20;

open kali Linux and click on the kali icon and search for wireshark

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

Chose eth0 and press Enter

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Now go back and open terminal in the other machine and run:

`netcat -l -p 8000 -u -v`

> &#x20;This command creates a listening connection on port 8000.

Then open terminal in the Kali machine and run:

`netcat <ip address> 8000 -u`

> Now any message typed in the second machine will appear in the first machine.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

as you can see here Whireshark catch the messages

<figure><img src="../../.gitbook/assets/image (30).png" alt="" width="563"><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>



