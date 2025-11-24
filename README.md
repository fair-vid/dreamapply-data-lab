# dreamapply-data-lab

**DreamApply Analytics Lab** is a Google Colab–based project for securely connecting to the **DreamApply API**, retrieving applicant data, and producing analytical and reporting outputs.

This repository contains Colab notebooks and helper scripts for:
- Secure API access  
- Data extraction and transformation  
- Encrypted data storage  
- Analytical dashboards and reports

---

## 🚀 Key Features

- 🔐 **Secure Secrets Handling** — all passwords, API keys, and endpoints are stored in **Google Secrets / Colab userdata**, never in code.  
- 💾 **Temporary Storage** — sensitive data is stored only in Colab’s temporary runtime to reduce exposure.  
- 🔒 **Encrypted Permanent Storage** — data is encrypted with a password from Secrets before being saved to permanent storage (like Google Drive).  
- 📊 **Extensible Reporting** — the project includes examples and templates for generating analytical reports.  

---

## 🧱 Repository Structure
```
dreamapply-data-lab/
│
├── notebooks/
│ └── DREAM_data.ipynb # Example DreamApply API demo
│
├── utils/
│ ├── api_client.py # DreamApply API helper
│ ├── encryption.py # Data encryption / decryption
│ └── storage.py # Temporary and permanent storage logic
│
├── reports/
│ └── applicant_summary.ipynb # Example analytical report
│
└── README.md

```



---

## ⚙️ Setup in Google Colab

1. Open the notebooks  in **Google Colab**.

    [📓 DREAM_documents image extract - Colab Notebook](https://colab.research.google.com/drive/13dqsnwa40-gQkt6AdaGbr2Is0j4VVrcW?usp=sharing)

OR
   
   [📜 DREAM_applicant data_extract - Colab Notebook](https://colab.research.google.com/drive/1FY3YHnQMGXBJRgocjyINYT_A9wxgafi7#scrollTo=0kwGYKTX4QoB)

3. Store your secrets using the built-in `userdata` API:

```python
   from google.colab import userdata

   userdata.set("DREAM_API_KEY", "your_api_key_here")
   userdata.set("BASE_URL", "https://apply.yourinstitution.example")

```


3. Access them securely in your code:

```python
  api_key = userdata.get("DREAM_API_KEY")
  base_url = userdata.get("BASE_URL")
  encryption_password = userdata.get("ENCRYPTION_PASSWORD")
  
```

4. Run the notebook to retrieve data, process files, and export encrypted reports.


🛡️ Security Approach

This project follows best practices for handling sensitive applicant data:

Credentials and endpoints are never hardcoded in the notebook.

Temporary runtime storage in Colab ensures no long-term local data remains.

Data saved to Drive or other permanent storage is AES-encrypted using a password stored in Secrets.

Network requests use authenticated DreamApply API headers.


📄 License

This project is released under the MIT License.





