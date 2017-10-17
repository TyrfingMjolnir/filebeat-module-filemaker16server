# filebeat-module-filemaker16server
This is a project adopting the logs of FileMaker 16 Server to the filebeat shipper for elasticsearch aka elk-stack

The purpose of this module is to give you as the user the ability to browse your FileMaker 16 Server logs visually using kibana, or elasticsearch in other ways to analyze your logs.

This piece of software was written by Arne Rolf Heier and Gjermund Gusland Thorsen; even though we claim the copyright this software is free for you to use and modify as long as the original authors are credited. This piece of software comes with no warranty what so ever. Use it at your own risk.

# Current status is: access, deployment, event, fmdapi, stats, wpe, and wpe_debug -logs are ready for testing.

# Pre-requisite

```Sh
sudo bin/elasticsearch-plugin install ingest-geoip
```
```log
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@     WARNING: plugin requires additional permissions     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
* java.lang.RuntimePermission accessDeclaredMembers
See http://docs.oracle.com/javase/8/docs/technotes/guides/security/permissions.html for descriptions of what these permissions allow and the associated risks.
```
[link](http://docs.oracle.com/javase/8/docs/technotes/guides/security/permissions.html)

# Some notes

http://help.filemaker.com/app/answers/detail/a_id/6551/~/tracking-activity-in-log-files-in-filemaker-server
https://www.elastic.co/guide/en/beats/devguide/current/filebeat-modules-devguide.html

To reset the pipeline grok interpretation after making a change to the module:
```Sh
curl -XDELETE http://localhost:9200/_ingest/pipeline/filebeat-5.6.2--filemaker-pipeline
```
Remember \\\ in filebeat = \ in logstash for escaping.
