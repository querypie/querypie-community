# QueryPie ACP Community Edition

## What is QueryPie Access Control Platform (ACP)?

QueryPie Access Control Platform (ACP) is an integrated access control solution that provides **DAC, SAC, KAC, WAC** in a single unified platform.
It covers both cloud and on-premises environments, providing unified management of all access from databases to systems, Kubernetes, and web applications.

### Core Product Components

* DAC (Database Access Controller): [Preview of Key Features](https://www.querypie.com/solutions/acp/database-access-controller)
* SAC (System Access Controller): [Preview of Key Features](https://www.querypie.com/solutions/acp/system-access-controller)
* KAC (Kubernetes Access Controller): [Preview of Key Features](https://www.querypie.com/solutions/acp/kubernetes-access-controller)
* WAC (Web Access Controller): [Preview of Key Features](https://www.querypie.com/solutions/acp/web-access-controller)

It enhances enterprise data security through RBAC/ABAC-based dynamic access control, web SQL editor, real-time auditing, and anomaly detection alerts. With Docker-based easy installation and web-based interface, it provides a hybrid solution that combines the convenience of SaaS with the powerful security of on-premises.


## 🧭 Before You Start
**QueryPie ACP Community Edition** lets you experience the key features available in **QueryPie ACP Enterprise Edition**:

**Important:** Community Edition supports **up to 5 active users** only.
*(If you need to register more than 5 users, please consider upgrading to the [Enterprise Plan](https://www.querypie.com/plans).)*

QueryPie ACP runs as a typical web application and also includes proxy-based network server functionality.

---

## 🖥️ Server Requirements

### Basic Specifications

- **CPU:** 4 vCPUs (AMD64 Architecture)
- **Memory:** 16 GB RAM
- **Storage:** 100 GB+ disk space
- **OS:** Linux with Docker or Podman

**Cloud Instances:**
- **AWS EC2:** `m6i.xlarge` or `m7i.xlarge`
- **GCP Compute Engine:** `c4-standard-4`, `n4-standard-4` (or any AMD64 -standard-4 models)

### Trial Use
For developers testing and trial purposes (ARM64 supported):

- **CPU:** 4 vCPUs (ARM64 Architecture)
- **Memory:** 16 GB RAM
- **Storage:** 30 GB+ disk space
- **OS:** Linux or macOS with Docker

**Cloud Instances:**
- **AWS EC2:** `t4g.xlarge` or `m7g.xlarge`

### Recommended for Production
For multi-user production environments:

- **CPU:** 8 vCPUs (AMD64 Architecture)
- **Memory:** 32 GB RAM
- **Storage:** 100 GB+ disk space
- **OS:** Linux with Docker or Podman

**Cloud Instances:**
- **AWS EC2:** `m6i.2xlarge` or `m7i.2xlarge`
- **GCP Compute Engine:** `c4-standard-8`, `n4-standard-8` (or any AMD64 -standard-8 models)

> **Note:** ARM64 Architecture CPU environments or macOS environments are recommended for trial use and testing purposes for developers.

> 📄 For detailed requirements, see: [Prerequisites](https://docs.querypie.com/installation/prerequisites)

---

## 🚀 Quick Installation

QueryPie installation is automated using Docker. Follow these simple steps:

### Step 1: Run Installation Command

Open your Linux server terminal and run this single command from your home directory:

```bash
bash <(curl -s https://dl.querypie.com/setup.v2.sh)
```

> ⏱️ **Installation time:** Typically 7-10 minutes

<p align="center">
  <img src="https://usqmjrvksjpvf0xi.public.blob.vercel-storage.com/main/public/documentation/install-guide-1-5WCes9Q5upf7mJGAWmsYJ6GozyUabS.png" alt="Installation started" style="max-width: 800px;" />
  <br/><em>Installation in progress</em>
</p>

### Step 2: Request License (During Installation)

While installation is running, apply for your free license:

1. Fill out the [license application form](https://querypie.com/querypie/license/community/apply)
2. A `.crt` license file will be sent to your email

### Step 3: Access QueryPie

Once installation completes, open QueryPie in your browser:

```
http://<your-server-ip>
or  
https://<your-server-ip>
```

> **Note:** Make sure your server IP is accessible from your computer

<p align="center">
  <img src="https://usqmjrvksjpvf0xi.public.blob.vercel-storage.com/main/public/documentation/install-guide-2-hL1Wh22qpC6A0R1bH2oqgynVRseIJn.png" alt="Installation complete" style="max-width: 800px;" />
  <br/><em>Installation completed successfully</em>
</p>

### Step 4: Upload License

Upload your `.crt` license file or copy-paste the PEM content:

<p align="center">
  <img src="https://usqmjrvksjpvf0xi.public.blob.vercel-storage.com/main/public/documentation/install-guide-3-jWNZ6jDvITcS1N3BlQdTSDmHNazbcV.png" alt="License upload" style="max-width: 800px;" />
  <br/><em>Enter license in PEM format</em>
</p>

### Step 5: First Login

Use the default admin credentials:

- **Username:** `qp-admin`
- **Password:** `querypie`

> 🔒 You'll be prompted to change the password on first login for security

<p align="center">
  <img src="https://usqmjrvksjpvf0xi.public.blob.vercel-storage.com/main/public/documentation/install-guide-4-XhGsdCCZPEq83mDGlaC1Iw0pzNRfpb.png" alt="Login screen" style="max-width: 800px;" />
  <br/><em>Initial login screen</em>
</p>

### Step 6: Setup Complete! 🎉

Congratulations! QueryPie is now ready to use.

<p align="center">
  <img src="https://usqmjrvksjpvf0xi.public.blob.vercel-storage.com/main/public/documentation/install-guide-5-droULybwgvRVIs1M01ibShv23WHEmL.png" alt="Welcome screen" style="max-width: 800px;" />
  <br/><em>Welcome to QueryPie!</em>
</p>

**Next Steps:**
- Check out the [Administrator Manual](https://docs.querypie.com/administrator-manual) for environment setup
- Click the `Go to Admin Page` button in the top right corner to navigate to the administrator page
- Start configuring your database connections
- Invite team members (up to 5 users)

---

## 📁 Installation Location & Manual Operations

**Installation Location:**
- Mac, Linux: `<folder where the installation script was executed>/querypie/<version>`
- Example: `/Users/brendon/querypie/11.5.0` or `/home/brendon/querypie/11.5.0`

**Manual Start:**
```bash
cd ~/querypie/11.5.0
docker compose --profile=database up -d
docker compose --profile=app up -d
```

**Verify Normal Startup:**
```bash
docker compose --profile=app exec app readyz
```

**Manual Stop:**
```bash
cd ~/querypie/11.5.0
docker compose --profile=app down
docker compose --profile=database down
```

**Verify Normal Shutdown:**
```bash
docker compose ps
```

---

## 🔑 License Information

- **Requirement:** Valid license required after installation
- **Format:** Text file with `.crt` extension (PEM format)
- **Delivery:** Sent to your email address from application form
- **Duration:** Valid for one year from issue date
- **Usage:** Personal license, non-transferable

---

## 💬 Support & Community

Join our community for help and discussions:

🔗 [Official QueryPie Discord Channel](https://discord.com/invite/Cu39M55gMk)

Get support, ask questions, and share insights with other QueryPie users!
