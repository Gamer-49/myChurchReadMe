# myChurch

A modern **church website and ministry management platform** built to support both **public community engagement** and **internal church operations**.

Church website + ministry operations in one place.
Built with Laravel, React, Inertia.js, and Tailwind CSS.


>  **Alpha release**  
> `myChurch` is currently in the **alpha phase**. Some features are still being refined, workflows may change.

##  Overview

`myChurch` brings together the core tools many churches need in one place:

- a public-facing CMS website for visitors and members
- admin tools for managing ministry activity
- scheduling and service planning workflows
- outreach, missions, prayer, donations, and communications management
- role-based access control with invitation-based onboarding

The goal is to provide a practical, organized foundation for churches that want a lightweight digital system for both website content and day-to-day administration.

##  Why I Built This

Many churches manage announcements, schedules, outreach notes, communication, and ministry records across disconnected tools or manual processes. `myChurch` is being built as a more unified solution.

This project also reflects a hands-on full-stack build that combines backend business logic, admin workflows, and a modern frontend experience designed to be secure and simple to use.

##  Features

### Public site
-  **Welcome page** — church info, upcoming schedule (services, missions, outreach), and current/most-recent Sunday service snapshot
-  **Past services archive** — browsable list of published weekly services
-  **Full public schedule** — all upcoming recurring and one-time events
-  **Announcements** — publicly visible church announcements
-  **Outreach page** — published outreach events visible to the community
-  **Missions page** — published mission campaigns with details
-  **Prayer request submission** — public form for submitting prayer requests (rate-limited)
-  **Donation form** — public donation submission flow (rate-limited)
-  **Contact form** — message submission with rate limiting
-  **About, Directions, Help, and Terms & Privacy** — standard informational pages

### Authentication & access control
-  **Invitation-based registration** — new users register via a secure emailed invitation token
-  **Access request workflow** — visitors can request access; admins approve or deny and trigger an invitation
-  **Login with email pre-check** — two-step login flow that detects whether an account exists
-  **Password reset** — forgot-password and reset-password flows
-  **Email verification** — required before accessing the dashboard
-  **Role-based access control** — assignable roles (e.g., Elevated Member, top admin) each carrying a set of permissions
-  **Granular permissions** — individual permission flags (e.g., `invitations.manage`, `users.access.manage`, `leadership.manage`) checked throughout the app
-  **Activity logging** — admin and public actions recorded with IP address, user agent, and metadata

### Admin dashboard
-  **Dashboard overview** — at-a-glance stats: unread messages, pending prayer requests, pending access requests, total members, active missions, upcoming outreach

#### Congregation & members
-  Full CRUD for congregation/member records
-  Fields: name, email, phone, address, gender, birthday, anniversary, joined date, church roll, privilege level, security clearance dates, emergency contact, allergies/needs, notes
-  Phone number auto-formatting

#### Weekly services
-  Create and manage weekly service records tied to a specific Sunday date
-  Fields: title, description, opening reading & scripture, prayer, opening hymn, songs, children's moment, sermon, announcements, offering doxology, praises & prayer, closing hymn, closing prayer, weekly readings
-  Rich-text editing with HTML sanitization for sermon and other long-form fields
-  Image upload per service
-  Carry-over announcements from a previous service
-  Published/unpublished toggle
-  Announcements attached or detached per service

#### Announcements
-  Create, edit, and delete standalone announcements
-  Attach or detach announcements to specific weekly services

#### Schedules
-  Create one-time and recurring schedule entries
-  Recurring wizard for complex recurrence patterns
-  Preset recurring schedule upsert (for missions, outreach, and service links)
-  Update or delete entries by unique ID
-  Public schedule visibility toggle (`usage` flags)

#### Events
-  General-purpose church event CRUD

#### Outreach
-  Create and manage outreach events (title, description, date, location, time, event type, items to bring)
-  Track attendance counts, item counts, and items-given counts
-  Manage ordered outreach items and purchase records per event
-  Public visibility toggle per event
-  Public outreach settings page (controls what visitors see)

#### Missions
-  Create and manage mission campaigns (title, details, start/end dates, completed flag)
-  Mission items with transaction history and item-count tracking
-  Unique-title validation
-  Public visibility toggle
-  Public missions settings page

#### Prayer list
-  View all submitted prayer requests
-  Moderate requests

#### Donations
-  Admin view and management of all donation submissions

#### Messages / Contact inbox
-  View all contact form submissions
-  Manage status per message

#### Church board
-  Manage board member records
-  Configurable leadership types and leadership roles
-  Manage custom title keys used across board listings
-  Leadership settings page

#### Church minutes
-  Create structured meeting minutes (meeting date, time, location, presiding officer, treasurer, secretary, members present/absent, called to order, opening prayer, reading of previous minutes with vote counts, old business items with discussion/action/status, next meeting info, closing prayer, adjournment details)
-  Business items list with sort order
-  Business updates log per minute
-  Full revision history per minute record
-  Editor lock — prevents simultaneous edits by multiple users
-  Browsable minutes list and detailed show view

#### User management
-  View all users with their roles and permissions
-  Send, edit, resend, and revoke invitations
-  Review and approve or deny access requests
-  Update a user's account type, roles, and individual permissions

### Settings
-  **Site profile** — church name, address, phone, email, service times, app logo, print header image, public banner image
-  **About page settings** — content shown on the public About page
-  **Public outreach settings** — control what outreach information is displayed publicly
-  **Public missions settings** — control what mission information is displayed publicly
-  **User profile** — update display name and email address
-  **Password** — change account password
-  **Appearance** — UI appearance preferences

##  Tech Stack

| Layer | Technology |
|---|---|
| Backend | `PHP 8.2`, `Laravel 12`, `Laravel Sanctum` |
| Frontend | `React 19`, `TypeScript`, `Inertia.js`, `Vite 6` |
| UI | `Tailwind CSS 4`, `shadcn/ui`, `Radix UI`, `MUI`, `Lucide` |
| Routing | `Ziggy` |
| Testing | `Pest`, `PHPUnit` |
| Quality | `ESLint`, `Prettier` |
| Local DB | `SQLite` |

##  Project Status

This project is being actively shaped and improved.

Current status:
- alpha-stage functionality is available
- core modules are in place
- UI/UX and workflows are still being refined
- documentation and presentation assets are still growing
