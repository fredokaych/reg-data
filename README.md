# Wiga Ward Voter Registration Dashboard

A real-time, cloud-synced dashboard designed to track and visualize daily voter registration statistics for the Wiga Ward. This project provides a clean, responsive interface for data entry, analytics, and reporting, secured by Supabase authentication.

**Live Demo:** [https://fredokaych.github.io/reg-data/](https://fredokaych.github.io/reg-data/)  
**Repository:** [https://github.com/fredokaych/reg-data](https://github.com/fredokaych/reg-data)

---

## ✨ Key Features

- **Real-Time Analytics:** Instant visualization of total registrations, daily averages, and top-performing kits.
- **Interactive Charts:** Dynamic Bar and Doughnut charts (Chart.js) visualizing daily trends and kit performance.
- **Admin Portal:** Secure authentication system powered by Supabase Auth. Only authorized users can add, edit, or delete data.
- **Inline Editing:** Click-to-edit functionality in the data table for quick updates.
- **Data Management:**
  - **CSV Import:** Bulk upload registration data via drag-and-drop CSV parsing (PapaParse).
  - **CSV Export:** Download all data instantly for external reporting.
- **Responsive Design:** Mobile-first layout that adapts seamlessly to desktops, tablets, and phones.
- **Theming:** Toggle between Dark and Light modes with preferences saved to local storage.

## 🛠️ Tech Stack

- **Frontend:** React 18 (CDN-based standalone build)
- **Backend & Auth:** Supabase (PostgreSQL Database & Authentication)
- **Styling:** Tailwind CSS (CDN) & Custom CSS Variables
- **Visualization:** Chart.js
- **Utilities:** PapaParse (CSV parsing)

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### Prerequisites

- A modern web browser.
- A [Supabase](https://supabase.com/) account (Free tier works perfectly).
- A local web server (optional, but recommended to avoid CORS issues with ES modules). VS Code's "Live Server" extension is ideal.

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/fredokaych/reg-data.git
   cd reg-data
   ```

2. **Set up the Supabase Database:**
   
   Log in to your Supabase dashboard and create a new table named `registrations` with the following schema:

   | Column Name | Type | Primary Key | Default |
   | :--- | :--- | :--- | :--- |
   | `date` | `date` | Yes | - |
   | `kit1` | `int8` | No | `null` |
   | `kit2` | `int8` | No | `null` |
   | `kit3` | `int8` | No | `null` |

   *Note: You must enable Row Level Security (RLS) and add policies to allow read access for everyone and write access for authenticated users.*

3. **Configure Credentials:**
   
   Open `index.html` in your code editor. Locate the `SB_URL` and `SB_KEY` constants near the top of the script section:

   ```javascript
   const SB_URL = 'YOUR_SUPABASE_PROJECT_URL';
   const SB_KEY = 'YOUR_SUPABASE_ANON_KEY';
   ```

   Replace the placeholders with your actual Supabase Project URL and `anon` (public) key found in your Supabase Project Settings > API.

4. **Run the Application:**
   
   Open the `index.html` file in your browser. If you are using Live Server, simply right-click the file and choose "Open with Live Server".

## 🔐 Admin Access

By default, the dashboard loads in "Read-Only" mode. To enable data entry:

1. Click the **Lock Icon** in the top-right header.
2. Sign in with an Admin email and password.
3. Once authenticated, the "Quick Entry" form and edit capabilities in the table will unlock.

To create an admin user:
- Go to your Supabase Dashboard > Authentication > Users > Add User.

## 📂 Project Structure

The project is built as a Single Page Application (SPA) contained within a single HTML file for simplicity and portability.

```
reg-data/
│
├── index.html          # Main application entry point (HTML, CSS, JS)
├── maiandra.woff2      # Custom font file (optional, linked in CSS)
└── README.md           # Project documentation
```

## 📄 Data Format for CSV Import

If using the CSV Upload feature, ensure your file follows this format:

```csv
Date,Kit 1,Kit 2,Kit 3
2026-03-30,15,12,18
2026-03-31,22,10,5
...
```

- **Date:** Must be in `YYYY-MM-DD` format.
- **Values:** Numeric values only. Leave empty if no data for that kit.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!.

## 📝 License

This project is [MIT](https://choosealicense.com/licenses/mit/) licensed.

---

**Designed & Engineered by [fredokaych](https://github.com/fredokaych)**
```
