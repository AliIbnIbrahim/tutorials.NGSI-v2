# Smart Supermarket Tutorials[<img src="https://img.shields.io/badge/NGSI-v2-5dc0cf.svg" width="90"  align="left" />]("https://fiware-ges.github.io/orion/api/v2/stable/)[<img src="docs/img/logo.png" align="left" width="162">](https://www.fiware.org/)

[![Documentation](https://nexus.lab.fiware.org/repository/raw/public/badges/chapters/documentation.svg)](https://fiware-tutorials.rtfd.io)
[![License: MIT](https://img.shields.io/github/license/fiware/tutorials.Step-by-Step.svg)](https://opensource.org/licenses/MIT)
[![Support badge](https://img.shields.io/badge/tag-fiware-orange.svg?logo=stackoverflow)](https://stackoverflow.com/questions/tagged/fiware)
[![Docker](https://img.shields.io/docker/pulls/fiware/tutorials.context-provider.svg)](https://hub.docker.com/r/fiware/tutorials.context-provider/)
<br> [![Documentation](https://img.shields.io/readthedocs/fiware-tutorials.svg)](https://fiware-tutorials.rtfd.io)
[![CI](https://github.com/FIWARE/tutorials.Step-by-Step/workflows/CI/badge.svg)](https://github.com/FIWARE/tutorials.Step-by-Step/actions?query=workflow%3ACI)

This is a collection of tutorials for the FIWARE ecosystem designed for **NGSI-v2** developers. Each tutorial consists
of a series of exercises to demonstrate the correct use of individual FIWARE components and shows the flow of context
data within a simple Smart Solution either by connecting to a series of dummy IoT devices or manipulating the context
directly or programmatically.

| :books: [NGSI-v2<br>Documentation](https://fiware-tutorials.rtfd.io) | <img src="https://assets.getpostman.com/common-share/postman-logo-stacked.svg" align="center" height="25"> [Postman<br>Collections](https://explore.postman.com/team/3mM5EY6ChBYp9D) | [![Docker Hub](https://nexus.lab.fiware.org/repository/raw/public/badges/docker/fiware.svg)](https://hub.docker.com/u/fiware) <br> [![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/fiware)](https://artifacthub.io/packages/search?repo=fiware) | <img src="https://fiware.github.io/catalogue/img/fiware-emoji.png" height="20px" width="20px"/><br/> [**developer&ZeroWidthSpace;.fiware.org**](https://www.fiware.org/developers/) |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

🇯🇵 このチュートリアルは[日本語](https://fiware-tutorials.letsfiware.jp/)でもご覧いただけます。<br/>

<h3>Data models</h3>

The following NGSI-v2 and NGSI-LD Data models are used within the tutorials:

-   <img src="https://json-ld.org/favicon.ico" align="center" height="25"/>
    [Tutorial-specific Data Models](https://fiware.github.io/tutorials.Step-by-Step/schema/)
-   <img src="https://json-ld.org/favicon.ico" align="center" height="25"/>
    [Smart Data Models](https://smartdatamodels.org)


## Systems:
Tested Ubuntu 22.04 8G disk 4GRam
- bare machine
- virtual box
- Openstack
- LXC (proxmox-pve)

next test:
Debian 11

https://www.fosslinux.com/49959/install-docker-on-debian.htm


## Install

To update upgrade and install needed tools:
```console
sudo apt update 
sudo apt upgrade
sudo apt install git
```


To download the full set of tutorials, simply clone this repository:

```console
git clone https://github.com/FIWARE/tutorials.NGSI-v2.git
cd tutorials.NGSI-v2/
git submodule update --init --recursive
```

### Docker and Docker Compose <img src="https://www.docker.com/favicon.ico" align="left"  height="30" width="30">

Each tutorial runs all components using [Docker](https://www.docker.com). **Docker** is a container technology which
allows to different components isolated into their respective environments.

-   To install Docker on Windows follow the instructions [here](https://docs.docker.com/docker-for-windows/)
-   To install Docker on Mac follow the instructions [here](https://docs.docker.com/docker-for-mac/)

#### Install Docker Engine on Ubuntu
-   from this  [link](https://docs.docker.com/engine/install/ubuntu/#set-up-the-repository)
Install using the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

1. Set up the repository:  Update the apt package index and install packages to allow apt to use a repository over HTTPS:

```console
 sudo apt-get update
 sudo apt-get install ca-certificates curl gnupg lsb-release
```
2. Add Docker’s official GPG key:

```console
 sudo mkdir -p /etc/apt/keyrings
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
3. Use the following command to set up the repository:

```console
 echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
4. Install Docker Engine
Update the apt package index:

```console
sudo apt-get update
```
 
  Install latest Docker Engine, containerd, and Docker Compose:
  
```console
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

**Docker Compose** is a tool for defining and running multi-container Docker applications. A series of `*.yaml` files
are used configure the required services for the application. This means all container services can be brought up in a
single command. 

You can check your current **Docker** and **Docker Compose** versions using the following commands:

```console
docker version
docker compose version
```

Please ensure that you are using Docker version 20.10 or higher and Docker Compose 1.29 or higher and upgrade if
necessary.

### Postman <img src="./docs/img/postman.png" align="left"  height="25" width="25">

The tutorials which use HTTP requests supply a collection for use with the Postman utility. Postman is a testing
framework for REST APIs. The tool can be downloaded from [www.postman.com](https://www.postman.com/downloads/). All the
FIWARE Postman collections can be downloaded directly from the
[Postman API network](https://explore.postman.com/team/3mM5EY6ChBYp9D)

### GitPod <img src="https://gitpod.io/favicon.ico" align="left"  height="30" width="30">

[Gitpod](https://github.com/gitpod-io/gitpod) is an open-source Kubernetes application for ready-to-code cloud
development environments that spins up an automated dev environment for each task, in the cloud. It enables you to run
the tutorials in a cloud development environment directly from your browser or your Desktop IDE.

### Cygwin for Windows <img src="https://www.cygwin.com/favicon.ico" align="left"  height="30" width="30" style="border-right-style:solid; border-right-width:10px; border-color:transparent; background: transparent">

The tutorials start up their services using a simple Bash script. When working locally, Windows users should download
[cygwin](http://www.cygwin.com/) to provide a command-line functionality similar to a Linux distribution on Windows.

### Apache Maven <img src="https://maven.apache.org/favicon.ico" align="left"  height="30" width="30" style="border-right-style:solid; border-right-width:10px; border-color:transparent; background: transparent">

[Apache Maven](https://maven.apache.org/download.cgi) is a software project management and comprehension tool. Based on
the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a
central piece of information. Maven can be used to define and download our dependencies and to build and package Java or
Scala code into a JAR file.

## Tutorials List [<img src="https://img.shields.io/badge/NGSI-v2-5dc0cf.svg" width="90"  align="left" />]("https://fiware-ges.github.io/orion/api/v2/stable/)

### Core Context Management: NGSI-v2 Fundamentals

&nbsp; 101. [Getting Started](https://github.com/AliIbnIbrahim/tutorials.Getting-Started)<br/> &nbsp; 102.
[Entity Relationships](https://github.com/AliIbnIbrahim/tutorials.Entity-Relationships/tree/NGSI-v2)<br/> &nbsp; 103.
[CRUD Operations](https://github.com/AliIbnIbrahim/tutorials.CRUD-Operations/tree/NGSI-v2)<br/> &nbsp; 104.
[Context Providers](https://github.com/AliIbnIbrahim/tutorials.Context-Providers/tree/NGSI-v2)<br/> &nbsp; 105.
[Altering the Context Programmatically](https://github.com/AliIbnIbrahim/tutorials.Accessing-Context/tree/NGSI-v2)<br/>
&nbsp; 106. [Subscribing to Changes in Context](https://github.com/AliIbnIbrahim/tutorials.Subscriptions/tree/NGSI-v2)

### Internet of Things, Robots and third-party systems

&nbsp; 201. [Introduction to IoT Sensors](https://github.com/FIWARE/tutorials.IoT-Sensors/tree/NGSI-v2)<br/> &nbsp; 202.
[Provisioning an IoT Agent](https://github.com/FIWARE/tutorials.IoT-Agent/tree/NGSI-v2)<br/> &nbsp; 203.
[IoT over an MQTT Transport](https://github.com/FIWARE/tutorials.IoT-over-MQTT/tree/NGSI-v2)<br/> &nbsp; 204.
[Using an alternative IoT Agent](https://github.com/FIWARE/tutorials.IoT-Agent-JSON/tree/NGSI-v2)<br/> &nbsp; 205.
[Creating a Custom IoT Agent](https://github.com/FIWARE/tutorials.Custom-IoT-Agent/tree/NGSI-v2)<br/> &nbsp; 206.
[IoT over an IOTA Tangle Transport](https://github.com/FIWARE/tutorials.IoT-over-IOTA/tree/NGSI-v2)<br/>

<!-- &nbsp; 250. [Introduction to Fast-RTPS and Micro-RTPS](https://github.com/FIWARE/tutorials.Fast-RTPS-Micro-RTPS/tree/NGSI-v2) -->

### Core Context Management: Manipulating Context Data and Persisting Historic Data

&nbsp; 301. [Persisting Context Data using Apache Flume](https://github.com/FIWARE/tutorials.Historic-Context-Flume) -
MongoDB, MySQL, PostgreSQL<br/> &nbsp; 302.
[Persisting Context Data using Apache NIFI](https://github.com/FIWARE/tutorials.Historic-Context-NIFI) - MongoDB, MySQL,
PostgreSQL<br/> &nbsp; 303.
[Querying Time Series Data (MongoDB)](https://github.com/FIWARE/tutorials.Short-Term-History/tree/NGSI-v2)<br/>
&nbsp; 304.
[Querying Time Series Data (CrateDB)](https://github.com/FIWARE/tutorials.Time-Series-Data/tree/NGSI-v2)<br/>
&nbsp; 305. [Big Data Analysis (Flink)](https://github.com/FIWARE/tutorials.Big-Data-Flink/tree/NGSI-v2)<br/>
&nbsp; 306. [Big Data Analysis (Spark)](https://github.com/FIWARE/tutorials.Big-Data-Spark/tree/NGSI-v2)

### Security: Identity Management

&nbsp; 401.
[Managing Users and Organizations](https://github.com/FIWARE/tutorials.Identity-Management/tree/NGSI-v2)<br/>
&nbsp; 402. [Roles and Permissions](https://github.com/FIWARE/tutorials.Roles-Permissions/tree/NGSI-v2)<br/> &nbsp; 403.
[Securing Application Access](https://github.com/FIWARE/tutorials.Securing-Access/tree/NGSI-v2)<br/> &nbsp; 404.
[Securing Microservices with a PEP Proxy](https://github.com/FIWARE/tutorials.PEP-Proxy/tree/NGSI-v2)<br/> &nbsp; 405.
[XACML Rules-based Permissions](https://github.com/FIWARE/tutorials.XACML-Access-Rules/tree/NGSI-v2)<br/> &nbsp; 406.
[Administrating XACML via a PAP](https://github.com/FIWARE/tutorials.Administrating-XACML/tree/NGSI-v2)<br/> &nbsp; 407.
[Authenticating Identities (Open-ID Connect)](https://github.com/FIWARE/tutorials.Securing-Access-OpenID-Connect/tree/NGSI-v2)

### Processing, Analysis and Visualization

&nbsp; 501. [Creating Application Mashups](https://github.com/FIWARE/tutorials.Application-Mashup/tree/NGSI-v2)<br/>
&nbsp; 503. [Introduction to Media Streams](https://github.com/FIWARE/tutorials.Media-Streams/tree/NGSI-v2)<br/>
&nbsp; 507. [Cloud-Edge Computing](https://github.com/FIWARE/tutorials.Edge-Computing/tree/NGSI-v2)

### NGSI-LD for NGSI-v2 Developers

&nbsp; 601. [Introduction to Linked Data](https://github.com/FIWARE/tutorials.Linked-Data/tree/NGSI-v2)<br/> &nbsp; 602.
[Linked Data Relationships and Data Models](https://github.com/FIWARE/tutorials.Relationships-Linked-Data/tree/NGSI-v2)<br/>
&nbsp; 603.
[Traversing Linked Data Programmatically](https://github.com/FIWARE/tutorials.Accessing-Linked-Data/tree/NGSI-v2)<br/>
&nbsp; 604.
[Linked Data Subscriptions and Registrations](https://github.com/FIWARE/tutorials.LD-Subscriptions-Registrations/tree/NGSI-v2)<br/>

## Usage

Most tutorials supply a `services` script to start the containers:

```console
cd <tutorial-name>
./services start
```

### Following the tutorial exercises via Postman

Each tutorial submodule contains one or more `docker-compose.yml` files, along with a Postman collection containing the
necessary HTTP requests: import the collection into Postman and follow the instructions.

### Following the tutorial exercises from the command-line

Each submodule contains full instructions in README which details the appropriate bash commands (cUrl and Docker
Compose) to run.

Full instructions can be found within the [documentation](https://fiware-tutorials.rtfd.io)

---

## License

[MIT](LICENSE) © 2018-2023 FIWARE Foundation e.V.

https://choosealicense.com/licenses/

