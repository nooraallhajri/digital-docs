# 🧩 Digital-Docs — Phase 1: Encrypted Document Transfer (Symmetric Only)

This project demonstrates secure file encryption and decryption using **AES-256-GCM** with a shared passphrase.  
It represents the **Phase 1 deliverable**, focusing only on symmetric encryption and decryption.

---

## ⚙️ Setup

```bash
pip install -r requirements.txt
```

Folder layout:

```
data/
├── in/       # place your input files here (e.g. a.txt, report.pdf)
└── out/      # generated encrypted packages and decrypted outputs
```

---

## ▶️ Usage

### 🔐 Encrypt

```bash
python main.py encrypt
```

1. Enter the **file name** located in `data/in/` (for example: `a.txt`)  
2. Enter a **passphrase** when prompted  
3. Output files will appear in `data/out/`:

```
a.txt.package.json
a.txt.payload.bin
```

---

### 🔓 Decrypt

```bash
python main.py decrypt
```

1. Enter the **base file name** (for example: `a.txt`)  
2. Enter the **same passphrase** (re-prompts until correct)  
3. The decrypted file will appear in:

```
data/out/a.txt
```

---

## ✅ Quick Test

1. Create a sample file:

   ```bash
   echo "Hello Phase 1" > data/in/test.txt
   ```

2. Run encryption:

   ```bash
   python main.py encrypt
   # → file name: test.txt
   # → passphrase: yourpassword
   ```

   Output →  
   `data/out/test.txt.package.json`  
   `data/out/test.txt.payload.bin`

3. Run decryption:

   ```bash
   python main.py decrypt
   # → base file name: test.txt
   # → passphrase: yourpassword
   ```

   Output →  
   `data/out/test.txt`

4. Verify that the decrypted file matches the original.

---

## ℹ️ Notes

- Works with **any file type** (`.txt`, `.pdf`, `.jpg`, etc.).  
- If a file with the same name already exists in `data/out/`, it will be **overwritten** when decrypted.  
- Wrong passphrases are automatically rejected until the correct one is entered.  
- No asymmetric encryption or digital signatures are implemented — those belong to **Phase 2**.

---

© 2025 Digital-Docs Team | FAU Project Phase 1
