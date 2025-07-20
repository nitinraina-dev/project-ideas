
## 💡 SkillSync – Peer-to-Peer Skill Swapping Platform

### 🚩 **Problem**

People want to learn valuable skills but **can't afford courses**. At the same time, many **know something useful** they could teach — if only they could **exchange skills directly**.

---

## 🎯 **Solution**

A platform where users can **list skills they can teach** and **skills they want to learn**, then **match with others** for peer-to-peer learning swaps. Think of it like barter, but for learning.

---

## 🖥️ Tech Stack

* **MongoDB**: Users, Skills, Matches, Sessions, Reviews
* **Express + Node.js**: Auth, Matching logic (non-AI), Session handling
* **React.js**: Skill dashboard, Match explorer, Chat, Profile system

---

## 🔑 Key Features

### 👤 User Profile

* Login/Register (Google OAuth or email)
* Set:

  * Skills you can teach (with experience level, optional proof)
  * Skills you want to learn
  * Availability slots
  * City/timezone (for better matches)
* Profile badge system:

  * "Verified Teacher" (after X sessions)
  * "Peer Rated" (positive reviews)

---

### 🔍 Explore & Match

* See a list of available swaps:

  * “You can teach A, they want to learn A”
  * “They can teach B, you want to learn B”
* Mutual match logic (not AI):

  * Only show when both needs align
* Match requests with status:

  * Pending, Accepted, Completed

---

### 🗓️ Sessions

* Request 1:1 session
* Schedule by selecting from each other’s availability
* Built-in video call link (Zoom/Google Meet integration or placeholder link)
* Track progress (notes, resources, milestones)
* Session reminders (email or in-app)

---

### 💬 In-app Chat

* Chat with matched users
* Only opens after match is accepted
* File sharing: docs, PDFs, images

---

### 🏅 Verification & Reviews

* Peer reviews after session (1–5 stars, comments)
* Admin skill verification (optional test or document upload)
* Complaints or abuse reporting

---

### 🛡️ Admin Panel

* Manage users, block if reported multiple times
* Verify skills (optional)
* Monitor active sessions, system health
* Analytics dashboard (matches made, top skills, user growth)

---

## 🔄 User Flow (Visual Style)

### 👤 User Journey

```
[Home Page]
   ↓
[Login/Register]
   ↓
[Create Profile: Skills to Teach + Learn]
   ↓
[View Matches]
   ↓
[Send Match Request]
   ↓
[Match Accepted]
   ↓
[Chat Opens + Schedule Session]
   ↓
[Attend Session]
   ↓
[Leave Review + Mark as Completed]
   ↓
[Track Progress → Next Match]
```

---

### 🛡️ Admin Journey

```
[Admin Login]
   ↓
[View New User Registrations]
   ↓
[Optional Skill Verification (Manual)]
   ↓
[View Sessions, Monitor Reports]
   ↓
[Handle Abuse Reports or Review Disputes]
```

---

## 📈 Bonus Features to Add

| Feature                           | Description                                        |
| --------------------------------- | -------------------------------------------------- |
| **Skill Progress Tracker**        | Users can track what they’ve learned from sessions |
| **Community Forum**               | Ask general doubts, discuss progress               |
| **Achievements System**           | "Completed 5 swaps", "Taught 10 learners", etc.    |
| **Skill Category Tags**           | Easier filtering (Tech, Music, Art, Language)      |
| **Swap History Badge**            | Builds user trust and community standing           |
| **Shared Notes / Resources Page** | Each session has a shared resource vault           |

---

## ✅ Use Cases

* A student teaches “Basics of Python” in exchange for “Beginner Guitar lessons”
* A designer offers “Logo Design” tutorials in return for “Excel Basics”
* A freelancer teaches “Freelance Portfolio Setup” in exchange for “Spoken English practice”

---
Deadline-4 weeks
