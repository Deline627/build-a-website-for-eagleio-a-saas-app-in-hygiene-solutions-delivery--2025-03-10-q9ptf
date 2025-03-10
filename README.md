# EagleiO Landing Page - Maintenance Guide

This guide will help you maintain and customize the EagleiO landing page. Whether you're new to web development or need a quick reference, follow these detailed instructions.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains the logo and navigation menu. To update:

1. **Logo Text:**
```html
<a href="/" class="text-2xl font-bold text-white tracking-tight">
    Eagle<span class="text-blue-500">iO</span>
</a>
```
- Change "Eagle" and "iO" to your desired text
- The blue highlight is controlled by `text-blue-500`

2. **Navigation Links:**
```html
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-300 hover:text-white transition-colors duration-300">Features</a>
    <!-- Other navigation items -->
</div>
```
- Update text between `<a>` tags
- Keep the `class` attributes to maintain styling
- `md:flex` ensures proper responsive behavior on medium screens

### Hero Section
Located at the top of the page:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight mb-8 bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent">
    Soar Above Service Hassles with EagleiO
</h1>
```
- Change the heading text while keeping the gradient effect
- Adjust text size using:
  - `text-4xl` (mobile)
  - `md:text-5xl` (medium screens)
  - `lg:text-6xl` (large screens)

### Features Cards
Each feature card follows this structure:
```html
<div class="bg-gray-900 rounded-2xl p-8 transform hover:scale-105 transition-all duration-300">
    <div class="w-16 h-16 bg-blue-600 rounded-full flex items-center justify-center mb-6">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-xl font-bold mb-4">On-demand Cleaning</h3>
    <p class="text-gray-400">Request professional cleaning services...</p>
</div>
```
- Update `<h3>` for feature titles
- Modify `<p>` for feature descriptions
- Keep `hover:scale-105` for hover animation
- Maintain padding (`p-8`) and margin (`mb-4`, `mb-6`) classes

## Managing Links

### Internal Navigation Links
Current internal links use hashtags for smooth scrolling:
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
```
To update:
1. Ensure section IDs match the href values
2. Example adding new section:
```html
<a href="#new-section">New Section</a>
<!-- Later in the code -->
<section id="new-section">
    <!-- Content -->
</section>
```

### External Links
The main call-to-action links point to:
```html
<a href="https://www.eagle360.app">Get Started</a>
```
To update:
1. Replace `https://www.eagle360.app` with your destination URL
2. Update all instances in:
   - Navigation menu
   - Hero section
   - CTA section
   - Mobile menu

## Adding Privacy and Terms Pages

### Footer Links Setup
Current placeholder links in footer:
```html
<ul class="space-y-2">
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
</ul>
```

To link to actual pages:
1. Create `privacy.html` and `terms.html` in your root directory
2. Update the href attributes:
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues

1. **Broken Responsive Layout:**
- Check that you haven't removed important Tailwind classes like `md:` or `lg:` prefixes
- Verify container classes remain: `container mx-auto px-6`

2. **Missing Hover Effects:**
- Ensure these classes are present:
  - `hover:text-white`
  - `hover:bg-blue-700`
  - `hover:scale-105`

3. **Incorrect Link Behavior:**
- Verify all `href` attributes start with `#` for internal links
- Check external URLs include `https://`
- Test all links in both desktop and mobile views

### Best Practices

1. Always test changes in multiple screen sizes
2. Keep the existing class structure for consistent styling
3. Maintain the same spacing patterns using Tailwind's margin/padding classes
4. Back up the file before making significant changes

Remember: This landing page uses Tailwind CSS and Alpine.js. Avoid removing the CDN links in the head section:
```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
```

For additional help, refer to:
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Alpine.js Documentation](https://alpinejs.dev/docs)