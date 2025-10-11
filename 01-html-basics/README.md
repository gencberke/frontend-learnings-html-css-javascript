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

**DOCTYPE**  
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

## Best Practices

Keep tag names in lowercase. While HTML is case-insensitive, lowercase is the widely accepted convention and makes code more readable.

Always close tags properly. Every opening tag needs a corresponding closing tag. Self-closing tags like img and input are exceptions.

Use proper heading hierarchy. Don't skip levels - go from h1 to h2 to h3. Think of it like a well-structured document outline.

Include the charset meta tag. This prevents character encoding issues, especially important for international content.

Write semantic HTML. Use tags that describe their meaning, not just their appearance. This helps with accessibility and SEO.

One h1 per page. This should be the main topic of your page. Multiple h1 tags confuse search engines about what your page is actually about.

## Project Files

**index.html**  
My first HTML page. A simple introduction with headings, paragraphs, and lists. Practicing proper document structure and semantic markup.

## What's Next

The natural progression from here is to learn more HTML elements (links, images, forms) and then move into CSS for styling. Since my end goal is building a frontend for my Todo application, forms will be particularly important.

## Notes

This is a learning project documenting my journey from backend to full-stack development. The goal is to build a React frontend for my existing Spring Boot Todo application.
