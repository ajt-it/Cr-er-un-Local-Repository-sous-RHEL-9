# "Creating a Red Hat ⛑ Local Repository: Practical Guide for Linux System Administrators"

In scenarios where a Red Hat server is offline, leaving users and client machines without access to necessary repositories, a practical solution is to establish a local Red Hat HTTP repository. This allows Linux system administrators to maintain operations even in isolated environments.

In this article, we will explore step-by-step procedures to set up a Red Hat local HTTP repository server from an installed ISO image on a server. This essential skill will contribute to ensuring operational continuity.


## A. Server Configuration

Step I: Setting up the Local Repository Server

![1](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/0ceae4f6-3aac-4ac3-902b-604a09af9131)

![2 - a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8d96ebf6-2466-4e7c-aa19-8de6be4178f3)


Step II

a- Creating the "rhl9-repo" folder in "/mnt" on the server

b- Mounting the ISO

c- Making the mount permanent

![3 -a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8112a858-ff93-47dd-be2f-0559005ddf8b)

![4 - a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/cea8f569-8f9d-45fc-b745-0c1f508ef5e6)


Step III

a- Creating the local repository configuration file in "/etc/yum.repos.d/rhl9.repo"

Note: If necessary, assign permission 644 to the "rhl9.repo" file

Configuration as follows:

![4 - b](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/a3d24c0d-58f5-4d94-a499-c55236c6d8a9)

![4 - c](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/72225561-e613-4f56-bcbe-8e42f9deb897)


b- Executing the following commands: "dnf clean all"; "dnf repolist"; "subscription-manager clean"

![5](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/1145cab8-7fc9-4291-9dea-1f57c864df2e)


c- Testing repository functionality and installing the HTTP server

![6](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e219f0cc-7e88-4cbe-b8ad-1198e009d0a6)

![7](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/6b104d62-67dd-4349-9ae7-b737b23683d5)


Step IV

a- Once the HTTP server is installed, start and enable automatic service startup at boot.

b- Check HTTP server status

![8](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/bf11b47c-acd6-44f6-bc88-d139cc0f058c)

c- Firewall configuration

![22](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e794c7ff-52c9-47b5-bb99-435bfdc19f0d)


Step V

a- Installation of required packages to create, configure, and manage the local repository

![9](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/02891e7c-d2fb-4ecd-a38f-a71b8e0474f8)

![10](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8581d073-d7e8-4b7e-bd4d-40186d73fc47)

![11](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/4b113440-8ccf-4f03-bb70-71915ad35cf3)

![12](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/7b2b1ac1-1030-4b38-a934-042a219b8d58)

![14](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e4252e02-8b48-4e4c-a5c2-d81146b7e888)


b- Creating the folder "/var/www/html/rhl9-repo/rhl9-repo/" & copying content from "/mnt/rhl9-repo/" to "/var/www/html/rhl9-repo/"

![13](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/07452fa1-2e10-46ea-89d3-e85ecbe566e3)


c- Comparison of content between "/mnt/rhl9-repo/" and "/var/www/html/rhl9-repo/"

![14 -a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e2ffe139-05cd-4dc4-a488-064af8f445f8)


![image](https://github.com/ajt-it/Creating-a-Local-Repository-Server-on-RHEL-9/assets/46109209/8fb5da60-64fc-4bc8-810e-e41290b1355a)



## B. Client Configuration

![15](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/045b1169-2209-497f-9e96-296c607a005f)

![16](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/5fb84d68-7cdf-4ec8-8d8e-5126bc607f2d)

![17](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/af051c94-5ac9-4dab-ae9f-7754e5aac84d)

![18](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/01dc445d-2649-4d90-bd56-433b0931db30)


Step II

a- Create a configuration file for the local repository in the directory "/etc/yum.repos.d/local.repo"

![19-a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/ef16fb6b-9cbd-4c1c-a9b1-517758921bb6)


![19-b](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/b4084ee9-0d0a-418a-9981-b890596c944a)


b- Execute the following commands: "dnf clean all"; "dnf repolist"; "subscription-manager clean"

![20](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/78430768-c69d-4d2f-9e5b-3baa6e84fe1f)


c- Test repository functionality

![21](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/ac431497-0710-44e5-8ace-fcbef99f1a51)


Conclusion:

Setting up a Red Hat local HTTP repository provides a robust solution for offline environments, ensuring users and client machines access to necessary packages even in the absence of an internet connection. By carefully following configuration steps on the server and client machine, system administrators can maintain operational continuity in isolated environments, ensuring system stability and reliability.




