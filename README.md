<h1 align="center">Amazon Clone</h1>

<p align="center">
  A full-featured e-commerce web application replicating Amazon's core shopping experience — from product browsing to order tracking.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Day.js-FF5F4C?style=for-the-badge&logo=clockify&logoColor=white" alt="Day.js" />
  <img src="https://img.shields.io/badge/Jasmine-8A4182?style=for-the-badge&logo=jasmine&logoColor=white" alt="Jasmine" />
</p>

<br />

<h3 align="center">
  <a href="https://lnm31.github.io/Amazon-Clone/">&rarr; View Live Demo &larr;</a>
</h3>

<br />

---

## Key Features

- **Product Catalog** — Browse 40+ products across multiple categories with star ratings, price display, and keyword search
- **Smart Search** — Filter products in real-time by name and keywords
- **Shopping Cart** — Add items, update quantities, remove products, with full localStorage persistence
- **Checkout Flow** — Review order, choose from 3 delivery speeds (free 7-day, $4.99 3-day, $9.99 next-day), and see an itemized payment breakdown with tax
- **Order Placement** — Submit orders via backend API with confirmation and automatic order history tracking
- **Order History** — View all past orders with dates, totals, and a one-click "Buy it again" option
- **Delivery Tracking** — Visual progress bar showing real-time delivery status (Preparing → Shipped → Delivered)
- **Responsive Design** — Fully adaptive layout from ultra-wide desktops (8-column grid) down to mobile (single column)

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Markup** | HTML5 with semantic structure |
| **Styling** | CSS3 — Grid, Flexbox, Media Queries |
| **Logic** | Vanilla JavaScript (ES6 Modules, Classes, Async/Await) |
| **Date Handling** | Day.js |
| **State** | Browser LocalStorage |
| **Backend API** | RESTful service (fetch products, place orders) |
| **Testing** | Jasmine 5.1.1 |
| **Fonts** | Google Fonts (Roboto) |

---

## Architecture

The project follows a clean **separation of concerns** with modular ES6 architecture:

```
Amazon-Clone/
│
├── index.html / checkout.html / orders.html / tracking.html
│
├── scripts/                  # Application logic
│   ├── amazon.js             # Homepage — product grid, search, add-to-cart
│   ├── checkout.js           # Checkout page initialization
│   ├── orders.js             # Order history rendering
│   ├── tracking.js           # Delivery tracking with progress bar
│   ├── checkout/
│   │   ├── orderSummary.js   # Cart items, quantities, delivery options
│   │   ├── paymentSummary.js # Price breakdown and order submission
│   │   └── checkoutHeader.js # Checkout header component
│   └── utils/
│       └── money.js          # Currency formatting (cents → dollars)
│
├── data/                     # Data layer & state management
│   ├── products.js           # Product classes (Product, Clothing, Appliance)
│   ├── cart.js               # Cart state with localStorage persistence
│   ├── orders.js             # Order history management
│   └── deliveryOptions.js    # Shipping options & date calculation
│
├── styles/
│   ├── shared/               # Global styles & header
│   └── pages/                # Page-specific stylesheets
│
├── images/                   # Logos, icons, product images, rating stars
├── backend/                  # Product data (JSON)
└── tests/                    # Jasmine test suite
```

---

## How It Works

```
Browse Products  ➜  Add to Cart  ➜  Choose Delivery  ➜  Place Order  ➜  Track Delivery
     |                  |                 |                  |                |
  Fetch API        localStorage      Date calc          Backend API     Progress bar
  + Search         persistence     (excludes weekends)  POST /orders    with status
```

- **Products** are fetched from a backend API and rendered as class instances (`Product`, `Clothing`, `Appliance`) with polymorphic behavior
- **Cart & Orders** persist entirely in the browser via localStorage — no login required
- **Delivery dates** are calculated dynamically, automatically skipping weekends
- **All prices** are stored as integers (cents) and formatted on display to avoid floating-point issues

---

<p align="center">
  <b><a href="https://lnm31.github.io/Amazon-Clone/">View the Live Demo</a></b>
</p>
