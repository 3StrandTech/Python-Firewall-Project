<h1> Python Firewall Project </h1> 

<h2> Project Overview </h2>

A Python program meant to illustrate the mechanical function of a firewall. The program was run in Visual Studio Code (Microsoft) on an Ubuntu virtual machine running on Oracle VirtualBox. 

<h2> Project Objective </h2>

Use Python coding and logic to replicate an IP network environment where a firewall evaluates an IP address that is attempting to connect. Random IP addresses are generated by the code and then the program checks the IP addresses in a dictionary (properly called a "blacklist" in the cybersecurity world) and if the generated IP address matches a listing in the dictionary then the firewall will block the IP address. If the IP address doesn't match a listing in the dictionary, then the firewall will allow the connection. The firewall decision will print to the console. 

Before fully presenting the code, here is the entire program in totality. I will break down each component of the code in small segments thereafter

![TheCompleteCode](https://github.com/user-attachments/assets/197fb3d7-775d-4550-a62f-4ed7b1896dc1)

<h2> Code Breakdown </h2> 

We start by importing the random module which is a library that is natively part of Python. It helps generate random numbers. For the purposes of this exercise it will help the program simulate network traffic to help illustrate the conditional review that a firewall does each time an IP address tries to access the network. 

![Random ModuleTrial](https://github.com/user-attachments/assets/b6d900ab-08a2-40b5-9131-4d8ffb2a8bc4)

Two functions are then created. One function is the "ip_gen_random" which generates a random ip address within the 172.16.0 ip address range where the fourth octet is a random number between 1 and 15. 

The "firewall_check" function which involves a for loop that evaluates the random IP address that was generated and compares it to the dictionary which is part of our "main" function (discussed in a moment). If the random IP address matches an IP address in the dictionary then the return condition of the for loop will be whatever the value is in the dictionary. If it does not match, then the return condition of the function, which is "allow," will be the result (more on how this is used later). 

![TwoFunctionsAreCreated](https://github.com/user-attachments/assets/3105d9de-b033-488d-9c6b-7afcaf35388a)

The "main" function consists of two main parts:

"rule_of_firewall" which is a dictionary with key value pairs, numerical IP addresses and a text string denoting in this case that these specific IP addresses will be denied access to the network if they try to obtain access. 

![RuleOfFirewall](https://github.com/user-attachments/assets/035229cb-4f8c-41f4-8111-b4bd8bc366a8)

The second part of the main function is a for loop. It has the range set to run 23 times in an effort to "pretend" to create network traffic on a fictitious network.  

![ForLoop](https://github.com/user-attachments/assets/a2f9b9c4-8b3d-49ba-8bf3-52d4642af8f2)

There will be three different variables as part of this for loop, they are: 

address_ipv4

![Address_IPv4](https://github.com/user-attachments/assets/2df67cf2-5d8e-4cde-b239-b15988a78c25)

The address_ipv4 will be the result of whatever IP address that the ip_gen_random function generates.


decision

![Decision](https://github.com/user-attachments/assets/5c248b1f-b6b4-4554-9aa5-56b3f77475da)

The decision variable is the result of the "rule_of_firewall" and "address_ipv4" arguments. "address_ipv4" is going to be the random IP address that is generated and the "rule_of_firewall" causes the "firewall" to check our dictionary. If the randomly generated IP address matches an IP address in the dictionary,  then the result of the "firewall_check" will be to "deny" the IP Address entry to the network. If the randomly generated IP does not match a key-value pair in the dictionary, then the returned result will be "allow." 

random_number 

![Radint](https://github.com/user-attachments/assets/2eaf6c13-993c-432c-a7ad-87972e43081c)

Lastly, the random_number variable calls on the "random" module to generate a number between 0 and 864. This serves to be a unique ID number and/or "label" for the particular attempt that an IP address is trying to access the network.

The last part of the for loop is to print the result of the check that the firewall does on the generated IP addresses, which one can see in the console output below. 

![Print](https://github.com/user-attachments/assets/d12cd92b-d5d7-46bf-8cfa-8a527cbbad17)

At the very bottom of the program the "main guard" is used to make sure that the program runs properly and that the result is actually printed to the console as without it, the console won't print the output as intended. I deleted the "main guard" out of the code and tried to run the code a couple times and the output didn't print to the console. 

![MainGuard](https://github.com/user-attachments/assets/50657284-45b8-4580-b5bd-58363cbe004d)

<h2> Output of the Code </h2> 

As you can see, the code was run multiple times and the desired output was correct. If the IP address matched an IP address on the blacklist, then the message that printed was an "deny," meaning that the IP address was not allowed access. If the IP address was not on the list, then the message that printed was "allow," allowing access.

![CodeOutput](https://github.com/user-attachments/assets/74b95740-046e-4b79-a7a2-ab43db2e9bda)

<h2> Lessons Learned </h2>

This exercise was very useful. In my mind I considered the logic of each part of the code. Included in my considerations were how the script worked, how each loop and function integrated their respective roles into the final result and as demonstrated with the "main guard" comment above, I also checked to see how deleting or not including certain components would affect the script, for good or for ill. 

This exercise has helped me understand the mechanical aspects of how a firewall performs its functions in an effort to protect a network from unauthorized access. In addition, it has helped me understand the Python programming language a little more as well. Thank you for reviewing this exercise with me. 

<h2> Tools Used </h2>

<br> Visual Studio Code (Microsoft) </br>
Oracle Virtualbox 
<br> Ubuntu Linux LTS 24.01.1 </br> 


