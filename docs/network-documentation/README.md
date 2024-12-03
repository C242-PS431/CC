# Dokumentasi VPC Network: Freshguard Network

## Overview
- **Maximum Transmission Unit**: 1460
- **VPC Network ULA Internal IPv6 Range**: Disabled
- **Subnet Creation Mode**: Custom subnets
- **Dynamic Routing Mode**: Regional
- **Best Path Selection Mode**: Legacy
- **Tags**: —

---

## Subnets

### Subnet: `privat`
- **Region**: asia-southeast2
- **IP Stack Type**: IPv4 (single-stack)
- **Primary IPv4 Range**:
  - **CIDR**: `192.168.2.0/24`
  - **Access Type**: Internal
  - **Reserved Internal Range**: None
- **Gateway**: `192.168.2.1`
- **Private Google Access**: On
- **Flow Logs**: Off
- **Hybrid Subnets**: Off

### Subnet: `public`
- **Region**: asia-southeast2
- **IP Stack Type**: IPv4 (single-stack)
- **Primary IPv4 Range**:
  - **CIDR**: `192.168.1.0/24`
  - **Access Type**: Internal
  - **Reserved Internal Range**: None
- **Gateway**: `192.168.1.1`
- **Private Google Access**: On
- **Flow Logs**: Off
- **Hybrid Subnets**: Off

---

## Static Internal IP Addresses

- **Name**: `serverless-ipv4-1733207977580884515`
- **Internal IP Address**: `192.168.2.16`
- **Subnetwork**: `privat`
- **Region**: asia-southeast2
- **Version**: IPv4

---

## Firewall Rules

### Rule: `freshguard-network-allow-https`
- **Logs**: Off
- **Network**: `freshguard-network`
- **Priority**: 1000
- **Direction**: Ingress
- **Action on Match**: Allow
- **Target Tags**: `https-server`
- **IP Ranges**: `0.0.0.0/0`
- **Protocols and Ports**: `tcp:443`
- **Enforcement**: Enabled
- **Insights**: None

### Rule: `freshguard-network-allow-http`
- **Logs**: Off
- **Network**: `freshguard-network`
- **Priority**: 1000
- **Direction**: Ingress
- **Action on Match**: Allow
- **Target Tags**: `https-server`
- **IP Ranges**: `0.0.0.0/0`
- **Protocols and Ports**: `tcp:80`
- **Enforcement**: Enabled
- **Insights**: None

---

## VPC Network Peering

- **Name**: `servicenetworking-googleapis-com`
- **Network**: `freshguard-network`
- **Peered VPC Network**: `servicenetworking`
- **Peered Project ID**: `s9c50239878dce03cp-tp`
- **IP Stack Type**: IPv4 (single-stack)
- **Exchange IPv4 Custom Routes**: Export custom routes
- **Exchange Subnet Routes with Public IPv4**: None

---

## Private Service Access

- **Name**: `freshguard-network-service-range`
- **IP Range**: `10.240.0.0/16`
- **Service Producers**: Google Cloud Platform
- **VPC Peering Names**: `servicenetworking-googleapis-com`
