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
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [License](#license)

## Features

-   Automated login to Spectrum.net using Puppeteer with the `puppeteer-extra-plugin-stealth` to help avoid detection.
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
    git clone <your-repository-url>
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