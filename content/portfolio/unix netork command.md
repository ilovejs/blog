+++
showonlyimage = true
draft = false
image = ""
date = 2017-11-10T10:04:01+11:00
title = "Unix Network Commands"
weight = 0
tags = [ "Development", "Tool", "Blogging" ]
categories = [ "Development" ]
series = [ "Dev Tools" ]
slug = "unix_network_cmd"
+++

# traceroute

wait time 3s, send 1 query for each, max hop is 16. So stop at the 16th query to map out network layout.
    
    traceroute -w 3 -q 1 -m 16 blog.hurryduckling.com


