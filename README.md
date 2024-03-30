# Born2beRoot

## Description
    "Born to be Root" is a comprehensive guide aimed at empowering individuals who are new to system administration, specifically focusing on mastering the Linux environment. This repository serves as a gateway for beginners to delve into the world of root access and system management with confidence.

    Whether you're a budding enthusiast or a professional seeking to enhance your skills, this guide provides step-by-step instructions, tips, and best practices for navigating Linux systems effectively. From understanding fundamental concepts like file systems, permissions, and processes, to advanced topics such as networking, security, and automation, "Born to be Root" equips users with the knowledge and tools necessary to become proficient in system administration.

    Through clear explanations, hands-on tutorials, and real-world examples, this guide fosters a deeper understanding of Linux administration principles, empowering users to tackle a wide range of tasks and challenges with ease. By embracing the mindset of being 'root' — the superuser with unrestricted access — individuals are encouraged to explore, experiment, and take control of their Linux systems, ultimately unlocking the full potential of their computing environment.

    With "Born to be Root," users embark on a journey of discovery and mastery, gaining the skills and confidence needed to thrive in the dynamic world of Linux system administration. Whether it's setting up servers, troubleshooting issues, or optimizing performance, this guide serves as a trusted companion for anyone seeking to harness the power of Linux and become a true root user.

    For more to understand better what is required I have uploaded the pdf of the subject inside this repository.

## STEP1: Download the VirtualBox

    If you do not have installed VirtualBox you can go at this link https://www.virtualbox.org/ and download it. We will need to use it to install the operating system we want to use.

## STEP 2: Choosing the operating system
    DEBIAN OR ROCKY LINUX

    Based on the requirements provided in the subject, Debian is highly recommended "Born to be Root" project. Here's why:

    1- Stability and Ease of Use: Debian is known for its stability and reliability, making it an excellent choice for a server environment. It has a well-established release cycle and extensive documentation, making it suitable for both beginners and experienced users.

    2- Strong Community Support: Debian has a large and active community with a wealth of resources available online. This support network can be invaluable, especially for those new to system administration.

    3- Suitability for System Administration: The project specifically mentions that Debian is highly recommended for newcomers to system administration. Debian's user-friendly package management system (apt) and comprehensive documentation make it well-suited for learning and implementing the required tasks.

    4- Security Features: Debian comes with robust security features, including SELinux, which must be running at startup and configured according to the project's needs. Additionally, AppArmor must be running at startup for Debian, further enhancing security.

    5- Compatibility with Project Requirements: Debian aligns well with the project's requirements, including setting up encrypted partitions using LVM, implementing a strong password policy, configuring sudo, setting up SSH with restricted access, and configuring the firewall using UFW.

    6- Bonus Part Consideration: If you decide to pursue the bonus part of the project, Debian provides a stable platform for setting up additional services such as WordPress or a custom service of your choice.

    7- The latest version now that im writing this guide is Debian 12.5. Go to this link to download Debian image - https://www.debian.org/download.

Overall, Debian offers a reliable, stable, and well-supported platform that aligns closely with the project's objectives and requirements. It provides a solid foundation for learning system administration and implementing the necessary configurations and tasks outlined in the project description.

## STEP 3: New Virtual Machine with Oracle VirtualBox
1- Open Oracle VirtualBox

2- Click on the new command on the top
![New Virtual Machine](photos/installation/newVm.png)

3- It will prompt to Create Virtual Machine window. Fill the specific fields like in the photo.
If you are not a 42 student you can just store the Machine Folder where you want. After filling
the fields type next.
![Virtual Machine Name and Operating System](photos/installation/vmNameAndOs.png)

4- Now we have to set up the memory size we want to use for our VM. You are free to choose
How much memory you want to use from your computer but I would suggest that 1024MB is enough
for this project.
![Hardware](photos/installation/Hardware.png)

5- Now the next prompts are asking to set up a virtual Hard disk. In the VirtualBox setup process, ensure to select 'Dynamically allocated' for storage on the physical hard disk. This option allows the virtual hard disk file to grow in size as needed, optimizing disk space usage. Avoid checking the option to pre-allocate the full size, as it may lead to unnecessary disk space allocation."
![Virtual Hard Disk Memory](photos/installation/VirtualHardDiskSize.png)

6- So now you should have a summary similar with the photo below. Type finish.
![Summary](photos/installation/vmSummary.png)

7- After pressing finished you should see your new Vm created like below. You should go to
settings to start with the next step of mounting an ISO file.
![VmCreated](photos/installation/VmCreated.png)

## STEP 4: Mount iso file and Start VM
1- Controller: Under the "Controller: IDE" or "Controller: SATA" section (depending on your VM's configuration), you'll find an empty optical drive (usually labeled "Empty"). Click on the optical drive.
Attributes: In the attributes section to the right, you'll see a small disk icon next to "IDE Secondary Master" or "SATA Port 1." Click on the disk icon.
Choose a Disk File: In the dropdown menu, select "Choose a disk file..." Navigate to the location of the ISO file on your computer and select it.
![Choose Disk File](photos/installation/ChooseDiskFile.png)

2- After choosing Debian ISO image that we dowloaded in the beginning you should have the
same results as below, and then type ok.
![Debian Iso Image](photos/installation/DebianIsoImage.png)

3- Now we start the machine by clicking at the Start icon, so we can continue with the next
step to install Debian.
![Start Machine](photos/installation/InstallDebian.png)

## STEP 5: Installing Debian

### 1- Setting up the languange, time zone, keyboard layout
1- It will have the view like below. To have a larger view for your eyes, right click with your
mouse, choose the option Virtual Screen 1 and scale it to 200%. After choose the install 
option since we will use it without Graphical Interface.
![Install](photos/installation/installOption.png)

2- Now it will ask for the languange im going with English.
![Choose Language](photos/installation/EnglishLanguage.png)

3- We enter our Country, territory or area. Since I'm in Germany I will put Other.
![Choose Country](photos/installation/Country.png)

4- We select the country. In my case Germany 🇩🇪
First I select Europe.
![Other section for Country select](photos/installation/europe.png)
After I select Germany.
![Germany](photos/installation/Germany.png)

5- Configuring locales: I will go with United States
![Configuring Locales](photos/installation/configuringLocales.png)

6- It is important to select American English as the keyboard configuration, otherwise we will have the keys linked incorrectly.
![Keyboard Configuration](photos/installation/Keyboard.png)

7- Finally by finishing with this step we should the window below;
![Finished Language, Area and Keyboard Configuration](photos/installation/configuredLanguageAndKeyboard.png)

### 2- Configuring the Network
1- It will first require the hostname which by the subject we have to put the user intraname
followed by 42 -> eseferi42 in my case
![Setting the Hostname](photos/installation/Hostname.png)

2- Domain name. We will leave this section empty, since the subject does not mention anything about Domain name.
![Setting the Domain Name](photos/installation/DomainName.png)

3- We must enter a password for the system administration account. It is important to write it 
down or take a photo, since we will use it. If you want to see the password to make sure you 
have written it correctly, you must tab until you reach the Show Password in Clear option, you 
must press the space bar and the password will be displayed. So you should see something like
the photo below:
![Setting Password](photos/installation/Pasword.png)

4- Now we have to reconfirm our password
![Confirming Password](photos/installation/PasswordConfirmation.png)

5- For not using the root account for non-administrative activities it will request to create
a normal user account. Since for the root account I put eseferi42 for the user I'm writing
eseferi
![Non root-user](photos/installation/NonRootUser.png)

6- Now it will require a nickname or username for this non-root user, but I'm proceeding with 
the previous User name also for the nickname;
![Nickname for the Non root-user](photos/installation/Nickname.png)

7- We have to choose a password for the Non-root user, I'm proceeding with the same as for the
Root User, Kinda have bad memory 🥱
![Password for the Non root-user](photos/installation/NonRootUserPassword.png)

8- Again we have to confirm the password. As I showed while setting the passord for the root user, we can move with arrows do show password and press space.
![Password confirmation for the Non root-user](photos/installation/NonRootUserPasswordConfirmation.png)

### Setting up the partitions
Partitioning is essential for organizing disk space on your server. It divides the disk into separate sections, each serving a specific purpose.

1- use entire disk and set up encrypted LVM: This refers to selecting the guided partitioning 
option in the installation process, which will automatically partition the disk and set up 
encrypted Logical Volume Manager (LVM). This option is chosen because the project specifies 
that encrypted partitions must be used. 
BUT...
⚠️❗️ If you want to do the bonus you must click Manual and click here ❗️⚠️: This part serves 
as a reminder or alert for users who wish to complete the bonus part of the project. It 
instructs them that if they want to deviate from the automatic guided partitioning and set up 
the partitions manually (which may be necessary for certain bonus tasks), they should select 
the "Manual" option instead. I will do first what is required for the bonus but if you want 
you can skip it and go straight here.
![Manual Partitioning](photos/installation/ManualConfiguringPartitions.png)

2- In this section it shows us a general description of our partitions and mount points. 
Currently, we do not have partitions made. To create a new partition table we must choose the 
device where we want to create them. In our case we will choose the only one available, 
SCSI2 (0, 0, 0) (sda) - 32.2 GB ATA VBOX HARDDISK in my case. Don't be confused if you have
SCSI3 because in VirtualBox, the SCSI controller number is assigned automatically by the   
software and may vary between installations or configurations. It's essentially a virtual 
representation of the disk controller used by the virtual machine. As long as you're referring 
to the correct disk (sda) and its capacity (32.2GB ATA VBOX HARDDISK), you should be fine.
![Device](photos/installation/SCSI2.png)

3- Click yes to confirm the device
![Confirm Device](photos/installation/ConfirmDevice.png)

4- Once we have completed the previous step we can see how our empty partition table appears. 
Now we must configure it, to do this we must select the FREE SPACE to create the partitions.
![Selec FREE SPACE](photos/installation/FreeSpace.png)

5- Create new partition
![Create New partition](photos/installation/CreateNewPartition.png)

6- Taking the subject's image how the partitions should be we will create them one by one
![Create New partition for Sda1](photos/installation/SettingSDA1.png)

7- As the subject indicates, the size of the partition must be 500 megabytes.
![Set size for the first sda](photos/installation/SDA1size.png)

8- Brief description of all types of partitions:

    ◦ Primary: The only partition on which an OS can be installed. There can only be 4 primary partitions per hard drive or 3 primary and one extended.

    ◦ Secondary/Extended: It was designed to break the limitation of 4 primary partitions on a single physical disk. There can only be one partition of this type per disk, and it is only used to contain logical partitions.

    ◦ Logical: Occupies a portion of the extended/primary partition or its entirety, which has been formatted with a specific type of file system (in our case we will use ext4) and a drive has been assigned to it, thus the system The operating system recognizes the logical partitions or their file system. There can be a maximum of 23 logical partitions in an extended partition, however, Linux, the OS we currently work with, reduces this to 15, more than enough to carry out this project.
For this step we will choose primary since it will be the partition where the Operating System will be installed.
![Set partition to primary](photos/installation/Primary.png)

9- We will select beginning since we want the new partition to be created at the beginning of 
the available space.
![Set partition to the beginning of the available space.](photos/installation/BeginningSda1.png)

10- The following screenshot shows us the details of the partition. We will modify the mount 
point to which the subject specifies.
![Configure Mount point for sda1](photos/installation/MountPointSda1.png)

11- We choose boot as the mount point of our partition.
![Mounting with Boot option](photos/installation/BootMounting.png)

12- We finish configuring the current partition.
![Finishing sda1 partition](photos/installation/doneWithSda1.png)

13- Once we have completed the previous step, the partition should appear. Now we must create 
a logical partition with all the available disk space, which has no mount point and which is 
encrypted. To do this, we select the free space where we want to create it.
![Create sda5 partition](photos/installation/CreateSda5.png)

14- Create new partition
![Create New partition](photos/installation/CreateNewPartition.png)

15- We will use the example from the subject
![Sda5 subject example](photos/installation/sda5example.png)

16- We select max for this partition
![set max size for sda5](photos/installation/maxsize.png)

17- Since we have to create The LVM we have to choose Logical
![Choose Logical](photos/installation/Logical.png)

18- Select the mount point
![Choose mount point](photos/installation/MountPointSda1.png)

19- in the context of virtual machines (VMs) and disk management, logical partitions are       
typically not mounted directly because they are part of a larger virtual disk image or disk 
file. 
![Do not mount it](photos/installation/DoNotMountIt.png)

20- Finish this partition
![Finish partition after not mounting](photos/installation/finishedAfterNotMounting.png)

21- Lets configure the encrypred volumes now
![Configure Encrypted Volumes](photos/installation/ConfigEncryptVolumes.png)

22- Accept the confirmation message.
![Accept to configure Encrypted Volumes](photos/installation/ConfirmToConfigEnrcyptVolumes.png)

23- We start to create encrypted volumes.
![Create Encrypted Volumes](photos/installation/CreateEncryptedVolumes.png)

24- We select which partition we want to perform the encryption on. Move with arrows to 
/dev/sda5/ and select it with space.
![Select sda5 for encryption](photos/installation/SelectSda5ForEncryption.png)

25- We finish configuring the current partition.
![Done setting up partition](photos/installation/DoneSettingUpPartition.png)

26- We are done, since we do not want to create more encrypted volumes.
![Finish Encryption](photos/installation/FinishEncryption.png)

27- We accept the confirmation message which tells us that everything inside the partition 
will be encrypted and that it shouldn't take long to finish.
![Confirm Finishing Encryption](photos/installation/ConfirmFinishingEncription.png)

28- We don't care if it takes a long time or a short time, we click cancel, since there is 
nothing to encrypt, because the partition is empty.
![Wait till encryption finishes](photos/installation/WaitTillEncryptionFinishes.png)

29- Again we will have to enter a password, this time it will be the encryption phrase. As I 
have previously told you, you must repeat the process and you must write it down, since it 
will be important in the future.
![Put password for Encryption](photos/installation/EncryptionPassword.png)

30- Confirm the password
![Confirm password for Encryption](photos/installation/ConfirmEncryptionPasword.png)

31- We will configure the logical volume manager.
![Configure Logical Volume Manager](photos/installation/ConfigLogVolMan.png)

32- We will accept the confirmation message, since we agree that the changes will be saved to  
disk.
![Confirm writing to disk](photos/installation/ConfirmWritingToDisk.png)

33- Let's create a new volume group. Volume groups group partitions together.
![Create Volume Group](photos/installation/CreateVolumeGroup.png)

34- We have to give the name as indicated in the subject: LVMGroup.
![Enter name LVMGroup](photos/installation/EnterLVMGroupName.png)

35- Select the partition where we should create the group.
![Select Device](photos/installation/SelectSda5forVolumeGroup.png)

36- We have to create them as the example in the subject
![Logical Partitions Example](photos/installation/LogicalPartitionsExample.png)
![Create First Logical Volume](photos/installation/CreateFirstLogicalVolume.png)

37- We will start by choosing the group where we want them to be created. We select the only 
one available (the one we just created).
![Select Logical Volumes Group](photos/installation/SelectVolumeGroup.png)

38- The order of creating the logical units will be the same as indicated in the subject, so 
we will start with root and end with var-log. Then we will select the name of the logical 
volume.
![Put Root Name](photos/installation/putRootName.png)

39- Size, as the subject indicates, will be 10g.
![Put size](photos/installation/putsize.png)

40- To not cause repetition, go on and do the same for all partitions in the group volume
and give the same name and size the same as in the example above

41- If you made them all you should have exact window like below, and type finish.
![Finish logical Partitions](photos/installation/finishedLogicalPartitions.png)

42- Now we can see how in the section where they show us all our partitions and free space, 
all the logical partitions that we just created already appear. Well, we must configure all of 
them to select the file system we want and the mount point indicated by the subject. Again we 
will go in order and select by pressing enter the first one that appears to us, which is home.
![Set up Home](photos/installation/setupHome.png)

43- It shows us the partition configuration. We must choose a file system since it currently does not have one by pressing with enter at use as do not use.
![Use Home as Do not Use](photos/installation/useHomeAsDoNotUse.png)

44- Choose the Ext4 file system, it is the most used file system in Linux distributions.
![Journalist File System](photos/installation/Ext4.png)

45- We must select the mount point by pressing enter on it
![Select Mount Point](photos/installation/SelectMountPoint.png)

46- For home select home and for others in the future choose the specific for them to not
repeat the same thing
![Mount Home with home](photos/installation/homemount.png)

46- Done setting up partition
![Done setting up partition](photos/installation/DoneSettingUpPartitionHome.png)

46- Go now and do the same for all partitions.
Only for the var/log you have to enter the mounting point manually and for the swap do not 
choose Journalist File System but choose swap area after you click use as do not use.
In the end Finish partitioning and write changes to disk.
![Finish partitioning](photos/installation/FinishingPartWriteChangesToDisk.png)
Confirm and after it you will see the installation bar.
![Installing base system](photos/installation/InstallingBaseSystem.png)

47- It will ask for us to install additional packages but we select no since we don't need them
![No Extra Packages](photos/installation/NoextraPackages.png)

48- Choose the country that is specific to you.
![Choose a country](photos/installation/CountryForMirroringDebian.png)

49- I choose deb.debian.org, since taking into account my region, it is where we will have a
better connection.
![Choose the archive mirror](photos/installation/debianOrg.png)

50- Leave this field empty and continue.
![Continue](photos/installation/httpProxy.png)

51- We do not want developers to see our statistics so select no
![Don't sent statistics to no one](photos/installation/NoStatistics.png)

52- We will remove all software options (with the space bar) and click Continue
since in the subject they are forbidden.
![Continue without softwares](photos/installation/Forbidden.png)

53- We will select Yes to install GRUB boot on the hard drive.
GRUB plays a crucial role in the boot process of Linux-based operating systems, providing a flexible and customizable bootloader solution that facilitates system booting, kernel loading, and system recovery.
![Accept to install GRUB](photos/installation/GRUB.png)

53- Next choose the device for the /dev/sda bootloader installation (ata_VBOX_HARDDISK).
![Config grup-pc](photos/installation/ConfigGrup-Pc.png)

54- Type continue to finish the installation.
![Complete Installation](photos/installation/CompleteInstallation.png)

Now your system will open and ask for password lets jump to the next steps :)

## STEP 6: Virtual Machine Configuration

1- The first thing we must do is select Debian GNU/Linux.
We must enter the encryption password that we previously used.
![Enter sda5 Password](photos/MachineConfiguration/EnterSda5Password.png)

2- Enter Non root user username and password
![Enter Non root user password](photos/MachineConfiguration/EnterNonRootUserPassword.png)
We now have everything ready to start configuring our Debian virtual machine 🥳

### Installing sudo and configuring users and groups

1- To install sudo we must first be in the root user, to do this we will put Su in the 
terminal and enter the root password. Once we have accessed the root user, we must enter the 
apt install sudo command to install the necessary packages.
![Installing sudo](photos/MachineConfiguration/InstallingSudo.png)

2- We must restart the machine for the changes to be applied. To do this we will use the sudo reboot command and wait for it to reboot.

![sudo reboot](photos/MachineConfiguration/sudoReboot.png)


3- Once restarted we must re-enter the encryption and user passwords. To verify that we have 
installed sudo correctly, we will enter the root user again and enter the command sudo -V. 
This command, in addition to showing us the version of sudo, will also show the arguments 
passed to configure when sudo was created and the plugins that can show more information. 
Optional: Since the output of the command is very long, if we want to see it completely we 
must redirect its output to a file sudo -V > file.txt and then edit the file nano file.txt. Or 
put | more after the command.

![check sudo](photos/MachineConfiguration/sudo-v.png)

4- Continuing with the root user, we will create a user with the name of our non root user
which is loged in with the command sudo adduser login, as we have already created the user in 
the installation, it should appear that the user already exists.
![sudo add user](photos/MachineConfiguration/sudoAddUsser.png)

5- Now we will have to create a new group called user42. To create it we must do sudo addgroup 
user42.

![sudo add group](photos/MachineConfiguration/sudoAddGroups.png)

🤔 Ever heard of GID? It stands for Group Identifier, abbreviated as Group ID. Essentially, it's a unique identifier assigned to a group 🆔 in a Unix-like operating system. Just like how each user has a UID (User ID), each group gets its own GID. This identifier helps the system manage permissions and access control, allowing users within the same group to share resources and collaborate effectively. So, think of GID as the group's digital fingerprint—it ensures smooth coordination and organization within the operating system!

🤔 Has the group been created correctly? The truth is that yes, since there has been no error message, we can still check if it has been created with the command getent group group_name or we can also do cat /etc/group and we can see all the groups and users there are inside them.

![sudo getent group_name](photos/MachineConfiguration/sudoGetEnt.png)

And this will be the output of <b>cat /etc/group</b>
![cat /etc/group](photos/MachineConfiguration/catetcgroup.png)

6- With the command <b>sudo adduser user group</b> we will include the user in the group. We 
must include the user in the sudo and user42 groups.
Once we have entered them, to check that everything has been done correctly, we can execute 
the command getent group group_name or we can also edit the file /etc/group nano /etc/group 
and our user should appear in the sudo and login42 groups.
![Add eseferi to user42 and sudo](photos/MachineConfiguration/addEseferiToSudo.png)

### Installation and Configuration of SSH
🔒 SSH, or Secure Shell, is both a protocol and a program used for remote access to servers. It establishes a secure channel, encrypting all data exchanged between the client and server. This ensures confidentiality and integrity, making SSH a vital tool for secure remote administration and file transfer.

1- The first thing we will do is do sudo apt update to update the repositories that we defined 
in the /etc/apt/sources.list file
![Update](photos/MachineConfiguration/sudoaptupdate.png)

2- Next we will install the main connectivity tool for remote login with the SSH protocol, 
this tool is OpenSSH. To install it we must enter the command <b><i>sudo apt install openssh-server</i></b>. 
In the confirmation message we put Y, then we will wait for the installation to finish.
![Install openshh-server](photos/MachineConfiguration/installopenssh.png)

You should see something like below:

![Installed openshh-server](photos/MachineConfiguration/installedSSH.png)

To check that it has been installed correctly we will do <b><i>sudo service ssh status</i></b> and it should appear active.

![Check ssh status](photos/MachineConfiguration/sshCheckstatus.png)

3- After completing the installation, there are configuration files we need to adjust. We'll 
utilize Nano, or any preferred text editor, for this task. The initial file to modify is 
located at /etc/ssh/sshd_config. If you're not logged in as the root user, writing permissions 
may be restricted. In such cases, you can either switch to the root user using 'su' followed 
by the root password, or alternatively, prepend 'sudo' to the command, like so: '<b><i>sudo nano etc/ssh/sshd_config</b></i>'."

![open sshd_config with nano](photos/MachineConfiguration/nano-sshd_config.png)


🕒 By the way, if you're planning to take a break like I did between sections, I highly 
recommend creating a snapshot of your virtual machine before shutting it down. You can do this 
easily by navigating to the 'Machine' menu at the top of your VM window, selecting 'Take 
Snapshot,' and giving it a name. This way, when you restart your machine later, you can simply 
use this snapshot to restore it to its previous state. 📸

![Take snapshot](photos/MachineConfiguration/snapshoot.png)

This is the way how you can start it 

![Restore snapshot](photos/MachineConfiguration/startSnapshot.png)

Let's go back where we left it. The # at the beginning of a line means that it is commented, 
the lines that we are going to modify you must remove the comment. Once we are editing the 
file we must modify the following lines:

#Port 22 -> Port 4242
#PermitRootLogin prohibit-password -> PermitRootLogin no
![configure the sshd_config](photos/MachineConfiguration/configSshd_config.png)

4- Now we must edit the file /etc/ssh/ssh_config.

![configure the ssh_config](photos/MachineConfiguration/configSsh_config.png)

Uncoment the Port 22 and change it to 4242

![Uncoment port of the ssh_config](photos/MachineConfiguration/activatePort.png)

7- Finally, we must restart the ssh service so that the modifications we have just made are 
updated. To do this we must write the command <b><i>sudo service ssh restart</b></i> and once 
reset we will look at the current status with sudo service ssh status and to confirm that the 
changes have been made to the server listening, Port 4242 should appear.

![Restart ssh after updating it](photos/MachineConfiguration/restartSSH.png)

### Installing and Configuring UFW
🔒 UFW, or Uncomplicated Firewall, is a user-friendly front-end for managing iptables, the default firewall configuration tool for many Linux distributions. It simplifies the process of configuring firewall rules through a straightforward command-line interface, allowing users to easily control network traffic and enhance system security with just a few simple commands. With UFW, even users with limited experience in firewall management can efficiently set up and maintain robust firewall policies to safeguard their systems against unauthorized access and potential threats.

1- 🛡️ To begin, the initial step is to install UFW. Execute the command <b><i>sudo apt 
install ufw</b></i> in your terminal. When prompted, type 'y' to confirm your intention to 
install the package, then patiently wait for the process to complete. This sets the stage for 
configuring your firewall and bolstering your system's security.

![Instal ufw](photos/MachineConfiguration/installufw.png)

2- 🔥 Once UFW is installed, the next crucial step is to enable it. Simply enter the command 
<b><i>sudo ufw enable</b></i> in your terminal. Upon execution, you should receive an 
immediate indication confirming that the firewall is now active. This ensures that your system 
is fortified against unauthorized access, bolstering its overall security posture.

⚙️ Now, let's configure our firewall to allow connections through port 4242. Execute the command sudo ufw allow 4242 in your terminal. This command ensures that traffic on port 4242 is permitted, enabling smooth communication for your desired services or applications.

🔍 Lastly, let's ensure everything is correctly configured by checking the status of our firewall. Execute the command sudo ufw status in your terminal. Here, you should observe connections through port 4242 already listed as allowed. This provides reassurance that your firewall is effectively safeguarding your system while permitting necessary communications.

![Check ufw after configuring](photos/MachineConfiguration/checkUfw.png)




