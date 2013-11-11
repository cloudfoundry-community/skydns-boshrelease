# BOSH Release for SkyDNS

SkyDNS is a distributed service for announcement and discovery of services. It leverages Raft for high-availability and consensus, and utilizes DNS for queries to discover available services. This is done by leveraging SRV records in DNS, with special meaning given to subdomains, priorities and weights.

[Source Code](https://github.com/skynetservices/skydns) | [Announcement Blog Post](http://blog.gopheracademy.com/skydns "Gopher Academy Blog")

This project is a BOSH release for describing a single or cluster group of SkyDNS servers.

## Cluster of skydns

```
# skydns/0
2013/11/11 06:03:50 Initializing Server. DNS Addr: "0.0.0.0:53", HTTP Addr: "0.0.0.0:8080", Data Dir: "/var/vcap/data/sys/log/skydns"
2013/11/11 06:03:50 Initializing new cluster
2013/11/11 06:04:14 Processing incoming join
2013/11/11 06:04:14 Processing incoming join

# skydns/1
2013/11/11 06:04:14 Initializing Server. DNS Addr: "0.0.0.0:53", HTTP Addr: "0.0.0.0:8080", Data Dir: "/var/vcap/data/sys/log/skydns"
2013/11/11 06:04:14 Joining cluster: 10.244.0.6:8080
2013/11/11 06:04:14 Attempting to connect to: 10.244.0.6:8080
2013/11/11 06:04:14 Post returned
2013/11/11 06:04:14 Joined cluster
```


## Using this BOSH release

To upload the latest final release to your BOSH:

```
git clone https://github.com/drnic/skydns-boshrelease.git
cd skydns-boshrelease
bosh upload release releases/skydns-1.yml
```

