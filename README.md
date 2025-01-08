### **Animation Guidelines**

---

### **1. Header Animations**

#### **Navigation Hover:**
- **Effect**: Underline slides in and color changes on hover.
- **CSS Example**:
  ```css
  nav a {
    position: relative;
    text-decoration: none;
    transition: color 0.2s ease-in-out;
  }
  nav a::after {
    content: "";
    position: absolute;
    width: 0;
    height: 2px;
    background: #FFCC00;
    left: 0;
    bottom: -5px;
    transition: width 0.2s ease-in-out;
  }
  nav a:hover::after {
    width: 100%;
  }
  ```

#### **Logo Entrance:**
- **Effect**: Fade-in on page load with slight scaling.
- **CSS Example**:
  ```css
  .logo {
    opacity: 0;
    transform: scale(1.1);
    animation: fadeInLogo 0.4s ease-in-out forwards;
  }
  @keyframes fadeInLogo {
    to {
      opacity: 1;
      transform: scale(1);
    }
  }
  ```

---

### **2. Hero Titles**

#### **Effect**: Fade-in with upward motion on page load.
- **CSS Example**:
  ```css
  .hero h1 {
    opacity: 0;
    transform: translateY(-10px);
    animation: fadeInTitle 0.6s ease-in-out forwards;
  }

  .hero p {
    opacity: 0;
    transform: translateY(-10px);
    animation: fadeInSubtitle 0.6s ease-in-out forwards 0.2s;
  }

  @keyframes fadeInTitle {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes fadeInSubtitle {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  ```

---

### **3. Category Hover Animations**

#### **Effect**: Scale up the card (1.03x) on hover. No shadow.
- **CSS Example**:
  ```css
  .category-card {
    transition: transform 0.3s ease-in-out;
  }
  .category-card:hover {
    transform: scale(1.03);
  }
  ```

---

### **4. Button Animations**

#### **General Behavior**:  
- Buttons follow defined states: Default, Hover, Focused, Active, and Disabled.  
- Smooth transitions enhance the user experience.


#### **Example CSS for Primary-Filled Buttons**:
```css
.button-primary {
  background-color: #FFCC00;
  color: #132446;
  border: none;
  padding: 10px 20px;
  transition: background-color 0.3s ease-in-out, transform 0.3s ease-in-out;
}

.button-primary:hover {
  background-color: #FFD580;
  transform: scale(1.05);
}

.button-primary:disabled {
  background-color: #ddd;
  color: #666;
  cursor: not-allowed;
}
```

---

### **5. Image Animations**

#### **Fade-in on Scroll**:
- **Effect**: Images fade in as they enter the viewport.
- **CSS Example**:
  ```css
  .image {
    opacity: 0;
    transform: translateY(10px);
    transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
  }
  .image.in-view {
    opacity: 1;
    transform: translateY(0);
  }
  ```

#### **JavaScript to Trigger the Effect**:
```javascript
const images = document.querySelectorAll('.image');
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('in-view');
    }
  });
});

images.forEach(image => observer.observe(image));
```

---

### **6. Inputs**

#### **UI Elements:**
- Text Inputs  
- Textarea  
- Search Bar  
- Password Fields  
- Dropdowns  
- Checkboxes  
- Radio Buttons  
- File Uploads   
- Date Pickers  
- Range Sliders  

#### **Animations for Inputs**:

#### **Default State**:
- Borders and backgrounds should adapt to the surrounding context (e.g., contrasting borders on dark/light backgrounds).  
- Maintain clear text readability.  
- No scaling or shadow effects.  

#### **Focus State**:
- Border changes to `#FFB30C` (yellow) for contrast with brand colors.  
- Slight scaling (`scale(1.02)`) for interactive emphasis.  

#### **Disabled State**:
- Grayed-out appearance with `#ddd` border.  
- No focus or hover effect.  

---

#### **Example CSS**:
```css
input, textarea, select {
  border: 1px solid #ccc;
  transition: border-color 0.3s ease-in-out, transform 0.3s ease-in-out;
}

input:focus, textarea:focus, select:focus {
  border: 3px solid #FFB30C; /* Yellow focus border */
  transform: scale(1.02); /* Slight scaling */
}

input:disabled, textarea:disabled, select:disabled {
  border: 1px solid #ddd; /* Gray border for disabled state */
  background-color: #f1f1f1;
}
```

---

### **7. General Guidelines**
- **Timing**: All animations should take 200-300ms for smooth, consistent transitions.
- **Performance**: Use CSS animations over JavaScript where possible to ensure optimal performance.
- **Accessibility**: Provide reduced motion options for users who prefer minimal animations using `@media (prefers-reduced-motion: reduce)`.


