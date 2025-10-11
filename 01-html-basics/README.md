# HTML Basics

## Overview

This directory contains my first steps in learning HTML as part of my journey to become a full-stack developer. I'm coming from a backend development background with Spring Boot, and now expanding into frontend technologies.

## What is HTML?

HTML (HyperText Markup Language) is the standard markup language for creating web pages. It was invented by Tim Berners-Lee at CERN in 1991, initially designed for scientists to share documents. The revolutionary idea was the hyperlink, which allowed seamless navigation between documents.

### The Problem It Solved

Before the web, different platforms (Windows, Mac, Unix) used incompatible document formats. HTML created a universal language that any browser on any platform could understand. Think of it like JSON in the backend world - a standard format everyone can parse.

### Evolution Timeline

- **1991 - HTML 1.0:** Started with just 18 tags
- **1995 - HTML 2.0:** Added forms for user interaction
- **1999 - HTML 4.01:** Enhanced CSS integration
- **2000 - XHTML:** Stricter XML-based syntax rules
- **2014 - HTML5:** Modern features like semantic tags, native video/audio, canvas for graphics

The interesting part is that Tim Berners-Lee never patented the web. He made it free and open, which is why we have the internet as we know it today. The first website is still online at http://info.cern.ch.

## Core Philosophy

HTML is not a programming language. It's a markup language that gives meaning to content, not appearance. The separation of concerns is important here:

- HTML defines structure and meaning
- CSS handles presentation and styling
- JavaScript adds behavior and interactivity

As a backend developer, I think of it like this: HTML is like your entity structure, CSS is like your DTO layer (same data, different presentation), and JavaScript is like your service layer (business logic).

## SEO and HTML

Search Engine Optimization is about making your website discoverable in search results. Since most users never go past the first page of Google, good SEO can make the difference between a successful site and an invisible one.

HTML plays a crucial role in SEO:

- Title tags appear in search results and browser tabs
- Meta descriptions give search engines context about your page
- Proper heading hierarchy helps search engines understand content structure
- Semantic HTML makes your content more machine-readable
- Alt text on images helps with image search and accessibility

From a business perspective, good SEO means free traffic. A well-optimized site can get thousands of visitors organically, while a poorly optimized one might need to pay for every click through ads.

## Basic Document Structure

Every HTML document follows a standard structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <!-- Visible content goes here -->
</body>
</html>
```

The DOCTYPE declaration tells the browser this is an HTML5 document. The html element is the root containing everything. The head section holds metadata that browsers use but users don't see. The body contains all visible content.

## Essential Tags

### Structure Tags

**DOCTYPE declaration**  
Tells the browser which HTML version to use. For modern development, always use HTML5.

**html element**  
The root container with a lang attribute specifying the content language. Important for search engines and screen readers.

**head section**  
Contains metadata, links to stylesheets, and other non-visible information.

**body section**  
All visible page content lives here.

### Metadata Tags

**meta charset**  
Defines character encoding. UTF-8 supports all languages and special characters. Without this, characters like ü, ş, ğ might break.

**meta viewport**  
Essential for responsive design. Tells mobile browsers how to scale the page.

**title**  
Appears in browser tabs and search results. Should be descriptive and unique for each page. This is one of the most important elements for SEO.

### Content Tags

**Headings (h1-h6)**  
Create content hierarchy. h1 is the most important and should only appear once per page. h2 through h6 create subsections. Search engines pay special attention to headings, so they should accurately describe the content beneath them.

**Paragraphs (p)**  
Standard text blocks. Most written content goes in paragraph tags.

**Strong**  
Indicates important text. Browsers typically render it as bold, but the semantic meaning is what matters.

**Emphasis (em)**  
Indicates emphasized text. Usually rendered as italic. Again, the meaning is more important than the appearance.

**Comments**  
Written as `<!-- comment text -->`. Not visible to users but useful for developers. Good for explaining complex markup or temporarily disabling code.

### Lists

**Unordered lists (ul)**  
Create bullet-point lists. Good for items where order doesn't matter.

**Ordered lists (ol)**  
Create numbered lists. Use when sequence is important.

**List items (li)**  
Individual items within any list. Must be direct children of ul or ol elements.

## Links and Navigation

### The Anchor Tag

The anchor tag creates hyperlinks, which are the foundation of the web. Invented in 1991, the concept of linking documents together revolutionized how we access information.

**Basic syntax:**
```html
<a href="destination-url">Clickable Text</a>
```

The href attribute (hypertext reference) specifies where the link points to.

### Link Types

**Internal Links**  
Point to other pages within your own website. Use relative paths.

```html
<a href="about.html">About Page</a>
<a href="pages/contact.html">Contact</a>
<a href="../index.html">Home</a>
```

**External Links**  
Point to other websites. Always use the full URL with https://.

```html
<a href="https://github.com/gencberke" target="_blank" rel="noopener noreferrer">
  My GitHub
</a>
```

**Anchor Links**  
Jump to specific sections within the same page.

```html
<a href="#section-id">Jump to Section</a>
<!-- Later in the page -->
<h2 id="section-id">Section Title</h2>
```

**Special Links**  
Email and phone links that trigger native applications.

```html
<a href="mailto:email@example.com">Send Email</a>
<a href="tel:+905551234567">Call Me</a>
```

### The target Attribute

Controls where the linked document opens:

- No target: Opens in the same tab (default)
- `target="_blank"`: Opens in a new tab

### Security: rel="noopener noreferrer"

When using `target="_blank"`, always include `rel="noopener noreferrer"` for security and privacy. This is critical for external links.

**The Security Issue:**

When you open a link with `target="_blank"`, the new page gets access to your original page through the `window.opener` JavaScript object. Malicious sites can exploit this to redirect your original page to a phishing site.

**Attack Scenario:**

1. User clicks a link that opens in a new tab
2. User reads content in the new tab
3. Meanwhile, malicious JavaScript in the new tab executes:
   ```javascript
   window.opener.location = 'https://fake-login-page.com';
   ```
4. When user returns to the original tab, they see a fake login page
5. User enters credentials thinking they were logged out
6. Credentials are stolen

This attack is called "Reverse Tabnabbing" or "Tab Nabbing."

**The Solution:**

```html
<a href="https://external-site.com" target="_blank" rel="noopener noreferrer">
  Safe External Link
</a>
```

**What it does:**

- `noopener`: Sets `window.opener` to null, preventing the new page from accessing your page
- `noreferrer`: Prevents the browser from sending the Referrer header, adding privacy protection

**Performance Bonus:**

Pages opened with `noopener` run in a separate process, so if the new page is resource-intensive, it won't slow down your original page.

**Modern Browser Behavior:**

Chrome 88+ and Firefox 79+ automatically apply `noopener` behavior to `target="_blank"` links. However, you should still explicitly include it for:
- Backward compatibility with older browsers
- Clear security intent in your code
- Passing security audits

**When to use:**

- Always on external links with `target="_blank"`
- Always on user-generated content links
- Not needed for internal navigation within your own site
- Not needed for mailto: or tel: links

Think of it like SQL injection protection in the backend. Even if modern frameworks have some built-in protection, you still sanitize inputs explicitly.

## Images

Images make web pages visually engaging. Web image support was added to browsers in 1993 with the Mosaic browser, which triggered the explosive growth of the web.

**Basic syntax:**
```html
<img src="image-path.jpg" alt="Description of image">
```

The img tag is self-closing and doesn't have a closing tag.

### Essential Attributes

**src (source)**  
Specifies the image location. Can be a relative path or full URL.

```html
<img src="profile.jpg" alt="Profile picture">
<img src="images/logo.png" alt="Company logo">
<img src="https://example.com/photo.jpg" alt="Remote image">
```

**alt (alternative text)**  
Provides a text description of the image. This is crucial for:
- Accessibility: Screen readers speak this text to visually impaired users
- SEO: Search engines can't see images, they read alt text
- Fallback: Shows if the image fails to load
- Context: Describes what the image shows

**Width and height**  
Specify image dimensions in pixels. Modern practice is to set these in CSS instead, but they can be useful for preventing layout shifts during page load.

```html
<img src="photo.jpg" alt="Description" width="300" height="200">
```

### Relative Paths

Understanding relative paths is essential for organizing your project:

```
project/
├── index.html
├── pages/
│   └── about.html
└── images/
    └── photo.jpg
```

From index.html:
```html
<img src="images/photo.jpg" alt="Photo">
```

From pages/about.html:
```html
<img src="../images/photo.jpg" alt="Photo">
```

The `../` means "go up one directory level."

### Best Practices

Write descriptive alt text that explains what's in the image, not just labels. Compare:

Bad: `alt="image"`  
Better: `alt="profile picture"`  
Best: `alt="Berke coding on a laptop at a coffee shop"`

## Best Practices

Keep tag names in lowercase. While HTML is case-insensitive, lowercase is the widely accepted convention and makes code more readable.

Always close tags properly. Every opening tag needs a corresponding closing tag. Self-closing tags like img and input are exceptions.

Use proper heading hierarchy. Don't skip levels - go from h1 to h2 to h3. Think of it like a well-structured document outline.

Include the charset meta tag. This prevents character encoding issues, especially important for international content.

Write semantic HTML. Use tags that describe their meaning, not just their appearance. This helps with accessibility and SEO.

One h1 per page. This should be the main topic of your page. Multiple h1 tags confuse search engines about what your page is actually about.

For external links with target="_blank", always include rel="noopener noreferrer" for security.

Write meaningful alt text for all images. This improves accessibility and SEO.

Use relative paths for internal resources. This makes your site portable and easier to maintain.

## Project Files

**first-index.html**  
The main landing page with introduction, learning goals, and backend experience. Includes internal navigation to the about page.

**pages/about.html**  
Personal profile page with skills, education information, and social media links. Demonstrates proper use of external links with security attributes and image implementation with alt text.

**pages/images/profile-picture.jpeg**  
Profile image demonstrating local image usage and proper file organization.

## What's Next

The natural progression from here is to learn form elements, which are essential for the Todo application. Forms will allow user input, which connects directly to the backend API endpoints I'm familiar with from Spring Boot.

## Notes

This is a learning project documenting my journey from backend to full-stack development. The goal is to build a React frontend for my existing Spring Boot Todo application.
