# Module 1 — Password Cracking with JTR

**Tools:** John the Ripper (JTR) + Johnny (GUI front-end)
**Target files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`

## Background

John the Ripper is a widely used password-auditing tool that works across
Unix, Windows, Linux and Mac, and can crack many hash types as well as
password-protected PDFs, ZIPs and Office files. Johnny is its GUI, aimed at
people who'd rather not use the command line directly.

## Task

Crack the password of each locked PDF file using JTR (`john`) and the Johnny
GUI, on Windows (or Kali Linux, where JTR ships pre-installed).

## Steps

1. **Install John the Ripper** — download the Windows build from the Openwall
   site (openwall.com/john) or the provided mirrors.
2. **Install Johnny** — download the GUI from openwall.info/wiki/john/johnny.
3. **Point Johnny at John** — open Johnny → Settings → Browse → select
   `john.exe` (found inside the extracted `run` folder).
4. **Extract the hash from each PDF:**
   - Visit an online PDF-hash extractor (e.g. onlinehashcrack.com's PDF hash
     tool).
   - Upload the locked PDF and copy the resulting hash (it must start with
     `$pdf$...`; strip any stray characters like a leading `b'`).
   - Paste the hash into Notepad and save as a `.txt` file (e.g. `hash1.txt`,
     `hash2.txt`, `hash3.txt`).
5. **Load the hash into Johnny** — "Open password file" → select the
   relevant hash `.txt` file.
6. **Run the attack** — click "Start new attack" and wait for JTR to work
   through its wordlist/rules against the hash.
7. **Recover the password** — once cracked, Johnny displays it next to the
   hash entry.
8. **Unlock the PDF** — open the PDF in a PDF reader and enter the recovered
   password when prompted.
9. **Repeat for each file** — `My Locked PDF2.pdf` and `My Locked PDF3.pdf`
   follow the same process, each against its own extracted hash.

## Results

| File | Cracked password | Confirmation |
|---|---|---|
| `My Locked PDF1.pdf` | `good-luck` | "Congratulations!" screen |
| `My Locked PDF2.pdf` | `password1` | "Congratulations! You have captured another flag." |
| `My Locked PDF3.pdf` | `1qaz2wsx` | Flag: `nw{networkwalks_flag_260821_1}` |

Each file had its own distinct password — the JTR/Johnny wordlist attack
recovered all three correctly.

## Notes

- Encryption is reversible with the right key; hashing is one-way (a hash
  can only be matched, not decrypted).
- Cracking time depends on machine speed and password complexity — this is
  precisely why short/common passwords are risky in the real world.
