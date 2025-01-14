# Personal Dev Site Example

A personal development site created using Firebase Hosting. This project is set up for easy deployment and continuous integration with GitHub Actions.

## Project Overview

This project includes:
- Static assets served from the `public` directory.
- Firebase Hosting for deployment.
- GitHub Actions for automated deployment workflows.

## Project Structure

```bash
$ tree -L 2
.
└── public
    ├── assets
    └── index.html
```


## Prerequisites

Before you begin, ensure you have the following installed on your system:
- [Node.js](https://nodejs.org/)
- [Firebase CLI](https://firebase.google.com/docs/cli)
- A GitHub account

## Getting Started

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/f3lin/personal-dev-site-example.git
cd personal-dev-site-example
```

### 2. Install Firebase CLI
Ensure Firebase CLI is installed. If it’s not, install it globally:

```bash
npm install -g firebase-tools
```

### 3. Set Up Firebase Hosting
Run the following command to initialize Firebase Hosting in the project directory:

```bash
firebase init hosting
```

Firebase Hosting Setup Steps:
1. Choose Create a new project if prompted.
2. Provide a unique project ID (e.g., personal-dev-site-example).
3. Set the public directory to public.
4. Configure as a single-page app by selecting Yes.
5. Enable automatic builds and deploys with GitHub.
6. Use the detected .git folder for integration.

### 4. Push Workflow Files to GitHub
Firebase CLI generates workflow files for GitHub Actions and additional files. 

```text
Folder PATH listing
C:.
│   .firebaserc
│   .gitignore
│   firebase.json
│   README.md
│   tree.txt
│   
├───.github
│   └───workflows
│           firebase-hosting-merge.yml
│           firebase-hosting-pull-request.yml
│           
├───ChatGpt
│       response.html
│       
└───public
    │   index.html
    │   
    └───assets
```
Key Files:

- ``firebase.json``: This file contains Firebase Hosting configuration, including public directory paths, rewrite rules, redirects, and other deployment settings.
- ``.firebaserc``: This file associates the project directory with a Firebase project ID, ensuring correct deployment to the specified Firebase project.

Push these to your repository:

```bash
git add .
git commit -m "Add Firebase Hosting workflows"
git push origin main
```

### 5. Test the Site localy:

```bash
firebase emulators:start

┌──────────┬────────────────┐
│ Emulator │ Host:Port      │
├──────────┼────────────────┤
│ Hosting  │ 127.0.0.1:5000 │
└──────────┴────────────────┘
Emulator Hub running at 127.0.0.1:4400
Other reserved ports: 4500
```

### 6. Deploy the Site
To deploy your site, use the following command:

```bash
firebase deploy --only hosting
```

Alternatively, if you worked on another branch let say ``dev``, merge a pull request into the ``main`` branch, and the site will be deployed automatically through GitHub Actions.

This is also called [Preview Channels](https://firebase.blog/posts/2020/10/preview-channels-firebase-hosting/)

## Accessing Your Site

Once deployed, your site will be live at the Firebase Hosting URL:
https://personal-dev-site-example-id.web.app or https://personal-dev-site-example-id.firebaseapp.com

You can find the URL in the Firebase Console:
[firebase](https://console.firebase.google.com/)