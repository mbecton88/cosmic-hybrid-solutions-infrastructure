# Cosmic Hybrid Solutions - Initial Server Documentation

Hey everyone! As the new Linux System Administrator at Cosmic Hybrid Solutions, a really exciting SaaS startup based in Dover, Delaware, I've been tasked with getting a handle on our initial infrastructure. We're building an innovative productivity platform for small to medium-sized businesses, and a solid foundation is key.

## The Vision for Cosmic Hybrid Solutions (Our "Why")

Cosmic Hybrid Solutions aims to revolutionize team collaboration and productivity by providing an intuitive and powerful web-based platform. We're starting lean but have big dreams of scaling and becoming the go-to solution for SMBs looking to streamline their workflows. Our initial infrastructure is focused on a core Linux server to host our application and database.

## Project Goal: Laying the Documentation Foundation

My first project is to create a comprehensive document detailing the initial configuration of this primary Linux server. This will serve as a crucial reference point as our infrastructure evolves and our team grows. Good documentation from the start will save us headaches down the line!

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
    * `hostname`: To see the server's name.
    * `uname -a`: For the nitty-gritty kernel details.
    * `lsb_release -a` (if available) / `cat /etc/os-release`: To figure out which flavor of Linux we're running (it's Ubuntu Server!).
    * `df -h`: To check how much storage we've got and how it's being used.
    * `free -h`: To see how our memory is looking.
    * *(Screenshot of `hostname` output)*
    * *(Screenshot of `uname -a` output)*
    * *(Screenshot of OS release info)*
    * *(Screenshot of `df -h` output)*
    * *(Screenshot of `free -h` output)*
3.  **User Deep Dive:** I then looked into the existing user accounts using:
    * `cat /etc/passwd`: This gave me a list of all the users, their IDs, and primary groups. I noted down the initial system users, as well as the accounts I set up for our initial team: `alice.smith`, `bob.jones`, `charlie.brown`, and my own.
    * `groups <username>`: For each of these key users, I ran the `groups` command to see any secondary groups they belong to.
    * *(Screenshot of a relevant section of `/etc/passwd`)*
    * *(Screenshot of `groups alice.smith` output)*
    * *(Screenshot of `groups bob.jones` output)*
    * *(Screenshot of `groups charlie.brown` output)*
    * *(Screenshot of `groups my_username` output)*
4.  **Group Exploration:** Finally, I checked out the groups on the system with:
    * `cat /etc/group`: This listed all the groups and their IDs. I made sure to document the `developers`, `operations`, `support` groups, and the `sysadmins` group I added myself to.
    * *(Screenshot of a relevant section of `/etc/group`)*

All this information has been compiled into the `initial_server_documentation.txt` file in this repository.

## Project Summary and What I Learned

This initial documentation project was a great way to get my hands dirty and understand the very basics of our new Linux server at Cosmic Hybrid Solutions. I learned (or reinforced):
# cosmic-hybrid-solutions-infrastructure
Initial infrastructure documentation for Cosmic Hybrid Solutions
