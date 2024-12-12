# Zabbix for Mainframe

In the actual Mainframe transformation and modernization processes, key aspects are lack of skills and cost reduction, one way to mitigate this is using distributed world tools that allow to extend its capabilities (human resources and software) at least support level 1 and/or 2, leaving Mainframe specialists to the limited deep analysis.

Among the tools available today and that have proven their usability on the Mainframe platform, we have:

## Distributed side

  - Zabbix: is an open-source software tool to monitor IT infrastructure such as networks, servers, virtual machines, and cloud services [https://www.zabbix.com]

  - Prometheus: is an open-source systems monitoring and alerting toolkit [https://prometheus.io/]

  - Grafana:  is a multi-platform open source analytics and interactive visualization web application. It can produce charts, graphs, and alerts for the web when connected to supported data 
    sources [https://grafana.com/]

  - Zebra: XML2JSON adapter for RMF DDS portal [https://github.com/zowe/zebra] 

## Mainframe side

RMF (Resource Measurement Facility):

  - Monitor III: gives you a single point of control for monitoring resource usage within a sysplex

  - DDS portal: offers an HTTP API which can access short-term data from the Monitor III as well as long-term data from the Postprocessor. An application program can send an HTTP request for selected performance data to the DDS.

 
# Actual situation
Zebra collects the RMF III information in real time through DDS portal and write it in Prometheus (TSDB), MongoDB (optional) and/or may be accesses directly. Then Grafana do the magic presenting the information in different attractive ways with the capacity to stablish alarms and alerts and taking the traditional operational Mainframe environment to the observability world.

You have detailed information outside Mainframe, with the history you want (detailed: 3 months) and with the capacity to build a federated TSDB schema, where the aggregated information is stored in another DB (TSDB) for long term (aggregated: p.e 25 months) for capacity purpose.
For Mainframe people: the best defined WLM (appropriated report classes, transactions, etc.), provides more rich information you can process and present in real time.
 
 
# Prototype situation

With a similar reference model, but using Zabbix as a second collector, the complete Zabbix functionality is added to the monitoring of Mainframe platform 
 
In this stage we are now collecting the full information of 10 RMF tables.
The Zabbix reference model stablish in a way that it is very simple to add new servers (LPARs) is:

 

 
# Next steps:

•	Convert the full RMF III tables (37 tables with ~ 800 metrics) (https://www.ibm.com/docs/en/zos/2.4.0?topic=midrt-monitor-iii-data-reporter-tables) to a Zabbix Mainframe template (now are 10 tables)

•	Add Anomaly detection, Base Monitoring and Predicitive Monitoring to selected metrics of the model

•	Do the process with a Python program so the process is easily repeatable and enhanced, with the option to decide which metrics activate and the statistical functions you want to apply

•	Define and refine the tags assignment (host and metrics level)

•	Convert (Prometheus) and complement (Zabbix) the actual solution in Grafana




