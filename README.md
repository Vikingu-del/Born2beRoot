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
![New Virtual Machine](photos/newVm.png)

3- It will prompt to Create Virtual Machine window. Fill the specific fields like in the photo.
If you are not a 42 student you can just store the Machine Folder where you want. After filling
the fields type next.
![Virtual Machine Name and Operating System](photos/vmNameAndOs.png)

4- Now we have to set up the memory size we want to use for our VM. You are free to choose
How much memory you want to use from your computer but I would suggest that 1024MB is enough
for this project.
![Hardware](photos/Hardware.png)

5- Now the next prompts are asking to set up a virtual Hard disk. In the VirtualBox setup process, ensure to select 'Dynamically allocated' for storage on the physical hard disk. This option allows the virtual hard disk file to grow in size as needed, optimizing disk space usage. Avoid checking the option to pre-allocate the full size, as it may lead to unnecessary disk space allocation."
![Virtual Hard Disk Memory](photos/VirtualHardDiskSize.png)

6- So now you should have a summary similar with the photo below. Type finish.
![Summary](photos/vmSummary.png)

7- After pressing finished you should see your new Vm created like below. You should go to
settings to start with the next step of mounting an ISO file.
![VmCreated](photos/VmCreated.png)

## STEP 4: Mount iso file and Start VM
1- Controller: Under the "Controller: IDE" or "Controller: SATA" section (depending on your VM's configuration), you'll find an empty optical drive (usually labeled "Empty"). Click on the optical drive.
Attributes: In the attributes section to the right, you'll see a small disk icon next to "IDE Secondary Master" or "SATA Port 1." Click on the disk icon.
Choose a Disk File: In the dropdown menu, select "Choose a disk file..." Navigate to the location of the ISO file on your computer and select it.
![Choose Disk File](photos/ChooseDiskFile.png)

2- After choosing Debian ISO image that we dowloaded in the beginning you should have the
same results as below, and then type ok.
![Debian Iso Image](photos/DebianIsoImage.png)

3- Now we start the machine by clicking at the Start icon, so we can continue with the next
step to install Debian.
![Start Machine](photos/InstallDebian.png)

## STEP 5: Installing Debian

### 1- Setting up the languange, time zone, keyboard layout
1- It will have the view like below. To have a larger view for your eyes, right click with your
mouse, choose the option Virtual Screen 1 and scale it to 200%. After choose the install 
option since we will use it without Graphical Interface.
![Install](photos/installOption.png)

2- Now it will ask for the languange im going with English.
![Choose Language](photos/EnglishLanguage.png)

3- We enter our Country, territory or area. Since I'm in Germany I will put Other.
![Choose Country](photos/Country.png)

4- We select the country. In my case Germany 🇩🇪
First I select Europe.
![Other section for Country select](photos/europe.png)
After I select Germany.
![Germany](photos/Germany.png)

5- Configuring locales: I will go with United States
![Configuring Locales](photos/configuringLocales.png)

6- It is important to select American English as the keyboard configuration, otherwise we will have the keys linked incorrectly.
![Keyboard Configuration](photos/Keyboard.png)

7- Finally by finishing with this step we should the window below;
![Finished Language, Area and Keyboard Configuration](photos/configuredLanguageAndKeyboard.png)

### 2- Configuring the Network
1- It will first require the hostname which by the subject we have to put the user intraname
followed by 42 -> eseferi42 in my case
![Setting the Hostname](photos/Hostname.png)

2- Domain name. We will leave this section empty, since the subject does not mention anything about Domain name.
![Setting the Domain Name](photos/DomainName.png)

3- We must enter a password for the system administration account. It is important to write it 
down or take a photo, since we will use it. If you want to see the password to make sure you 
have written it correctly, you must tab until you reach the Show Password in Clear option, you 
must press the space bar and the password will be displayed. So you should see something like
the photo below:
![Setting Password](photos/Pasword.png)

4- Now we have to reconfirm our password
![Confirming Password](photos/PasswordConfirmation.png)

5- For not using the root account for non-administrative activities it will request to create
a normal user account. Since for the root account I put eseferi42 for the user I'm writing
eseferi
![Non root-user](photos/NonRootUser.png)

6- Now it will require a nickname or username for this non-root user, but I'm proceeding with 
the previous User name also for the nickname;
![Nickname for the Non root-user](photos/Nickname.png)

7- We have to choose a password for the Non-root user, I'm proceeding with the same as for the
Root User, Kinda have bad memory 🥱
![Password for the Non root-user](photos/NonRootUserPassword.png)

8- Again we have to confirm the password. As I showed while setting the passord for the root user, we can move with arrows do show password and press space.
![Password confirmation for the Non root-user](photos/NonRootUserPasswordConfirmation.png)

### Setting up the partitions


