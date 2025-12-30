#  CareerForge – MERN Stack Job Application Portal

##  Project Overview
**CareerForge** is a full-stack **Job Application and Recruitment Portal** built with the **MERN stack**.  
It connects **job seekers, employers, and companies** on a single platform, offering a seamless hiring experience.  
The platform also includes a **blog section** for tech updates and career tips, a **resume builder**, and an optional **ATS resume checker** to help candidates optimize their resumes for modern recruiting systems.

---

##  Key Features / Modules
- **User Authentication & Authorization** (JWT-based + Google OAuth)
- **Three User Roles**: User, Employer, and Company
- **OAuth Integration**: Login/Signup with Google
- **Job Posting & Application System**
- **Smart Job Search** with filters and recommendations
- **Resume Builder** with customizable templates
- **ATS Resume Checker (Optional)** – evaluates resume keyword match rate
- **Blog Section** for latest tech news and career tips
- **Profile Management** for users, employers, and companies
- **Admin Dashboard** to manage users, jobs, and reports
- **Email Notifications** for applications and approvals
- **Secure Data Storage** and input validation

---

##  User Roles
| Role | Description | Permissions |
|------|--------------|--------------|
| **User (Job Seeker)** | Searches and applies for jobs, builds resume, reads blogs | Create account, edit profile, upload resume, apply for jobs |
| **Employer** | Posts job listings, reviews applicants | Create/manage job posts, view applicant resumes, approve/reject applications |
| **Company** | Verifies employers, oversees recruitment process | Manage employer access, post official openings |
| **Admin** *(optional)* | Monitors the platform, handles reports | Manage all data, delete users/jobs/blogs |

---

##  Page / Screen List (Frontend)
###  Authentication
- Login / Register Page (Email/Password)
- **Google OAuth Login/Signup**
- Password Reset Page
- Session Management & JWT Tokens

###  User Section
- Dashboard (applied jobs, recommendations)
- Resume Builder Page  
- Profile Page  
- Job Listings & Job Details Page  
- Blog Page (Tech News, Articles)

###  Employer Section
- Post a Job Page  
- Manage Applicants Page  
- Employer Dashboard  

###  Company Section
- Company Dashboard  
- Manage Job Posts & Employer Access  

###  Admin (Optional)
- Manage Users / Jobs / Blogs  

###  General
- Home Page  
- About / Contact Page  
- Blog Reader Page  

---

##  Database Schema (Rough Draft)
**Tables (PostgreSQL with Prisma):**
- **users** → `{ id, name, email, password?, googleId?, provider?, avatar?, role, resume, profileInfo }`
- **jobs** → `{ id, title, description, companyId, employerId, applicants: [userId], status }`
- **companies** → `{ id, name, verified, employers: [employerId], about }`
- **applications** → `{ id, jobId, userId, resumeUrl, status }`
- **blogs** → `{ id, title, content, authorId, tags, createdAt }`
- **notifications** → `{ id, userId, message, isRead }`

**Note:** The User model now supports OAuth authentication with optional password field for OAuth users.

---

##  Tech Stack (Tentative)
**Frontend:** React.js, React Router, Tailwind CSS / Material UI  
**Backend:** Node.js, Express.js, Passport.js  
**Database:** PostgreSQL (Prisma ORM)  
**Authentication:** JWT, bcrypt, Passport.js, Google OAuth 2.0  
**Session Management:** Express Session  
**Optional Tools:**  
- Nodemailer (email notifications)  
- Cloudinary (for resume & image uploads)  
- NewsAPI (for tech blog section)  
- OpenAI / Resume Parser API (for ATS resume analysis)

---

##  Workflow (Simplified)
```text
[User] → registers → builds resume → applies for job
       ↳ gets feedback & notifications

[Employer] → posts jobs → reviews applicants → shortlists candidates

[Company] → manages employers → monitors postings → verifies legitimacy

[Admin] → ensures system health & data integrity
```

---

##  Expected Outcomes
- A **fully functional MERN-based Job Portal** with multi-role access  
- A **live demo website** showcasing full-stack CRUD operations  
- Resume Builder & optional ATS integration for added professionalism  
- **Responsive design** and **secure authentication**  
- Demonstration of **real-world workflow** and **data modeling skills**  
- A **portfolio-grade project** impressive to recruiters for **full-stack internships**

---

##  Future Enhancements
- Real-time chat between job seekers & employers  
- AI-based job recommendations  
- Integration with LinkedIn / GitHub APIs  
- Analytics Dashboard for employers & companies  
