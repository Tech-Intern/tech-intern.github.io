
**
---
layout: post
title:  Permission In Linux  Guide
date:   2020-01-07 18:03:00 +0400
image:  Se.jpg
tags:   [Guide, Permission In Linux]
---

## Permission In Linux


Two Type of Permission

 - DAC(Discretionary Access Control)
 - MAC(Mandatory Access Control)

**DAC  Permission**

![enter image description here](https://drive.google.com/drive/u/0/my-drive)

read(r)=4
write(w)=2
execute(x)=1

Three main component of file/floder

 1. User(owner)
 2. Group
 3. Other

![]({{site.baseurl}}/img/Selinux.jpg)
 
**Command for DAC permission** 

#chmod (change mode)

![enter image description here](https://drive.google.com/drive/u/0/my-drive)

In this case,
chmod  640 filename.txt

6(users can read and write of that file)
4(groups can only read)
0(there is no permission for other)

You want to add execute permission of all three component
#chmod  a+x filename.txt
#chmod 751 filename.txt

![enter image description here](https://drive.google.com/drive/u/0/my-drive)



