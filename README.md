# Password Cracking with John the Ripper
**Program:** Networkwalks Cybersecurity & Ethical Hacking (B084) | **Week:** 03 | **Author:** Carter Menlor

## 👤 Author
**CARTER MENLOR**
Cybersecurity Professional, B084
🔗 LinkedIn: [linkedin.com/in/carter-menlor-231613404](https://www.linkedin.com/in/carter-menlor-231613404/)
💻 GitHub: [@cartermenlor-wq](https://github.com/cartermenlor-wq)

---

## 📌 Task
Crack the password of a locked PDF (`My Locked PDF1.pdf`) provided for the lab.

The lab materials suggested doing this on Windows with Networkwalks' browser-based Hash Calculator and Password Cracker tools. I instead did it the way a real security tester would on Linux, using **John the Ripper**, to show the underlying mechanics.

## 🛠️ Tools Used
| Tool | Purpose |
|---|---|
| Kali Linux | Operating system |
| `pdf2john` | Extracts a crackable hash from a password-protected PDF |
| John the Ripper (`john`) | Dictionary attack engine |
| Johnny | GUI front-end for John the Ripper |

## 🔍 Method
1. Extracted the PDF's encryption hash with `pdf2john`, producing a `$pdf$...` formatted hash (the same format Networkwalks' own Hash Calculator produces).
2. Saved the hash to a text file.
3. Opened **Johnny** (the GUI for John the Ripper) and loaded the hash file.
4. Ran a dictionary attack against the hash.
5. John the Ripper matched the hash and recovered the password, confirmed at **100% (1/1 cracked)**.
6. Opened the PDF with the recovered password and retrieved the completion flag.

## ✅ Result
- PDF hash format: `$pdf$4*4*128*...` (RC4, 128-bit key, revision 4)
- Status: **Cracked — 1/1, 0 left**
- Password recovered: *(withheld — shared training flag, see note below)*

## 📝 Notes
- The hash is not the password itself — it's a mathematical fingerprint of it. Cracking means trying candidate words, hashing each one, and comparing it to the stored hash until one matches.
- A dictionary attack only succeeds if the real password (or something close to it) is in the wordlist. This one cracked in a single pass, showing the password was a weak, guessable word rather than a strong passphrase.
- I'm withholding the recovered password and the flag text in this public repo, since this is a shared course exercise and other students use the same file.

## ⚠️ Disclaimer
Performed only on files provided for this course exercise, for educational purposes only. Password cracking against files or accounts you don't own or have permission to test is illegal in most jurisdictions.
