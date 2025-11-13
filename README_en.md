# Homework for the Lesson “Network Technologies, Key Devices”

## Task: “Getting Started with Wireshark”

<details>
<summary>Preliminary Steps</summary>

Use a virtual machine with Kali Linux and the files mentioned in the previous section. If the Kali Linux VM does not start, you will need to install [Wireshark from the official website](https://www.wireshark.org/download.html) and use the corresponding executable files from the [assets](assets) directory.

#### Execution

1. Open the virtual machine and type `wireshark` into the search bar:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/01.png)

2. You will be asked to enter your user password for confirmation (`kali` if you downloaded the OVA from the official website):

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/02.png) (`kali` if you downloaded the OVA from the official website).

3. In the opened window, select the interface `Loopback: lo`:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/03.png)

4. Save the following files to any directory (e.g., `Downloads`):
   - `server-x64.bin`
   - `text-x64.bin`
   - `task-x64.bin`

5. Open a terminal in this directory.

6. In the first tab, grant execution rights: `chmod +x *.bin`.

7. Start the server in the first tab: `./server-x64.bin`.

8. Start the test client in the second tab to send a message: `./text-x64.bin "Hello, World"` (the server must remain running).

9. In Wireshark, you should see the captured packets:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/08.png)

10. Right-click the first line and select the options shown in the instructions:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/09.png)

11. You will see the interaction between the client and server in ASCII:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/10.png)

12. Start the target client in the second tab: `./task-x64.bin`.

Analyze the network interaction of the target client with the server. The client must send a SHA-256 hash as a message. Use precomputed hash tables such as [crackstation.net](https://crackstation.net) or, if necessary, [hashes.com](https://hashes.com) to identify the hashed message.

</details>

## Solution

<details>
<summary>Details of Capturing the Text Message</summary>

1. Preparing the files.

2. Starting the server.

3. Sending a request to the server.

4. Viewing packets in Wireshark.

5. Intercepted text message.

6. Intercepted message from `task-x64.bin`.

The issue encountered: a proper SHA-256 hash must be 64 hexadecimal characters, but the captured one was only 63 characters long.

It is possible to extract the hash in ASCII format and convert it to readable text.

CrackStation confirms the hash type as SHA-256. The hashed word is **"IPv6"**.

Verification: the hash matches.

</details>

