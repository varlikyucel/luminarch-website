# LuminArch Website Documentation

## Overview

This document outlines the design principles, libraries used, and key UI components of the LuminArch website. The design aims for a "Techno-Experimental" aesthetic, characterized by a dark theme, futuristic elements, dynamic animations, and a dense, information-rich interface.

## Design Philosophy: Techno-Experimental UI

The core goal was to create a visually striking and highly interactive user experience reflecting a cutting-edge, technological theme. Key characteristics include:

- **Dark Mode Dominance:** Utilizing dark backgrounds (`bg-gray-900`, `bg-gray-950`) with contrasting text (`text-gray-100`) and vibrant accents (teal, purple, pink gradients).
- **Futuristic Elements:** Incorporating blurred backgrounds (`backdrop-blur-lg`), animated gradients (`bg-futuristic-animated`), subtle grid overlays (`bg-animated-grid`), clipped corners (`card-clip-path`), and scanline effects.
- **High Interactivity:** Emphasis on hover effects (scaling, translation, glows, shimmers), entrance animations (`animate-text-focus-in`, `animate-text-decode`), and dynamic feedback (pulsing borders, reactive decorative elements).
- **Structure Density:** Compact layout with reduced spacing and padding to create a visually dense, information-packed feel.
- **Smooth Transitions:** Utilizing `scroll-smooth` for navigation and CSS transitions/animations for smooth visual changes.

## Libraries & Dependencies

The site primarily relies on modern web standards (HTML5, CSS3, JavaScript) and leverages the following external resources via CDNs for rapid development and styling:

1.  **Tailwind CSS (via CDN):** The core utility-first CSS framework used for the vast majority of styling, layout, and responsiveness.
2.  **Font Awesome (via CDN):** Used for icons, primarily in the footer and on some buttons.
3.  **Google Fonts (Inconsolata):** Used as the base `font-sans` and for specific `font-mono` elements to enhance the technological feel.
4.  **(Locally Hosted):** Project-specific assets like images (`images/`) and videos (`videos/`).

## Key Features & UI Components

### 1. Overall Layout & Feel

- **Background:** Multi-layered dark background featuring a slowly shifting animated gradient (`bg-futuristic-animated`) overlaid with a subtle, slowly panning dot grid (`bg-animated-grid`), creating a dynamic "digital canvas".
- **Scrolling:** Smooth scrolling enabled globally (`scroll-smooth`), with top scroll padding (`scroll-pt-20`) added to the `<html>` element to ensure navigation links land correctly below the fixed header.
- **Theme:** Dark, with teal, purple, and pink gradients used for accents and highlights.

### 2. Preloader

- **Appearance:** A full-screen, dark overlay (`bg-gray-950`) displaying a custom spinning loader (`animate-spin-slow`) centered on the page.
- **Behavior:** Appears instantly on page load, hides the main content initially (`body.overflow-hidden`), and fades out smoothly (`preloader-hidden` class) once all page resources are loaded (`window.onload`), revealing the content. Includes a minimum display time to prevent flashing.

### 3. Navigation Bar (`<nav>`)

- **Positioning:** Fixed to the top (`fixed`), always visible.
- **Appearance:** Dark (`bg-gray-950`), semi-transparent (`bg-opacity-85`), blurred background (`backdrop-blur-lg`), with a subtle teal bottom border.
- **Logo:** Sharp, bold text with an animated underline effect on hover. Links to `index.html`.
- **Links:** Compact text size, subtle background change (`hover:bg-teal-600/70`) and animated purple underline reveal on hover. Uses `hover-subtle-float` animation. Links point to corresponding sections on `index.html`.

### 4. Header (`<header>`)

- **Layout:** Full viewport height (`min-h-screen`), centered content.
- **Background:** Full-screen autoplaying video (`<video>`) with slight opacity reduction.
- **Content Block:** Centralized text block wrapped in an anchor (`<a>`) linking to the `#about` section. Features:
  - Frosted glass effect (`bg-black/75`, `backdrop-blur-md`).
  - Clipped corner shape (`card-clip-path`).
  - Pulsing gradient border (`border-teal-500/50`).
  - Animated gradient main title (`<h1>`) using `animate-pulse`.
  - Mono-spaced subtitles (`<p>`) with "decode" entrance animation (`animate-text-decode`).
  - Subtle animated scanline effect across the block.
  - Interactive decorative blurred glows (`decorative-glow-1`, `decorative-glow-2`).
- **Interaction:** Clicking the block smoothly scrolls (respecting `scroll-padding-top`) to the "About" section.

### 5. Main Content Sections (`<section>`)

- **General Card Design:** All main content sections (About, Promo Video, Download, Contact) share a consistent card aesthetic:
  - Semi-transparent dark background with blur (`bg-gray-800/85`, `backdrop-blur-lg`).
  - Rounded corners (`rounded-xl`).
  - Drop shadow (`shadow-xl`).
  - Clipped corner (`card-clip-path`).
  - Base border (`border-gray-700/80`).
- **Interactivity:**
  - Entrance animation (`animate-text-focus-in` with staggered delays).
  - Border pulses with color/shadow animation on hover (`border-animated-pulse` triggered by `.group:hover`).
  - Overall section shadow changes color on hover (`hover:shadow-purple-500/30` or `hover:shadow-teal-500/30`).
  - Decorative blurred glows (`decorative-glow-1`, `decorative-glow-2`) react to section hover (scale, opacity, blur changes).
- **Titles (`<h2>`):** Use gradient text effects (`bg-gradient-to-r...`) and are centered.

### 6. Specific Sections

- **Promo Video:** Features the video player with a custom gradient play button overlay. Includes JavaScript for play functionality and handling fullscreen exit scrolling.
- **Download:** Tabbed interface using buttons. JavaScript swaps background classes on button spans to indicate the active tab (gradient vs. gray). Buttons and download links use the `btn-shimmer` effect on hover.
- **Contact:** Includes a styled "FYI" box (`.fyi-box`) with hover effects. Form inputs use custom focus styling (`input-tech-focus`) and `card-clip-path`. The submit button is a large gradient button with `btn-shimmer`.

### 7. Footer (`<footer>`)

- **Appearance:** Dark (`bg-gray-950/85`), blurred background, teal top border. Includes subtle animated background patterns and a bottom scanline effect.
- **Content:** Centered copyright info and social media icons. Includes a "version" indicator in mono font.
- **Social Icons:** Enhanced hover effects including scaling, rotation, color-specific outer shadow (`hover:shadow-[...]`), and icon pulsing (`group-hover:animate-pulse-glow`).

## Custom CSS & Animations (`<style>` block)

The `<style>` block at the end of `index.html` (and copied to `download-form.html`) defines several custom `@keyframes` animations and utility classes to achieve the unique effects:

- `@keyframes scanline`: Creates a horizontal line sweeping effect.
- `@keyframes pulse-glow`: Provides a pulsing shadow/glow effect.
- `@keyframes subtle-float`: A gentle up/down floating effect on hover.
- `@keyframes futuristic-bg`: Animates the background gradient position for the main body.
- `@keyframes text-focus-in`: Fades text in from a blurred state.
- `@keyframes border-pulse`: Animates border color and shadow for section hover.
- `@keyframes shimmer`: Creates a light sweep effect for buttons.
- `@keyframes spin-slow`: A slower version of the standard spin for the preloader.
- `@keyframes text-decode-glitch`: Simulates text glitching/decoding on appearance.
- `.card-clip-path`: Applies the specific `clip-path` for the clipped corner effect.
- `.input-tech-focus:focus`: Defines the custom focus style for form inputs.
- `.bg-animated-grid::before`: Creates and animates the subtle background grid overlay.
- `.decorative-glow-1`, `.decorative-glow-2`: Base classes for decorative elements, styled further on `.group:hover`.
- `.fyi-box:hover`: Styles for the contact section FYI box hover state.
- Preloader styles (`#preloader`, `.preloader-hidden`, `.body-loaded`, `.animate-spin-slow`).
- Active tab button styles (`.active-tab-button`).

## Setup & Running

This is a static website. No build process is required.

1.  Ensure all files (`index.html`, `download-form.html`, `styles.css`, `site.webmanifest`, assets in `images/`, `videos/`) are in the correct directory structure.
2.  Open `index.html` in a modern web browser.

_(Note: The reliance on CDN links means an internet connection is required for Tailwind CSS, Font Awesome, and Google Fonts to load correctly.)_
