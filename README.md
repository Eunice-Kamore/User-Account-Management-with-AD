<H1>User Account Management in Active Directory</H1>
<p> This section of my home lab documentation demonstrates the process of creating and managing user accounts in Active Directory. Additionally, I will configure an account lockout policy using the Group Policy Management tool and test out the fuctionality.
</p>

<H2>Objectives</H2>

--Create two Organizational Units (HR and IT).  

--Create users in each OU and access the accounts using the Client Windows 10 VM.

--Configure an Account Lockout Policy.

--Test the policy functionality.


<H2>Documentation</H2>
<p>
In this home lab, I will demonstrate how to use create organizational units, create users in their respective organizational unit and then configure a group policy object to enforce a rule for locking out an account after 3 invalid login attempts as a security feature. Then I will test out the policy by using a wrong password to cause a lock out for the account.

To begin with we will open "Tools" at the top on the right and choose "Active Directory Users and Computers" 

1.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/One.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />
   
The Windows 10 PC has been successfully added to the domain and is visible in the "Computers" directory.

2.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Two.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Now we will begin with creating the two OU's that we will act as our departments in the production environment. Right click on the domain name "junicetechie.com", then "New" and choose "Organizational Unit".

3.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Three.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />
     
  Name the first one as "IT" and the second one as "HR" and check the "Protect the Container from Accidental Deletion"

4.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Four.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

   To create users in the OU, right click on the specific one select "New", then select user. It can also be done by double clicking on the OU and the right click inside the OU.
  
5.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Five.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Once the interface opens up, provide the first name and the last name. In this case "Hellena James" is the user's name and "hellena.james@junicetechie.com" is the User Logon Name. Click next and input the password and confirm the same.

6.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Six.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

7.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Seven.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

User "Hellena James" has been successfully created.

8.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Eight.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Now, following the steps above we will create another user in the "IT" Organizational Unit in the name "Collins Grey".

9.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Nine.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

10.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Ten.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Once the user accounts have been created and we'll configure a policy to lock out an account after 3 invalid login accounts. Open tools at the top on the right and choose "Group Policy Management"

11.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Eleven.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Click on the domain "junicetechie.com" and right click on the "Default Domain Policy" then click "Edit".

12.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Twelve.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

On Computer Configuration, open "Policies", "Windows Settings", "Security Settings"  then "Account Lockout Policy" 

13.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Thirteen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

We will define a policy for the 3 settings. Click on each of them and define the parameters for lockout duration (30 minutes), lockout threshold(3 times) and lockout counter (30 minutes)

14.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Fourteen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

15.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Fifteen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />
This will ensure everytime a user enters a wrong password 3 times, the account till lockout automatically.

16.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Seventeen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />


Now lets try and login to the Windows PC with the domain account.

17.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Eighteen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Successfully logged in using "Hellena James" domain account.

18.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Ninenteen.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Now to test out the policy we configured, I'll enter a wrong password for 3 times and confirm if the account is locked out in the fourth attempt.

19.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/Twenty.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

Consequently, the account shows a lockout warning in the fourth attempt.

20.
   <p align="center">
   <img src="https://github.com/Eunice-Kamore/User-Account-Management-with-AD/blob/main/Images/TwentyOne.png?raw=true"  height="80%" width="80%"/>
   <br />
   <br />

In the next lab we will explore some AD common issues and how to solve them as a helpdesk professional.










