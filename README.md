<h1>Configuring Network Drive Access via Security Group in a Domain Environment</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Project Overview</h2>
This project focuses on securing access to a shared network drive in a domain environment by implementing role-based access control through Active Directory. The steps include creating a Security Group, assigning permissions to the shared folder, and ensuring seamless access by mapping the drive for users through manual or automated methods like Group Policy. The solution enhances security, simplifies management, and ensures users can efficiently access resources with minimal administrative overhead.
<br />


<h2>Tools and Utilities Used</h2>

- <b>Virtual Box</b>
- <b>Windows Server</b>
- <b>Windows 10</b>
- <b>Active Directory Users and Computers</b>

<h2>Setup & Configuration</h2>

- <b>Windows Server 2019</b></br>
  Network Share Drive (S:)</br>
  
  
- <b>Windows 10</b></br>
  Basic User (Not added to any security Groups)</br>

<h2>Project Walkthrough</h2>

First we want to make sure that access on a LOCAL level is appropriate. We only want to grant access to people that need it.
- <b>ACTION:</b> Removed the "EVERYONE" option, even though there were no permissions set for them - it's one less thing we have to worry about from a security standpoint. We also want to grant access to the domain admins so that whoever is in control of the domain can make the appropriate changes when the time comes. <br/>
<img src="https://i.imgur.com/gbGcoYf.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<img src="https://i.imgur.com/U8k87jc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jcfscmm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We're setting up the share drive for the Finance Department, so we have to make sure we have a Group set to grant access to. As we can see - there isn't a Finance Group already set in permissions. Lets create one.
We have to make sure we have a Finance OU in our Active Directory. Once we create the OU we can add Users to it in a few ways. Here is 1 way. <br/>
<img src="https://i.imgur.com/6IFkpeZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FLzJSE1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- <b>ACTION:</b>We'll create the Finance Group in Active Directory and add a user to the group.</br>
<img src="https://i.imgur.com/slOvB0z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/yGrwxRL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
- <b>ACTION:</b> Added the entire Finance Group we just created to the Permissions of the Network Drive making sure they have Modify access as well. <br/>
<img src="https://i.imgur.com/5pVNZAO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/3LzJlyD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
We'll add one more user to the group by Finding them in the Domain and modifying "Member Of" to add them to the Finance Group.
- <b>ACTION:</b> Found Maria in User and Computers and added her to the already existing Finance Group. <br/>
<img src="https://i.imgur.com/9K040to.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/C9OwEub.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7mmX8T5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lhAkzL8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/iFxZyOk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now we'll Map the Network Drive to Maria so she can have access to it on her Windows 10 Machine. First we need to make sure we have the correct path to the Network Drive.
- <b>ACTION:</b> Copied the Network Drive Path and mapped the drive on Maria's Windows 10 Machine. We can see the Before and After. We'll also see a file Maria Created on the Windows 10 Machine and ALSO on our Windows Server. <br/>
<img src="https://i.imgur.com/KUmhnbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Maria's Windows 10 Machine BEFORE mapping the Network Drive.
<img src="https://i.imgur.com/8eTRFiO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Mapping the Drive
<img src="https://i.imgur.com/Y1adF36.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/agq6ozQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/3hVyKjA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Creating the File on Maria's machine and seeing it visible on both her machine and on Windows Server
<img src="https://i.imgur.com/Y0TjnhK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/UoC9A3L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 

<h2>Conclusion and Key Learnings</h2>
This project successfully demonstrated how to set up secure and efficient access to a shared network drive using Active Directory Security Groups and Group Policy in a domain environment. By implementing role-based access control, permissions were centrally managed, ensuring only authorized users could access the shared resource. Automating the drive mapping process through Group Policy reduced manual effort and minimized errors, improving user experience and administrative efficiency. Key learnings included the importance of carefully managing group memberships, understanding shared folder permissions, and effectively using Group Policy for enterprise-wide configurations. This approach not only enhances security but also lays a scalable foundation for managing shared resources in larger networks.

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
