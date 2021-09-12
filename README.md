# Pihole installation on a kubernetes cluster

Create a sample [Pi-hole](https://pi-hole.net/) installation in your kubernetes cluster. The DNS service is exposed on port 53 on a dedicated IP address made available by [MetalLB](https://metallb.universe.tf/). This serves purely a home lab intent, don't use this anywhere in production!

Make use of the cool [Pihole Prometheus Exporter](https://github.com/eko/pihole-exporter) to export your metrics to Prometheus.

Installation manual

1) Create a password the pihole web interface:
```bash
 kubectl create secret generic pihole --from-literal=password=mypassword -n pihole
```

2) Adjust IP addresses and/or ingress domain

3) Run `kubectl apply -f pihole.yml` to create the resources in your cluster

4) Enjoy your lab pihole environment :-)
