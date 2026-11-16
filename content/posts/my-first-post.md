+++
date = '2026-09-05T12:47:31+08:00'
title = 'What happens when a pod sends a request?'
tags = ['mubernetes','networking']
+++

# Overview
Kubernetes netwokring involves a few components, including the DNS server, CNI, and kube-proxy.

## ClusterIP

### Request time
1. app dns resolver asks DNS server for the VIP (fqdn to VIP)
2. app sends the request to that VIP address
3. Kernel intercepts and looks up the mapping of VIP to a list of pod ips on either iptable or eBPF map. Then sends the packets out.


## Headless

### Request Time
1. app dns resplver asks DNS server for the ip to fqdn, the server returns a list of actual pod ips.
2. app decides which pod ip to send to
3. Kernel intercept but finds no mapping to translate

## Introduction

This **blog** is powered by *hugo*.

Visit the [Hugo](https://gohugo.io) website!
