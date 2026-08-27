# VYRO Studios

VYRO Studios is a creative editing and visual design studio focused on video editing, photo editing, thumbnails, motion, VFX, color, sound and social media content.

The website is a **static, single-HTML application with page-style routing**. It does not require a backend, framework, CMS or database.

## Experience

The navigation behaves like separate pages while keeping the project lightweight:

- `#home`
- `#work`
- `#about`
- `#services`
- `#skills`
- `#contact`

Clicking a navigation item changes the active view, resets the viewport and updates the URL hash. This keeps the visual experience page-based without creating multiple HTML files.

## Files

```text
VYRO-Studios/
├── index.html
├── style.css
├── app.js
├── README.md
└── assets/
    ├── images/
    └── icons/
```

## Setup

No installation is required.

For a quick local preview, open `index.html` in a browser. For the most reliable local development experience, serve the folder with any simple static server.

The site uses vanilla HTML, CSS and JavaScript.

## 4K and responsive layout

The layout is fluid and is designed to scale from small phones through tablets, 1080p displays, 1440p displays and large 4K desktop screens.

The site does **not** force a 3840×2160 canvas. Instead, it uses responsive CSS, a large content max-width and viewport-based typography so the interface remains sharp and properly aligned at different resolutions.

For real portfolio media, use high-resolution source files. Recommended images are WebP or AVIF where practical. The website itself does not generate or upscale media.

## Adding portfolio projects

Open `app.js` and edit the `projects` array near the top.

Example:

```js
{
  id: 4,
  title: "My Real Project",
  category: "video",
  year: "2026",
  thumbnail: "assets/images/my-project.webp",
  description: "Short description of the project.",
  role: "Video Editor",
  tools: ["DaVinci Resolve"],
  beforeImage: "",
  afterImage: ""
}
```

Supported categories currently include:

- `video`
- `photo`
- `thumbnails`
- `motion`
- `vfx`
- `graphic design`

You do not need to modify the HTML to add a project.

## Adding images

Put portfolio images in:

```text
assets/images/
```

Then use the path in the project's `thumbnail` field.

If an image is missing, the project automatically receives a visual fallback instead of throwing a JavaScript error.

### Site icon

Place the VYRO Studios site icon at:

```text
assets/icons/icon.jpg
```

`index.html` is already configured to use this file as the favicon.

## Before / After

To enable a comparison slider for a project, provide both:

```js
beforeImage: "assets/images/project-before.webp",
afterImage: "assets/images/project-after.webp"
```

The viewer automatically adds the range slider when both assets exist.

## Editing skills

The current configured skills include:

- DaVinci Resolve — Advanced
- Video Editing — Advanced
- Adobe Photoshop — Advanced
- Photo Editing — Advanced
- Thumbnail Design — Advanced
- Graphic Design — Advanced
- Photo Manipulation — Advanced
- Motion Design — Advanced
- Visual Effects — Advanced
- Color Correction — Advanced
- Color Grading — Advanced
- Sound Design — Advanced
- Audio Editing — Advanced

These labels are editable in the `skills` array in `app.js`.

They are qualitative labels, not fabricated percentages.

## Editing services

Services are configured in the `services` array in `app.js`.

You can change the title and description without editing the main HTML structure.

## Editing contact information

At the top of `app.js`, edit `siteConfig.contact`. The current real VYRO Studios contacts are already configured.

### Facebook

```js
facebook: "https://www.facebook.com/profile.php?id=61594069011944"
```

### TikTok

```js
tiktok: "https://www.tiktok.com/@vyrostudios2?lang=en"
```

### Instagram

```js
instagram: "https://www.instagram.com/vyrostudioos/"
```

### WhatsApp

The current number is already configured:

```text
40730062060
```

WhatsApp uses:

```text
https://wa.me/40730062060
```

The number must use international digits only, without `+`, spaces, hyphens or parentheses.

### Email

Current email:

```text
vyrostudioos@gmail.com
```

It is converted to a `mailto:` link automatically.

### Phone

Current phone:

```text
0730 062 060
```

The site converts it to an international `tel:` link automatically.

## Changing colors

At the top of `style.css`, edit the CSS variables:

```css
--bg
--surface
--surface-2
--text
--muted
--line
--accent
```

`--accent` is also configurable from `siteConfig.accent` in `app.js`.

## Changing text

Main content is split between the semantic HTML structure and the data arrays in `app.js`.

Portfolio, services, skills, vision and contact data are generated from JavaScript so they can be edited without manually duplicating HTML cards.

## Animations

The site includes:

- cinematic page transitions
- text reveal animations
- staggered navigation animation
- hero scanline
- ambient floating light
- responsive grid movement
- hover image scale
- image sweep interaction
- magnetic buttons
- custom cursor states on desktop
- animated service arrows
- contact card motion
- marquee motion
- scroll reveal using IntersectionObserver
- modal entrance animation
- Before / After slider
- scroll progress indicator

No scroll hijacking is used.

If the visitor has `prefers-reduced-motion: reduce` enabled, nonessential animations are disabled or simplified.

## Accessibility

The project includes:

- semantic sections and headings
- keyboard-accessible project cards
- visible focus states
- ARIA labels where needed
- Escape-to-close project viewer
- focus restoration after modal close
- modal focus trapping
- mobile menu keyboard access
- reduced-motion support
- touch-safe layout
- custom cursor disabled on coarse pointers

## Deployment

### Recommended: GitHub Pages

For a simple static website, GitHub Pages is an easy option.

1. Create a GitHub repository.
2. Upload the contents of `VYRO-Studios`.
3. Open repository Settings.
4. Open Pages.
5. Select the branch and root folder.
6. Save and wait for the deployment.

### Cloudflare Pages

Connect the GitHub repository and deploy it as a static project. No build command is required.

### Netlify

Drag the project folder into Netlify's deployment interface or connect a Git repository.

### Vercel

Import the repository. Because this is a static site, no framework configuration is required.

## Custom domain

If you own a domain such as:

```text
vyrostudios.com
```

connect it through the hosting provider's Domains section. Domain availability and pricing are not assumed here.

After connecting the domain, update the placeholder canonical and Open Graph URL values in `index.html`.

## Troubleshooting

### Image does not appear

Check the filename and path in `projects` and make sure the file is inside `assets/images/`.

### Video does not appear

Check the filename, path and browser-supported video format. MP4 with a common H.264/AAC encoding is a safe web choice.

### WhatsApp does not open

Check that the number is international digits only. The configured number is `40730062060`.

### Email does not open

The website opens the user's configured mail client with `mailto:`. It does not send emails itself.

### Social link does not appear

Check the corresponding URL in `siteConfig.contact`. The supplied Facebook, TikTok and Instagram links are already configured. Empty social URLs are intentionally treated as unavailable.

### Mobile menu does not open

Make sure JavaScript is enabled and that `app.js` is in the same directory as `index.html`.

### Animations do not appear

Check whether the operating system or browser has reduced motion enabled. The site intentionally disables nonessential animations in that mode.

### Page does not change when clicking navigation

JavaScript controls the hash-based page routing. Check the browser console for syntax errors if the issue persists.

## Production notes

Before launch:

1. Replace every placeholder portfolio item with real work.
2. Add real portfolio images to `assets/images/`.
3. Add the real Facebook, TikTok and Instagram URLs.
4. Replace the placeholder canonical URL in `index.html`.
5. Replace the placeholder Open Graph URL/image when you have the final assets.
6. Test the final site on desktop, tablet and mobile.

No API keys, passwords, private tokens or credentials are stored in the frontend.


## Project Orders

The **ORDER** route uses FormSubmit's AJAX endpoint so a visitor can submit a project request without opening their own email application. The request is delivered to `vyrostudioos@gmail.com`. FormSubmit documents that AJAX submissions can be sent cross-origin without leaving the page. https://formsubmit.co/ajax-documentation

### First activation

The first real submission to a new FormSubmit endpoint requires email confirmation. Submit a test order after deployment and confirm the activation email sent to `vyrostudioos@gmail.com`. FormSubmit keeps submissions received before activation for a limited period. https://formsubmit.co/documentation

### Order fields

The order form requires name, email, phone number, service, deadline, budget and project description. The phone number is collected so VYRO Studios can contact the client about the request. The phone number is not displayed publicly.

### Important

The browser does not send WhatsApp messages automatically. This version intentionally sends orders only to the studio email, as requested.
