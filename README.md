# Social Platform for Military Enthusiasts with Educational 3D Weapon Module

[Polish version (Wersja polska)](README_PL.md)

> **Note:** This application is developed in Polish language. All screenshots, videos, and user interface elements shown in this documentation are displayed in Polish. The source code is not publicly available as this project was developed as an engineering thesis for university studies.

## Table of Contents

1. [Project Description](#project-description)
2. [Technologies](#technologies)
3. [Platform Overview](#platform-overview)
4. [Step-by-Step User Experience](#step-by-step-user-experience)
5. [Social Features](#social-features)
6. [Educational Weapon Module](#educational-weapon-module)
7. [Role-Based Features](#role-based-features)
8. [Responsiveness and Themes](#responsiveness-and-themes)
9. [Visual Materials](#visual-materials)
10. [Contact Information](#contact-information)

## Project Description

The goal of this project was to create a REST API web application that combines social functionalities with an interactive educational module featuring 3D models for military enthusiasts. The backend is built on Laravel 11 with Laravel Sanctum authentication, while the frontend is developed in React with TypeScript, utilizing React Three Fiber for 3D model rendering and Tailwind CSS with DaisyUI for styling.

The application consists of two key modules:
- **Educational Module** enables interaction with realistic 3D weapon models that can be viewed, animated, and explored by clicking individual parts to see their function and description. The system also includes detailed technical data, weapon history, and maintenance schemes.
- **Social Module** utilizes Laravel Gates and Policies mechanisms for user permission management. It offers registration, login, likes, commenting, following, and interaction notifications. The application also provides private chat functionality between users.

During project implementation, the author faced challenges related to 3D model optimization for browser performance, user interaction synchronization, and integration of notification and chat systems. The project addresses the growing interest in military topics, offering a modern educational tool integrated with social features.

## Technologies

### Backend
- 🖥️ **Language**: PHP 8.2.4
- 🛠️ **Framework**: Laravel 11
- 🔒 **Authentication**: Laravel Sanctum
- 💾 **Database**: MySQL/MariaDB 10.4.28
- 🔑 **Authorization**: Laravel Gates & Policies

### Frontend
- ⚛️ **Framework**: React with TypeScript
- 🎮 **3D Rendering**: React Three Fiber
- 🎨 **Styling**: Tailwind CSS, DaisyUI and FlowBite

### 3D Modeling
- 🧊 **Modeling**: Blender
- 🖌️ **Textures**: Custom Diffuse, Normal and Roughness maps
- 📦 **Export**: GLB format

## Platform Overview

> **Language Note:** All interface elements shown below are in Polish language.

### Homepage for Different User Types

<p align="center">
  <img src="assets/images/home-logged-out.png" width="48%" alt="Homepage for logged out users">
  <img src="assets/images/home-logged-in.png" width="48%" alt="Homepage for logged in users">
  <br>
  <em>Homepage: view for logged out user (left) and logged in user (right)</em>
</p>

Logged out users have limited access to system functionality, including only browsing public 3D models and the 30 most popular posts of the week, while logged in users have full access to all social and educational platform features.

### Main Platform Modules

<p align="center">
  <img src="assets/images/posts-logged-out.png" width="48%" alt="Posts for logged out users">
  <img src="assets/images/posts-logged-in.png" width="48%" alt="Posts for logged in users">
  <br>
  <em>Posts view for logged out user (left) and logged in user (right)</em>
</p>

<p align="center">
  <img src="assets/images/guns-logged-out.png" width="48%" alt="Models for logged out users">
  <img src="assets/images/guns-logged-in.png" width="48%" alt="Models for logged in users">
  <br>
  <em>3D models view for logged out user (left) and logged in user (right)</em>
</p>

The platform consists of two main modules:
- **Social Module** - enables posting, commenting, liking and interaction with other users. For logged out users, only the 30 most popular posts of the week are available, while logged in users have full access to all content with filtering options.
- **Educational Module** - provides interactive 3D weapon models with detailed descriptions, animations and technical data. Logged out users see only public models, while logged in users have access to all models except drafts.

## Step-by-Step User Experience

### 1. Registration and Login

<p align="center">
  <img src="assets/images/registration-form.png" width="48%" alt="Registration">
  <img src="assets/images/login-form.png" width="48%" alt="Login">
  <br>
  <em>Registration process (left) and login (right)</em>
</p>

Logged out users can expand available functions by logging into an existing account or creating a new account. The system guides users through an intuitive registration process requiring basic personal data and a password that meets security requirements.

### 2. Email Verification

<p align="center">
  <img src="assets/images/email-verification.png" width="48%" alt="Email verification status in profile">
  <img src="assets/images/email-verification-message.png" width="48%" alt="Email message with verification link">
  <br>
  <em>Email verification (left) and actual email message with verification link (right)</em>
</p>

After registration, users can verify their email address by clicking the activation link sent to the provided address. The user profile displays verification status information, and the system sends a real email containing a personalized verification link.

### 3. Password Reset

<p align="center">
  <img src="assets/images/password-reset-form.png" width="48%" alt="Password reset form">
  <img src="assets/images/password-reset-email.png" width="48%" alt="Email with password reset token">
  <br>
  <em>Password reset form (left) and email with security token (right)</em>
</p>

The password reset system allows account recovery by clicking the "Forgot password?" button in the login form. After entering an email address, the system sends a message containing a unique security token and a link redirecting to the password change form. After entering a new password, the account is updated and the user can log in.

### 4. Profile Personalization

<p align="center">
  <img src="assets/images/profile-view-full.png" width="48%" alt="Profile view">
  <img src="assets/images/profile-edit.png" width="48%" alt="Profile editing">
  <br>
  <em>User profile view (left) and profile editing (right)</em>
</p>

The user profile displays profile picture, background image, personal data, post list and email verification status. Available by clicking the profile picture in the navigation menu, it allows editing data, managing images and using social features.

## Social Features

### Creating and Browsing Posts

<p align="center">
  <img src="assets/images/post-creation.png" width="48%" alt="Post creation">
  <img src="assets/images/posts-logged-in.png" width="48%" alt="Posts list">
  <br>
  <em>Post creation form (left) and browsing posts list (right)</em>
</p>

The system has a post display function with filtering by thematic categories. The platform offers an intuitive post creation form equipped with a text editor with extended formatting capabilities.

**📹 Video demonstration:** `assets/videos/posts-browsing.mp4`

### Managing Own Posts

<p align="center">
  <img src="assets/images/post-menu.png" width="30%" alt="Post management menu">
  <img src="assets/images/post-edit-form.png" width="30%" alt="Post edit form">
  <img src="assets/images/post-edited.png" width="30%" alt="Post after editing">
  <br>
  <em>Own post management menu (left), edit form (center) and post with edit information (right)</em>
</p>

The post author has access to a context menu after clicking the three dots icon, which allows editing or deleting content. The edit form uses the same interface as when creating posts, automatically filled with existing data. After editing, the system automatically marks the post with appropriate modification time and editor information.

### Content Reporting

<p align="center">
  <img src="assets/images/report-menu.png" width="48%" alt="Post reporting menu">
  <img src="assets/images/report-form.png" width="48%" alt="Report form">
  <br>
  <em>Reporting someone else's post menu (left) and content report form (right)</em>
</p>

Users can report inappropriate content by clicking the three dots icon on other users' posts. The system then displays a report form with the ability to choose a reason and add additional description.

### Comment System (Posts and Weapon Models)

<p align="center">
  <img src="assets/images/comment-creation.png" width="48%" alt="Comment creation">
  <img src="assets/images/comment-reply.png" width="48%" alt="Replying to comment">
  <br>
  <em>Creating comment (left) and replying to comment (right)</em>
</p>

<p align="center">
  <img src="assets/images/comment-edit.png" width="30%" alt="Comment editing">
  <img src="assets/images/comment-edited.png" width="30%" alt="Comment after editing">
  <img src="assets/images/comment-report.png" width="30%" alt="Comment reporting">
  <br>
  <em>Comment editing (left), comment after editing (center) and comment reporting (right)</em>
</p>

The comment system is universal and works identically for both social posts and weapon models in the educational module. Users can comment on posts and 3D models and reply to others' comments. Own comments show edit and delete buttons, while others' comments show a report button. The system automatically marks edited comments with appropriate information along with update date.

### Following Users and Search

<p align="center">
  <img src="assets/images/following-system.png" width="48%" alt="Following system">
  <img src="assets/images/user-search.png" width="48%" alt="User search">
  <br>
  <em>User following system (left) and user search engine (right)</em>
</p>

The user following system works intuitively - hovering over a name or profile picture shows a profile preview with a follow button. The platform also offers an advanced user search system, available by clicking the "Search people" button in the sidebar.

### Notification System

<p align="center">
  <img src="assets/images/notifications-center.png" width="48%" alt="Notification center">
  <img src="assets/images/notification-redirect.png" width="48%" alt="Notification redirect">
  <br>
  <em>Notifications window (left) and view after clicking on liked comment notification (right)</em>
</p>

The notification system informs users about new followers, likes and comments. Clicking on a notification redirects the user to the appropriate content with clear element highlighting.

### Communication System

<p align="center">
  <img src="assets/images/chat-dropdown.png" width="48%" alt="Chat menu">
  <img src="assets/images/chat-modal.png" width="48%" alt="Conversation window">
  <br>
  <em>Chat menu in navigation (left) and conversation window (right)</em>
</p>

<p align="center">
  <img src="assets/images/chat-fullscreen.png"  width="48%" alt="Fullscreen chat">
  <img src="assets/images/new-conversation.png"  width="48%" alt="Creating new conversation">
  <br>
  <em>Fullscreen messages view (left) and new conversation creation interface (right)</em>
</p>

The chat system is available from two interface levels: dropdown menu in the navigation bar and fullscreen messages page. Both interfaces implement dynamic loading of older messages when scrolling up. Creating new conversations is done through a dedicated view, enabling user search and filtering.

## Educational Weapon Module

### Model Details and Basic Information

<p align="center">
  <img src="assets/images/gun-overview.png" width="48%" alt="Weapon overview">
  <img src="assets/images/gun-contents-history.png" width="48%" alt="Table of contents and history">
  <br>
  <em>Brief weapon description with table of contents (left) and detailed history with extended description (right)</em>
</p>

### Technical Data and Maintenance

<p align="center">
  <img src="assets/images/gun-technical-data.png" width="48%" alt="Technical data">
  <img src="assets/images/gun-maintenance-scheme.png" width="48%" alt="Maintenance scheme">
  <br>
  <em>Weapon technical data (left) and maintenance scheme (right)</em>
</p>

### Weapon Elements

<p align="center">
  <img src="assets/images/gun-parts-collection.png" width="100%" alt="Weapon parts collections">
  <br>
  <em>Interactive weapon parts system with collection divisions</em>
</p>

### Renders and 3D Model

<p align="center">
  <img src="assets/images/gun-renders.png" width="48%" alt="Weapon renders">
  <img src="assets/images/gun-3d-model-viewer.png" width="48%" alt="3D model preview">
  <br>
  <em>Weapon renders (left) and 3D weapon models (right)</em>
</p>

### 3D Model (Assembled Weapon) and Part Clicking

<p align="center">
  <img src="assets/images/gun-3d-model-part-click.png" alt="Clicking on element">
  <br>
  <em>Clicking on selected weapon element</em>
</p>

### 3D Model - Disassembly Animation and Parts List

<p align="center">
  <img src="assets/images/gun-3d-model-animation.png" width="48%" alt="Disassembly animation">
  <img src="assets/images/gun-3d-model-disassembled.png" width="48%" alt="Disassembled weapon with parts list">
  <br>
  <em>Weapon disassembly animation (left) and disassembled weapon with parts selection from list (right)</em>
</p>

### Sources and Comments

<p align="center">
  <img src="assets/images/gun-sources-comments-start.png" width="48%" alt="Sources and comment beginning">
  <img src="assets/images/gun-comments-continuation.png" width="48%" alt="Comments continuation">
  <br>
  <em>Sources section with comment beginning (left) and comments continuation (right)</em>
</p>

---

The educational module combines interactive 3D models with comprehensive weapon information, offering users exploration possibilities through both model part clicking and disassembly animations. The system also enables knowledge exchange through comments and access to information sources.

**📹 Full page walkthrough:** `assets/videos/gun-educational-page-scrolling.mp4`

**📹 3D model interaction demonstration:** `assets/videos/3d-model-animations-and-exploration.mp4`

## Role-Based Features

### 3D Graphic Artist
<p align="center">
  <img src="assets/images/3d-graphic-gun-list.png" width="48%" alt="Weapon list for graphic artist">
  <img src="assets/images/3d-model-upload.png" width="48%" alt="3D model upload">
  <br>
  <em>Weapon list with additional management options (left) and new 3D model upload (right)</em>
</p>

<p align="center">
  <img src="assets/images/gun-educational-sections-edit-buttons.png" width="48%" alt="Information sections with edit buttons">
  <img src="assets/images/gun-information-edit-form.png" width="48%" alt="Information edit form">
  <br>
  <em>Information sections with edit buttons in top right corner (left) and information edit form (right)</em>
</p>

<p align="center">
  <img src="assets/images/gun-3d-model-edit-options.png" width="48%" alt="3D model with edit options">
  <img src="assets/images/gun-model-texture-replacement.png" width="48%" alt="3D model and texture replacement">
  <br>
  <em>3D model with edit options (left) and 3D model or texture replacement panel (right)</em>
</p>

<p align="center">
  <img src="assets/images/gun-animation-management-1.png" width="48%" alt="Animation management - frame setting">
  <img src="assets/images/gun-animation-management-2.png" width="48%" alt="Animation management - part highlighting">
  <br>
  <em>Setting start and end frames for weapon disassembly/assembly (left) and configuring part highlighting with descriptions in specific frames (right)</em>
</p>

<p align="center">
  <img src="assets/images/gun-renders-management.png" width="48%" alt="Render management">
  <br>
  <em>3D model render management panel</em>
</p>

The 3D Graphic Artist has full access to managing all aspects of 3D models. Each information section (history, technical data, maintenance) contains edit buttons in the top right corner, enabling quick content modification through a dedicated form. The system also offers advanced 3D model editing options, including the ability to replace GLB files and textures (Diffuse, Normal, Roughness).

Animation management consists of two stages: the first allows setting start and end frames for weapon disassembly and assembly animations, while the second enables precise configuration of which parts should be highlighted in specific animation frames along with their assigned descriptions that appear during playback. The render management panel enables adding, editing and organizing all presentation images related to 3D models.

### Moderator

<p align="center">
  <img src="assets/images/moderator-menu.png" width="48%" alt="Moderator menu">
  <img src="assets/images/moderator-edit.png" width="48%" alt="Moderator editing">
  <br>
  <em>Moderator menu for content management (left) and content editing with moderator designation (right)</em>
</p>
<p align="center">
  <img src="assets/images/moderator-reports-panel.png" width="48%" alt="Reports panel">
  <img src="assets/images/moderator-user-management.png" width="48%" alt="User management">
  <br>
  <em>Reports panel (left) and user management panel (right)</em>
</p>
<p align="center">
  <img src="assets/images/moderator-report-solution.png" width="48%" alt="Report resolution by moderator">
  <img src="assets/images/moderator-ban-form.png" width="48%" alt="User ban form">
  <br>
  <em>Report resolution panel with ready templates (left) and user ban form (right)</em>
</p>

The Moderator can edit content of all users' comments and posts and has access to a dedicated panel for managing reports and users with search, filtering and banning options. The report resolution system enables direct editing of reported content and describing taken actions using ready templates. The Moderator can also remove inappropriate profile pictures, backgrounds and user descriptions (partial profile modification).

### Administrator

<p align="center">
  <img src="assets/images/admin-dashboard.png" width="48%" alt="Administrator dashboard">
  <img src="assets/images/admin-posts-category.png" width="48%" alt="Category management">
  <br>
  <em>Dashboard with system statistics (left) and post category management panel (right)</em>
</p>

<p align="center">
  <img src="assets/images/admin-user-management.png" width="68%" alt="User management">
  <img src="assets/images/add-user.png" width="30%" alt="Adding user">
  <br>
  <em>User management panel (left) and new user creation form (right)</em>
</p>

The Administrator has access to all platform functionalities and a dedicated management panel. The dashboard presents comprehensive system statistics. In the "Categories" tab, the administrator can manage post categories. In the "Users" tab, they manage system user accounts, with the ability to edit data, delete accounts and add new accounts with appropriate role assignment.

## Responsiveness and Themes

### Light Theme Interface

<p align="center">
  <img src="assets/images/posts-light-theme.png" width="48%" alt="Posts in light theme">
  <img src="assets/images/gun-3d-model-light-theme.png" width="48%" alt="Educational page in light theme">
  <br>
  <em>Posts view in light theme (left) and 3D model educational page in light theme (right)</em>
</p>

### Mobile View

<p align="center">
  <img src="assets/images/posts-mobile.png" width="30%" alt="Posts on mobile device">
  <img src="assets/images/gun-3d-model-mobile.png" width="30%" alt="Educational page on mobile device">
  <img src="assets/images/moderator-user-management-mobile.png" width="30%" alt="Moderator panel on mobile device">
  <br>
  <em>Posts view on mobile (left), educational page on mobile (center) and user management panel for moderator on mobile (right)</em>
</p>

The application offers full responsiveness and light theme interface support, ensuring optimal user experience regardless of the device used or visual preferences.

## Visual Materials

All application views shown use a camouflage pattern background from Vecteezy[1], while photos and videos featured in the portal come from Adobe Stock[2] and Pexels[3] under free license.

**Sources:**
- [1] Vecteezy.com – https://www.vecteezy.com/photo/51259018-green-stylish-camouflage-military-pattern
- [2] Adobe Stock – https://stock.adobe.com/
- [3] Pexels – https://www.pexels.com/

## Contact Information

For more information about this project, please contact:
- Email: [calka.szymek@gmail.com]

---

*Note: This project was created as an engineering thesis, therefore the source code is not publicly available. The project is presented as a portfolio element and is not available for public use or distribution. All visual materials and demonstrations are shared solely to showcase the programmer's skills and capabilities.*
