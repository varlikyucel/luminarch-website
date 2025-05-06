# LuminArch Website

This repository contains the website for LuminArch, a serious game for architects.

https://luminarch.app

## Download Form Implementation

The website includes a user registration system for downloads. When users click the download button, they are directed to a form where they need to provide:

- Full Name
- Email Address
- School/Company Affiliation

### How It Works

1. User clicks the "Download" button on the main page
2. User is directed to `download-form.html` where they fill out the required information
3. Upon submission, the form data is sent to Formspree (a ready-made form backend service)
4. Instead of redirecting to another page, the form:
   - Shows a success message with the installation password on the same page
   - Automatically starts the download
   - Provides a manual download link as backup

### Form Setup

The implementation uses [Formspree](https://formspree.io/) which is a ready-made solution that:

- Collects form submissions
- Sends you email notifications
- No backend code or server setup needed

This is the same service already used for the contact form on the website.

The form uses JavaScript to:

1. Validate user input
2. Submit the data to Formspree via AJAX
3. Show the success message without page redirection
4. Start the download automatically

### Password Management

The current implementation displays a static password directly on the form page after submission. For enhanced security in the future, you could:

1. Create different forms for different user groups
2. Show different passwords based on user information
3. Use Formspree webhooks to integrate with more advanced systems if needed

## Files Overview

- `index.html` - Main website with link to download form
- `download-form.html` - Form for collecting user information and handling the download

## Notes

- This implementation doesn't require any backend setup (PHP, database, etc.)
- All form submissions will be collected in your Formspree dashboard
- You can export user information from Formspree if needed
