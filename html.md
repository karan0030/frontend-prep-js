## HTML & CSS Interview Questions (With Answers)

### ✅ HTML Questions

1. **What is HTML and why is it used?**  
   HTML (HyperText Markup Language) is the standard markup language for creating web pages. It structures the content using elements like headings, paragraphs, images, and links.

2. **What are semantic HTML elements? Give examples.**  
   Semantic elements clearly describe their meaning. Examples: `<article>`, `<section>`, `<header>`, `<footer>`, `<nav>`.

3. **Difference between `id` and `class` attributes?**  
   `id` is unique and used once per page, while `class` can be reused on multiple elements.

4. **What are block-level and inline elements?**  
   Block-level elements (e.g., `<div>`, `<p>`) take up full width. Inline elements (e.g., `<span>`, `<a>`) only take up as much width as needed.

5. **What is the purpose of the `doctype` declaration?**  
   It tells the browser which version of HTML to use. For HTML5, it's `<!DOCTYPE html>`.

6. **What are data-* attributes in HTML?**  
   Custom attributes used to store extra information: `<div data-user-id="123"></div>`.

7. **How do you optimize HTML for SEO?**  
   Use semantic tags, proper heading structure, alt attributes for images, meta tags, and clean URLs.

8. **What is the difference between `<script>`, `<script async>`, and `<script defer>`?**  
   - `<script>`: blocks parsing until script loads and runs.  
   - `async`: loads script in parallel and runs ASAP.  
   - `defer`: loads in parallel but executes after DOM parsing.

9. **Explain forms and input types in HTML.**  
   Forms collect user input. Input types include `text`, `email`, `number`, `checkbox`, `radio`, etc.

10. **What are some new features in HTML5?**  
    Semantic tags, audio/video support, canvas for drawing, local storage, new input types.

---

### ✅ CSS Questions

1. **What is the difference between `relative`, `absolute`, `fixed`, and `sticky` positioning?**  
   - `relative`: relative to its normal position  
   - `absolute`: relative to nearest positioned ancestor  
   - `fixed`: relative to viewport  
   - `sticky`: toggles between relative and fixed based on scroll

2. **What is the Box Model in CSS?**  
   It describes the layout structure of an element: content → padding → border → margin.

3. **Difference between `em`, `rem`, `%`, `px`, and `vw/vh` units?**  
   - `em`: relative to parent font-size  
   - `rem`: relative to root font-size  
   - `%`: relative to parent dimension  
   - `px`: absolute pixels  
   - `vw/vh`: viewport width/height units

4. **What are pseudo-classes and pseudo-elements in CSS?**  
   - Pseudo-classes: `:hover`, `:nth-child()` (target specific states)  
   - Pseudo-elements: `::before`, `::after` (style parts of elements)

5. **What is specificity in CSS and how is it calculated?**  
   Specificity determines which CSS rule applies when multiple rules match. Calculated by: inline styles > IDs > classes/attributes > elements.

6. **How does CSS inheritance work?**  
   Some properties (like `color`, `font-family`) are inherited by child elements. Others are not unless explicitly set.

7. **Difference between `visibility: hidden` and `display: none`?**  
   - `visibility: hidden`: hides element but still takes space  
   - `display: none`: removes element from layout

8. **What are media queries? Provide an example.**  
   Media queries make designs responsive by applying styles based on device size.  
   Example: `@media (max-width: 600px) { body { font-size: 14px; } }`

9. **How can you center a div (horizontally & vertically)?**  
   Use Flexbox:
   ```css
   display: flex;
   justify-content: center;
   align-items: center;
   ```

10. **What is the difference between Flexbox and Grid?**  
    - Flexbox: 1D layout (row or column)  
    - Grid: 2D layout (rows and columns)

---

### ✅ Bonus Questions

1. **How do you improve website performance with HTML/CSS best practices?**  
   Minify code, use external stylesheets, use semantic HTML, avoid inline styles, and reduce HTTP requests.

2. **What tools do you use for debugging CSS?**  
   Chrome DevTools, Firefox Inspector, browser developer consoles, Stylelint.

3. **Explain the difference between inline, internal, and external CSS.**  
   - Inline: style directly in tag  
   - Internal: within `<style>` tag in `<head>`  
   - External: separate `.css` file linked to HTML

4. **What are common accessibility best practices in HTML/CSS?**  
   Use semantic HTML, `alt` tags, ARIA labels, proper tab order, and readable color contrast.

5. **What is a z-index, and how does stacking context work?**  
   `z-index` controls the vertical stacking of elements. A stacking context is formed by positioned elements with `z-index`, certain CSS properties, or `transform` values.

