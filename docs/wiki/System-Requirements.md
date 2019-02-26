## Contents

- [Machine Software and Hardware Requirements](#machine-software-and-hardware-requirements)
- [Data Source Requirements](#data-source-requirements)
- [Security Requirements](#security-requirements)
- [User and Group Requirements](#user-and-group-requirements)
- [Client Requirements](#client-requirements)

## Machine Software and Hardware Requirements

The software and minimum hardware requirements for the machine(s)/infrastructure that you use to build and run the images are provided below. 

- Two tables list the software and hardware requirements. The first table lists the requirements for the machine that is used to build the SAS Viya image(s). The second table lists the requirements for the one or more machines where you will run the SAS Viya image(s) to launch the container(s).
- A quick path to a containerized programming-only deployment is to use a single machine to build and run a single image. In that case, consult the Run Machine table for hardware requirements.
- A containerized programming-only deployment can be built and run from a single image or multiple images.
- A containerized full deployment always requires multiple images.
- The information in this section represents what is required to start all system services and to enable a single user to operate against a small sample data set in order to validate operational functionality. These out-of-the-box requirements should be increased for larger deployments.
- Additional RAM should be added based on the expected amount of data that will be processed. More resources are required for multiple-user, production-scale deployments that use large data sets. These guidelines do not attempt to account for all ordering scenarios, but instead are intended to illustrate typical software orders.

### Build Machine

The following software and hardware requirements are for the machine that is used to build the SAS Viya image(s).

| **Software and Hardware** | **Build a Single Image** | **Build Multiple Images** |
| --- | --- | --- | 
| Docker | Community Edition or Enterprise Edition, Docker 17.06 or later | Community Edition or Enterprise Edition, Docker 17.06 or later |
| Docker storage driver <sup>1</sup>  | overlay2 | overlay2 | 
| Operating system | Any Linux-based operating system or Mac <sup>2</sup> | Any Linux-based operating system or Mac. <sup>2</sup> |
| Java | n/a | Java 1.8 | 
| Python | n/a | Python 2.7 or Python 3.5|
| pip and virtualenv | n/a | Both pip and virtualenv are required. <sup>3</sup> |
| Docker registry | (Optional) Access to a Docker registry | Access to a Docker registry is required. <sup>4</sup> | 
| Kubernetes |(Optional) Kubernetes 1.10 or later and kubectl installed | Kubernetes 1.10 or later and kubectl installed <sup>5</sup>| 
| Disk space | Approximately 15-20 GB of free disk space in the /var/lib/docker directory | Approximately 50 GB of free disk space in the /var/lib/docker directory | 
| Cores | 2 (minimum) <sup>6</sup> | 2 (minimum)  | 
| RAM | 8GB (minimum) |  8GB (minimum) | 
| Internet access| Required | Required |

**Notes:**

- <sup>1</sup> Use of overlay is not supported.
- <sup>2</sup> Windows is not supported.
- <sup>3</sup> Python2 with python-pip2 and virtualenv, or Python3 and python-pip3.
- <sup>4</sup> The build process will push built Docker images automatically to the Docker registry. Before running build.sh do a docker login docker.registry.company.com and make sure that the $HOME/.docker/config.json is filled in correctly.
- <sup>5</sup> Required for the deployment step but not required for the build step.
- <sup>6</sup> If you plan to use a single machine to build and run a single image, check the cores requirements in the Run Machine Requirements table below.

### Run Machine(s)

The following software and hardware requirements are for the one or more machines where you will run the SAS Viya image(s) to launch the container(s)

| **Software and Hardware** | **Run a Single Image** | **Run Multiple Images** |
| --- | --- | --- |
| Docker | Community Edition or Enterprise Edition, Docker 17.06 or later. Using `docker run` is required. | Community Edition or Enterprise Edition, Docker 17.06 or later |  
| Kubernetes | n/a | Kubernetes 1.10 or later and kubectl installed | 
| Cores | 4 (minimum) | 6 (minimum) for a programming-only deployment or 8 (minimum) for a full deployment  | 
| RAM | 8GB (minimum) | 10 GB (minimum) for a programming-only deployment or 80 GB (minimum) for a full deployment |  

## Data Source Requirements

SAS/ACCESS products and SAS In-Database Technologies products are configured to enable SAS Viya to access data sources, such as a Hadoop data store, Oracle database, PC files, and so on. Consider the following requirements to ensure that access to the data source(s) is configured correctly.

**Before you build the image:** Some data sources require configuration before you build the SAS Viya image. For example, additional SAS software is required in order to enable data retrieval from a Hadoop data store and from various data storage appliances. Depending on your software order, the image build process might include one or more SAS/ACCESS products or a SAS In-Database Technologies product. The data access software is included in the single image and the programming, computeserver and sas-casserver-primary images. As a best practice, modify settings in the corresponding addons/access-* directory before building the images. For more information, see the following sources:

  - [Data Sources](Pre-build-Tasks#data-sources)
  - [Data Source and Storage Requirements](https://go.documentation.sas.com/?docsetId=dplyml0phy0lax&docsetTarget=n0ebm6161pdn20n1qg77ukdantd0.htm&docsetVersion=3.4) in the _SAS Viya for Linux: Deployment Guide_. Look for the different topics about SAS/ACCESS products and SAS In-Database Technologies products. 

**As part of the build process:** You might be required to install additional software on your CAS machines. For example, the database client must be installed in the sas-casserver-primary image. For users running a CAS massively parallel processing (MPP) environment, you can use the multi-node data transfer feature. For more information about the multi-node option, see [Data Connectors: Using Data Transfer Modes with Data Connectors for DBMS Data Sources](http://documentation.sas.com/?cdcId=pgmsascdc&cdcVersion=9.4_3.4&docsetId=casref&docsetTarget=p12gi5eub04169n1x62tz74kvwt2.htm) in the _SAS Cloud Analytic Services: User’s Guide_.

## Security Requirements

### Host Authentication

For programming-only environments (single or multiple containers), the Compute Server and CAS containers must be configured for host authentication. For more information, see [User and Group Requirements](#user-and-group-requirements).

### LDAP Requirements

LDAP is required only for a full deployment. It is not required in a programming-only deployment.

For a full deployment:

- SAS Viya must have Read access to your LDAP server.
- SAS Viya requires a userDN and password in order to bind to the LDAP server. Anonymous binding is supported for clients that are authenticating to the LDAP server.
- If the mail attribute is specified for LDAP accounts, it must have a non-null value that is unique for each user.
- LDAPS is supported, but the required certificates are not configured automatically by the deployment process.

For most user interfaces, such as SAS Drive, configuring SAS Viya to access your LDAP server is a post-run task. For more information, see [Configure the Connection to Your Identity Provider](Post-run-Tasks#configure-the-connection-to-your-identity-provider).

### Transport Security Layer

SAS provides encryption in two contexts:

- Data at rest is data stored in databases, file servers, endpoint devices, and various storage networks. This data can be on-premises, virtual, or in the cloud. This data is usually protected in conventional ways by firewalls. Numerous layers of defense are needed, and encrypting sensitive data is another layer. You can also encrypt SAS data sets.
- Data in motion is data that is being transmitted to another location. Data is most vulnerable while in transit. Sensitive data in transit should be encrypted. You can also choose to protect all traffic in transit between servers and clients.

For a single container, see [How to Run: Docker](Build-and-Run-SAS-Viya-Single-Container#docker) for information about how to run with Transport Security Layer (TLS) enabled via Docker. For Kubernetes, see [Ingress Configuration](Pre-build-Tasks#ingress-configuration) for information about how to set up TLS.

For multiple containers, see [Ingress Configuration](Pre-build-Tasks#ingress-configuration) for information about how to set up TLS.

In this configuration, network connections from the httpproxy container to backend services are not encrypted.

## User and Group Requirements

### Requirements for the User Who Performs the Deployment

If you are using Docker run, instead of granting sudoers privileges to any user who will run Docker commands, you can create a Linux group named docker on the Docker host machine. Any users that you add to this group will automatically have Read/Write ownership of the Docker process. They will be able to run Docker commands without using sudo.

For more information about the `docker` group, see [https://docs.docker.com/install/linux/linux-postinstall/](https://docs.docker.com/install/linux/linux-postinstall/).

If you are using Kubernetes to deploy the software, there are no specific requirements for the deployment user.

### CAS Administrator Account Requirements

For a programming-only deployment, an administrative user is the only type of user that can log on to the CAS Server Monitor user interface in order to manage CAS settings. Therefore, a CAS administrator must be configured when the Docker image is launched. You can designate a user account for the CAS administrator by specifying the desired user name for the CASENV_ADMIN_USER variable.

For programming-only deployments, the CAS Administrator Account must have a valid host account. To support this, SAS provides the addons/auth-demo and addons/auth-sssd addons which allow for configuring the running container to have valid host accounts.
- If you use addons/auth-demo, the user defined will automatically be set as the CAS Administrator.
- If you use addons/auth-sssd, set the CASENV_ADMIN_USER to a user name available via the sssd configuration.

**Note:** For more information about the _auth_ addons, see [Host Authentication](Pre-build-Tasks#host-authentication).

If you provide a different way to setup host level authentication in the container, then make sure to set CASENV_ADMIN_USER to a valid user name.

For full deployments, see [Identity Management: CAS Roles](https://go.documentation.sas.com/?cdcId=calcdc&cdcVersion=3.4&docsetId=calids&docsetTarget=p1ekhq4bpia742n1lmk8ylsrtgao.htm) in _SAS Viya Administration_.

### User Account Requirements

- For the single Docker image and the programming, computeserver and sas-casserver-primary Docker images, the following requirements exist:

  - Users must have a home directory
  - Users must be able to authenticate via the host
  - Users must be configured the same way across the set of running containers, which means they should have the same user ids, group ids, home directories and password.

- For a full deployment, you will configure the system for Identity Management as a post-deployment task.

**Note:** For more information about which users are used for the different images, see [Appendix: Under the Hood](https://gitlab.sas.com/sassoftware/sas-container-recipes/wikis/Appendix:-Under-the-Hood).

## Client Requirements

### Web Browsers

End users can access the product user interfaces for SAS Viya applications from a desktop computer, using a supported web browser. Because SAS software is not installed on this machine, the requirements are minimal. UNIX and 64-bit Windows operating systems are supported.

Some SAS Viya user interfaces include some advanced features that require recent versions of popular web browsers. For information about supported web browsers and the corresponding platforms to access SAS user interfaces, see [Support for Web Browsers in SAS Viya 3.4](https://support.sas.com/en/documentation/third-party-software-reference/viya/34/support-for-web-browsers.html).

### Mobile Platform and Touchscreen Support

The SAS Visual Analytics Apps run natively on iOS, Android, and Windows 10, and provide the ability to view and explore reports using a touchscreen.

Some SAS Viya user interfaces are not currently supported on mobile devices.

For more information about mobile device support, see [Support for Web Browsers in SAS Viya 3.4](https://support.sas.com/en/documentation/third-party-software-reference/viya/34/support-for-web-browsers.html).

### Database Drivers

Make sure that each client where users will access SAS software has the required database drivers already installed.

### Screen Resolution

The minimum screen resolution for each client machine that will access the SAS Viya user interfaces is 1280 x 1024.