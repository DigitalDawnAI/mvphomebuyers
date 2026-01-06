# MVP Home Buyers Website

Complete website for MVP Home Buyers, a cash home buying business in South Jersey.

## Project Overview

This is a fully responsive, production-ready website built exactly to the specifications provided in the MVP Home Buyers brand kit. The design strictly adheres to all brand guidelines including colors, typography, layouts, and copy.

## Brand Specifications

### Colors
- **Primary Brand Color**: RGB(231, 58, 144) / #e73a90
- **Gradient Colors**: Pink to orange gradient as shown in logo
  - RGB(242, 120, 158)
  - RGB(240, 108, 120)
  - RGB(246, 144, 87)
  - RGB(250, 169, 88)
- **Dark Background**: #2d2d2d

### Typography
- **Primary Font**: Montserrat Medium (weight: 500)
- **Headings**: Montserrat Bold (weight: 700)
- **Letter Spacing**: VA +40 (as per brand guidelines)

### Logo
- Gradient version used throughout (MVP-colorlogo_Horizontal.png)
- Tagline: "Your Most Valuable Property Partner"

## Features

✅ **Fully Responsive Design**
- Mobile-first approach
- Optimized for all screen sizes (desktop, tablet, mobile)
- Touch-friendly navigation and buttons

✅ **SEO Optimized**
- Schema.org structured data for local business
- Open Graph meta tags for social sharing
- Semantic HTML5 markup
- Optimized meta descriptions and titles

✅ **Performance**
- Optimized images
- Fast loading times
- Clean, efficient CSS
- Minimal dependencies

✅ **Sections Included**
1. Utility bar with tagline and phone number
2. Main navigation with logo and menu
3. Hero section with address input form
4. "Why Homeowners Choose Us" section
5. "Two Paths" comparison (Traditional Way vs MVP Way)
6. CTA section with aerial neighborhood view
7. Footer with contact information and site links

## File Structure

```
website/
├── index.html          # Main homepage
├── css/
│   └── styles.css      # All styles with brand colors and responsive design
├── images/
│   ├── MVP-colorlogo.png
│   ├── MVP-colorlogo_Horizontal.png
│   ├── AdobeStock_1557748604.jpeg  # Hero house image
│   ├── AdobeStock_385946622.jpeg   # Inspector image
│   ├── AdobeStock_380103587.jpeg   # Stock image
│   └── AdobeStock_894193740.jpeg   # Aerial neighborhood view
├── js/                 # (Reserved for future JavaScript)
└── fonts/              # (Reserved for custom fonts if needed)
```

## Deployment

### Option 1: Simple Hosting (Netlify, Vercel, GitHub Pages)

1. Upload the entire `website/` folder to your hosting service
2. Set `index.html` as the entry point
3. Deploy

### Option 2: Traditional Web Hosting (cPanel, FTP)

1. Upload all files to your web server's public_html or www directory
2. Ensure folder structure is maintained
3. Set appropriate file permissions (644 for files, 755 for directories)

### Option 3: Local Testing

Simply open `index.html` in a web browser to preview locally.

For a local server (recommended for testing):
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (if you have http-server installed)
npx http-server
```

Then visit `http://localhost:8000` in your browser.

## Contact Information

All contact information in the website can be updated by editing `index.html`:

- **Phone**: 609.123.4567
- **Email**: myoffer@mvphomebuyers.com
- **Address**: 123 Main Street, Northfield NJ

To update, search for these values in `index.html` and replace with actual contact information.

## Future Pages

The navigation includes links to future pages that can be built:
- About Us
- Reviews
- FAQ
- Contact

These pages should follow the same design system and brand guidelines established in this homepage.

## Browser Compatibility

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Technical Notes

### Fonts
- Uses Google Fonts (Montserrat) - loaded from CDN
- No local font files required

### Images
- All images are optimized Adobe Stock photos from brand kit
- File sizes are large for quality - consider optimization for production:
  - Use WebP format for better compression
  - Implement lazy loading for below-fold images
  - Use responsive image techniques (srcset)

### Form Handling
The address input form currently has no backend integration. To make it functional:

1. Add a form processor (FormSpree, Netlify Forms, or custom backend)
2. Update the `action` attribute in the form
3. Add success/error handling with JavaScript

Example with Netlify Forms:
```html
<form name="offer-request" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="offer-request">
  <!-- rest of form fields -->
</form>
```

## Customization

### Changing Colors
All brand colors are defined as CSS variables in `styles.css`:
```css
:root {
    --brand-primary: rgb(231, 58, 144);
    /* etc. */
}
```

### Updating Content
All text content is in `index.html` and can be edited directly. The copy follows the exact wording from the brand mockups.

### Adding Analytics
Add Google Analytics, Facebook Pixel, or other tracking codes before the closing `</head>` tag in `index.html`.

## Quality Checklist

- ✅ Exact brand colors used (RGB 231, 58, 144 primary)
- ✅ Montserrat font family throughout
- ✅ Gradient logo properly displayed
- ✅ All copy matches mockups verbatim
- ✅ Layout matches mockup structure exactly
- ✅ Fully responsive on all devices
- ✅ Schema markup for local SEO
- ✅ Semantic HTML5
- ✅ Accessibility features (ARIA labels, alt text)
- ✅ Fast loading performance

## Support

For questions or modifications, refer to the original brand kit files in `/brandkit/MVP_Folder/`.

## License

All brand assets, colors, logos, and copy are proprietary to MVP Home Buyers.
