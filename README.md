<div align="center">

# 🎓 LearnSphere Labs — NextGen Enterprise LMS

<p align="center">
  <strong>High-performance enterprise Learning Management System (LMS) with course tracking, analytics, and interactive student dashboards.</strong>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-key-features">Key Features</a> •
  <a href="#-tech-stack--architecture">Tech Stack</a> •
  <a href="#-project-structure">Project Structure</a> •
  <a href="#-getting-started">Getting Started</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Category-Enterprise%20Full--Stack%20%26%20SaaS-2563eb?style=for-the-badge" alt="Category: Enterprise Full-Stack & SaaS" />
  <img src="https://img.shields.io/badge/Tech%20Stack-Next.js%20%7C%20TypeScript%20%7C%20Tailwind%20CSS-10b981?style=for-the-badge" alt="Tech Stack: Next.js | TypeScript | Tailwind CSS" />
  <img src="https://img.shields.io/badge/Status-Production%20Ready-8b5cf6?style=for-the-badge" alt="Status: Production Ready" />
  <img src="https://img.shields.io/badge/License-MIT-f59e0b?style=for-the-badge" alt="License: MIT" />
</p>

</div>

---

## ✨ Key Features

- **⚡ Modern Architecture**: Built on Next.js App Router, React 19 Server Actions, and Tailwind CSS.
- **🛡️ 3-Role RBAC System**: Distinct portals and workflows for **Students**, **Instructors**, and **Administrators**.
- **🚀 1-Click Demo Profiles**: Instant access buttons for all 3 roles with zero manual typing or setup required.
- **🎥 MasterClass Video Player**: Theater-mode video learning environment with playback speed controls (0.75x - 2x), synchronized notes with auto-save, interactive Q&A discussion board, downloadable resources, and assessment quizzes.
- **🏆 Verifiable Certificates**: Instant completion certificate generation with celebration confetti, unique serial IDs, and print/download support.
- **👨‍🏫 Instructor Creator Studio**:
  - **Create**: Add new engineering masterclasses with sections, lectures, video URLs, and pricing.
  - **Edit**: Update title, headline, difficulty level, category, and media links.
  - **Delete**: Remove courses with confirmation dialogs.
  - **Preview**: Test player video preview modals and student-facing pages.
  - **Earnings & Payouts**: Request revenue withdrawals directly to Stripe/Bank accounts.
- **💼 Administrator Hub**:
  - Executive financial telemetry and transaction ledger.
  - One-click payment refund engine.
  - Instructor payout review and approval pipeline.
  - Course status toggling (Publish / Draft / Feature).
  - User directory with status toggles (Active / Suspended).
- **🌗 Flawless Theme Engine**: Fluid transition between Sleek Dark Mode and Crisp Light Mode with zero contrast mismatches.
- **🔍 Keyboard Navigation**: Global command-palette search modal accessible via `⌘K` or `Ctrl+K`.
- **🖼️ Bulletproof Image Fallbacks**: Custom `CourseImage` component that replaces broken thumbnail URLs with high-tech category icons.

---

## 🔑 Demo Personas & Credentials

You can log in directly using the **1-Click Demo Profile buttons** on the [`/login`](http://localhost:3000/login) page, or enter these manual credentials:

| Role | Email | Password | Access Level |
| :--- | :--- | :--- | :--- |
| **Student** | `student@learnsphere.io` | `student123` | Enrolled courses, notes, assessments, certificates |
| **Instructor** | `instructor@learnsphere.io` | `instructor123` | Studio, curriculum authoring, course CRUD, payouts |
| **Admin** | `admin@learnsphere.io` | `admin123` | Financial ledger, refunds, payout approvals, users |

---

## 🛠️ Tech Stack & Architecture

- **Framework**: [Next.js 16 (Turbopack, App Router)](https://nextjs.org/)
- **UI Library**: [React 19](https://react.dev/)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) with CSS Custom Properties
- **Icons**: [Lucide React](https://lucide.dev/)
- **Database Layer**: [Mongoose](https://mongoosejs.com/) (with automatic fallback to in-memory store if `MONGODB_URI` is not provided)
- **Effects & Feedback**: Canvas Confetti & Toast Notification System

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/nikhilcodeworks/LmsPortalDemo.git
cd LmsPortalDemo
```

### 2. Install dependencies
```bash
npm install
```

### 3. Environment Variables (Optional)
Create a `.env.local` file in the root directory if you want to connect to a real MongoDB Atlas cluster:
```env
# Optional: Defaults to robust in-memory mock store if omitted
MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/learnsphere?retryWrites=true&w=majority
```

### 4. Run the development server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📂 Project Structure

```text
├── src/
│   ├── app/
│   │   ├── admin/                # Administrator Control Center & Payment Ledger
│   │   ├── api/
│   │   │   ├── courses/          # Course listing and course creation endpoints
│   │   │   ├── enroll/           # Student course enrollment endpoint
│   │   │   └── progress/         # Lesson progress & note saving endpoint
│   │   ├── courses/
│   │   │   ├── page.tsx          # Filterable Curriculum Catalog
│   │   │   ├── [id]/page.tsx     # Course Overview & Syllabus Accordion
│   │   │   └── [id]/learn/       # Masterclass Player & Assessment Runner
│   │   ├── dashboard/            # Student Learning Dashboard & Heatmap
│   │   ├── instructor/           # Creator Studio (Course CRUD & Payouts)
│   │   ├── login/                # Dedicated Login page with 1-click profiles
│   │   ├── signup/               # Dedicated Signup page with role selection
│   │   ├── globals.css           # Design tokens, variables & button utilities
│   │   ├── layout.tsx            # Global app layout & font configurations
│   │   └── page.tsx              # Homepage with Hero, Tabs, and Tracks
│   ├── components/
│   │   ├── CertificateModal.tsx  # Downloadable Verified Certificate modal
│   │   ├── CourseCard.tsx        # Standard course display card
│   │   ├── CourseImage.tsx       # Resilient image with fallback category icon
│   │   ├── Navbar.tsx            # Global navigation, role switch & theme toggle
│   │   ├── QuizRunner.tsx        # Interactive assessment engine
│   │   ├── SearchModal.tsx       # Quick ⌘K command search modal
│   │   └── Toast.tsx             # Global feedback toast notifications
│   ├── context/
│   │   ├── AuthContext.tsx       # Authentication, enrollment & progress state
│   │   └── ThemeContext.tsx      # Dark / Light theme provider
│   └── lib/
│       ├── courseStore.ts        # Database / In-Memory hybrid CRUD store
│       ├── db.ts                 # Mongoose database connection client
│       ├── mockData.ts           # Curated engineering tracks & sample data
│       ├── models.ts             # Mongoose schemas (Course, User, Progress, Payout)
│       └── types.ts              # TypeScript interfaces
```

---

## 🧪 Production Build & Verification

To verify that the application compiles without any TypeScript or bundling errors:

```bash
npm run build
```

---

## 📄 License

This project is licensed under the MIT License.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.
