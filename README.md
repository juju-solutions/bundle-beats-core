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

Deployment is straight forward. Deploy the beats-core bundle to stand up the
log aggregation and visualization applications, and relate the agents to your
services. Load the example dashboard and you're ready to go!

    juju deploy myservice
    juju deploy ~containers/bundle/beats-core
    juju add-relation filebeat:beats-host myservice
    juju add-relation topbeat:beats-host myservice

With our services on the way, once the model has settled deploy the beats
dashboard in Kibana.

    juju action do kibana/0 deploy-dashboard dashboard=beats

You will notice new indexes in kibana, and some default demonstration dashboards
have been loaded. This is a full beats suite dashboard. You can now navigate
to http://<kibana-public-ip>/dashboards and load up the topbeat dash and you're
in business!

Note: This demo dashboard also ships with visualizations we are not yet
populating for winlogbeat beats.

## Contact information

- Charles Butler &lt;charles.butler@canonical.com&gt;
- Matt Bruzek &lt;matthew.bruzek@canonical.com&gt;

# Need Help?

- [Juju mailing list](https://lists.ubuntu.com/mailman/listinfo/juju)
- [Juju Community](https://jujucharms.com/community)
