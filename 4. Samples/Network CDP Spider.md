---
sort: 1
---

# Network CDP Spider

jimiFlow to spider a network from a given swtich using CDP

## Download

[Download](https://raw.githubusercontent.com/z1pti3/jimiFlows/master/CDP%20Spider/Network%20CDP%20Spider.json)

## Install

1. Import flow into a jimi conduct

2. Replace ssh_username, ssh_password and ssh_enable with the required values to enable swtich connection over ssh

3. Update the trigger to contain the starting switch information

![image](https://user-images.githubusercontent.com/66521110/135755097-c69802eb-56d8-4407-b3a2-4bfaa78d6079.png)

### *Note*
name within the events field for a given swtich must match the swtich name that you are connecting to otherwise the connection will fail

## Flow Screenshot

![image](https://user-images.githubusercontent.com/66521110/135755065-cdc4a0bd-36f4-4a73-a3e0-7a69f9bcf59f.png)
