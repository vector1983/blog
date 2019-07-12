---
title: "Visual studio code can't run in ubuntu, how to?"
date: 2019-07-11T11:25:55+08:00
draft: false
tags: ["visual studio code", "ubuntu"]
---
+ **Root Cause**: 
   This problem is that VS Code uses Electron, which is the root cause of the bug.  

+ **Fix**:  
   1. mkdir ~/lib
   2. cp /usr/lib/x86_64-linux-gnu/libxcb.so.1 ~/lib
   3. sed -i 's/BIG-REQUESTS/_IG-REQUESTS/' ~/lib/libxcb.so.1
   4. export LD_LIBRARY_PATH=~/lib && code

[reference!]https://stackoverflow.com/questions/55802252/visual-studio-code-wont-open-on-ubuntu-16-04-via-vnc 

