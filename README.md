<div align="center">  
<h1>SAS<sup>®</sup> Viya<sup>®</sup> Container Recipes</h1>
<img src="docs/sas-container-icon.jpg" alt="SAS Containers Icon" height="200">
<p>Framework to build SAS Viya Docker images and create deployments using Kubernetes.</p>

<a href="https://www.sas.com/en_us/software/viya.html">
    <img src="https://img.shields.io/badge/SAS%20Viya-3.4-blue.svg?&colorA=0b5788&style=for-the-badge&logoWidth=30&logo=data:image/png;base64,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"
        alt="SAS Viya Version"/></a>
<a href="https://www.docker.com/">
    <img src="https://img.shields.io/badge/Docker--ce-18+-blue.svg?&style=for-the-badge&colorA=066da5"
        alt="Docker Version"></a>
<a href="https://kubernetes.io/">
    <img src="https://img.shields.io/badge/Kubernetes-1.0+-blue.svg?&style=for-the-badge&colorA=0b5788"
        alt="Kubernetes Version"></a>
<a href="https://github.com/ansible/ansible-container" alt="Ansible Container">
    <img src="https://img.shields.io/badge/Ansible%20Container-0.9+-lightgrey.svg?&style=for-the-badge" 
        alt="Ansible Container Version"/></a>
</div>

<br>
Container deployments are more lightweight and don't have as much
overhead as traditional virtual machines. By running a SAS engine inside a 
container, you can provision resources more efficiently to address a wide variety
of SAS workloads. Select a base SAS recipe and create custom containers 
with specific products or configurations – e.g, access to data sources, in-database
code and scoring accelerators, or specific analytic capabilities.
For more information see [SAS for Containers](http://support.sas.com/rnd/containers/).

<br>

## Quick Start
Use the instructions on this page to quickly build and launch SAS Viya containers. 
For more extensive infomation about building and launching SAS Viya containers, see the [GitHub Project Wiki Page](https://github.com/sassoftware/sas-container-recipes/wiki)

1. Locate your SAS Viya for Linux Software Order Email (SOE) and retrieve the 
`SAS_Viya_deployment_data.zip` file from it. Not sure if your organization 
purchased SAS Software? [Contact Us](https://www.sas.com/en_us/software/how-to-buy.html) 
or get [SAS License Assistance](https://support.sas.com/en/technical-support/license-assistance.html). 
If you have not purchased SAS Software but would like to give it a try, 
please check out our [Free Software Trials](https://www.sas.com/en_us/trials.html).
    
2. Download the latest <a href="https://github.com/sassoftware/sas-container-recipes/releases" alt="SAS Container Recipes Releases">
        <img src="https://img.shields.io/github/release/sassoftware/sas-container-recipes.svg?&colorA=0b5788&colorB=0b5788&style=for-the-badge&" alt="Latest Release"/></a> 
or `git clone git@github.com:sassoftware/sas-container-recipes.git`

3. Choose your flavor and follow the recipe to build, test, and deploy your container(s).

    a. If you are looking for an environment tailored towards individual data scientists and developers, you will be interested in a [SAS programming-only deployment running on a single container](https://github.com/sassoftware/sas-container-recipes#for-a-single-user---sas-viya-programming-only-deployment-running-on-a-single-container).

    b. If you would like an environment suitable for collaborative data science work, then you may be interested in a SAS programming-only deployment or a SAS Viya full [deployment on multiple containers](https://github.com/sassoftware/sas-container-recipes#for-one-or-more-users---sas-viya-programming-only-or-sas-viya-full-deployment-running-on-multiple-containers).

    c. For either single or multiple containers, addons found in the [addons/ directory](https://github.com/sassoftware/sas-container-recipes/tree/master/addons) can enhance the base SAS Viya images with SAS/ACCESS, LDAP configuration, and more. For each addon, review the [Appendix](https://github.com/sassoftware/sas-container-recipes/wiki/Appendix:-Under-the-Hood#addons) for important information and any possible prerequisite requirements.

<br>

---

<br>

# For a Single User - SAS Viya Programming-Only Deployment Running on a Single Container
Use these instructions to create a SAS Viya programming-only deployment in a single container for
an independent data scientist or developer to execute SAS code. All code and
data should be stored in a persistent location outside the container.
This deployment includes SAS Studio, SAS Workspace Server, and a CAS server,
which provides in-memory analytics for symmetric multi-processing (SMP).

**A [supported version](https://success.docker.com/article/maintenance-lifecycle) of [Docker-ce (community edition)](https://docs.docker.com/install/linux/docker-ce/centos/) is required.**

### Build the Image
Run the following to create a user 'sasdemo' with the password 'sasdemo' for product evaluation.
A [non-root user](https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user) 
is recommended for all build commands.
```
 ./sas-container-recipes --zip ~/my/path/to/SAS_Viya_deployment_data.zip --addons "addons/auth-demo"
```                         

### Run the Container

After the container is built then instructions for how to run the image will be printed out.
```
 docker run --detach --rm --hostname sas-viya-programming \
 --env CASENV_CAS_VIRTUAL_HOST=<my_host_address> \
 --env CASENV_CAS_VIRTUAL_PORT=8081 \
 --publish-all \
 --publish 8081:80 \
 --name sas-viya-programming \
 sas-viya-programming:<VERSION-TAG>  
```
Use the `docker images` command to see what images were built and what the most recent tag is (example: tag `19.0.1-20190109112555-48f98d8`).
Once the docker run command is completed, use docker ps to list the running container.  
Finally go to the address `http://<myhostname>:8081` and start using SAS Studio!

For more info see the [GitHub Project Wiki Page](https://github.com/sassoftware/sas-container-recipes/wiki).

<br>

---

<br>

# For One or More users - SAS Viya Programming-Only or SAS Viya Full Deployment Running on Multiple Containers
Use these instructions to build multiple Docker images and then use the images 
to create a SAS Viya programming-only or a SAS Viya full deployment in Kubernetes. 
These deployments can have SMP or massively parallel processing (MPP) CAS servers,
which provide in-memory analytics, and can be used by one or more users. 

A programming-only deployment supports data scientists and programmers who use 
SAS Studio or direct programming interfaces such as Python or REST APIs. 
Understand that this type of deployment does not include SAS Drive, 
SAS Environment Manager, and the complete suite of services that are 
included with a full deployment. Therefore, make sure that you are providing 
your users with the features that they require.

### Prerequisites
- A [supported version](https://success.docker.com/article/maintenance-lifecycle) of [Docker-ce](https://docs.docker.com/install/linux/docker-ce/centos/) (community edition) on Linux or Mac must be installed on the build machine
- Python2 with python-pip2 and virtualenv or Python3 and python-pip3 must be installed on the build machine
- `java-1.8.0-openjdk` or another Java Runtime Environment (1.8.x) must be installed on the build machine
- **Access to a Docker registry:** The build process will push built Docker images automatically to the Docker registry. Before running `sas-container-recipes` do a `docker login docker.registry.company.com` and make sure that the `$HOME/.docker/config.json` is filled in correctly.
- Access to a Kubernetes environment and [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed: required for the deployment step but not required for the build step.
- **Strongly recommended:** A local mirror of the SAS software. [Here's why](https://github.com/sassoftware/sas-container-recipes/wiki/The-Basics#why-do-i-need-a-local-mirror-repository). 

### How to Build
Examples of running sas-container-recipes to build multiple containers are provided below. A non-root user is recommended for all build commands.

**Example: Programming-Only Deployment, Mulitple Containers**

```    
  ./sas-container-recipes \
  --type multiple \
  --zip /path/to/SAS_Viya_deployment_data.zip \
  --docker-registry-namespace myuniquename \
  --docker-registry-url myregistry.myhost.com \
  --virtual-host user-myproject.mylocal.com \
  --addons "addons/auth-demo"
```

**Example: Full Deployment, Multiple Containers**

```
  ./sas-container-recipes \
  --type full \
  --zip /path/to/SAS_Viya_deployment_data.zip \
  --docker-registry-namespace myuniquename \
  --docker-registry-url myregistry.myhost.com \
  --virtual-host user-myproject.mylocal.com \
  --addons "addons/auth-sssd"
```

**sas-container-recipes Arguments**

```
# Required Arguments

  --type [multiple | full]
    sets the deployment type.
    multiple: SAS Viya programming-only deployment, multiple containers using Kubernetes
    full: SAS Viya full deployment, multiple containers using Kubernetes.

  --zip <value>
    specifies the path to the SAS_Viya_deployment_data.zip file, which is from your Software Order Email (SOE).
    Example: /my/path/to/SAS_Viya_deployment_data.zip
    
  --docker-registry-namespace <value>
    specifies the namespace in the Docker registry where the Docker images will be pushed. 
    Use a unique name to prevent collisions.
    Example: myuniquename

  --docker-registry-url <value>
    specifies the URL of the Docker registry where Docker the images will be pushed.
    Required for Kubernetes.
    Examples: 10.12.13.14:5000 or myregistry.myhost.com                  

# Optional Arguments 

  --virtual-host
    specifies the Kubernetes Ingress path that defines the location of the HTTP endpoint.
    For details about Ingress, see the official Kubernetes documentation at 
    https://kubernetes.io/docs/concepts/services-networking/ingress/.
    Example: user-myproject.mylocal.com

  --addons "[<value>] [<value>]"
    adds one or more software layers to the main SAS image.
    For more information about addons, see 'Appendix: Under the Hood' in the wiki at 
    https://github.com/sassoftware/sas-container-recipes/wiki/Appendix:-Under-the-Hood
    Example: --addons \"addons/auth-sssd addons/access-postgres\"

  --baseimage <value>
    specifies the Docker image from which the SAS images will build on top of
    Default: centos

  --basetag <value>
    specifies the Docker tag for the base image that is being used.
    Default: latest

  --mirror-url <value>
    specifies the location of the mirror URL. See the Mirror Manager guide at
    https://support.sas.com/en/documentation/install-center/viya/deployment-tools/34/mirror-manager.html

  --platform <value>
    specifies the type of distribution of the image defined by the \"baseimage\" option.
    Options: [ redhat ]
    Default: redhat

  --skip-docker-url-validation
    skips validating the Docker registry URL.

  --skip-mirror-url-validation
    skips validating the mirror URL from the --mirror-url flag.

  --sas-docker-tag
    specifies the tag to apply to the images before pushing to the Docker registry.
    Default: ${recipe_project_version}-${datetime}-${last_commit_sha1}
    Example: 18.12.0-20181209115304-b197206
```

### How to Run

* For a SAS Viya programming-only deployment, the Kubernetes manifests are located at `$PWD/viya-programming/viya-multi-container/working/manifests`
* For a SAS Viya full deployment, the Kubernetes manifests are located at `$PWD/viya-visuals/working/manifests`

Choose between SMP or MPP and run a 
`kubectl create --file` or `kubectl replace --file` on the manifests inside the kubernetes directory.

**Note:** If you are running the build process process multiple times then use `kubectl replace` to add your new manifests instead of `kubectl create`.

Then add hosts to your Kubernetes Ingress for `sas-viya-httpproxy` and other services using `kubectl edit ingress`. In the following example, `user-myproject.mylocal.com` represents the Kubernetes Ingress path.

```
# Kubernetes Ingress Example

  apiVersion: extensions/v1beta1
  kind: Ingress
  metadata:
    namespace: <myuniquename>
    name: example ingress
  spec:
    rules:
    - host: user-myproject.mylocal.com
      http:
        paths:
        - backend:
            serviceName: sas-viya-httpproxy
            servicePort: 80
```
For more details on Ingress Controllers see [the official Kubernetes documentation](https://kubernetes.io/docs/concepts/services-networking/ingress/).

Finally, go to the host address that's defined in your Kubernetes Ingress to view your SAS product(s). Using the example Ingress configuration above, the URL is http://<span></span>user-myproject.mylocal.com.

If there is no response from the host, then check the status of the containers by running `kubectl get pods`.
There should be one or more `sas-viya-<service>` pods, depending on your software order. It may take several
minutes to see a login screen, even with all pods showing a "Running" status.
You may also need to correct the host name on your Ingress Controller and check your Kubernetes configurations.

<img src="docs/sas-logon-screen.png" alt="SAS Logon Screen" style="width: 100%; height: 100%; object-fit: contain;">

<br>

---

<br>

## Additional Resources

- [Wiki: Documentation](https://github.com/sassoftware/sas-container-recipes/wiki)
- [Issues: Questions and Project Improvements](https://github.com/sassoftware/sas-container-recipes/issues)
- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [Docker Documentation](https://docs.docker.com/)
- [SAS License Assistance](https://support.sas.com/en/technical-support/license-assistance.html)
- [SAS Software Purchase](https://www.sas.com/en_us/software/how-to-buy.html)
- [SAS Software Trial](https://www.sas.com/en_us/trials.html)

<br>

---

<br>

## Copyright

Copyright 2018 SAS Institute Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

&nbsp;&nbsp;&nbsp;&nbsp;https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
