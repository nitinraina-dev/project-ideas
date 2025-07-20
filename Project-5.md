## 💡 Project: **CampusCrate – Lost & Found System for College**

---

### 🧩 **Problem It Solves:**

Students frequently lose or find items (ID cards, notebooks, water bottles, power banks, etc.) with **no reliable platform** to report or retrieve them. Relying on WhatsApp/Telegram threads leads to **lost messages, no searchability, and chaos**.

---

## 🧑‍🤝‍🧑 Key Users:

* **Student (Finder)** – Posts item they found
* **Student (Loser)** – Searches for their lost item
* **Admin** – Moderates abuse, verifies item matches, manages reports

---

## 🌐 System Features:

### 🧭 Core Features:

1. **Post Lost Item**
2. **Post Found Item**
3. **Search Lost/Found Listings**
4. **Claim an Item** (with match questions)
5. **Messaging system for clarification**
6. **QR Code / Tag-based return (for ID cards, etc.)**
7. **Report Abuse**
8. **Admin approval for spam prevention**
9. **Mark Item as Returned**

---

## 🔁 User Flow

### 🧍‍♂️ 1. **Lost Item Flow (Loser):**

1. Student logs in via college email (Google Auth)
2. Clicks on “I Lost Something”
3. Fills form:

   * Title: “Lost Blue Bottle”
   * Category: Bottle, ID card, Electronic, Book, etc.
   * Description, color, tags
   * Date lost, location
   * Upload photo (optional)
4. Searches existing “Found” posts before submitting
5. If not found, submits the Lost Post
6. Receives notification if someone claims a match

---

### 🧍‍♀️ 2. **Found Item Flow (Finder):**

1. Logs in
2. Clicks “I Found Something”
3. Fills similar form:

   * Description + image
   * Date & location found
4. System auto-checks against recent "Lost" items
5. Can message person who reported lost
6. Once returned:

   * Clicks "Mark as Returned"

---

### 🔐 3. **Claim Flow (For Lost or Found):**

1. Click “Claim this item”
2. System asks matching question (set by poster):

   * e.g., “What’s the sticker on the back of your laptop?”
3. Optional: Chat to verify
4. Once both agree:

   * Poster marks item as **Returned**
   * System records exchange

---

### 🔧 4. **Admin Flow:**

1. Admin dashboard shows:

   * Pending claims
   * Reported abuse
   * Suspicious posts (spam detection)
2. Can approve/reject posts
3. Can **block users** who misuse the platform

---

## 🧱 Tech Stack (MERN):

### 🔹 MongoDB Collections:

#### 1. `users`

```js
{
  _id,
  name,
  email,
  role: "student" | "admin",
  blocked: Boolean,
  createdAt
}
```

#### 2. `items`

```js
{
  _id,
  type: "lost" | "found",
  title,
  description,
  category,
  location,
  date,
  photoUrl,
  status: "active" | "claimed" | "returned",
  postedBy, // ref to users
  claimQuestion,
  tags: [String],
  createdAt
}
```

#### 3. `claims`

```js
{
  itemId,
  claimantId,
  message,
  status: "pending" | "approved" | "rejected",
  createdAt
}
```

---

## 🧑‍💻 React Pages:

* `/login`
* `/dashboard/lost`
* `/dashboard/found`
* `/post-lost`
* `/post-found`
* `/item/:id`
* `/admin`

---

## 🔐 Backend (Express/Node):

* JWT Auth + Google Auth
* Image uploads (Cloudinary)
* REST APIs:

  * `GET /items`
  * `POST /items`
  * `POST /claim`
  * `PATCH /items/:id/status`
  * `POST /report`

---

Deadline -3 weeks
