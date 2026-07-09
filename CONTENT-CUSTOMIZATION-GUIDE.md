# Content Customization Guide

This guide explains how to customize the content for the Ooty Coffee Estates website.

## 📝 Text Content Updates

All text content has been updated from the original milk drink theme to coffee. Here's what was changed:

### Hero Section (`src/sections/HeroSection.jsx`)
- **Headline**: "Fresh Coffee from Ooty"
- **Subheadline**: "Straight from the Estates"
- **Description**: "Handpicked coffee beans grown in the misty hills of Ooty and roasted fresh to preserve their rich aroma and bold flavor."
- **CTA Button**: "Shop Fresh Coffee"

### Message Section (`src/sections/MessageSection.jsx`)
- **First Message**: "Discover the authentic taste of"
- **Highlighted Text**: "Ooty Hills"
- **Second Message**: "in every cup of our premium estate coffee"
- **Description**: "Experience the essence of Ooty's misty plantations with every sip. Our coffee is grown at high altitudes, handpicked at peak ripeness, and roasted to perfection."

### Coffee Collection Section (`src/components/FlavorTitle.jsx`)
- **Title**: "Explore our 6"
- **Highlighted**: "premium"
- **Subtitle**: "coffee varieties"

### Coffee Products (`src/constants/index.js`)

#### Product List:
1. **Estate Arabica** - ₹499
   - "Smooth, aromatic coffee with floral notes"

2. **Estate Robusta** - ₹449
   - "Bold and strong with earthy undertones"

3. **Premium Filter Coffee** - ₹549
   - "Traditional South Indian blend"

4. **Dark Roast** - ₹599
   - "Rich, intense flavor profile"

5. **Espresso Blend** - ₹649
   - "Perfect for your espresso machine"

6. **Gift Box Collection** - ₹1,499
   - "Curated selection of our finest coffees"

### Benefits Section (`src/sections/NutritionSection.jsx`)
- **Title**: "Pure & Natural"
- **Highlighted**: "Coffee Benefits"
- **Description**: "Our coffee is rich in antioxidants and natural compounds that boost energy, enhance focus, and promote overall well-being."

#### Health Benefits:
- Antioxidants: High
- Caffeine: 95mg
- Polyphenols: Rich
- Vitamins: B2, B3
- Magnesium: 7mg

### Why Choose Us Section (`src/sections/BenefitSection.jsx`)
- **Intro**: "What Makes Us Special: Discover Why Ooty Coffee Estates Stand Out"

#### Key Benefits:
1. Farm Fresh Daily
2. High Altitude Grown
3. Hand Roasted Perfection
4. Sustainable Farming

### Testimonials Section (`src/sections/TestimonialSection.jsx`)
- **Title Words**: "Coffee Lovers Stories"

#### Customer Names & Testimonials:
1. **Priya** - "The aroma reminds me of the Ooty hills!"
2. **Arjun** - "Best coffee I've ever tasted"
3. **Lakshmi** - "Fresh and authentic taste"
4. **Vikram** - "Premium quality, worth every rupee"
5. **Meera** - "My morning routine essential"
6. **Rohan** - "Simply outstanding flavor"
7. **Anjali** - "Ooty's finest coffee estates"

### Footer Section (`src/sections/FooterSection.jsx`)
- **Hashtag**: #BREWOOTY

#### Navigation Links:
**Column 1:**
- Our Coffee

**Column 2:**
- Coffee Club
- Farm Tours
- Wholesale

**Column 3:**
- About Us
- Contact
- Blog

#### Newsletter:
- "Subscribe to Our Newsletter for Exclusive Offers, New Coffee Releases, and Stories from Our Ooty Estates!"

#### Copyright:
- "Copyright © 2025 Ooty Coffee Estates - All Rights Reserved"

## 🎨 Color Theme

The website uses a warm, earthy coffee-inspired color palette:

### Primary Colors:
- **Dark Brown**: `#3e2723` - Main text, headings
- **Medium Brown**: `#6f4e37` - Accent elements
- **Light Brown**: `#a67c52` - Highlights, buttons

### Secondary Colors:
- **Cream**: `#efebe9` - Main background
- **Beige**: `#d7ccc8` - Section backgrounds
- **Forest Brown**: `#5d4037` - Dark accents
- **Warm Brown**: `#8d6e63` - Subtle accents

### Usage:
- Backgrounds: Cream and beige tones
- Text: Dark brown for readability
- Accents: Medium to light brown
- Highlights: Warm brown tones

## 🔧 How to Customize Further

### Adding New Coffee Products

Edit `src/constants/index.js`:

```javascript
const flavorlists = [
  {
    name: "Your Coffee Name",
    color: "brown", // Must match image file prefix
    rotation: "md:rotate-[-8deg] rotate-0",
    description: "Your coffee description",
    price: "₹XXX"
  },
  // ... add more products
];
```

### Updating Benefits

Edit `src/constants/index.js`:

```javascript
const nutrientLists = [
  { label: "Benefit Name", amount: "Value" },
  // ... add more benefits
];
```

### Modifying Testimonials

Edit `src/constants/index.js`:

```javascript
const cards = [
  {
    src: "/videos/f1.mp4",
    rotation: "rotate-z-[-10deg]",
    name: "Customer Name",
    img: "/images/p1.png",
    translation: "translate-y-[-5%]",
    testimonial: "Their testimonial quote"
  },
  // ... add more testimonials
];
```

### Changing Typography

The website uses two fonts:
- **Antonio** - For headings (bold, uppercase)
- **Proxima Nova** - For body text (readable, elegant)

To change fonts, edit `src/index.css`:
1. Update the `@import` statement for new Google Fonts
2. Update `@font-face` for custom fonts
3. Modify the `@theme` variables

### Updating Meta Information

Edit `index.html`:
- Title tag
- Meta description
- Favicon reference

## 📱 Responsive Design

The website is mobile-first and fully responsive:
- **Mobile**: < 768px
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px
- **2XL**: > 1536px

All content automatically adjusts for different screen sizes.

## 🎯 SEO Optimization

Current SEO elements:
- Descriptive page title
- Meta description
- Semantic HTML structure
- Alt tags on images (update when replacing assets)
- Fast loading times

To improve SEO:
1. Add more meta tags in `index.html`
2. Include structured data (JSON-LD)
3. Optimize image alt texts
4. Add sitemap.xml
5. Include robots.txt

## 🚀 Performance Tips

- Images are lazy-loaded automatically
- Videos use `playsInline` for mobile compatibility
- Smooth scrolling with GSAP ScrollSmoother
- Optimized animations for 60fps
- Tailwind CSS for minimal CSS bundle

## 📞 Support

For questions about customization:
1. Check the code comments in each component
2. Review GSAP documentation for animation customization
3. Refer to Tailwind CSS docs for styling changes
