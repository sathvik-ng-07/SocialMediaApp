

# 📄 Requirements Report for Social Media App

## 1. Project Overview

The goal is to create a lightweight **social media web app** that mimics basic Instagram functionality using only **HTML, CSS, and Bootstrap** for the UI.
Data will be populated from the **JSONPlaceholder API** (fake JSON data for prototyping).
The app will have **user login**, a **home feed**, **profile pages with albums**, and an **admin panel** for user management.

---

## 2. Functional Requirements

### 2.1 User Management

* **Login Page**

  * Users can log in using credentials created by the admin.
  * No self-registration option.
  * Redirect to the home page after login.

* **Admin Panel**

  * Only accessible by admin.
  * Admin can:

    * Add users (username, password, profile picture, etc.)
    * Remove users
    * View list of all users
  * No API integration for authentication (static data stored for prototype).

---

### 2.2 Home Feed

* Display posts in a **scrollable feed (Instagram-like)**.
* Each post contains:

  * User profile picture and username (at top of post)
  * Image or content (fetched from JSONPlaceholder `/photos` or `/posts`)
  * Caption (fetched from `/posts`)
* Posts are stacked vertically, scrollable.
* Profile button in navbar redirects to the logged-in user’s profile page.

---

### 2.3 Profile Page

* Contains:

  * User’s profile picture, username, and name.
  * Posts grid (user-specific posts).
  * Albums section:

    * Groups posts into albums (using JSONPlaceholder `/albums`).
    * Each album links to a page showing photos from that album.
* **Click on a post → open detailed post view** (single post page with caption, likes/comments placeholder).

---

### 2.4 Post View

* When clicking a post from home or profile:

  * Show full image/content.
  * Show caption/title.
  * Show user info (profile pic, name).
  * Placeholder area for comments (optional).

---

## 3. Non-Functional Requirements

* **Technology Stack**:

  * HTML5
  * CSS3
  * Bootstrap 5
  * (No JavaScript for now, but data placeholders will be used).

* **UI/UX Requirements**:

  * Responsive design (Bootstrap grid).
  * Navigation bar with:

    * Home button
    * Profile button
    * Logout option
  * Instagram-like look & feel: cards for posts, grid layout for profiles.

* **Performance**:

  * Fast loading (static prototype).
  * Images scaled properly with Bootstrap classes (`img-fluid`).

* **Security**:

  * Basic (since no real backend).
  * Login page will not have actual authentication, just placeholder behavior.

---

## 4. Pages Breakdown

| Page                 | Purpose                         | Key Features                                           |
| -------------------- | ------------------------------- | ------------------------------------------------------ |
| **Login Page**       | User authentication entry point | Username/password input, admin-controlled users only   |
| **Home Page (Feed)** | Main user feed                  | Infinite scroll style feed (simulated), profile button |
| **Profile Page**     | User’s personal space           | Profile info, posts grid, album section                |
| **Album Page**       | Grouped photos                  | Displays photos in that album                          |
| **Post Detail Page** | Single post view                | Enlarged post with caption, user info                  |
| **Admin Panel**      | Manage users                    | Add/remove users, view user list                       |

---

## 5. Data Mapping with JSONPlaceholder

Since you’re using JSONPlaceholder API:

* **Users → `/users`**

  * Provides user profile info (name, username, email, etc.).
* **Posts → `/posts`**

  * Provides text posts (can be captions for images).
* **Albums → `/albums`**

  * Groups of photos per user.
* **Photos → `/photos`**

  * Provides actual photo URLs (to be displayed in posts & albums).
* **Comments → `/comments`**

  * Can be used for post comments (if required later).

---

## 6. Navigation Flow

1. **Login Page → Home Page**
2. **Home Page → Profile Page** (via navbar profile button)
3. **Profile Page → Album Page** (via album click)
4. **Profile Page → Post Detail Page** (via post click)
5. **Home Page → Post Detail Page**
6. **Login Page → Admin Panel** (if logged in as admin)

---

## 7. Limitations

* No **real authentication** (static login).
* No **real-time interactions** (likes, comments won’t persist).
* No **backend** (only UI prototype).
* Data is **fetched from JSONPlaceholder**, not user-generated.

