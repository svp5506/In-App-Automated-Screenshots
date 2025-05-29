<p align="center">
  <a href="https://pptr.dev/">
    <img src="https://user-images.githubusercontent.com/10379601/29446482-04f7036a-841f-11e7-9872-91d1fc2ea683.png" alt="Puppeteer logo" width="103" height="150">
  </a>
</p>

# In-App Automated Screenshots for Spectrum.net

[![Node.js Version](https://img.shields.io/badge/Node.js-%3E%3D14-brightgreen.svg)](https://nodejs.org/)
[![Powered by Puppeteer](https://img.shields.io/badge/powered%20by-Puppeteer-24A770.svg?logo=Puppeteer)](https://pptr.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This project uses Puppeteer to automate logging into Spectrum.net and capturing screenshots of various pages, primarily for documentation or QA purposes.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Screenshot Samples](#screenshot-samples)
- [Important Security Note](#important-security-note)
- [Troubleshooting](#troubleshooting)
- [Disclaimer](#disclaimer)

## Features

-   Automated login to Spectrum.net using Puppeteer.
-   Interactive progress bar indicating the screenshot workflow status.
-   Captures screenshots of key account pages:
    -   Homepage
    -   Billing (including Payment Methods section)
    -   Services (overview and individual pages for Internet, Home Phone, TV, Mobile)
    -   Upgrades
    -   Support Home

## Getting Started

### Prerequisites

-   Node.js (v14 or higher recommended)
-   npm (comes with Node.js) or yarn

### Installation

1.  **Clone the repository (if you haven't already):**
    ```sh
    git clone <https://github.com/svp5506/In-App-Automated-Screenshots>
    cd In-App-Automated-Screenshots
    ```

2.  **Install dependencies:**
    ```sh
    npm install
    ```
    Or if you use yarn:
    ```sh
    yarn install
    ```

## Usage

Run the script from your terminal. You will be prompted to enter your Spectrum username and password.

```sh
node puppeteer.js
````

Screenshots will be saved in the `Screenshots/` directory within the project folder, organized by page section.

## How It Works

The script performs the following actions:

  - Launches a headless Chromium browser instance using Puppeteer.
  - Applies the stealth plugin to make the automated browser appear more like a regular user.
  - Prompts the user for their Spectrum.net username and password securely via the terminal.
  - Navigates to the Spectrum.net login page.
  - Enters the provided credentials and submits the login form.
  - Waits for successful login and navigation to the account homepage.
  - Iterates through a predefined list of pages/URLs.
  - For each page:
      - Navigates to the URL.
      - Waits for specific elements to load (if necessary) to ensure the page is fully rendered.
      - Takes a full-page screenshot.
      - Saves the screenshot to the `Screenshots/` directory.
  - Displays progress using a CLI progress bar.
  - Closes the browser upon completion or if an error occurs.

## Important Security Note

Your Spectrum.net credentials are **NOT** hardcoded into the script.

For your safety, you are prompted to enter your username and password directly in the terminal at runtime. This information is used only for the current session to log in and is not stored or written to any file. This method prevents accidental exposure of sensitive information in your codebase or version control system.

## Screenshot Samples

**Homepage**
![./Screenshots/Homepage.png](https://github.com/svp5506/In-App-Automated-Screenshots/blob/main/Screenshots/Homepage.png)


## Troubleshooting

  - **Login Fails:**
      - Spectrum.net might have updated its login page structure. The Puppeteer selectors in the script may need updating.
      - Incorrect credentials entered.
      - CAPTCHAs or other anti-bot measures might have been triggered. The stealth plugin helps, but isn't foolproof. You might need to solve a CAPTCHA manually in non-headless mode (by setting `headless: false` in Puppeteer launch options for debugging).
  - **Page Not Found / Incorrect Screenshots:**
      - URLs or page structures on Spectrum.net might have changed. Update the navigation logic and selectors.
  - **Puppeteer Errors:**
      - Ensure you have a compatible version of Node.js.
      - Chromium might not have downloaded correctly during `npm install`. Try removing `node_modules` and `package-lock.json` and running `npm install` again.


## Disclaimer

This script is intended for educational, personal documentation, and internal QA purposes only.

  - **Do not share your credentials with others.**
  - Automating login to third-party services may be against their Terms of Service. Use this script responsibly and at your own risk.
  - The maintainers of this project are not responsible for any misuse of this script or for any actions taken against your Spectrum account as a result of its use.
