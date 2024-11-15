# Estimasi Cloud Cost (Back-End menggunakan GCE)

## Cost Total
Total : $54.34

>Tambahan: ML VM Instace bisa ditingkatkan lagi hingga e2-standard-2 vCPUs: 2, RAM: 8 GiB dengan Total Cost $87.23 / month

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

2. Back-End Cloud Run
    * Resource Type: Service
    * Amount CPU per Instance: 2
    * RAM: 1GB
    * CPU Alocation: CPU allocated only request processing
    * Minimum Instance: 0
    * Request per month: 1 million
    * Execution time per Request: 500ms
    * Number of concurrent request per instance: 80
    * Region: asia-southeast2 (Jakarta) - Tier 2
    * Cost : $0.44 / month

3. Cloud Run Job
    * Resource Type: Job
    * Amount CPU per Instance: 1
    * RAM: 0.5GB
    * Execution permonth: 100
    * Execution time per Task: 5 minutes
    * Region: asia-southeast2 (Jakarta) - Tier 2
    * Cost : $0.68 / month

4. Cloud SQL (MySQL)
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

5. Artifact Registry
    * Storage: 1GB
    * Cost: $0.05 / month
> Note: Artifact Registry memiliki free tier 0.5GB, untuk lebih dari itu dikenakan 0.1$/GB <br>
> Note: Artifact Repository harus menggunakan lokasi yang sama dengan service yang lain, agar tidak dikenakan biaya transfer data 

6. Cloud Build
    * Pool Type: Standard
    * Machine Type: e2-medium
    * Build Minutes: 300 (5 Jam)
    * Cost: $0.90 / month

7. Network Data Transfer
    * Internet Transfer
        * Network Service Tier: Standard Tier
        * Data: 5GB
        * Source Location: Jakarta (asia-southeast2)
    * Internal Transfer
        * Network Traffic Type: Intra-Region
        * Data: 5GB
        * Region: Indonesia
    * Cost: $0.05 / month

8. NAT Gateway
    * Type: public NAT
    * Instance: 1
    * Data: 2GB
    * IP Address used: 1
    * Cost: $4.76 / month
