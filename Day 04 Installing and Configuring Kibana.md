# Day 04 Installing and Configuring Kibana

## 1. Introduction

- Goal: Set up and install a Kibana instance.
    
- Visit [elastic.co/downloads/kibana](https://www.elastic.co/downloads/kibana) to download Kibana.

## 2. Download and Install Kibana

Select `Deb x86_64` version (as of recording, version 8.15).

Copy the download link and use `wget` to download it in the SSH session:
   
```
wget https://artifacts.elastic.co/downloads/kibana/kibana-8.17.2-amd64.deb
```

Verify the download:

```
 ls
```

Install Kibana:
  
```
dpkg -i kibana-8.17.2-amd64.deb
```
## 3. Configure Kibana



