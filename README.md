<h1>Active Directory: PowerShell Logon Script</h1>


<h2>Description</h2>
This project demonstrates the creation of a PowerShell logon script and its deployment through a Group Policy Object (GPO) in an Active Directory environment.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Virtual Box</b> 

<h2>Environments Used </h2>

- <b>Windows 2019 Server</b>
- <b>Windows 10 Pro</b>




<h2>Project walk-through:</h2>

<p>
I have already configured a shared drive locally on my domain controller in my previous project. Now I just need to create a script that will map it to a consistent drive letter for the users and clients in the network. Y is a free letter that I have available so I will use Y as the shared drive across the network. PowerShell Integrated Script Environment is an application in Windows that allows you to create scripts. I started by going to PowerShell ISE and using the net use command to map the shared drive. The script that I ran to map the drive is: “net use Y: \\WIN-0MVN6QJHVFC\SharedHomeDrive /persistent:yes”

<br>
<br>

 <img width="975" height="501" alt="image" src="https://github.com/user-attachments/assets/1f7f54ac-aab8-4ac1-9bf3-7f0494fdbec3" />


The script ran and tested successfully so now I can save the script.
 
<img width="975" height="528" alt="image" src="https://github.com/user-attachments/assets/205b1a44-e1fc-47a7-98bc-d19b2cbca5bf" />
<br>
<br>

With the script saved, I can now create a Group Policy Object that will allow the script to run when users’ login onto the network. I went to Group Policy Management which is an application you can launch to create and enforce different types of GPOs, and I created a GPO for the Groups OU named Shared Y Drive Mapping. 
<br>
<br>
<img width="975" height="538" alt="image" src="https://github.com/user-attachments/assets/01e0ec1e-a782-4975-a840-fb7358eba89d" />
<br>
<br>
 
Since I am creating a logon script for users logging into the network, I can access this area under User Configuration, Policies, Windows Settings, Scripts.
<br>
<br>
 <img width="975" height="508" alt="image" src="https://github.com/user-attachments/assets/8a668335-6130-4b18-88f0-65eadfb2dfec" />
<br>
<br>

From here I navigated to the Logon scripts and added my PowerShell script that I saved to my PC earlier.
<br>
<br>
 <img width="975" height="503" alt="image" src="https://github.com/user-attachments/assets/1830e9f1-2f57-450b-b57a-2b074045e3c6" />
<br>
<br>

I’ve realized that it’s important to keep the scripts organized since each GPO contains a folder that maps to specific scripts, so I cleared the path of the previous script since it was local and copied the script itself into the GPO’s script folder. Now I can see that the GPO is configured and enabled.
 <br>
<br>
<img width="975" height="526" alt="image" src="https://github.com/user-attachments/assets/ed49522b-6265-43b7-a553-5076ccfe6e53" />

<br>
<br>
<img width="975" height="502" alt="image" src="https://github.com/user-attachments/assets/401f6247-c42c-4cfa-b88c-54ef1ebb7c3c" />

 <br>
<br>

I already have groups of users apart of the Groups OU but the groups inside didn’t automatically inherit the GPO so I didn’t see any new mappings at first. I added one of the users to the Groups OU directly and I can now see the mapped drive.
 <br>
<br>
 <img width="975" height="505" alt="image" src="https://github.com/user-attachments/assets/08ecbbf1-de89-4a03-82c5-e0c8e9c3ab11" />
<br>
<br>
 <img width="975" height="509" alt="image" src="https://github.com/user-attachments/assets/261a5d1e-a1cf-48cd-8b1d-b49e02103692" />
<br>
<br>
<img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/b769bf24-1f98-4f37-9792-0d6a5304acf5" />


This wraps up the project as I have learned a lot about creating logon scripts, assigning group policy and adding users to inherit the group policy. This project was a lot of fun and I love how much I am learning and progressing as an IT support professional.




</p>
