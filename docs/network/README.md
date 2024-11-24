# Fresh Guard - VPC Configuration

### VPC
- **Name:** `freshguard-network`
- **Mode:** Custom

#### **Subnets**
- **Subnet: Backend**
  - **IP Range:** `192.168.1.0/28`
  - **Region:** `southeast2` (Jakarta).

- **Subnet: Machine Learning**
  - **IP Range:** `192.168.1.16/28`
  - **Region:** `southeast2` (Jakarta).

- **Subnet: Database**
  - **IP Range:** `192.168.1.32/28`
  - **Region:** `southeast2` (Jakarta).

#### **Firewalls**
- **Allow SSH**
  - **Protocol:** TCP
  - **Port:** `22` (default SSH)
  - **Source IP Range:** `0.0.0.0/0` (bisa dibatasi untuk IP internal/administrator tertentu).

- **Allow HTTPS to Backend API**
  - **Protocol:** TCP
  - **Port:** `443` (karena HTTPS menggunakan port 443)
  - **Source IP Range:** `0.0.0.0/0` (publik).

- **Internal Communication**
  - **Protocol:** Semua (TCP, UDP, ICMP)
  - **Source IP Range:** `192.168.1.0/24` (untuk komunikasi antar subnet).

#### **Cloud NAT**
- **External IP:** Otomatis (gunakan IP public Google Cloud).
- **Region:** `southeast2` (Jakarta).

#### **Service Accounts**
- **Backend**
  - **Roles:**
    - `roles/compute.instanceAdmin.v1` (pengelolaan VM backend).
    - `roles/storage.objectViewer` (akses baca bucket GCS jika diperlukan).

- **ML VM**
  - **Roles:**
    - `roles/ml.developer` (menjalankan job Machine Learning).
    - `roles/storage.objectAdmin` (akses data model dan data training di bucket GCS).

- **Cloud SQL**
  - **Roles:**
    - `roles/cloudsql.client` (untuk menghubungkan VM ke database).
    - `roles/storage.objectViewer` (untuk membaca snapshot di bucket).

---

## Notes
1. Pastikan firewall rules hanya mengizinkan akses dari sumber yang terpercaya untuk meningkatkan keamanan.
2. Gunakan **Private Google Access** jika diperlukan agar resource dapat mengakses layanan Google Cloud tanpa menggunakan IP publik.
3. Monitor trafik dan performa dengan **Cloud Monitoring** dan **Cloud Logging** untuk menganalisa aktivitas jaringan dan resource.

---

> Konfigurasi ini dirancang untuk proyek **Fresh Guard** dengan fokus pada keamanan, efisiensi, dan skalabilitas jaringan di region Jakarta.
