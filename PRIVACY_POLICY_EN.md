# Privacy Policy — Steticapp

**Last updated:** January 27, 2025

---

## 1. Who we are

**Steticapp** (“the app”, “we”, “us”) is a mobile application for managing aesthetic practices, beauty centers, and aesthetic clinics. It allows managing patients, appointments, treatments, teams, and statistics, with offline support and real-time synchronization.

- **Application name:** Steticapp  
- **Developer / Data controller:** [Developer or company name — **replace**]  
- **Contact:** [privacy/support email — **replace**]

---

## 2. Scope

This policy describes what personal data we collect, what we use it for, where it is stored, with whom it is shared (if applicable), how long it is kept, and what rights you have. It applies to anyone using the Steticapp application on Android and iOS.

---

## 3. Data we collect

We collect the data outlined below, grouped by category and source.

### 3.1 Data you provide

| Data | Purpose | Where it is stored |
|------|---------|--------------------|
| **Email** | User account, authentication, and session recovery | Device (SharedPreferences), Firebase Authentication, Firebase Realtime Database |
| **Password** | Authentication (stored locally for “remember session”) | Device (SharedPreferences) — see note in section 10 |
| **Name and surname** | User identification and profile within the practice | Device, Firebase Realtime Database |
| **Patient data** (name, surname, phone, email, date of birth, gender, notes, social networks, suggested treatment history) | Managing patient records and appointments | Firebase Realtime Database (per practice), devices with the app (cache/offline) |
| **Appointment data** (patient, date/time, operator, payment method, discounts, notes, etc.) | Managing schedule and statistics | Firebase Realtime Database, offline queue and local logs (see 3.3) |
| **Practice data** (name, type, description, invite codes, members and roles) | Multi-practice and team functionality | Firebase Realtime Database, device (current practice, preferences) |

### 3.2 Data generated or collected by the system

| Data | Purpose | Where it is stored |
|------|---------|--------------------|
| **Unique user identifier (UID)** | Linking data to the Firebase Auth account | Firebase, device |
| **Current practice identifier** | Knowing which practice the user is working in during the session | Device (SharedPreferences) |
| **Pending sync actions** (create/update/delete appointments, patients, etc.) | Offline operation and later synchronization | Device (SharedPreferences, local backups in `queue_backups`) |
| **Action logs** (action type, entity type, ID, entity name, user ID/name, description, metadata) | Diagnostics and operation traceability | Only on the device (SteticappLogs folder / app documents directory) |

### 3.3 Usage and technical data (third parties)

| Data / Service | Purpose | Provider |
|-----------------|---------|----------|
| **Firebase Authentication** | Creating and maintaining the session (email/password) | Google (Firebase) |
| **Firebase Realtime Database** | Storing users, practices, patients, appointments, treatments and invite codes | Google (Firebase) |
| **Internet connectivity** | Checking connectivity for offline/online mode | Local use only (connectivity_plus); not sent to our own servers |

**Note:** Firebase Analytics, Firebase Crashlytics, and Firebase Cloud Messaging are **not** integrated in the current code. If they are added in the future, this policy must be updated and consent obtained where required by applicable law.

---

## 4. How we use your data

We use the data to:

- **Provide the service:** authentication, managing practices, patients, appointments and treatments.  
- **Sync and offline:** saving changes on the device and syncing them with Firebase when connected.  
- **Security and operation:** access rules in Firebase (per user and practice), and local logs for support and diagnostics.  
- **Legal compliance:** responding to valid requests from authorities when required by law.

We do not use the data for advertising or to build profiles for marketing purposes.

---

## 5. Legal basis and consent

- **Contract / service performance:** processing of email, name, password (and patient/appointment/practice data) is necessary to provide the application and the described features.  
- **Consent:** by registering and using the app, you accept this policy and the processing described.  
- **Legitimate interests:** local logs and synchronization for stability, security and technical support (without sharing those logs with third parties).

If your jurisdiction requires explicit consent for sensitive data (e.g. health), notes or treatments related to patients may require an additional legal basis; in that case, the controller will state this in the app or in an update to this policy.

---

## 6. Sharing with third parties

We do not sell or rent personal data. We share data only in these cases:

| Type of data | With whom | Purpose |
|--------------|------------|---------|
| Account and app data (users, practices, patients, appointments) | **Google Firebase** (Auth + Realtime Database) | Authentication and cloud storage |
| Any data | **Competent authorities** | When required by law or a valid court order |

Firebase is part of Google LLC and is subject to [Google’s Privacy Policy](https://policies.google.com/privacy). Data is stored in the Firebase projects used by the application (project `steticapp-39adf`).

**External links:** the app may open links to WhatsApp, Instagram or websites (e.g. wa.me, instagram.com). Those platforms have their own privacy policies; we do not control the data you share with them.

---

## 7. Storage and international transfers

- **Firebase:** Google may process and store data on servers outside your country (e.g. USA or Google Cloud regions). Google offers safeguards (standard contractual clauses and, where applicable, certifications) in line with data protection regulations.  
- **Device:** data in SharedPreferences, the offline queue and logs remains on your device and is not sent to our own servers.  

---

## 8. Security

- We use **Firebase Authentication** (email/password) and **security rules** in Realtime Database to restrict access by user and practice.  
- Communication with Firebase is over encrypted channels (HTTPS/TLS).  
- Data on the device is stored in the app’s local storage (SharedPreferences, app directories).  
- **Important:** the app may temporarily store email and password on the device for “remember session”. You should use strong passwords and not share the device with others. The controller should consider reducing or removing local password storage (see “Assumptions” section).

No system is infallible; we cannot guarantee absolute security against unauthorized access or technical failures.

---

## 9. Retention and deletion

- **Account and Firebase data:** kept while the account exists and you use the service. If you request **account deletion**, we will delete or anonymize the personal data we hold within a reasonable period (e.g. 30 days), unless the law requires retention.  
- **Device data:** when you uninstall the app, SharedPreferences, the offline queue and local logs are removed with the app. Backups and logs in accessible folders (e.g. Documents/SteticappLogs on some devices) may remain until you delete them manually.  
- **Firebase:** deletion of data in Firebase (Auth and Realtime Database) must be done from the developer account or through processes defined by the controller (e.g. email request).  
- **Local logs:** they are rotated and their number/size is limited in the code; they are not sent to any server.

---

## 10. Your rights

Under applicable law (GDPR, CCPA, LGPD, etc.), you may have the right to:

- **Access:** know what data we hold about you.  
- **Rectification:** correct inaccurate or incomplete data.  
- **Erasure:** request deletion of your personal data.  
- **Restriction:** in certain cases, restrict processing.  
- **Portability:** receive your data in a structured, commonly used format.  
- **Objection:** object to certain processing.  
- **Withdraw consent:** when processing is based on consent.

To exercise these rights, write to: **[privacy/support email — replace]**.

If you believe the processing breaches the law, you may lodge a complaint with the relevant data protection authority.

---

## 11. Minors and “Designed for Families”

Steticapp is **not** directed at children under 13 and is not designed as a “Designed for Families” app. It is a professional tool for businesses (aesthetic practices and beauty centers). We do not knowingly collect data from children under 13. If we become aware that we have obtained data from a child without the required parental consent, we will take steps to delete that information.

---

## 12. Contact

For questions about privacy, exercising your rights or reporting incidents:

- **Email:** [privacy/support email — **replace**]  
- **Suggested subject:** “Privacy – Steticapp”

---

## 13. Changes to this policy

We may update this policy to reflect changes in the app, the law or our practices. Material changes will be communicated via a new version in the app or at the URL where this policy is published, with the **last updated** date at the top of the document. Continued use of the app after changes are published constitutes acceptance of the updated policy, unless the law requires explicit consent for certain processing.

---

*Document produced as part of a compliance audit for Google Play (User Data Policy / Data Safety).*
