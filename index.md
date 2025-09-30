---
layout: default
title: Harrison Bassey │ Network-Automation Engineer
description: HCIA│HCIP│CCNP│Python│Linux│Ansible│Docker│MTN│9Mobile│Huawei│Cisco
---

&lt;!-- ---------------  HERO  --------------- --&gt;
&lt;section id="hero"&gt;

# 👋 Hi, I’m **Harrison Bassey**  
### I turn **multi-vendor networks** into **self-driving infrastructures** with **Python + Linux + Open-Source**.

&lt;a href="#contact"&gt;&lt;button class="glow"&gt;Hire Me&lt;/button&gt;&lt;/a&gt;
&lt;a href="https://github.com/harrison-bassey"&gt;&lt;button class="outline"&gt;GitHub&lt;/a&gt;
&lt;a href="https://linkedin.com/in/harrison-bassey"&gt;&lt;button class="outline"&gt;LinkedIn&lt;/button&gt;&lt;/a&gt;

&lt;/section&gt;

&lt;!-- ---------------  BADGES  --------------- --&gt;
&lt;p align="center"&gt;
  &lt;img src="https://img.shields.io/badge/CCNP-Enterprise-1B273F?logo=cisco" /&gt;
  &lt;img src="https://img.shields.io/badge/HCIP-Datacom-FF0000?logo=huawei" /&gt;
  &lt;img src="https://img.shields.io/badge/AWS-SAA-FF9900?logo=amazon-aws" /&gt;
  &lt;img src="https://img.shields.io/badge/Python-3.11-3776AB?logo=python" /&gt;
  &lt;img src="https://img.shields.io/badge/Linux-Ubuntu%20%7C%20CentOS-E95420?logo=ubuntu" /&gt;
  &lt;img src="https://img.shields.io/badge/Docker-2496ED?logo=docker" /&gt;
  &lt;img src="https://img.shields.io/badge/Ansible-EE0000?logo=ansible" /&gt;
&lt;/p&gt;

---

&lt;!-- ---------------  INTERACTIVE DEMOS  --------------- --&gt;
## 🚀 Live Network-Automation Demos
*(All notebooks open directly in Google Colab – zero install)*

| Demo | Stack | One-Click Run |
|------|-------|---------------|
| **Mass VLAN Creator** | Netmiko + Jinja2 + CSV | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrison-bassey/netauto-lab/blob/main/mass_vlan.ipynb) |
| **BGP Peer Checker** | Nornir + TextFSM + Graphviz | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrison-bassey/netauto-lab/blob/main/bgp_peer.ipynb) |
| **Config Drift Guard** | Oxidized + GitHub Actions + Slack | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrison-bassey/netauto-lab/blob/main/drift_guard.ipynb) |
| **Dockerised TACACS+** | Ubuntu + Docker-Compose + tac_plus | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrison-bassey/netauto-lab/blob/main/tacacs_docker.ipynb) |

---

&lt;!-- ---------------  STATS  --------------- --&gt;
## 📊 What I’ve automated so far
&lt;div id="stats" align="center"&gt;

| Metric | Number | Tooling |
|--------|--------|---------|
| CGNAT throughput | **400 Gbps/site** | `Huawei Eudemon 8000-X8v6 + Python health-poller` |
| TE tunnels built | **5 000+** | `MPLS-TE + Nornir + Jinja2` |
| RSG upgrades (zero downtime) | **30+** | `Ansible + Huawei iMaster NCE` |
| Managed routers | **1 300+** | `Seamless MPLS + PRTG + SNMP` |
| Team upskilled (L0→L2) | **12 engineers** | `Internal Python-for-Networkers bootcamp` |

&lt;/div&gt;

---

&lt;!-- ---------------  CODE SNIPPETS  --------------- --&gt;
## 🧪 Code Snippets
*(Click the grey area → copy to clipboard)*

```python
# BGP peer flapping auto-healer
import napalm, time, datetime as dt
def heal_flapping(host, peer):
    dev = napalm.get_network_driver("ios")
    with dev(hostname=host, username="admin", password="***") as d:
        while True:
            bgp = d.get_bgp_neighbors_detail()[peer]
            if bgp["connection_state"] == "Established":
                break
            if bgp["flaps"] &gt; 5:
                d.cli(["clear ip bgp %s soft" % peer])
                print(f"{dt.datetime.now()}  Soft-reset {peer}")
            time.sleep(30)
#!/usr/bin/env bash
# Quick VXLAN sanity checker
for vni in $(bridge vni show | awk '{print $2}'); do
  echo "VNI $vni – learning entries:"
  bridge fdb show dev vxlan$vni | wc -l
done

<img width="1012" height="432" alt="image" src="https://github.com/user-attachments/assets/46348852-5140-4e86-81f9-3c8781af6360" />

| Area           | Technologies                                | Proficiency   |
| -------------- | ------------------------------------------- | --------------|
| **Protocols**  | BGP, OSPF, ISIS, MPLS, VXLAN, EVPN          | ★★★★★       |
| **Automation** | Python, Paramiko, Netmiko, Ansible, Docker  | ★★★★★       |
| **Cloud**      | AWS VPC, Direct-Connect, S3, IAM            | ★★★☆☆       |
| **Monitoring** | Huawei iMaster NCE, PRTG, SNMP, Syslog      | ★★★★☆       |
| **Security**   | Firewalls (Huawei/Cisco), ACL, CGNAT, IPSec | ★★★★☆       |
| **Linux**      | Ubuntu, CentOS, Bash, Systemd, KVM          | ★★★★★       |


<!-- ---------------  BLOG / DEV.TO  --------------- -->
✍️ Latest Posts
(fetched automatically via GitHub Actions every night)
Automating CGNAT Health Checks with Python & PRTG
Lessons from upgrading 1300 routers without console cables
Building a TACACS+ container in under 5 minutes
<!-- ---------------  CONTACT  --------------- -->
<section id="contact">
📬 Let’s build the next self-driving network together
<form action="https://formspree.io/f/xwkgwkeq" method="POST">
  <input type="text" name="name" placeholder="Your Name" required />
  <input type="email" name="_replyto" placeholder="Your Email" required />
  <textarea name="message" placeholder="Tell me about your automation challenge..." required></textarea>
  <button type="submit">Send Message</button>
</form>
</section>
<!-- ---------------  FOOTER  --------------- -->
<footer>
Made with ❤️ & Markdown.  
Hosted free on GitHub Pages.  
<a href="#hero">Back to top ↑</a>
</footer>
<!-- ---------------  OPTIONAL CSS  --------------- -->
<style>
:root{
  --bg:#0d1117;
  --fg:#c9d1d9;
  --accent:#238636;
  --border:#30363d;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;
}
body{background:var(--bg);color:var(--fg);margin:0;padding:0 1rem;line-height:1.6;}
h1,h2,h3{color:#58a6ff;}
a{color:#58a6ff;text-decoration:none;}
button{padding:.6rem 1.2rem;border-radius:6px;border:1px solid var(--border);background:var(--accent);color:#fff;cursor:pointer;margin:.25rem;}
button.outline{background:transparent;color:var(--accent);}
button.glow{box-shadow:0 0 8px var(--accent);}
button.copy{font-size:.7rem;padding:.2rem .4rem;margin:0;display:block;margin-top:-1rem;}
section,footer{margin:3rem auto;max-width:900px;}
form{display:grid;gap:.75rem;}
input,textarea{width:100%;padding:.5rem;border:1px solid var(--border);border-radius:6px;background:#161b22;color:var(--fg);}
textarea{resize:vertical;min-height:120px;}
</style>

