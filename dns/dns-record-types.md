# 🌐 DNS Records Explained

DNS (Domain Name System) records map domain names to various types of data, such as IP addresses or mail servers. Here's a breakdown of the most common DNS record types.

---

## ✅ Common DNS Record Types

### 1. A Record (Address Record)
- **Purpose**: Maps a domain name to an IPv4 address.
- **Example**: `example.com → 192.0.2.1`

---

### 2. AAAA Record (IPv6 Address Record)
- **Purpose**: Maps a domain name to an IPv6 address.
- **Example**: `example.com → 2001:0db8::1`

---

### 3. CNAME Record (Canonical Name)
- **Purpose**: Aliases one domain name to another.
- **Example**: `www.example.com → example.com`
- **Note**: Cannot coexist with other records for the same name.

---

### 4. MX Record (Mail Exchange)
- **Purpose**: Directs email to a mail server.
- **Includes**: Priority and mail server hostname.
- **Example**: `10 mail1.example.com`

---

### 5. TXT Record (Text Record)
- **Purpose**: Holds arbitrary text. Common for SPF, DKIM, and verification.
- **Example**: `v=spf1 include:_spf.google.com ~all`

---

### 6. NS Record (Name Server)
- **Purpose**: Specifies authoritative DNS servers for the domain.
- **Example**: `example.com → ns1.exampledns.com`

---

### 7. SOA Record (Start of Authority)
- **Purpose**: Provides domain metadata including primary nameserver, contact email, refresh timers, etc.
- **Used By**: DNS zone transfers.

---

### 8. PTR Record (Pointer Record)
- **Purpose**: Reverse DNS — maps an IP address to a domain name.
- **Example**: `192.0.2.1 → example.com`

---

### 9. SRV Record (Service Locator)
- **Purpose**: Specifies port and hostname for services.
- **Example**: `_sip._tcp.example.com → 10 60 5060 sipserver.example.com`

---

### 10. CAA Record (Certification Authority Authorization)
- **Purpose**: Specifies which certificate authorities can issue SSL certificates for a domain.
- **Example**: `example.com CAA 0 issue "letsencrypt.org"`

---

### 11. ALIAS Record
- **Purpose**: CNAME-like record used at the root level (`@`). Proprietary to some DNS providers.
- **Example**: `example.com → otherdomain.com`

---

## 🛠️ Use Case Summary Table

| Record | Use Case Description |
|--------|----------------------|
| `A` / `AAAA` | Direct a domain to an IP address (IPv4 / IPv6) |
| `CNAME` | Redirect one domain name to another |
| `MX` | Email server routing |
| `TXT` | Domain verification, SPF/DKIM records |
| `NS` | Delegate DNS responsibility to other servers |
| `SOA` | Domain metadata and zone transfer control |
| `PTR` | Reverse IP to domain mapping |
| `SRV` | Service discovery (ports and protocols) |
| `CAA` | Control SSL certificate authority access |
| `ALIAS` | Root-level CNAME-like redirection |

---

