# animation-guidelines

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

#### **2. Logo Entrance:**
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

### **3. Category Hover Animations**

#### **Hover Effect**:
- **Effect**: Scale up the card (1.03x) on hover. No shadow.
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



### **4. Button Animations Based on Button Instances**

#### **General Behavior**
- All button animations should adhere to the defined states:
  - **Default**
  - **Hover**
  - **Focused**
  - **Active**
  - **Disabled**

Each state will follow the button styles (e.g., `Primary-Filled`, `Secondary-Filled`, etc.) with transitions to enhance the user experience.
### **6. Image Animations**

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
- **Code**:
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

### **7. Input Field Animations**

#### **Focus Effect**:
- **Effect**: Border changes to 3px yellow solid (#FFCC00) on focus.
- **CSS Example**:
  ```css
  input, textarea {
    border: 1px solid #ccc;
    transition: border-color 0.2s ease-in-out, border-width 0.2s ease-in-out;
  }
  input:focus, textarea:focus {
    border: 3px solid #FFCC00;
    outline: none;
  }
  ```

---

### **General Guidelines**

1. **Timing**: All animations should take 200-300ms for smooth, consistent transitions.
2. **Performance**: Use CSS animations over JavaScript where possible.
3. **Accessibility**: Offer a reduced motion option for users who prefer minimal animations.

---
