## 🚀 Problem:

Students often study from different materials or in silos. There's no common place to **track progress by syllabus**, especially for groups preparing for **exams** or **semester subjects** together.

---

## 🎯 Solution Summary:

A platform where students can create syllabus-wise subject trackers, **mark topics done**, **collaborate in groups**, and **visualize how much they've completed**.

---

## 👨‍🏫 Target Users:

* College students
* Self-learners preparing for competitive exams
* Study groups

---

## ⚙️ Core Features:

### ✅ For All Users:

* Sign in with Google
* Create or join subject groups
* Add syllabus with topics and subtopics
* Mark progress (done, in progress, not started)
* Group-wise visualizations (heatmap or progress bar)
* Export progress to PDF (print-friendly for revision)

### 👥 For Group Admins:

* Invite peers via link or email
* Edit syllabus structure
* Track individual member’s contributions

---

## 🧭 Full User Flow

### 1. **Landing Page**

* Options: Login | Explore Public Subjects | About

### 2. **User Authentication**

* Login via Google (OAuth)
* Create user profile (optional: name, branch, year)

---

### 3. **Dashboard (after login)**

* Tabs:

  * 📘 My Subjects
  * 👥 Joined Groups
  * ➕ Create New Subject
  * 🔍 Explore Subjects (public/shared)

---

### 4. **Create New Subject Flow**

1. Add subject name (e.g., "DBMS", "Gate Physics", "12th Bio")
2. Add syllabus (manually or import from template)

   * Topic → Subtopic (multi-level tree support)
3. Choose:

   * Private (just you)
   * Group (invite peers)

✅ Subject created!

---

### 5. **Join Subject Group**

* Use invite code or public URL
* On joining:

  * See group members
  * Track joint progress
  * Get read-only or editable permission

---

### 6. **Marking Progress**

* Click checkbox (Done/In Progress/Not Started)
* Hover to see who marked what
* Each topic has:

  * % of users who completed it
  * Comments/notes (optional)
* Changes reflected across group in real time (Socket.IO optional)

---

### 7. **Visualization**

* 📊 Overall subject progress bar
* 🔥 Heatmap (by topic, subtopic)
* 🧑‍🤝‍🧑 Contribution heatmap (who did what)
* 📄 Export PDF button → Download clean syllabus with your markings

---

### 8. **Profile Page**

* View all subjects
* Stats: Topics completed, Groups joined, Contributions

---

### 9. **Admin Controls**

* Edit syllabus
* Approve or remove members
* Lock topics (e.g., for mock tests)

---

## 🗂 Tech Stack

| Layer        | Tech Used                                             |
| ------------ | ----------------------------------------------------- |
| **Frontend** | React + Tailwind + React Router                       |
| **Backend**  | Node.js + Express                                     |
| **Database** | MongoDB (Mongoose)                                    |
| **Auth**     | Google OAuth via Passport.js                          |
| **Extra**    | Chart.js/Recharts (for graphs), PDFKit or html2pdf.js |

---

## 🧱 Sample MongoDB Schema

```js
// User
{
  _id,
  name,
  email,
  subjectsJoined: [groupId],
  personalSubjects: [subjectId]
}

// Subject
{
  _id,
  name: "DBMS",
  isGroup: true,
  members: [userIds],
  createdBy: userId,
  syllabus: [
    {
      topic: "ER Model",
      subtopics: [
        { title: "Entity Types", statusByUser: { userId1: "done", userId2: "inprogress" } }
      ]
    }
  ]
}

// Progress (denormalized if needed)
{
  subjectId,
  userId,
  topicId,
  status: "done" // or "not started", etc.
}
```

---

Deadline : 3 weeks
