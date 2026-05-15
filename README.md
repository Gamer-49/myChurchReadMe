# myChurch

A modern **church website and ministry management platform** built to support both **public community engagement** and **internal church operations**.

Church website + ministry operations in one place.
Built with Laravel, React, Inertia.js, and Tailwind CSS.


>  **Beta release**  
> `myChurch` is currently in the **beta phase**. Some features are still being refined.

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
-  **Home carousel** — configurable image/content carousel on the welcome page, pulling from missions, outreach, and schedule items
-  **Past services archive** — browsable list of published weekly services
-  **Full public schedule** — all upcoming recurring and one-time events
-  **Announcements** — publicly visible church announcements
-  **Outreach page** — published outreach events visible to the community
-  **Missions page** — published mission campaigns with details
-  **Prayer request submission** — public form for submitting prayer requests (rate-limited)
-  **Donation form** — public donation submission flow with fund selection (rate-limited)
-  **Contact form** — message submission with rate limiting
-  **About, Directions, Help, and Terms & Privacy** — standard informational pages

### Logged-in member area
-  **Member home** — personalized home page for authenticated non-admin members

### Authentication & access control
-  **Invitation-based registration** — new users register via a secure emailed invitation token
-  **Access request workflow** — visitors can request access; admins approve or deny and trigger an invitation
-  **Login with email pre-check** — two-step login flow that detects whether an account exists
-  **Password reset** — forgot-password and reset-password flows
-  **Email verification** — required before accessing the dashboard
-  **Role-based access control** — assignable roles (e.g., Elevated Member, Admin, Public User, Volunteer) each carrying a set of customizable permissions
-  **Granular permissions** — individual permission flags (e.g., view, create, edit, delete) checked throughout the app
-  **Activity logging** — admin and public actions recorded with IP address, user agent, and metadata. Full admin tracking for administative items.
-  **Security logging & risk scoring** — configurable security event logging with country-based risk signals and configurable log retention

### Admin dashboard
-  **Dashboard overview** — at-a-glance stats: unread messages, pending prayer requests, pending access requests, total members, active missions, upcoming outreach
-  **Dashboard role configuration** — configurable widget layout per role so each user type sees the most relevant information

#### Congregation & members
-  Full CRUD for congregation/member records
-  Complete member record set including general info, sercuity clearence status, and easily accessable emergency contact info
-  Phone number auto-formatting
-  **At-rest encryption** — sensitive member PII is encrypted for migrating existing records

#### Weekly services
-  Create and manage weekly service records tied to a specific Sunday date
-  Rich-text editing with HTML sanitization for sermon and other long-form fields
-  Image upload per service
-  Import from a previous service feature with selectable content to import
-  Published/unpublished toggle
-  **Printable service bulletins** — print-ready bulletin generation with configurable cover image, border style, and typography settings

#### Announcements
-  Create, edit, and delete standalone announcements
-  Attach or detach announcements to specific weekly services, members or public

#### Schedules
-  Create one-time and recurring schedule entries
-  **Calendar view** — visual calendar interface for browsing and managing schedule entries
-  Pint options available to control what is printed (hide personal reminders, print public and admin only schedules)
-  Recurring wizard for complex recurrence patterns
-  Preset recurring schedule upsert (for missions, outreach, and service links)
-  Update or delete entries by unique ID
-  Public schedule visibility toggle
-  Schedule ownership and user assignment controls

#### Events
-  General-purpose church event CRUD

#### Outreach
-  Create and manage outreach events
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
-  Moderate requests: accept, fullfilled, create (notes for admins function scheduled for next update)
-  Customizable print options

#### Donations
-  Admin view and management of all donation submissions
-  **Donation funds** — categorized fund management (e.g., general, building, missions) with active/sort-order controls
-  **Payment gateway integration** — pluggable gateway support for Stripe, PayPal, and Square; gateway settings configurable from admin
-  **Giving statements** — generate and view donor giving summaries
-  **My Giving** — logged-in members can view their own donation history
-  **Donation receipts** — automated email receipts sent to donors on submission

#### Messages / Contact inbox
-  View all contact form submissions
-  Track read/unread status per message

#### Church board
-  Manage board member records
-  Configurable leadership types and leadership roles
-  Manage custom title keys used across board listings
-  Leadership settings page

#### Church minutes
-  Create structured meeting minutes
-  Business items list with sort order
-  Business updates log per minute
-  Full revision history per minute record
-  Editor lock — prevents simultaneous edits by multiple users
-  Browsable minutes list and detailed show view
-  Print customization

#### User management
-  View all users with their roles and permissions
-  Send, edit, resend, and revoke invitations
-  Review and approve or deny access requests
-  Update a user's account type, roles, and individual permissions

### Settings
-  **Site profile** — church name, address, phone, email, service times, app logo, print header image, public banner image
-  **About page settings** — content shown on the public About page
-  **Public outreach settings** — content shown on the public outreach page
-  **Public missions settings** — content shown on the public mission page
-  **Home carousel settings** — manage carousel items shown on the public welcome page
-  **Donation gateway settings** — configure active payment gateway and credentials
-  **Notification preferences** — per-user control over notification delivery (none, dashboard, email, or both) for each notification type
-  **User profile** — update display name and email address
-  **Password** — change account password
-  **Appearance** — UI appearance preferences

### Notifications
-  **In-app notifications** — dashboard notification dropdown and widget for real-time alerts
-  **Email notifications** — email delivery option respecting per-user preferences
-  **Notification types** — access requests, invitations, announcements, task assignments, prayer list updates, schedule changes, and outreach reminders

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
