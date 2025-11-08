# Travel Booking Portal – Technical Documentation

## Project Overview
- **Goal**: Deliver a responsive travel booking portal that demonstrates core HTML5 semantics, form controls, data tables, lists, and rich CSS styling across inline, internal, and external stylesheets.
- **Key Files**:
  - `travel-booking1.html` – Main HTML document containing structure, content, inline styles, and the internal stylesheet.
  - `voyager_theme.css` – External theme file providing advanced layout, typography, and interaction styling.
  - `images/dubai-skyline.jpg` – Destination hero image referenced from markup (create the `images` folder and add this asset locally).

## HTML Implementation

### Document Skeleton & Metadata
- Declares the HTML5 doctype and uses `<html lang="en">` for language metadata.
- `<head>` defines UTF-8 charset, responsive viewport, document title, internal `<style>` block, and a `<link>` to the external stylesheet.
- Inline comment documents team members and the purpose of the page for maintainability.

```8:93:travel-booking1.html
    <title>Group 6 – Travel Booking Portal</title>
    <link rel="stylesheet" href="voyager_theme.css" type="text/css" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Poppins", Arial, sans-serif;
            color: #1b1f3b;
            background-color: transparent;
            line-height: 1.6;
            letter-spacing: 0.2px;
            scroll-behavior: smooth;
            transition: all 0.3s ease;
            text-rendering: optimizeLegibility;
        }
```

### Structural Layout
- A single wrapper `<div id="main-content" class="page-container">` anchors all sections; the ID supports internal styling while the class enables external theme rules.
- Content is split into semantic `<section>` blocks (`intro-section`, `feature-section`, `packages-section`, `steps-section`, `glossary-section`, `table-section`, `form-section`) for clarity and targeted styling.
- Each section uses `<h1>`–`<h3>` headings and `<p>` paragraphs; horizontal rules (`<hr>`) separate thematic blocks.

### Text Formatting & Inline Elements
- Demonstrates inline emphasis (`<strong>`, `<em>`), abbreviations (`<abbr>` with explanatory `title`), inline code (`<code>`), plus subscripts and superscripts (`<sub>`, `<sup>`) in pricing notes.
- Comments label block vs. inline examples in the introductory narrative.

### Media & Hyperlinks
- Featured destination includes an `<a>` tag with `title` and `target="_blank"` wrapping an `<img>` tag that supplies `alt` text for accessibility; the image source is a project-relative path (`./images/dubai-skyline.jpg`).
- Inline styling on the hero heading, lead paragraph, and submit button demonstrates the inline CSS requirement.

### Lists & Data Presentation
- **Unordered list**: `Popular Travel Packages` shows `<ul type="square">` with themed list items.
- **Ordered list**: `Steps to Book Your Trip` uses `<ol type="A">`.
- **Description list**: `Travel Terms You Should Know` transformed into card-like entries while retaining the semantic `<dl>`, `<dt>`, `<dd>` hierarchy.
- **Table**: `Available Travel Packages` illustrates `<thead>`, `<tbody>`, `<tfoot>` plus `colspan` and `rowspan` for merged cells.

### Registration Form
- Implements `method="post"` with a mix of inputs: text (`<input type="text">`), select dropdown (`<select>`), radio group, checkboxes, and submit (`<input type="submit">`).
- Uses `label` elements with matching `for` attributes to improve accessibility.
- Attribute selectors in CSS target `[type='text']`, `[type='radio']`, `[type='checkbox']`, ensuring consistent control styling.

## CSS Implementation

### Styling Strategy
1. **Inline Styles** (HTML file):
   - Hero heading, introductory paragraph, and submit button receive inline properties (color, gradients, padding, borders, shadows) to showcase direct element styling.
2. **Internal Styles** (`<style>` block in head):
   - Universal selector (`*`) sets the base typography, rhythm, and transitions.
   - Body, `#main-content`, `section`, `table`, and `form` rules each contain at least ten properties controlling layout, spacing, borders, color, shadows, and interaction.
3. **External Styles** (`voyager_theme.css`):
   - Expands theme with class-based and attribute selectors covering lists, glossary cards, featured image area, and forms.
   - Maintains the ten-property minimum per selector to satisfy the specification.

### Selector Coverage
- **Universal**: `*` establishes global resets and smooth scrolling.
- **Type**: `p`, `table`, `form`, `input[type='submit']` target specific HTML elements.
- **Class**: `.page-container`, `.section-title`, `.package-list li`, `.steps-list li`, `.featured-link`, `.featured-image`, `.definition-item`, etc., allow reusable styling and complex effects.
- **ID**: `#main-content` controls the outer container's sizing, spacing, and glassmorphism effect.
- **Attribute**: `input[type='text']`, `input[type='radio']`, `input[type='checkbox']`, `select` enforce consistent appearance for form controls.

```66:233:voyager_theme.css
.definition-item {
    display: flex;
    flex-direction: column;
    gap: 12px;
    padding: 18px 20px;
    border: 1px solid rgba(15, 23, 42, 0.16);
    border-radius: 16px;
    background: linear-gradient(160deg, rgba(14, 165, 233, 0.12), rgba(15, 23, 42, 0.06));
    box-shadow: 0 14px 28px rgba(15, 23, 42, 0.14);
    transform: translateY(0);
    transition: transform 0.3s ease;
    position: relative;
    overflow: hidden;
    isolation: isolate;
}
```

### Interactive Effects
- Hover/focus states on the submit button, featured image, anchor wrapper, and glossary cards provide visual feedback (transform, shadow, outline, color adjustments).
- Form controls use modern `accent-color` for radios/checkboxes and smooth transitions between focused/hovered states.

### New Styling Enhancements
- **Image Presentation**: `.featured-link` centers the image; `.featured-image` rounds corners, adds drop shadows, and scales smoothly on hover.
- **Glossary Redesign**: `.glossary-section`, `.definition-grid`, and `.definition-item` turn the description list into responsive cards with layered gradients and spotlight effects.
- **Layout Improvements**: `.page-container` uses a CSS grid with consistent gaps, while `section` blocks share a glassmorphism aesthetic through translucent backgrounds and blurred shadows.

## Asset & Folder Structure
```
TravBook/
├── images/
│   └── dubai-skyline.jpg        # Add this image to enable the featured destination hero
├── travel-booking1.html
├── voyager_theme.css
└── README.md
```

## Viewing the Page
1. Place the `TravBook` folder (with the image asset) on your machine.
2. Open `travel-booking1.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Verify that the hero image loads; adjust `src` if your image name differs.

## Summary of Specification Coverage
- **HTML Tasks**: All required tags, attributes, lists, tables, inline/block examples, formatting tags, and comprehensive form elements are implemented.
- **CSS Tasks**: Inline, internal, and external styles coexist; selectors span universal, type, class, ID, and attribute categories; each rule contains 10+ properties; interactive hover/focus effects are present across the UI.

The combination of semantic HTML and layered CSS results in a polished travel booking experience with strong typographic hierarchy, responsive visuals, and intuitive interactions.

