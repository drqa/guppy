# Guppy — User Stories (Sprint 1)

Stories are grouped by feature area and ordered to reflect logical development dependencies.

---

## Authentication & Accounts

**US-01 — Register an account**
> As a new user, I want to create an account with an email and password so that I can access the platform and my projects.

Acceptance criteria:
- User can submit a registration form with email, username, and password
- Email must be unique; duplicate registration shows a clear error
- Password has a minimum complexity requirement
- On success, the user is automatically signed in and redirected to their dashboard

---

**US-02 — Sign in**
> As a returning user, I want to sign in with my credentials so that I can access my projects securely.

Acceptance criteria:
- User can sign in with email and password
- Invalid credentials show a generic error (no enumeration of whether email or password was wrong)
- Successful sign-in redirects to the user's dashboard
- Unauthenticated users attempting to access any protected route are redirected to the sign-in page

---

**US-03 — Sign out**
> As a signed-in user, I want to sign out so that my session is ended on shared or public devices.

Acceptance criteria:
- Sign-out is accessible from the main navigation
- Session is fully invalidated on the server after sign-out
- User is redirected to the sign-in page

---

## Projects

**US-04 — Create a project**
> As a user, I want to create a new project so that I have a workspace to organize my team's files.

Acceptance criteria:
- User can create a project by providing a name (required) and optional description
- The creating user is automatically assigned the Admin role on the project
- The new project appears in the user's project list after creation

---

**US-05 — View my projects**
> As a user, I want to see a list of all projects I belong to so that I can navigate to the one I'm working on.

Acceptance criteria:
- Dashboard lists all projects the user is a member of
- Each project entry shows its name and the user's role (Admin or Member)
- Selecting a project navigates to the project's file/folder view

---

**US-06 — Add a member to a project**
> As a project Admin, I want to invite other users to my project by their email so that my team can collaborate.

Acceptance criteria:
- Admin can search for a registered user by email and add them to the project
- Added user immediately sees the project in their dashboard
- Non-admin members cannot access the member management screen

---

**US-07 — Assign Admin role**
> As a project Admin, I want to designate another member as Admin so that project management responsibilities can be shared.

Acceptance criteria:
- Admin can promote any existing member to Admin
- A project must always have at least one Admin (cannot remove the last Admin)
- Role changes are reflected immediately without requiring a page reload

---

## Folder & File Organization

**US-08 — Create a folder**
> As a project member, I want to create folders within a project so that I can organize files into logical groups (e.g., by issue, chapter, or stage).

Acceptance criteria:
- Any project member can create a folder at the root level or nested inside an existing folder
- Folder name is required and must be unique within its parent
- The new folder appears in the folder tree immediately after creation

---

**US-09 — Navigate folder structure**
> As a project member, I want to browse the project's folder tree so that I can find and open the files I need.

Acceptance criteria:
- A collapsible sidebar or breadcrumb trail shows the full folder hierarchy
- Clicking a folder displays its immediate contents (subfolders and files)
- Breadcrumb navigation lets the user jump back to any ancestor folder

---

**US-10 — Move files between folders**
> As a project member, I want to drag and drop files (or use a move action) to reorganize them between folders so that the project structure stays tidy as work evolves.

Acceptance criteria:
- User can drag a file and drop it onto a destination folder
- A context-menu or toolbar "Move" option provides an alternative for accessibility
- Moving a file updates its location without duplicating it
- The UI reflects the change immediately after the move

---

## File Uploads

**US-11 — Upload images in batch**
> As a project member, I want to select and upload multiple image files at once so that I can quickly populate a folder without repeated individual uploads.

Acceptance criteria:
- User can select multiple image files (JPG, PNG, WEBP, GIF, TIFF) from a file picker or drag them onto the upload area
- An upload progress indicator is shown per file
- Successfully uploaded files appear in the current folder immediately
- Files that fail to upload show a per-file error; successful uploads in the same batch are not affected

---

**US-12 — Upload documents in batch**
> As a project member, I want to upload multiple document files at once so that scripts and other written materials are accessible alongside the artwork.

Acceptance criteria:
- User can select multiple documents (PDF, DOCX, TXT, MD) from a file picker or drag them onto the upload area
- Same progress and error behavior as image batch upload (US-11)
- Uploaded documents appear in the current folder immediately

---

## File Viewing

**US-13 — Full-size image viewer**
> As a project member, I want to open an image in a full-size in-browser viewer so that I can examine artwork at full resolution without downloading it.

Acceptance criteria:
- Clicking an image thumbnail opens a full-screen/modal viewer
- Viewer supports pan and zoom
- Previous/Next controls allow cycling through all images in the current folder
- Viewer can be closed to return to the folder view

---

**US-14 — Document viewer**
> As a project member, I want to view documents in the browser so that I can read scripts and notes without downloading them.

Acceptance criteria:
- Clicking a document opens an inline viewer (PDF rendered in-browser; plain text/MD displayed as formatted text)
- Viewer is scrollable and fills the available viewport
- A download button is available for users who need an offline copy

---

## Backlog (Desired Features — not in Sprint 1)

| ID     | Summary |
|--------|---------|
| US-15 | Leave notes/comments on images and documents |
| US-16 | Show commenter identity and allow resolving comments |
| US-17 | Simple image markup (highlighter, pen tool) |
| US-18 | Color-code files by progress status (In Progress / Needs Review / Completed) |
