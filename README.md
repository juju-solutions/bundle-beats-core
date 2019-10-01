# Beats

Beats are the core of data shipping in the new Elastic Stack by Elastic Co.
Famous for their ELK stack, these succeed any agents you might be familiar with.

### Filebeat

A lightweight, open source shipper for log file data. As the next-generation
Logstash Forwarder, Filebeat tails logs and quickly sends this information to
Logstash for further parsing and enrichment or to Elasticsearch for centralized
storage and analysis.

### Topbeat

 A lightweight way to gather CPU, memory, and other per-process and
 system wide data, then ship it to Elasticsearch to analyze the results.

### Packetbeat

An open source project that is designed to provide
real‑time analytics for web, database, and other network protocols.

### Dockerbeat

A lightweight, open source shipper for docker daemon data. Dockerbeat polls
the Docker Engine daemon, and sends cpu, network, memory, and host
information to Logstash for further parsing and enrichment or to Elasticsearch
for centralized storage and analysis.


# Usage

Deployment is straight forward. Deploy the `beats-core` bundle to stand up the
log aggregation and visualization applications, and add relations to anything
you want to monitor. The following example monitors a simple `ubuntu`
application with `filebeat`:

    juju deploy ~elasticsearch-charmers/bundle/beats-core
    juju deploy bionic/ubuntu
    juju add-relation filebeat:beats-host ubuntu

Beat indexes are automatically created in kibana, and default demonstration
dashboards have been loaded. Once the model has settled, you can navigate to
`http://<kibana-public-ip>/`, select the filebeat index as the default, and
head over to the Discover tab to view logs collected from the `ubuntu`
application.

Note: This demo dashboard also ships with visualizations we are not yet
populating for winlogbeat beats.


# Contact information

- Elasticsearch Charmers &lt;elasticsearch-charmers@lists.launchpad.net&gt;


# Need Help?

- [Juju mailing list](https://lists.ubuntu.com/mailman/listinfo/juju)
- [Juju Community](https://jujucharms.com/community)
