# NETWORKWALKS-BO84A-WEEK-3-PASSWORD-CRACKING-USING-JTR-NW-TOOLS
# Password Cracking Labs — Week 3 Project

**Course:** Networkwalks Cybersecurity & Ethical Hacking Training
**Module:** Week 3 — Project Modules 1 & 2
**Target files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`
**Author:** Ian Bungei Imbayi
**Submission deadline:** 2300H, Friday 28-August-2026

## Overview

This repo documents two lab exercises that recover passwords from locked PDF
files using two different tool sets. Both follow the same underlying
workflow:

1. Extract a crackable hash from the PDF (`pdf2john` format: `$pdf$...`)
2. Run a dictionary attack against that hash
3. Use the recovered password to open the PDF

| Module | Tools used | Folder |
|---|---|---|
| 1 | John the Ripper (JTR) + Johnny GUI | [`module1-jtr-johnny/`](./module1-jtr-johnny) |
| 2 | Networkwalks Hash Calculator + Password Cracker (web-based) | [`module2-networkwalks-tools/`](./module2-networkwalks-tools) |

Both essential modules are mandatory this week — there is no choice between
them. (Optional modules — an AI/MCP-based JTR lab and a hospital-portal
hacking exercise — were not required and are not covered here.)

## Results

| File | Module | Tool | Cracked password | Outcome |
|---|---|---|---|---|
| `My Locked PDF1.pdf` | 1 | JTR / Johnny | `good-luck` | PDF unlocked — "Congratulations!" |
| `My Locked PDF1.pdf` | 2 | Networkwalks Hash Calculator + Password Cracker | `password1` | PDF unlocked |
| `My Locked PDF2.pdf` | 1 | JTR / Johnny | `password1` | PDF unlocked — "Congratulations! You have captured another flag." |
| `My Locked PDF3.pdf` | 1 | JTR / Johnny | `1qaz2wsx` | Flag: `nw{networkwalks_flag_260821_1}` |

**Note:** Module 1 and Module 2 each used their own copy of a file named
`My Locked PDF1.pdf` — these are separate files that happen to share a
filename, not the same file with two different results. Module 1 additionally
cracked `My Locked PDF2.pdf` and `My Locked PDF3.pdf`, which Module 2 did not
cover.

## Ethical Note

This exercise was performed only against a training file provided by the
course, for learning purposes. Password-cracking tools and techniques shown
here should only ever be used on systems and files you own or have explicit
written authorization to test.

## Repo Structure

```
password-cracking-labs/
├── README.md                        ← you are here
├── module1-jtr-johnny/
│   └── README.md
└── module2-networkwalks-tools/
    └── README.md
```
