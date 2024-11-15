# Estimasi Cloud Cost (Back-End menggunakan GCE)

## Cost Total
Total : $71.06 / month
## Resources
1. ML VM Instance
    * Machine Type: e2-medium
    * Number of Instance: 1
    * vCPU: 1
    * RAM: 4GB
    * Boot Disk Type: Balanced Persistent Disk
    * Boot Disk: 10GB
    * Region: Jakarta (asia-southeast2)
    * Time : 730 Ours per month
    * Cost : $34.19/month

2. Back-End VM Instance
    * Machine Type: e2-small
    * Number of Instance: 1
    * vCPU: 0.5
    * RAM: 2GB
    * Boot Disk Type: Balanced Persistent Disk
    * Boot Disk: 10GB
    * External Static IP: 1
    * Region: Jakarta (asia-southeast2)
    * Time : 730 Ours per month
    * Cost : $17.79 / month

3. Cloud SQL (MySQL)
    * Edition: Enterprise
    * Machine Type: db-f1-micro
    * Number of Instance: 1
    * vCPU: 1
    * RAM: 3.75GB
    * Storage Type: SSD
    * Storage: 10GB
    * Region: Jakarta (asia-southeast2)
    * Time : 730 Ours per month
    * Cost : $13.32 / month

4. Artifact Registry
    * Storage: 1GB
    * Cost: $0.05 / month
> Note: Artifact Registry memiliki free tier 0.5GB, untuk lebih dari itu dikenakan 0.1$/GB <br>
> Note: Artifact Repository harus menggunakan lokasi yang sama dengan service yang lain, agar tidak dikenakan biaya transfer data 

5. Cloud Build
    * Pool Type: Standard
    * Machine Type: e2-medium
    * Build Minutes: 300 (5 Jam)
    * Cost: $0.90 / month

6. Network Data Transfer
    * Internet Transfer
        * Network Service Tier: Standard Tier
        * Data: 5GB
        * Source Location: Jakarta (asia-southeast2)
    * Internal Transfer
        * Network Traffic Type: Intra-Region
        * Data: 5GB
        * Region: Indonesia
    * Cost: $0.05 / month

<!-- 6. Pub/Sub
    * Published Data Daily: 0.3GB
> Note: Pubsub punya free tier 10GB / month -->

