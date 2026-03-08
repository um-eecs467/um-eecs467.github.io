# EECS 467 Course Website

Jekyll-based course website for **EECS 467: Autonomous Robotics Design Experience** at the University of Michigan.

Live site: [um-eecs467.github.io](https://um-eecs467.github.io)

---

## Table of Contents

1. [Directory Structure](#directory-structure)
2. [Running Locally](#running-locally)
3. [How to Update Course Content](#how-to-update-course-content)
   - [Course Info & Semester Settings](#course-info--semester-settings)
   - [Staff (Instructors & TAs)](#staff-instructors--tas)
   - [Navigation](#navigation)
   - [Home Page](#home-page)
   - [Schedule](#schedule)
   - [Lectures](#lectures)
   - [Assignments (Botlab Docs)](#assignments-botlab-docs)
   - [Project Page](#project-page)
   - [Materials Page](#materials-page)
4. [Adding a New Semester](#adding-a-new-semester)
5. [Styling & Theming](#styling--theming)

---

## Directory Structure

```
um-eecs467.github.io/
│
├── _config.yml               # Site-wide settings (course name, URL, semester)
│
├── _data/
│   ├── nav.yml               # Top navigation bar links
│   ├── people.yml            # Instructor and TA info (name, email, office hours)
│   ├── semesters.yml         # Semester dropdown selector data
│   ├── previous_offering.yml # Links to previous semester sites
│   └── botlab_nav.yml        # Sidebar navigation for the Assignments/Botlab docs
│
├── _includes/
│   ├── header.html           # Site header
│   ├── nav.html              # Navigation menu (reads from _data/nav.yml)
│   ├── head.html             # HTML <head> (meta, CSS links)
│   └── footer.html           # Site footer
│
├── _layouts/
│   ├── default.html          # Base layout wrapping all pages
│   ├── home.html             # Home page layout (staff headshots, announcements)
│   ├── docs.html             # Botlab docs layout (sidebar + content)
│   ├── lectures.html         # Lectures page layout
│   ├── schedule.html         # Schedule page layout
│   └── assignments.html      # Assignments index layout
│
├── _sass/
│   ├── _user_vars.scss       # Color theme variables (primary/secondary colors)
│   ├── _docs.scss            # Styles for Botlab docs layout, callouts, copy button
│   ├── _syntax-highlighting.scss  # Code block syntax highlighting (GitHub Light)
│   ├── _header.scss          # Header styles
│   └── _layout.scss          # General layout styles
│
├── _css/
│   └── main.scss             # Master CSS file — imports all partials above
│
├── _images/
│   └── pp/                   # Staff profile pictures (webp/svg)
│
├── assets/
│   ├── images/botlab/        # All images used in Botlab documentation
│   └── pdfs/                 # PDF files (schematics, architecture diagrams)
│
├── index.md                  # Home page content
├── lectures.md               # Lectures page content
├── assignments.md            # Legacy assignments page (not primary)
├── materials.md              # Legacy materials page (not primary)
├── project.md                # Legacy project page (not primary)
│
├── w26/                      # Winter 2026 semester content (all under /w26/ URL)
│   ├── schedule.md           # /w26/schedule/ — weekly course schedule
│   ├── lectures.md           # /w26/lectures/ — lecture links and resources
│   ├── project.md            # /w26/project/ — design project requirements
│   ├── materials.md          # /w26/materials/ — course resource links
│   └── assignments/          # /w26/assignments/ — Botlab documentation
│       ├── index.md          # Botlab overview page
│       ├── get-started.md
│       ├── mbot-hardware-setup-pi5.md
│       ├── mbot-system-setup-pi5.md
│       ├── mbot-hardware-design.md
│       ├── mbot-software-library.md
│       ├── checkpoints/
│       │   ├── index.md
│       │   ├── checkpoint0.md through checkpoint4.md
│       │   ├── design-lab.md
│       │   └── competition.md
│       └── how-to-guide/
│           ├── index.md
│           ├── slam-toolbox-guide.md
│           ├── mbot-xl320-guide.md
│           └── misc.md
│
├── Gemfile                   # Ruby gem dependencies
└── resources/                # Source material used to build the site (not served)
    ├── website_requirements.txt
    ├── course_info.md
    ├── course_schedule.md
    ├── relevant_links.txt
    └── design_project_info.md
```

---

## Running Locally

Requires Ruby 3.2+ (e.g., via Homebrew: `brew install ruby`).

```bash
# From the repository root
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
gem install bundler
bundle install
bundle exec jekyll serve --livereload
```

Site will be available at `http://localhost:4000`. Changes to files trigger an automatic rebuild.

---

## How to Update Course Content

### Course Info & Semester Settings

Edit **`_config.yml`**:

```yaml
course_name: "EECS 467: Autonomous Robotics Design Experience"
course_semester: "Winter 2026"
course_description: "..."
url: "https://um-eecs467.github.io/"
```

Restart the local server after changing `_config.yml` (it is not hot-reloaded).

---

### Staff (Instructors & TAs)

Edit **`_data/people.yml`**:

```yaml
instructors:
  - name: Xiaoxiao Du
    profile_pic: /_images/pp/xiaoxiao.webp  # place image in _images/pp/
    webpage: https://xiaoxiaodu.net
    role: Instructor
    email: xiaodu@umich.edu
    office: "3257 FMCRB"
    office_hours: "By appointment"

teaching_assistants:
  - name: Rishad Hasan
    profile_pic: /_images/pp/blank.svg      # use blank.svg if no photo
    email: rishadh@umich.edu
    role: Graduate Assistant
    office_hours: "Mondays 3–5pm, BBB 3rd floor"
```

To add a profile photo, place a `.webp` or `.jpg` file in `_images/pp/` and update the `profile_pic` path.

---

### Navigation

Edit **`_data/nav.yml`** to change top-bar links. All semester-specific pages use the `/w26/` prefix:

```yaml
items:
  - url: /w26/schedule/
    name: Schedule
    icon_class: fas fa-calendar-alt
  - url: /w26/assignments/
    name: Assignments
    icon_class: fas fa-tasks
```

The semester dropdown in the nav is driven by **`_data/semesters.yml`**:

```yaml
current: w26
semesters:
  - label: "W26"
    key: w26
    url: /w26/
    name: "Winter 2026"
```

---

### Home Page

Edit **`index.md`** directly. It uses Markdown with HTML tables and supports standard Markdown formatting.

Key sections to update each semester:
- Lecture times and room (HTML table near the top)
- Important links table (Piazza, GitLab, PrairieLearn, etc.)
- Grading breakdown table
- Course policies (collaboration, GenAI, lab equipment)

---

### Schedule

Edit **`w26/schedule.md`**. The schedule is a hand-authored HTML table. Each row corresponds to one week.

**Row classes for color coding:**
- `class="schedule-row-exam"` — light red highlight (competitions, midterms)
- `class="schedule-row-project-due"` — light yellow highlight (checkpoint due dates)
- `class="schedule-week-header"` — blue header row (week label)

Example row:
```html
<tr class="schedule-row-project-due">
  <td>Week 5<br><small>Feb 10</small></td>
  <td>Lecture: SLAM</td>
  <td>Lab: <a href="/w26/assignments/checkpoints/checkpoint2/">Checkpoint 2</a> due</td>
  <td>Feb 14</td>
</tr>
```

The "Checkpoints reference" link at the top points to `/w26/assignments/checkpoints/`.

---

### Lectures

Edit **`w26/lectures.md`**. Update the YouTube playlist URL and PrairieLearn URL at the top of the file.

---

### Assignments (Botlab Docs)

All Botlab documentation lives under **`w26/assignments/`**. The content is kept in sync with the [rob550-docs](https://rob550-docs.github.io/docs/botlab/) source.

**To update a doc page:**
1. Edit the corresponding file under `w26/assignments/` (e.g., `checkpoints/checkpoint1.md`).
2. Keep all internal links pointing to `/w26/assignments/...` (not `/docs/botlab/...`).
3. Keep all image paths as `/assets/images/botlab/...` (local copies, not external URLs).

**To add a new doc page:**
1. Create a `.md` file under the appropriate subdirectory.
2. Add the following front matter:
   ```yaml
   ---
   layout: docs
   title: Your Page Title
   permalink: /w26/assignments/your-page/
   last_modified_at: 2026-01-01
   ---
   ```
3. Add an entry to **`_data/botlab_nav.yml`** so it appears in the sidebar:
   ```yaml
   - title: "Your Page Title"
     url: /w26/assignments/your-page/
   ```

**Sidebar navigation order** is controlled entirely by the order of entries in `_data/botlab_nav.yml`. Edit that file to reorder, rename, or restructure the sidebar.

**Callout blocks** (matching just-the-docs style) are applied via kramdown IAL syntax:
```markdown
This text will appear in a cyan "Required For the Report" box.
{: .required_for_report }

This is a warning.
{: .warning }

This is a note.
{: .note }

This is important.
{: .important }
```

**Images** used in Botlab docs are stored locally under `assets/images/botlab/`. If the rob550 source adds new images, copy them to the same relative path under `assets/` here.

---

### Project Page

Edit **`w26/project.md`**. Contains design project requirements: team formation, proposal, status update, and final presentation details. Update dates and requirements each semester.

---

### Materials Page

Edit **`w26/materials.md`**. Contains a table of course resource links (Piazza, Google Drive, GitLab, PrairieLearn, etc.). Update URLs at the start of each semester.

---

## Adding a New Semester

1. **Create a new semester directory**, e.g., `f26/` for Fall 2026.
2. **Copy** the contents of `w26/` into `f26/` and update all `permalink` values in front matter from `/w26/...` to `/f26/...`.
3. **Update `_data/nav.yml`** to point all links to `/f26/...`.
4. **Update `_data/semesters.yml`** to add the new semester and set it as current:
   ```yaml
   current: f26
   semesters:
     - label: "F26"
       key: f26
       url: /f26/
       name: "Fall 2026"
     - label: "W26"
       key: w26
       url: /w26/
       name: "Winter 2026"
   ```
5. **Update `_data/botlab_nav.yml`** — change all `/w26/assignments/...` URLs to `/f26/assignments/...`.
6. **Update `_layouts/docs.html`** — change the `Botlab Docs` header link from `/w26/assignments/` to `/f26/assignments/`.
7. **Update `index.md`** with new semester info (dates, staff, links).
8. **Update `_data/people.yml`** with new staff.
9. **Add the previous semester** to `_data/previous_offering.yml` for archival.

---

## Styling & Theming

**Colors** are set in `_sass/_user_vars.scss`:
```scss
$primary-color:   #00274C;  // Michigan blue
$clemson-purple:  #00274C;
$clemson-orange:  #FFCB05;  // Michigan maize
```

**Code block syntax highlighting** uses a GitHub Light theme defined in `_sass/_syntax-highlighting.scss`. To change themes, replace the token color values in that file.

**Callout styles** (required_for_report, warning, note, important) are in `_sass/_docs.scss`. Each uses the SCSS `callout()` mixin — adjust colors or padding there.

**Docs sidebar width** can be changed in `_sass/_docs.scss` under `.docs-sidebar { width: 260px; }`.
