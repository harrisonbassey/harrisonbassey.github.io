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

<!-- ====== READABILITY & RESPONSIVE FIXES ====== -->
<style>
:root{
  --bg:#0d1117;
  --fg:#c9d1d9;
  --accent:#238636;
  --border:#30363d;
  --radius:8px;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;
  scroll-behavior:smooth;
}
body{background:var(--bg);color:var(--fg);margin:0;padding:0;line-height:1.65;font-size:1rem;}
.wrapper{max-width:880px;margin:auto;padding:0 1rem;}
section,footer{@extend .wrapper;margin:3rem auto;}
h1{font-size:2.2rem}h2{font-size:1.6rem}h3{font-size:1.25rem}
h1,h2,h3{line-height:1.2;margin-top:1.5em;margin-bottom:.5em;color:#58a6ff;}
a{color:#58a6ff;}
.button,button{
  padding:.55rem 1.1rem;border:1px solid var(--border);border-radius:var(--radius);
  background:var(--accent);color:#fff;font-size:.95rem;cursor:pointer;margin:.25rem;
  display:inline-block;text-align:center;transition:all .2s;
}
.button:hover,button:hover{transform:translateY(-2px);box-shadow:0 4px 12px rgba(35,134,54,.35);}
.button.outline,button.outline{background:transparent;color:var(--accent);}
pre{overflow-x:auto;background:#161b22;padding:1rem;border-radius:var(--radius);}
code{font-size:.9em;}
button.copy{
  font-size:.7rem;padding:.2rem .4rem;background:var(--border);color:var(--fg);
  border:none;margin:-.5rem 0 .5rem auto;display:block;
}
form{display:grid;gap:.75rem;}
input,textarea{
  width:100%;padding:.6rem;border:1px solid var(--border);border-radius:var(--radius);
  background:#161b22;color:var(--fg);font-size:.95rem;
}
textarea{resize:vertical;min-height:120px;}
table{margin:1em 0;width:100%;border-collapse:collapse;}
th,td{padding:.5rem .75rem;border:1px solid var(--border);}
th{background:rgba(88,166,255,.1);}
p,li{max-width:75ch;}          /* keep line length readable */
img{max-width:100%;height:auto;}

/* ----- light-mode toggle ----- */
@media (prefers-color-scheme:light){
  :root{
    --bg:#ffffff;
    --fg:#222222;
    --border:#d0d7de;
    --accent:#1a7f37;
  }
  h1,h2,h3{color:#0550ae;}
  pre{background:#f6f8fa;}
}

/* ----- small screens ----- */
@media (max-width:600px){
  h1{font-size:1.75rem}
  h2{font-size:1.35rem}
  .button,button{font-size:.9rem;padding:.45rem .9rem}
}
</style>
