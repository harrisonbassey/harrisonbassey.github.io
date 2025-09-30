---
layout: default
name: Harrison Bassey
title: Network Automation Engineer
description: HCIA│HCIP│CCNP│Python│Linux│Ansible│Docker│Huawei│Cisco
---

&lt;!-- ---------------  HERO  --------------- --&gt;

&lt;section id="hero"&gt;

# 👋 Hi, I’m **Harrison Bassey**  
### I turn **multi-vendor networks** into **self-driving infrastructures** with **Python + Linux + Open-Source**.

&lt;a href="#contact" class="button glow"&gt;Hire Me&lt;/a&gt;
&lt;a href="https://github.com/harrisonbassey" class="button outline"&gt;GitHub&lt;/a&gt;
&lt;a href="https://linkedin.com/in/harrisonbassey" class="button outline"&gt;LinkedIn&lt;/a&gt;

&lt;/section&gt;

&lt;!-- ---------------  BADGES  --------------- --&gt;

&lt;p align="center"&gt;
  &lt;img src="https://img.shields.io/badge/CCNP-Enterprise-1B273F?logo=cisco" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/HCIP-Datacom-FF0000?logo=huawei" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/AWS-SAA-FF9900?logo=amazon-aws" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/Python-3.11-3776AB?logo=python" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/Linux-Ubuntu%20%7C%20CentOS-E95420?logo=ubuntu" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/Docker-2496ED?logo=docker" loading="lazy" /&gt;
  &lt;img src="https://img.shields.io/badge/Ansible-EE0000?logo=ansible" loading="lazy" /&gt;
&lt;/p&gt;

---

&lt;!-- ---------------  INTERACTIVE DEMOS  --------------- --&gt;

## 🚀 Live Network-Automation Demos
*(All notebooks open directly in Google Colab – zero install)*

| Demo | Stack | One-Click Run |
|------|-------|---------------|
| **Mass VLAN Creator** | Netmiko + Jinja2 + CSV | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrisonbassey/netauto-lab/blob/main/mass_vlan.ipynb) |
| **BGP Peer Checker** | Nornir + TextFSM + Graphviz | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrisonbassey/netauto-lab/blob/main/bgp_peer.ipynb) |
| **Config Drift Guard** | Oxidized + GitHub Actions + Slack | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrisonbassey/netauto-lab/blob/main/drift_guard.ipynb) |
| **Dockerised TACACS+** | Ubuntu + Docker-Compose + tac_plus | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harrisonbassey/netauto-lab/blob/main/tacacs_docker.ipynb) |

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
*(Click grey area → copy to clipboard)*

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


<button class="copy" onclick="navigator.clipboard.writeText(this.previousElementSibling.textContent)">

#!/usr/bin/env bash
# Quick VXLAN sanity checker
for vni in $(bridge vni show | awk '{print $2}'); do
  echo "VNI $vni – learning entries:"
  bridge fdb show dev vxlan$vni | wc -l
done

<button class="copy" onclick="navigator.clipboard.writeText(this.previousElementSibling.textContent)">

<!-- ---------------  CAREER MAP  --------------- -->

🗺️ Career Journey
%%{init: {'theme':'dark'}}%%
timeline
  title Harrison Bassey – 9 yrs in Networking
  2018 : NYSC @ Huawei – IP-RAN optimisation
  2019 : Datacom Engineer @ Omnicom – Airtel v5→v8 upgrade
  2021 : Project Delivery @ Lightening – 9Mobile IP-RAN expansion
  2022 : L3 Lead @ Huawei – MTN Core & CTN
  2024 : Manager – Networks Dept @ 21st Century Tech

<img width="1052" height="450" alt="mermaid" src="https://github.com/user-attachments/assets/7eb8b0b2-dc33-4b87-b27d-6adcebd90693" />

<!-- ---------------  SKILLS MATRIX  --------------- -->
🧰 Skills Matrix

| Area           | Technologies                                | Proficiency |
| -------------- | ------------------------------------------- | ----------- |
| **Protocols**  | BGP, OSPF, ISIS, MPLS, VXLAN, EVPN, HRP/HSRP, Ethernet  | ★★★★★       |
| **Automation** | Python, Paramiko, Nornir, Netmiko, Ansible, Docker      | ★★★★★       |
| **Cloud**      | AWS VPC, Direct-Connect, S3, IAM                        | ★★★☆☆       |
| **Monitoring** | Huawei iMaster NCE, PRTG, SNMP, Syslog                  | ★★★★☆       |
| **Security**   | Firewalls (Huawei/Cisco), ACL, CGNAT, IPSec             | ★★★★☆       |
| **Linux**      | Ubuntu, CentOS, Bash, Systemd, KVM                      | ★★★★★       |

<!-- ---------------  BLOG / DEV.TO  --------------- -->
✍️ Latest Posts
(auto-updated nightly via GitHub Actions)
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

<!-- ---------------  READABILITY + STYLE TWEAKS  --------------- -->
<style>
:root{
  --bg:#0d1117;
  --fg:#c9d1d9;
  --accent:#238636;
  --border:#30363d;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;
}
body{background:var(--bg);color:var(--fg);margin:0;padding:0;line-height:1.6;}
h1{font-size:2rem}h2{font-size:1.5rem}h3{font-size:1.25rem}
a{color:#58a6ff;}
.button,button{padding:.6rem 1.2rem;border-radius:6px;border:1px solid var(--border);background:var(--accent);color:#fff;cursor:pointer;margin:.25rem;display:inline-block;text-align:center;}
.button.outline,button.outline{background:transparent;color:var(--accent);}
.button.glow,button.glow{box-shadow:0 0 8px var(--accent);}
button.copy{font-size:.7rem;padding:.2rem .4rem;margin:0;display:block;margin-top:-1rem;}
section,footer{margin:3rem auto;max-width:900px;padding:0 1rem;}
form{display:grid;gap:.75rem;}
input,textarea{width:100%;padding:.5rem;border:1px solid var(--border);border-radius:6px;background:#161b22;color:var(--fg);}
textarea{resize:vertical;min-height:120px;}
pre{overflow-x:auto;}
@media (prefers-color-scheme:light){
 :root{--bg:#fff;--fg:#222;--border:#ddd;}
}
</style>
