
## 🧾 Wireshark Filter Cheatsheet

### 🔹 Protocol Filters
| Filter | What it shows |
|--------|---------------|
| `http` | Web traffic (HTTP requests/responses) |
| `dns`  | DNS lookups (domain name queries) |
| `tcp`  | Only TCP packets |
| `udp`  | Only UDP packets |
| `icmp` | Ping requests/replies |
| `arp`  | ARP requests/replies (used in LANs) |

#

### 🔹 IP Filters
| Filter | What it shows |
|--------|---------------|
| `ip.addr == 192.168.1.1` | Packets to/from IP `192.168.1.1` |
| `ip.src == 192.168.1.5`  | Packets sent **from** IP `192.168.1.5` |
| `ip.dst == 8.8.8.8`      | Packets going **to** IP `8.8.8.8` (Google DNS) |

#

### 🔹 Port Filters
| Filter | What it shows |
|--------|---------------|
| `tcp.port == 80`  | Traffic on port 80 (HTTP) |
| `tcp.port == 443` | Traffic on port 443 (HTTPS) |
| `udp.port == 53`  | DNS traffic |
| `tcp.port == 22`  | SSH traffic |
| `tcp.port == 25`  | Email (SMTP) |

#

### 🔹 Combine Filters
You can also combine filters with logic:
- `http && ip.addr == 192.168.1.10` → Show HTTP traffic for a specific IP  
- `tcp || udp` → Show TCP **or** UDP packets  
- `!(arp)` → Show everything **except ARP**  

#

### 🔹 Common Shortcuts

| Shortcut       | Action                  |
| -------------- | ----------------------- |
| `Ctrl+E`       | Start/Stop capture      |
| `Ctrl+F`       | Find packet             |
| `Ctrl+Shift+P` | Apply display filter    |
| `Ctrl+K`       | Clear display filter    |
| `Ctrl+H`       | Show capture statistics |

#

## Useful Tips

* **Green bar** = filter works ✅  
* **Red bar** = filter has an error ❌ 
* **Coloring rules**: Packets are color-coded for easier analysis.
* **Follow TCP stream**: Right-click a packet → *Follow* → *TCP Stream* to see full conversation.
* **Export packets**: `File → Export Specified Packets` to save for sharing.
* **Analyze protocols**: `Statistics → Protocol Hierarchy` shows protocol breakdown.

