# 8base-test

### Quick Start guide feedback https://docs.8base.com/docs/getting-started/quick-start/

The Quick Start guide is mostly clear and provides good start info of how 8base works.

Here is a few problems i notice in Quick Start doc:

- Links that suppose to lead to user workspace sections are lead to https://app.8base.com/developer-home/workspaces page (Bug-01, Bug-03, Bug-04)

- Screenshot in section "Add user to Notes" is confusing, checkboxes in screenshot are messed up (Bug-02)

- "8base init . --functions=resolver:myCustomResolver" command which suggested in guide to init a project are incorrect, project name
cannot start with period or be empty (Bug-05)

- The overall project structure is confusing. According to guide first we create project tree with server directory and later we init a project with no name in this directory which
is not possible. We must init a project with name "server" to get project tree described in guide.

- Had to add "SKIP_PREFLIGHT_CHECK=true" line in .env file for React starter app to run, because current babel-eslint ver 10.1.0 but app requires ver 10.0.1

- I wasnt able to login into Vue or React starter apps (Bug-06, Bug-07), i did not manage to fing the root of the problem, i followed every step of
Quick Start guide twice. I found community post with similar issue https://community.8base.com/t/login-not-working-in-react-starter-app/531 which
also has no solution.

**************************************
**Bug-01**

Paragraph 2.1: Data Builder link redirects to https://app.8base.com/developer-home/workspaces page

**Steps to reproduce:**

1. Open Quick Start doc, paragraph 2.1: https://docs.8base.com/docs/getting-started/quick-start/#21-building-a-data-model
2. Click on Data Builder link

**Actual result:** link redirects to https://app.8base.com/developer-home/workspaces page

**Expected result:** link leads to workspace data page or there should be no link at all

**Severity**: Minor

**Environment**: Win 10, 1920x1080 Chrome 90.0.4430.212

**************************************

**Bug-02**

Paragraph 2.1: Misguiding screenshot at "Add user to Notes" section

**Steps to reproduce:**

1. Open Quick Start doc, paragraph 2.1: https://docs.8base.com/docs/getting-started/quick-start/#21-building-a-data-model
2. Scroll to "Add user to Notes" section

**Actual result:** Screenshot has "Allow multiple Users per Note" checkbox highlighted and 
"Allow miltiple Notes per User" not hightlighted

**Expected result:** Screenshot has "Allow multiple Users per Note" checkbox NOT highlighted and 
"Allow miltiple Notes per User" hightlighted same as description above screenshot

**Severity**: Trivial

**Environment**: Win 10, 1920x1080 Chrome 90.0.4430.212

**************************************

**Bug-03**

Paragraph 2.1: API Explorer link redirects to https://app.8base.com/developer-home/workspaces page

**Steps to reproduce:**

1. Open Quick Start doc, paragraph 2.1: https://docs.8base.com/docs/getting-started/quick-start/#21-building-a-data-model
2. Click on API Explorer link

**Actual result:** link redirects to https://app.8base.com/developer-home/workspaces page

**Expected result:** link leads to workspace API explorer page or there should be no link at all

**Severity**: Minor

**Environment**: Win 10, 1920x1080 Chrome 90.0.4430.212

**************************************

**Bug-04**

Paragraph 2.3:  Authentication page link redirects to https://app.8base.com/developer-home/workspaces page

**Steps to reproduce:**

1. Open Quick Start doc, paragraph 2.3: https://docs.8base.com/docs/getting-started/quick-start/#21-building-a-data-model
2. Click on Authentication page link

**Actual result:** link redirects to https://app.8base.com/developer-home/workspaces page

**Expected result:** link leads to workspace Authentication page in App Services or there should be no link at all

**Severity**: Minor

**Environment**: Win 10, 1920x1080 Chrome 90.0.4430.212

**************************************

**Bug-05**

Paragraph 3.2: "8base init . --functions=resolver:myCustomResolver" command returns an error

**Description**

Paragraph 3.2 suggests Init new 8base project with one function called myCustomResolver using the
"8base init . --functions=resolver:myCustomResolver" command, which is not correct because "8base init" command
requires project name which cannot start with period or be empty. This is most likely a documentation bug which can confuse user

**Steps to reproduce:**

1. Open 8base CLI
2. Move into any directory
3. Try to init new 8base project with one function called myCustomResolver using the
"8base init . --functions=resolver:myCustomResolver" command as described in Paragraph 3.2 of Quick start

**Actual result:** error: Invalid project name: name cannot start with a period.

**Expected result:** As described in Quick start guide, this command should init new 8base project in working directory

**Severity**: Minor

**Environment**: Win 10, Node.js 16.2.0 (x64), 8base CLI 0.0.109

**************************************

**Bug-06**

An error occurs when trying to sign in in Vue starter app

**Steps to reproduce:**

1. Follow the first 3 paragraphs of Quick Start guide https://docs.8base.com/docs/getting-started/quick-start , on paragraph 3.3 choose Vue app,
dont forget to fill environmental variables of your workspace
2. Run the app using "npm run serve" command
3. Go to http://localhost:3000/
4. Click "Sign in" button

**Actual result:** Page <YOUR_AUTH_DOMAIN>/error?error=invalid_request&client_id=<YOUR_AUTH_CLIENT_ID> opens with message "An error was encountered with the requested page.",
where <YOUR_AUTH_DOMAIN> and <YOUR_AUTH_CLIENT_ID> are environmental variables of your workspace.

**Expected result:** Successful login

**Severity**: Critical

**Environment**: Win 10, Chrome 90.0.4430.212, Node.js 16.2.0 (x64), 8base CLI 0.0.109

**************************************

**Bug-07**

An error occurs when trying to sign in in React starter app

**Steps to reproduce:**

1. Follow the first 3 paragraphs of Quick Start guide https://docs.8base.com/docs/getting-started/quick-start , on paragraph 3.3 choose React app,
dont forget to fill environmental variables of your workspace
2. Run the app using "npm run start" command
3. Go to http://localhost:3000/
4. Click "Sign in" button

**Actual result:** Page <YOUR_AUTH_DOMAIN>/error?error=invalid_request&client_id=<YOUR_AUTH_CLIENT_ID> opens with message "An error was encountered with the requested page.",
where <YOUR_AUTH_DOMAIN> and <YOUR_AUTH_CLIENT_ID> are environmental variables of your workspace.

**Expected result:** Successful login

**Severity**: Critical

**Environment**: Win 10, Chrome 90.0.4430.212, Node.js 16.2.0 (x64), 8base CLI 0.0.109

**************************************
