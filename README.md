# Home IT Lab — Active Directory Environment (v2)

A deliberately-built Windows Server / Active Directory lab, documented as a series of discrete projects. The goal is not a checkbox lab but a **defendable** one: every configuration choice is made intentionally and explained, including a final round of fault injection to practice diagnosis under realistic break conditions.

Built by **Woldoph Monteus** — CompTIA A+, Network+ | [github.com/W-Monteus](https://github.com/W-Monteus)

---

## Why this lab exists

Anyone can click through an AD install. The value is in being able to explain *why* each decision was made and *what* each component does to the system. This lab is structured so that every project ends with a written record of the design reasoning — the same reasoning I'd give a hiring manager who asks "walk me through your lab."

The build philosophy follows a deliberate-design approach: proper OU structure, intentional GPOs, DNS and DHCP configured on purpose (not by wizard default), and a capstone where I break the environment and diagnose it.

---

## Host environment

| Component | Spec |
|-----------|------|
| Host OS | Windows |
| CPU | AMD Ryzen 7 5800X |
| RAM | 32 GB |
| GPU | RTX 4060 |
| Motherboard | MSI B550 |
| Hypervisor | Oracle VirtualBox |

## Target topology (v2 complete)

| Hostname | Role | OS | IP |
|----------|------|-----|-----|
| **DC01** | Domain Controller (AD DS, DNS, DHCP) | Windows Server 2022 | 10.10.10.10 (static) |
| **WIN-CLIENT01** | Domain-joined workstation | Windows desktop | DHCP (.100–.200) |
| **UBUNTU-CLIENT01** | Linux client, bound to AD | Ubuntu | DHCP (.100–.200) |
| *DC02 (later)* | Second DC for redundancy | — | — |
| *FILE01 (later)* | Member server, shares + GPO testing | — | — |

**Network:** Isolated VirtualBox NAT Network `MonteusLab` — `10.10.10.0/24`, gateway `10.10.10.1`.
**Domain:** `monteus.lab`

---

## Project index

| # | Project | Status |
|---|---------|--------|
| 1 | [VirtualBox networking + Windows Server preparation](./Project-1-Network-Foundation/README.md) | ✅ Complete |
| 2 | [Active Directory Domain Services + integrated DNS](./Project-2-AD-DS/README.md) | ✅ Complete |
| 3 | Organizational Unit structure + users and groups | ⬜ Planned |
| 4 | DHCP scope configuration | ⬜ Planned |
| 5 | Group Policy Objects (practical GPOs) | ⬜ Planned |
| 6 | Domain-joining the Windows client + Ubuntu integration | ⬜ Planned |
| 7 | Intentional fault injection + diagnosis (capstone) | ⬜ Planned |
