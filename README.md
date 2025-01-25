![Image of Manage Landing Page](screenshot.png)

### 📝 Key Takeaways

I this project, I practiced writing Tailwind CSS classes and working with responsiveness. I also re-learned how to create a toggle for a burger menu and the importance of using comments to help navigate and understand the code.

---

#### HTML
```html
<!-- Hamburger Icon -->
<button id="menu-btn" class="block hamburger md:hidden focus:outline-none">
  <span class="hamburger-top"></span>
  <span class="hamburger-middle"></span>
  <span class="hamburger-bottom"></span>
</button>
```

#### JS
```js
const btn = document.getElementById('menu-btn')
const nav = document.getElementById('menu')

btn.addEventListener('click', () => {
  btn.classList.toggle('open')
  nav.classList.toggle('flex')
  nav.classList.toggle('hidden')
})
```

#### CSS
```css
/* Hamburger Menu */
.hamburger {
  cursor: pointer;
  width: 24px;
  height: 24px;
  transition: all 0.25s;
  position: relative;
}

.hamburger-top,
.hamburger-middle,
.hamburger-bottom {
  position: absolute;
  top: 0;
  left: 0;
  width: 24px;
  height: 2px;
  background: #000;
  transform: rotate(0);
  transition: all 0.5s;
}

.hamburger-middle {
  transform: translateY(7px);
}

.hamburger-bottom {
  transform: translateY(14px);
}

.open {
  transform: rotate(90deg);
  transform: translateY(0px);
}

.open .hamburger-top {
  transform: rotate(45deg) translateY(6px) translate(6px);
}

.open .hamburger-middle {
  display: none;
}

.open .hamburger-bottom {
  transform: rotate(-45deg) translateY(6px) translate(-6px);
}