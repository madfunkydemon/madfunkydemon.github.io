---
layout: post
title: 'Quickly Remove Comments from Configuration Files'
categories:
- linux/unix
- os x
---
Configuration files can be long and complex and it is hard to see which values have been set. There are numerous ways to do this however, grep with -v (--invert-match) is a quick way to achieve this. The following example removes all the comments from an elasticsearch configuration file:

```
ed@es01:~$ sudo grep -v '#' /etc/elasticsearch/elasticsearch.yml
```

Which returns:

```
cluster.name: es
node.name: es01
network.host: 10.1.10.187
discovery.zen.ping.unicast.hosts: ["10.1.10.187", "10.1.10.124"]
discovery.zen.minimum_master_nodes: 2
```

Five lines where it is easy to see what has been configured. Rather than:

```
ed@es01:~$ sudo wc -l /etc/elasticsearch/elasticsearch.yml
94 /etc/elasticsearch/elasticsearch.yml
```

So we have removed 89 lines of comments and can review the configuration in five. Time saved!