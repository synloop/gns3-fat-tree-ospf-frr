# GNS3 Fat‑Tree OSPF / FRRouting 8.4

A **k = 4 Clos Fat‑Tree** datacenter topology (20 Debian 12 + FRRouting 8.4 routers + 4 hosts) ready to import in **GNS3**.  The project showcases multi‑area OSPF v2 & v3, ECMP, and IPv4/IPv6 dual‑stack routing.

---

## Repository layout

```text
configs/                # All copy‑paste router & host configs
 ├─ 1-core/             # 4 core routers  (R1 – R4)
 ├─ 2-agg/              # 8 aggregation   (P1‑R3 … P4‑R4)
 ├─ 3-edge/             # 8 edge routers  (P1‑R1 … P4‑R2)
 └─ 4-hosts/            # 4 Linux hosts   (H1 – H4)

docs/                   # Diagrams & report
 ├─ Topology.png        # Overview diagram
 ├─ Topology_Plan.pdf   # Address‑plan table
 └─ OSPF_report.pdf     # 15‑page lab report (EN)

gns3/                   # Lightweight GNS3 project stub (< 100 kB)
 └─ project.gns3        # References the external QCOW2 disks
```

> **Why two delivery formats?**  GitHub blocks files > 25 MB, so QCOW2 disks are distributed separately (see below).  You can still `git clone` the repo and immediately read docs/configs.

---

## Quick start

### 1. Download the full project

- **Google Drive (one‑click)**  – [ fat‑tree‑frr.gns3project.zip (≈ 80 MB) ](https://drive.google.com/file/d/1lRXQm11yiwaAHLXwQSe6QbnUiOQnN-b6/view?usp=sharing)

- **GitHub Release (versioned)** – [latest release ▶](https://github.com/synloop/gns3-fat-tree-ospf-frr/releases/latest) → grab `fat-tree-frr.gns3project.zip`

> Both archives contain `project.gns3` **+** all per‑VM QCOW2 disks inside `project-files/qemu/*/hda_disk.qcow2`.

### 2. Import into GNS3

1. **File ▸ Import portable project** ↪ select the ZIP.
2. Leave *“Copy base images”* checked (recommended).
3. Press **Finish** → the full topology appears, already wired and named.
4. Start all nodes, then copy the configs from `configs/` if you want to (re)apply them.

---

##  Config files

*All text files can be pasted directly in **``**.*

```
configs/1-core/R1.txt   # core example
configs/2-agg/P2-R3.txt # aggregation example
configs/3-edge/P4-R2.txt
configs/4-hosts/H1.txt
```

Naming: **P x – R y** means router *Ry* inside *Pod x*.

---

## Documentation

| File                   | What’s inside                                      |
| ---------------------- | -------------------------------------------------- |
| **Topology.png**       | Single‑page diagram with areas and links           |
| **Topology\_Plan.pdf** | Exhaustive address table (20 routers + 4 hosts)    |
| **OSPF\_report.pdf**   | Step‑by‑step lab report                            |

---

##  Requirements

- GNS3 ≥ 2.2 (local or server)
- QEMU ≥ 4.2 installed by GNS3
- At least **4 vCPU / 8 GB RAM** to run the full lab

---

## Author

Yassin El Hakouni – 2025

---

## License

Distributed under the **MIT License** – see [`LICENSE`](LICENSE).
