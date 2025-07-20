## 💡 Project: **CredCheck** – Certificate & Internship Verifier for Students

### 🔧 Problem it solves:

Makes it easier for **students to prove their achievements** and for **recruiters or colleges to verify them**. Prevents **fake internships and certificates**.

---

## 🎯 Key Users:

1. **Students** – Upload certificates & internship proof
2. **Verifiers (Startups / Orgs / Course Providers)** – Verify certificates
3. **Recruiters / Placement Cells** – Check authenticity of links or QR
4. **Admins** – Manage platform, approve abuse reports

---

## 🔄 Full User Flow:

### 👨‍🎓 Student Flow:

1. **Sign up/Login** via Google
2. Fill profile: Name, college, degree, batch
3. Go to “My Certificates”
4. Click **Upload Certificate**

   * Fill details (Title, Organization, Date, Description)
   * Upload PDF/image
   * Enter email of verifier (issuer)
5. Submit for verification
6. Wait for verifier approval
7. Once verified:

   * Student gets a **public certificate link + QR code**
   * Can add to resume or share

---

### 🏢 Verifier Flow (Organization/Startup):

1. Verifier signs up using organization email (with email verification)
2. Gets a **“Verifier Dashboard”**

   * See all incoming certificate verification requests
   * Approve or reject with optional comments
3. On approval:

   * The certificate is marked as “Verified”
   * Verifier’s name/logo is added to the certificate record

---

### 🕵️ Recruiter Flow (No login needed):

1. Open public **link or scan QR**
2. View certificate details:

   * Student name
   * Certificate details
   * “Verified by XYZ Organization” tag
   * Timestamp of issue
3. Can’t edit or fake this — secure read-only page

---

### 🛠️ Admin Flow:

1. Admin dashboard to:

   * View all users
   * View all verifiers
   * Moderate abuse reports
   * Remove false verifiers or spam certificates
   * Promote trusted organizations

---

## 📁 Collections (MongoDB Models):

### 1. `users`

```js
{
  _id,
  name,
  email,
  role: "student" | "verifier" | "admin",
  college,
  verified: Boolean,
  createdAt
}
```

### 2. `certificates`

```js
{
  _id,
  studentId, // ref to users
  title,
  organization,
  fileUrl,
  verifierEmail,
  status: "pending" | "verified" | "rejected",
  comments,
  publicLinkId,
  qrCodeUrl,
  createdAt
}
```

### 3. `verifier_requests`

```js
{
  _id,
  organizationName,
  email,
  status: "pending" | "approved" | "rejected",
  requestedAt
}
```

---

## ⚙️ Tech Stack (MERN)

* **MongoDB:** Users, Certs, Verifiers
* **Express.js:** Auth, API routes, file uploads
* **React:** Dashboards (Student, Verifier, Admin), Public view
* **Node.js:** QR generation, email notifications
* **Cloudinary / Firebase Storage:** For certificate file storage
* **UUID:** For public certificate link
* **JWT:** For user sessions
* **Nodemailer:** Email verifiers on new cert requests

---

## 🖼️ React Pages:

* `/login` – Google login
* `/dashboard/student` – Upload certs, view status
* `/dashboard/verifier` – Approve/reject certs
* `/dashboard/admin` – User/Verifier management
* `/cert/:id` – Public certificate view
* `/verify-request` – Become a verifier

---


Deadline - 3 weeks
