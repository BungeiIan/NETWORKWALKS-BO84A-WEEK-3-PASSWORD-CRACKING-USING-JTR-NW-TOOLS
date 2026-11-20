# Module 2 — Password Cracking with NetworkWalks Tools

**Tools:** NetworkWalks Hash Calculator + NetworkWalks Password Cracker
(both free, browser-based, no installation required)
**Target file:** `My Locked PDF1.pdf`

## Background

Locked PDF/ZIP/Office files store their password as a hash. To recover the
real password you first extract that hash from the file, then run it through
a tool that tries candidate passwords until one matches. This module performs
that workflow entirely in the browser.

## Task

Crack the password of `My Locked PDF1.pdf` using the NetworkWalks Hash
Calculator and Password Cracker, on Windows or Kali Linux (browser-only, so
either OS works).

## Steps

1. **Get the target file** — download `My Locked PDF1.pdf` from the lab page
   (networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/).
2. **Open the Hash Calculator** — networkwalks.com/hash-calculator/.
3. **Upload the PDF** — the tool parses it locally in-browser and, since it's
   encrypted, extracts a crackable hash starting with `$pdf$...`.
4. **Copy the full hash** — make sure the entire string is copied, starting
   from `$pdf$`.
5. **Open the Password Cracker** — networkwalks.com/password-cracker/.
6. **Paste the hash and start cracking** — the tool runs a dictionary attack
   (built-in ~100-word list, or you can upload your own wordlist) against the
   hash.
7. **Wait for a match** — the tool displays progress (words tried per
   second) and stops once it finds the correct password.
8. **Unlock the PDF** — enter the cracked password in your PDF reader.

## Result

Password cracked: **`password1`** — same result as Module 1, confirming both
methods are equivalent in outcome.

## Notes

- No install needed — useful for quick checks or when you can't install
  desktop tools.
- A built-in ~100-word list is enough here because the demo password is
  deliberately weak/common; real-world audits would need much larger
  wordlists or rule-based attacks (which is where a full JTR setup, as in
  Module 1, has the edge).
