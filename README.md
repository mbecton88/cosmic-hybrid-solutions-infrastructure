<img src="https://github.com/user-attachments/assets/ec17bc81-ce1e-4991-8b20-1d2a61fe985b" width="200">


# Cosmic Hybrid Solutions - Initial Server Documentation

Hey everyone! As the new Linux System Administrator at Cosmic Hybrid Solutions, a really exciting SaaS startup based in Dover, Delaware, I've been tasked with getting a handle on our initial infrastructure. We're building an innovative productivity platform for small to medium-sized businesses, and a solid foundation is key.

## The Vision for Cosmic Hybrid Solutions (Our "Why")

Cosmic Hybrid Solutions aims to revolutionize team collaboration and productivity by providing an intuitive and powerful web-based platform. We're starting lean but have big dreams of scaling and becoming the go-to solution for SMBs looking to streamline their workflows. Our initial infrastructure is focused on a core Linux server to host our application and database.

## Project Goal: Laying the Documentation Foundation

My first project is to create a comprehensive document detailing the initial configuration of this primary Linux server. This will serve as a crucial reference point as our infrastructure evolves and our team grows. Good documentation from the start will save us headaches down the line! Below is the final result. Following are the steps that I took to create this text file.

![init_config](https://github.com/user-attachments/assets/06fb0830-8024-4c3d-b84d-d105e825bdb4)



## Requirements: What I Needed to Capture

For this initial documentation, I needed to gather the following key information about the server:

* Basic system identification (hostname, kernel, OS).
* Current disk space and memory usage.
* A list of the initial user accounts and their primary/secondary group memberships.
* A list of the initial groups present on the system.

## Steps Taken: My Journey Through the Server

Here's a breakdown of the steps I took to gather this information:

1.  **Simulated Server Access:** I started by accessing the server's terminal (in my case, my local Linux environment, mimicking an SSH connection).
2.  **System Discovery:** I used the following commands to get the lay of the land:
    * `hostname`: To see the server's name.<br>
       ![hostname](https://github.com/user-attachments/assets/1d6b15a3-bdb0-4606-97ef-16c194aa264e)<br>
    * `uname -a`: For the nitty-gritty kernel details.<br>
       ![uname](https://github.com/user-attachments/assets/6d4bfb33-cd0e-4e96-bfae-384229e70199)<br>
    * `cat /etc/os-release`: To figure out which flavor of Linux we're running (it's Ubuntu Server!).<br>
       ![os-release](https://github.com/user-attachments/assets/42b97b90-aa52-4f59-8f9d-d6fc1a9e3d77)<br>
    * `df -h`: To check how much storage we've got and how it's being used.<br>
       ![df-h](https://github.com/user-attachments/assets/b433ddfb-1670-4104-89a4-ea791a4d950c)<br>
    * `free -h`: To see how our memory is looking.<br>
       ![Screenshot from 2025-05-13 11-55-55](https://github.com/user-attachments/assets/c9661cb1-155a-47d9-beee-4e4a2028996a)<br>

4.  **User Deep Dive:** I then looked into the existing user accounts using:
    * `cat /etc/passwd`: This gave me a list of all the users, their IDs, and primary groups. I noted down the initial system users, as well as the accounts I set up for our initial team:       
      `alice.smith`,`bob.jones`,`charlie.brown`, and my own.<br>
      ![passwd1](https://github.com/user-attachments/assets/f702bce7-9646-4433-aa7b-22e346e63b50)<br>
      ![passwd2](https://github.com/user-attachments/assets/980f4de1-8e42-46b8-bcd6-d2ef159fa055)<br>
    * `groups <username>`: For each of these key users, I ran the `groups` command to see any secondary groups they belong to.<br>
    * ![groupsusers](https://github.com/user-attachments/assets/346c077b-7c22-4ef3-8fd1-f88fdb59e69f)<br>

5.  **Group Exploration:** Finally, I checked out the groups on the system with:<br>
    * `cat /etc/group`: This listed all the groups and their IDs. I made sure to document the `developers`, `operations`, `support` groups, and the `sysadmins` group I added myself to.<br>
      ![group1](https://github.com/user-attachments/assets/5c1c5fe8-7182-44c1-99b2-f9bd64152152)<br>
      ![group2](https://github.com/user-attachments/assets/744297ba-2b81-4be7-b635-5c8a6bd14f68)<br>



All this information has been compiled into the `initial_server_documentation.txt` file in this repository.

## Project Summary and What I Learned

This initial documentation project was a crucial first step in understanding the foundational elements of our new Linux server at Cosmic Hybrid Solutions. Through this process, I gained practical experience in:

* **System Identification:** Utilizing commands like `hostname`, `uname -a`, and `cat /etc/os-release` to pinpoint the server's identity (`ubuntuserver`), its detailed kernel information (Linux 6.11.0-25-generic on Ubuntu 24.04.2 LTS), and the specific operating system distribution. This understanding is vital for system administration and ensuring compatibility.

* **Resource Monitoring:** Employing `df -h` to analyze disk space usage across the server's file system, allowing me to assess current storage capacity and utilization. Similarly, using `free -h` provided a clear view of the server's memory usage, including total, used, free, and available RAM, which is critical for performance monitoring.

* **User and Group Management Fundamentals:** Examining the `/etc/passwd` file provided a detailed look at the initial user accounts, including their User IDs and primary groups. By using the `groups <username>` command for key team members (`alice.smith`, `bob.jones`, `charlie.brown`, and myself), I identified their secondary group memberships, which directly influence access control and permissions within the system. This exercise highlighted how different roles within Cosmic Hybrid Solutions can be mapped to specific user accounts and group affiliations.

* **Group Identification:** Reviewing the `/etc/group` file allowed me to identify the initial groups configured on the server, such as `developers`, `operations`, `support` (created for our teams), and fundamental system groups like `sudo`. Documenting their Group IDs is essential for understanding the underlying permission structure of the Linux environment.

Furthermore, this project underscored the fundamental importance of **proactive and detailed documentation** from the very beginning of our infrastructure setup. Creating both a user-friendly `README.md` overview and a more detailed `initial_server_documentation.txt` file establishes a valuable baseline for future growth, troubleshooting, and team onboarding at Cosmic Hybrid Solutions. This documentation will serve as a key reference point as our platform evolves.
