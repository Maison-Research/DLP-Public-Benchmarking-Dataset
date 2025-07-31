<p align="center">
  <img src="https://brand.umich.edu/wp-content/themes/micbrand/img/um_logo_footer_withoutline.svg" alt="University of Michigan Logo" width="200">
</p>

# DLP-Public-Benchmarking-Dataset

## Dataset Structure and Concept

The dataset is organized into **10 high-level categories**, each representing a distinct class of sensitive data. Within each category, there are **10 granular points**, detailing specific subtypes of data. 

---

### 🔐 **Personal Contact Information**
- **Children's Information**: Ages, names in family accounts  
- **Email Addresses**: Personal or work emails shared for support  
- **Family Member Names**: Spouses, children, or relatives mentioned  
- **Full Names**: First, middle, last names of individuals  
- **Maiden Names**: Mother's maiden name used in security questions  
- **Phone Numbers**: Mobile, landline, or business contact numbers  
- **Physical Addresses**: Home, billing, or shipping addresses  
- **Places of Birth**: Location where individual was born  
- **Relative Contacts**: Emergency contacts  
- **Spouse Names**: Partner details in profiles  

---

### 👤 **Account and Profile Data**
- Account IDs, Business Addresses, DOB, Education History, Employers, Work History, Gaming Handles, Membership Numbers, Parental Controls, Social Media

---

### 🛡️ **Authentication Data**
- API Keys, Certs, Digital Signatures, Firmware Keys, License Keys, Mother’s Maiden Name, Passwords, PINs, OTPs, Security Questions

---

### 📱 **Device and Incident Data**
- Calendar Events, Contact Lists, Serial Numbers, File Paths, IMEIs, Incident Reports, MACs, Repair Histories, IoT Sensor Data, Smart Assistant Logs

---

### 💳 **Financial Data**
- Bank Info, Credit Scores, Crypto Wallets, Income, Insurance Policies, Loans, Payment Info, Purchases, Transaction IDs, Warranty Claims

---

### 🧬 **Health and Biometric Data**
- Allergies, Biometrics, Diet, DNA Tests, Exercise Logs, Genetic Info, Health Metrics, Medical Records, Medications, Sleep Patterns

---

### 🪪 **Identification Numbers**
- Citizenship, Driver's License, Employee ID, National ID, Passport, License Numbers, SSNs, Tax IDs, Visa Numbers, Voter IDs

---

### 📍 **Location and Network Data**
- EXIF in Photos, Flight Info, GPS/Geotags, Coordinates, Hotel Reservations, IPs, Itineraries, WiFi SSIDs & Passwords

---

### 📂 **Media and Content Data**
- App Logs, Browser History, Email Signatures, Error Logs, Feedback, Forum Quotes, Chats, Reviews, Shared Docs, Survey Responses

---

### 🧾 **Ancillary Sensitive Data**
- Family Profiles, Incident Descriptions, Mood Tracking, Narratives, Pet Names, Psych Profiles, Recovery Contacts, Session Tokens, 2FA Codes, URLs

---

Each **data point** provides 6 subtypes, capturing **real-world diversity**:

#### Positive Examples *(Sensitive — should be masked)*:
- **Direct**: e.g., "My SSN is 078-05-1120"  
- **Typo**: e.g., "S SN is 0 7 8 -0 5 -1 1 2 0"  
- **Contextual**: e.g., "Tax number starts with 078 and ends in 1120"  

#### Negative Examples *(Not sensitive — should not be masked)*:
- **Direct**: e.g., "What is the PIN requirement?"  
- **Typo**: e.g., "Wht is the P I N rqrmnt?"  
- **False Keywords**: e.g., "The test SSN is 000-00-0000"  

> Each subtype includes 2 samples, totaling **1,200 examples**:  
> *10 categories × 10 points × 6 subtypes × 2 messages*

---

## Rationale and Design Principles

- Built on **privacy risk taxonomy** (e.g., financial fraud, health inference, surveillance)
- Includes **direct**, **obfuscated**, and **implied** representations
- Enables benchmarking of algorithms for:
  - Regex robustness
  - Contextual understanding
  - Precision–recall tradeoffs
- Helps mitigate **false positives** and **false negatives**
- Suitable for **masking tools**, **LLMs**, **privacy-enhancing systems**

---

## 📘 License and Availability

This dataset is **open access** and intended for advancing research in sensitive data detection, masking, and privacy technology.


