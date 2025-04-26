# 🚀 Secure File Encryption and Upload to Google Drive

## 📜 Project Overview
This project **encrypts your files securely** using AES encryption and **uploads them automatically** to Google Drive using the Google Drive API.

---

### ✉️ Sending Confidential Files 

- If you want to send confidential material securely, you can use this project.
- **First**, encrypt your file using the encryption.
- **Then**, upload the encrypted file using the provided `index.html` uploader.
- Share the uploaded Google Drive link with the receiver.
  - **Note:** Since the file is encrypted, even Google Drive **cannot view** the actual content.
- Separately, send the **encryption key** (`.key` file) to the receiver through a secure channel.
- The receiver will:
  - Download the encrypted file from Google Drive.
  - Use the shared encryption key to **decrypt** the file safely using the decryption script.
- ✅ This ensures complete end-to-end security for your confidential files.

---

![Image](https://github.com/user-attachments/assets/7c23b7a0-1b11-4bd5-b7fd-ec5f2e88944b)  
This is how your file folder should look like this:  
 **`encrypted_files`**  &  **`encryption_key.key`** will be auto generated, so don't worry 
 
---

## 🔧 Setup Instructions

### 1. Clone this Repository
```bash
git clone https://github.com/your-username/secure-drive-upload.git
cd secure-drive-upload
```

### 2. Install Required Libraries
```bash
pip install -r requirements.txt
```

### 3. Setting up Google Drive API
- Go to [Google Cloud Console](https://console.developers.google.com/).
- Create a **New Project**.
- Open **Library** and **Enable Google Drive API**.
- Open **Credentials** > **Create Credentials** > **OAuth Client ID**.
- Choose **Desktop App** (or **Web App** if you are using Flask).
- Download the credentials JSON file.

📺 **Follow this YouTube tutorial:**  
[How to get Google Drive API Credentials](https://www.youtube.com/watch?v=HCjAK0QA_3w)

⚡ **Important:**  
After downloading the JSON file,  
**rename it to `client_secrets.json`** and place it in your main project folder.

---

## 🔐 How Encryption Works
- AES-256 Encryption using the `pycryptodome` library.
- A random encryption key and initialization vector (IV) are generated.
- The file is fully encrypted before upload to ensure security.
- The encryption key is stored separately in a `.key` file for later decryption.

---

## 📥 Upload and Encryption Flow
1. Select the file you want to encrypt.
2. The file gets encrypted using AES-256.
3. Encrypted file is uploaded to Google Drive automatically.

---

## 📢 Notes
- Keep your `client_secrets.json` safe and **DO NOT** share it publicly.
- Always store your encryption key (`.key` file) safely. Without it, the encrypted file **cannot be decrypted**.
- You must enable **Google Drive API** for your project before using the upload feature.

---

## 🤝 Contribution
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).
