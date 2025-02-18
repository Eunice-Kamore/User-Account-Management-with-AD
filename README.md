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
