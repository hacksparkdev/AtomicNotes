
#### Date: 2024-10-06
 Tags: [[TheHive]] [[Cyber Security]] 

---

## Overview: Specification 
RAM: 8GB+ (Recommend 16 GB)
HDD: 50+ GB
OS: Ubuntu 22.04 LTS
Installing TheHive 5

---

## Prerequisites: Dependencies

``` Terminal 

apt install wget gnupg apt-transport-https git ca-certificates ca-certificates-java curl  software-properties-common python3-pip lsb-release
```


---

## Installation Steps:

###  Step 1 - Install Java
``` Terminal 

wget -qO- https://apt.corretto.aws/corretto.key | sudo gpg --dearmor  -o /usr/share/keyrings/corretto.gpg
echo "deb [signed-by=/usr/share/keyrings/corretto.gpg] https://apt.corretto.aws stable main" |  sudo tee -a /etc/apt/sources.list.d/corretto.sources.list
sudo apt update
sudo apt install java-common java-11-amazon-corretto-jdk
echo JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto" | sudo tee -a /etc/environment
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto"

```


### Step 2 - Install Cassandra 
```Terminal 
wget -qO - [https://downloads.apache.org/cassandra/KEYS](https://downloads.apache.org/cassandra/KEYS) | sudo gpg --dearmor -o /usr/share/keyrings/cassandra-archive.gpg echo "deb [signed-by=/usr/share/keyrings/cassandra-archive.gpg] [https://debian.cassandra.apache.org](https://debian.cassandra.apache.org/) 40x main" | sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list sudo apt update sudo apt install cassandra

```

### Step 3 - Install Elastic Search 
```Terminal 

wget -qO - [https://artifacts.elastic.co/GPG-KEY-elasticsearch](https://artifacts.elastic.co/GPG-KEY-elasticsearch) | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg sudo apt-get install apt-transport-https echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] [https://artifacts.elastic.co/packages/7.x/apt](https://artifacts.elastic.co/packages/7.x/apt) stable main" | sudo tee /etc/apt/sources.list.d/elastic-7.x.list sudo apt update sudo apt install elasticsearch
```

#### Optional 
Create a jvm.options file under /etc/elasticsearch/jvm.options.d and put the following configurations in that file. -Dlog4j2.formatMsgNoLookups=true -Xms2g -Xmx2g

### Step 4 - Install The Hive 
```Terminal 
wget -O- [https://archives.strangebee.com/keys/strangebee.gpg](https://archives.strangebee.com/keys/strangebee.gpg) | sudo gpg --dearmor -o /usr/share/keyrings/strangebee-archive-keyring.gpg echo 'deb [signed-by=/usr/share/keyrings/strangebee-archive-keyring.gpg] [](https://deb.strangebee.com/)[https://deb.strangebee.com](https://deb.strangebee.com) thehive-5.2 main' | sudo tee -a /etc/apt/sources.list.d/strangebee.list sudo apt-get update sudo apt-get install -y thehive

Default Credentials on port 9000 credentials are 'admin@thehive.local' with a password of 'secret'
```

---

# Setup 

### Cassandra Configuration 

#### Step 1 - Nano 
```Terminal 
/etc/elasticsearch/cassandra.yaml 
```

- Use control W to search inside of nano 
- Look For Listen, rcp_client, and seed Provider 

```Terminal 
sudo systemctl stop cassandra 
```






---
## Troubleshooting (Optional):


---


