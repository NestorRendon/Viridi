# Experimental Music Album Website

A minimal, poetic single-page website for the release of an experimental music album. Designed as a digital art object rather than a commercial landing page, with an aesthetic inspired by collage art, contemporary galleries, and experimental music labels.

## Project Description

This is a fully static, single-page website built with pure HTML, CSS, and minimal JavaScript. It features:

- **Minimal, non-traditional aesthetic** with subtle grain texture
- **Experimental typography** combining a high-contrast serif (Cormorant Garamond) with a clean grotesk (Inter)
- **Soft fade-in animations** on scroll
- **Asymmetrical layouts** with careful use of negative space
- **Near-black background** with soft text contrast
- **Embedded YouTube videos** with cinematic aspect ratios
- **Poetic, introspective content** throughout

The website is structured as a vertical scroll with no navigation bar, creating an immersive, gallery-like experience.

## Folder Structure

```
proyecto/
├── index.html          # Main HTML file (all content and styling)
└── README.md           # This file
```

Everything is contained in a single HTML file for simplicity and easy deployment.

## How to Run Locally

1. **Clone or download** this repository to your local machine.

2. **Open the file directly** in a web browser:
   - Double-click `index.html`, or
   - Right-click and select "Open with" your preferred browser

3. **Or use a local server** (recommended for testing):
   ```bash
   # Using Python 3
   python3 -m http.server 8000
   
   # Using Node.js (with http-server installed)
   npx http-server
   
   # Using PHP
   php -S localhost:8000
   ```
   
   Then open `http://localhost:8000` in your browser.

## Deployment

### Option 1: Vercel (Recommended)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Deploy**:
   ```bash
   vercel
   ```
   
   Follow the prompts. Your site will be live at a `vercel.app` URL.

3. **Continuous deployment**: If you push to GitHub, connect your repository to Vercel for automatic deployments.

### Option 2: GitHub Pages

1. **Create a GitHub repository** and push your files:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/username/repo-name.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**:
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Source", select **Deploy from a branch**
   - Choose `main` branch and `/ (root)` folder
   - Click **Save**

3. Your site will be live at `https://username.github.io/repo-name/`

### Option 3: Netlify

1. Drag and drop the `index.html` file into [Netlify Drop](https://app.netlify.com/drop)
2. Your site will be instantly live with a random URL
3. You can customize the domain in the Netlify dashboard

## Customization Guide

### Replacing Album Text

Edit the content in `index.html`:

- **Album Title** (Landing section): Line 106
  ```html
  <h1 class="...">Album Title</h1>
  ```

- **Artist Name**: 
  - Landing section: Line 110
  - Footer: Line 261

- **Poetic Sentence** (Landing section): Line 113
  ```html
  <p class="...">A short poetic sentence that captures the essence of the work.</p>
  ```

- **Album Description** (About section): Lines 121-129
  Replace the paragraph content within the `<p>` tags.

- **Page Title** (Browser tab): Line 5
  ```html
  <title>Album Title — Artist Name</title>
  ```

### Replacing YouTube Videos

1. Find the video sections (around lines 137-158)
2. Replace `VIDEO_ID_1` and `VIDEO_ID_2` with your actual YouTube video IDs
3. To get a video ID: The ID is the string after `v=` in a YouTube URL
   - Example: `https://www.youtube.com/watch?v=dQw4w9WgXcQ` → ID is `dQw4w9WgXcQ`
4. To add more videos, copy the video container block:
   ```html
   <div class="video-container">
       <iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID?autoplay=0&mute=1&controls=1&modestbranding=1" ...></iframe>
   </div>
   ```

### Updating Tracklist

Edit the tracklist section (lines 167-198):
- Replace the Roman numerals (I, II, III...) if desired
- Replace track titles in the `<span>` elements with class `font-serif`
- Add or remove track items by copying/deleting the `.track-item` divs

### Updating Merch Links

Edit the Merch section (lines 202-215):
- Update the text descriptions
- Replace the Bandcamp URL: Line 211
  ```html
  <a href="https://bandcamp.com/artistname" ...>
  ```
- You can add additional links (Shopify, Instagram, etc.) by adding more `<p>` elements with links

### Updating Contact Information

Edit the Contact section (lines 219-232):
- Replace the email address: Line 224
  ```html
  <a href="mailto:artist@example.com" ...>
  ```
- Replace the Instagram link: Line 228
  ```html
  <a href="https://instagram.com/artistname" ...>
  ```
- Add or remove contact links as needed

### Changing Colors

Edit the CSS variables at the top of the `<style>` tag (around line 25):
```css
:root {
    --bg-color: #0a0a0a;        /* Background color */
    --text-primary: #e8e8e8;    /* Main text color */
    --text-secondary: #b0b0b0;  /* Secondary text color */
    --accent: #d4d4d4;          /* Accent color */
}
```

For an off-white theme, try:
```css
:root {
    --bg-color: #f5f5f5;
    --text-primary: #1a1a1a;
    --text-secondary: #4a4a4a;
    --accent: #2a2a2a;
}
```

### Changing Fonts

1. Replace the Google Fonts link (lines 8-12) with your preferred fonts
2. Update the font-family references in the CSS:
   - `.font-serif` (line 61): Used for headings and album title
   - `.font-sans` (line 65): Used for body text and small text

**Font suggestions**:
- Serif: Playfair Display, Libre Baskerville, Crimson Text, EB Garamond
- Sans-serif: Work Sans, Space Grotesk, DM Sans, Poppins

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). The Intersection Observer API is used for scroll animations, which is supported in all modern browsers.

## License

Free to use and modify for personal or commercial projects.

---

Built with care for experimental music and digital art.
