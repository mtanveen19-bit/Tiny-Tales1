<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#111827">
<title>Tiny Tales — Everyday Finds</title>

<style>
:root{
  --bg:#f8fafc;
  --card:#ffffff;
  --text:#111827;
  --muted:#64748b;
  --line:#e2e8f0;
  --primary:#111827;
  --soft:#f1f5f9;
  --accent:#f59e0b;
  --danger:#ef4444;
  --radius:20px;
}

*{box-sizing:border-box;margin:0;padding:0}

html{scroll-behavior:smooth}

body{
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Arial,sans-serif;
  background:var(--bg);
  color:var(--text);
}

button,input,select,textarea{font:inherit}

button{cursor:pointer}

a{text-decoration:none;color:inherit}

.container{
  width:min(1180px,92%);
  margin:auto;
}

/* HEADER */

header{
  position:sticky;
  top:0;
  z-index:1000;
  background:rgba(255,255,255,.92);
  backdrop-filter:blur(15px);
  border-bottom:1px solid var(--line);
}

.nav{
  min-height:72px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:20px;
}

.logo{
  display:flex;
  align-items:center;
  gap:10px;
  font-size:22px;
  font-weight:900;
  white-space:nowrap;
}

.logo-icon{
  width:40px;
  height:40px;
  border-radius:13px;
  display:grid;
  place-items:center;
  background:#111827;
  color:white;
  font-size:20px;
}

.search{
  flex:1;
  max-width:500px;
  position:relative;
}

.search input{
  width:100%;
  height:44px;
  padding:0 45px 0 17px;
  border:1px solid var(--line);
  border-radius:14px;
  outline:none;
  background:#f8fafc;
  transition:.25s;
}

.search input:focus{
  border-color:#111827;
  background:white;
  box-shadow:0 0 0 4px rgba(17,24,39,.07);
}

.search-icon{
  position:absolute;
  right:15px;
  top:12px;
}

.nav-actions{
  display:flex;
  gap:8px;
}

.icon-btn{
  width:44px;
  height:44px;
  border:1px solid var(--line);
  background:white;
  border-radius:13px;
  display:grid;
  place-items:center;
  transition:.2s;
  position:relative;
}

.icon-btn:hover{
  transform:translateY(-2px);
  border-color:#111827;
}

.icon-btn:active{
  transform:scale(.92);
}

.badge{
  position:absolute;
  top:-5px;
  right:-5px;
  background:#ef4444;
  color:white;
  width:19px;
  height:19px;
  border-radius:50%;
  font-size:11px;
  display:grid;
  place-items:center;
  font-weight:800;
}

/* HERO */

.hero{
  margin-top:25px;
  min-height:430px;
  border-radius:30px;
  overflow:hidden;
  background:
    radial-gradient(circle at 80% 20%,#fde68a 0,transparent 28%),
    linear-gradient(135deg,#111827,#334155);
  color:white;
  display:flex;
  align-items:center;
  position:relative;
}

.hero-content{
  padding:55px;
  max-width:680px;
  position:relative;
  z-index:2;
}

.hero small{
  display:inline-block;
  padding:7px 12px;
  border:1px solid rgba(255,255,255,.3);
  border-radius:50px;
  margin-bottom:18px;
}

.hero h1{
  font-size:clamp(38px,6vw,68px);
  line-height:.98;
  letter-spacing:-3px;
  margin-bottom:20px;
}

.hero p{
  color:#cbd5e1;
  font-size:17px;
  line-height:1.7;
  max-width:560px;
}

.hero-buttons{
  display:flex;
  gap:12px;
  margin-top:28px;
  flex-wrap:wrap;
}

.btn{
  border:1px solid currentColor;
  background:transparent;
  color:inherit;
  padding:12px 18px;
  border-radius:13px;
  font-weight:750;
  transition:.2s;
}

.btn:hover{
  transform:translateY(-2px);
  background:rgba(255,255,255,.1);
}

.btn:active{
  transform:scale(.94);
}

.btn.primary{
  background:white;
  color:#111827;
  border-color:white;
}

.hero-decoration{
  position:absolute;
  right:7%;
  bottom:-30px;
  width:270px;
  height:270px;
  border-radius:50%;
  background:rgba(255,255,255,.08);
  box-shadow:
    0 0 0 40px rgba(255,255,255,.035),
    0 0 0 80px rgba(255,255,255,.02);
}

/* FEATURES */

.features{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:14px;
  margin:20px 0 45px;
}

.feature{
  background:white;
  border:1px solid var(--line);
  border-radius:18px;
  padding:18px;
  display:flex;
  gap:12px;
  align-items:center;
}

.feature-icon{
  font-size:24px;
}

.feature strong{
  display:block;
  font-size:14px;
}

.feature span{
  color:var(--muted);
  font-size:12px;
}

/* SECTION */

.section-head{
  display:flex;
  align-items:end;
  justify-content:space-between;
  margin-bottom:20px;
  gap:20px;
}

.section-head h2{
  font-size:30px;
  letter-spacing:-1px;
}

.section-head p{
  color:var(--muted);
  margin-top:5px;
}

/* CATEGORIES */

.categories{
  display:flex;
  gap:10px;
  overflow-x:auto;
  padding-bottom:8px;
  scrollbar-width:none;
  margin-bottom:25px;
}

.categories::-webkit-scrollbar{display:none}

.category{
  border:1px solid var(--line);
  background:white;
  padding:10px 16px;
  border-radius:50px;
  white-space:nowrap;
  transition:.2s;
}

.category:hover,
.category.active{
  background:#111827;
  color:white;
  border-color:#111827;
}

/* PRODUCTS */

.products{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:18px;
}

.product{
  background:white;
  border:1px solid var(--line);
  border-radius:20px;
  overflow:hidden;
  transition:.25s;
}

.product:hover{
  transform:translateY(-5px);
  box-shadow:0 15px 35px rgba(15,23,42,.08);
}

.product-img{
  height:220px;
  background:#f1f5f9;
  display:grid;
  place-items:center;
  font-size:80px;
  position:relative;
}

.discount{
  position:absolute;
  top:12px;
  left:12px;
  background:#111827;
  color:white;
  padding:5px 8px;
  border-radius:8px;
  font-size:11px;
  font-weight:800;
}

.product-body{
  padding:16px;
}

.product-category{
  color:var(--muted);
  font-size:11px;
  text-transform:uppercase;
  letter-spacing:.8px;
}

.product h3{
  margin:5px 0 9px;
  font-size:16px;
}

.price{
  font-weight:900;
  font-size:18px;
}

.old-price{
  color:#94a3b8;
  text-decoration:line-through;
  font-size:13px;
  margin-left:5px;
}

.rating{
  color:#f59e0b;
  font-size:12px;
  margin:7px 0;
}

.add-btn{
  width:100%;
  border:1px solid #111827;
  background:white;
  color:#111827;
  padding:10px;
  border-radius:11px;
  font-weight:750;
  transition:.2s;
  margin-top:8px;
}

.add-btn:hover{
  background:#111827;
  color:white;
}

.add-btn:active{
  transform:scale(.95);
}

/* EMPTY */

.empty{
  grid-column:1/-1;
  text-align:center;
  padding:60px 20px;
  color:var(--muted);
}

/* DEAL */

.deal{
  margin:55px 0;
  padding:35px;
  border-radius:25px;
  background:#fef3c7;
  border:1px solid #fde68a;
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:25px;
}

.deal h2{
  font-size:30px;
}

.deal p{
  color:#92400e;
  margin-top:8px;
}

.deal .btn{
  color:#92400e;
  border-color:#92400e;
  white-space:nowrap;
}

/* FOOTER */

footer{
  background:#111827;
  color:white;
  margin-top:70px;
  padding:45px 0 25px;
}

.footer-grid{
  display:grid;
  grid-template-columns:2fr 1fr 1fr 1fr;
  gap:35px;
}

footer h3{
  margin-bottom:14px;
}

footer p,
footer li{
  color:#94a3b8;
  line-height:1.8;
  font-size:14px;
}

footer ul{
  list-style:none;
}

.footer-bottom{
  border-top:1px solid #334155;
  margin-top:35px;
  padding-top:20px;
  color:#64748b;
  font-size:13px;
  display:flex;
  justify-content:space-between;
}

/* CART */

.overlay{
  position:fixed;
  inset:0;
  background:rgba(15,23,42,.5);
  z-index:1500;
  opacity:0;
  pointer-events:none;
  transition:.25s;
}

.overlay.show{
  opacity:1;
  pointer-events:auto;
}

.cart{
  position:fixed;
  right:0;
  top:0;
  height:100%;
  width:min(430px,100%);
  background:white;
  z-index:1600;
  transform:translateX(100%);
  transition:.3s ease;
  display:flex;
  flex-direction:column;
}

.cart.show{
  transform:translateX(0);
}

.cart-head{
  padding:20px;
  border-bottom:1px solid var(--line);
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.cart-items{
  flex:1;
  overflow:auto;
  padding:15px;
}

.cart-item{
  display:flex;
  gap:12px;
  padding:14px 0;
  border-bottom:1px solid var(--line);
}

.cart-item-img{
  width:70px;
  height:70px;
  border-radius:13px;
  background:#f1f5f9;
  display:grid;
  place-items:center;
  font-size:30px;
}

.cart-item-info{
  flex:1;
}

.cart-item-info h4{
  font-size:14px;
}

.cart-price{
  font-weight:800;
  margin-top:4px;
}

.qty{
  display:flex;
  align-items:center;
  gap:8px;
  margin-top:8px;
}

.qty button{
  width:27px;
  height:27px;
  border:1px solid var(--line);
  background:white;
  border-radius:7px;
}

.remove{
  border:0;
  background:none;
  color:#ef4444;
  font-size:12px;
}

.cart-foot{
  padding:20px;
  border-top:1px solid var(--line);
}

.summary-row{
  display:flex;
  justify-content:space-between;
  margin-bottom:10px;
}

.total{
  font-size:20px;
  font-weight:900;
  margin:14px 0;
}

.checkout-btn{
  width:100%;
  border:1px solid #111827;
  background:#111827;
  color:white;
  padding:13px;
  border-radius:12px;
  font-weight:800;
}

.cart-empty{
  text-align:center;
  padding:80px 20px;
  color:var(--muted);
}

/* MODAL */

.modal-overlay{
  position:fixed;
  inset:0;
  background:rgba(15,23,42,.6);
  z-index:2000;
  display:none;
  align-items:center;
  justify-content:center;
  padding:15px;
}

.modal-overlay.show{
  display:flex;
}

.modal{
  width:min(620px,100%);
  max-height:90vh;
  overflow:auto;
  background:white;
  border-radius:24px;
  padding:25px;
  animation:pop .25s ease;
}

@keyframes pop{
  from{transform:scale(.92);opacity:0}
  to{transform:scale(1);opacity:1}
}

.modal-head{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:20px;
}

.close{
  width:38px;
  height:38px;
  border:1px solid var(--line);
  background:white;
  border-radius:10px;
}

.form-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:14px;
}

.form-group{
  margin-bottom:14px;
}

.form-group.full{
  grid-column:1/-1;
}

.form-group label{
  display:block;
  font-size:13px;
  font-weight:700;
  margin-bottom:6px;
}

.form-group input,
.form-group textarea,
.form-group select{
  width:100%;
  padding:12px;
  border:1px solid var(--line);
  border-radius:11px;
  outline:none;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus{
  border-color:#111827;
}

.payment{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:9px;
}

.payment label{
  border:1px solid var(--line);
  padding:12px 8px;
  border-radius:11px;
  text-align:center;
  cursor:pointer;
}

.payment input{
  display:none;
}

.payment label:has(input:checked){
  border-color:#111827;
  background:#f8fafc;
}

.order-success{
  text-align:center;
  padding:25px 10px;
}

.success-icon{
  width:75px;
  height:75px;
  border-radius:50%;
  background:#dcfce7;
  color:#16a34a;
  display:grid;
  place-items:center;
  font-size:35px;
  margin:0 auto 18px;
}

/* TOAST */

.toast{
  position:fixed;
  left:50%;
  bottom:25px;
  transform:translate(-50%,100px);
  background:#111827;
  color:white;
  padding:12px 18px;
  border-radius:12px;
  z-index:3000;
  opacity:0;
  transition:.3s;
  font-size:14px;
}

.toast.show{
  transform:translate(-50%,0);
  opacity:1;
}

/* MOBILE */

@media(max-width:900px){
  .products{grid-template-columns:repeat(3,1fr)}
  .features{grid-template-columns:repeat(2,1fr)}
  .footer-grid{grid-template-columns:1fr 1fr}
}

@media(max-width:650px){
  .nav{
    flex-wrap:wrap;
    padding:10px 0;
  }

  .search{
    order:3;
    max-width:none;
    flex-basis:100%;
  }

  .hero{
    min-height:430px;
  }

  .hero-content{
    padding:35px 25px;
  }

  .hero h1{
    font-size:44px;
  }

  .hero-decoration{
    width:170px;
    height:170px;
    right:-40px;
    bottom:30px;
  }

  .features{
    grid-template-columns:1fr 1fr;
  }

  .feature{
    padding:13px;
  }

  .products{
    grid-template-columns:repeat(2,1fr);
    gap:12px;
  }

  .product-img{
    height:160px;
    font-size:60px;
  }

  .product-body{
    padding:12px;
  }

  .deal{
    flex-direction:column;
    align-items:flex-start;
  }

  .footer-grid{
    grid-template-columns:1fr 1fr;
  }

  .footer-bottom{
    flex-direction:column;
    gap:8px;
  }

  .form-grid{
    grid-template-columns:1fr;
  }

  .form-group.full{
    grid-column:auto;
  }
}

@media(max-width:400px){
  .products{
    grid-template-columns:1fr 1fr;
  }

  .features{
    grid-template-columns:1fr;
  }

  .logo{
    font-size:19px;
  }
}
</style>
</head>

<body>

<header>
  <div class="container nav">

    <a href="#" class="logo">
      <span class="logo-icon">✦</span>
      <span>Tiny Tales</span>
    </a>

    <div class="search">
      <input id="searchInput" type="search" placeholder="Search products...">
      <span class="search-icon">⌕</span>
    </div>

    <div class="nav-actions">
      <button class="icon-btn" onclick="scrollToProducts()" aria-label="Products">⌕</button>

      <button class="icon-btn" onclick="openCart()" aria-label="Cart">
        🛒
        <span class="badge" id="cartCount">0</span>
      </button>
    </div>

  </div>
</header>


<main class="container">

  <!-- HERO -->

  <section class="hero">

    <div class="hero-content">
      <small>✨ Little things. Big stories.</small>

      <h1>Discover your next tiny tale.</h1>

      <p>
        Carefully selected everyday products made to add a little more
        convenience, comfort and joy to your daily life.
      </p>

      <div class="hero-buttons">
        <button class="btn primary" onclick="scrollToProducts()">
          Shop Now →
        </button>

        <button class="btn" onclick="showAbout()">
          About Tiny Tales
        </button>
      </div>
    </div>

    <div class="hero-decoration"></div>

  </section>


  <!-- FEATURES -->

  <section class="features">

    <div class="feature">
      <span class="feature-icon">🚚</span>
      <div>
        <strong>Fast Delivery</strong>
        <span>Across Bangladesh</span>
      </div>
    </div>

    <div class="feature">
      <span class="feature-icon">🔒</span>
      <div>
        <strong>Secure Payment</strong>
        <span>Safe checkout</span>
      </div>
    </div>

    <div class="feature">
      <span class="feature-icon">↩️</span>
      <div>
        <strong>Easy Returns</strong>
        <span>Simple return policy</span>
      </div>
    </div>

    <div class="feature">
      <span class="feature-icon">💬</span>
      <div>
        <strong>Customer Support</strong>
        <span>We're here to help</span>
      </div>
    </div>

  </section>


  <!-- PRODUCTS -->

  <section id="shop">

    <div class="section-head">
      <div>
        <h2>Shop our collection</h2>
        <p>Small products, useful ideas and everyday essentials.</p>
      </div>
    </div>

    <div class="categories" id="categories"></div>

    <div class="products" id="products"></div>

  </section>


  <!-- DEAL -->

  <section class="deal">

    <div>
      <h2>🎁 Special Deal</h2>
      <p>Get 10% OFF on orders above ৳2,000.</p>
    </div>

    <button class="btn" onclick="scrollToProducts()">
      Explore Deals →
    </button>

  </section>

</main>


<!-- FOOTER -->

<footer>

  <div class="container">

    <div class="footer-grid">

      <div>
        <div class="logo">
          <span class="logo-icon">✦</span>
          <span>Tiny Tales</span>
        </div>

        <p style="margin-top:15px">
          Your destination for carefully selected everyday products,
          useful little things and delightful finds.
        </p>
      </div>

      <div>
        <h3>Shop</h3>
        <ul>
          <li>New Arrivals</li>
          <li>Best Sellers</li>
          <li>Home & Living</li>
          <li>Accessories</li>
        </ul>
      </div>

      <div>
        <h3>Help</h3>
        <ul>
          <li>Delivery Information</li>
          <li>Return Policy</li>
          <li>Payment Methods</li>
          <li>FAQ</li>
        </ul>
      </div>

      <div>
        <h3>Contact</h3>
        <ul>
          <li>📞 01XXXXXXXXX</li>
          <li>✉️ hello@tinytales.com</li>
          <li>📍 Dhaka, Bangladesh</li>
        </ul>
      </div>

    </div>

    <div class="footer-bottom">
      <span>© 2026 Tiny Tales. All rights reserved.</span>
      <span>Made with ♥ in Bangladesh</span>
    </div>

  </div>

</footer>


<!-- CART -->

<div class="overlay" id="overlay" onclick="closeCart()"></div>

<aside class="cart" id="cart">

  <div class="cart-head">
    <h2>Your Cart</h2>
    <button class="close" onclick="closeCart()">×</button>
  </div>

  <div class="cart-items" id="cartItems"></div>

  <div class="cart-foot">

    <div class="summary-row">
      <span>Subtotal</span>
      <strong id="subtotal">৳0</strong>
    </div>

    <div class="summary-row">
      <span>Delivery</span>
      <strong id="delivery">৳0</strong>
    </div>

    <div class="summary-row" id="discountRow" style="display:none">
      <span>Discount</span>
      <strong style="color:#16a34a" id="discount">-৳0</strong>
    </div>

    <div class="summary-row total">
      <span>Total</span>
      <span id="total">৳0</span>
    </div>

    <button class="checkout-btn" onclick="openCheckout()">
      Proceed to Checkout →
    </button>

  </div>

</aside>


<!-- CHECKOUT MODAL -->

<div class="modal-overlay" id="checkoutModal">

  <div class="modal">

    <div class="modal-head">
      <h2>Checkout</h2>
      <button class="close" onclick="closeCheckout()">×</button>
    </div>

    <form id="checkoutForm">

      <div class="form-grid">

        <div class="form-group">
          <label>Full Name *</label>
          <input id="customerName" required placeholder="Your name">
        </div>

        <div class="form-group">
          <label>Phone Number *</label>
          <input id="customerPhone" required type="tel" placeholder="01XXXXXXXXX">
        </div>

        <div class="form-group">
          <label>Division *</label>
          <select id="division" required>
            <option value="">Select division</option>
            <option>Dhaka</option>
            <option>Chattogram</option>
            <option>Rajshahi</option>
            <option>Khulna</option>
            <option>Barishal</option>
            <option>Sylhet</option>
            <option>Rangpur</option>
            <option>Mymensingh</option>
          </select>
        </div>

        <div class="form-group">
          <label>Delivery Area *</label>
          <input id="area" required placeholder="Area / Thana">
        </div>

        <div class="form-group full">
          <label>Full Address *</label>
          <textarea id="address" rows="3" required placeholder="House, road, area..."></textarea>
        </div>

        <div class="form-group full">
          <label>Payment Method *</label>

          <div class="payment">

            <label>
              <input type="radio" name="payment" value="Cash on Delivery" checked>
              💵<br>Cash on Delivery
            </label>

            <label>
              <input type="radio" name="payment" value="bKash">
              🟣<br>bKash
            </label>

            <label>
              <input type="radio" name="payment" value="Nagad">
              🟠<br>Nagad
            </label>

          </div>
        </div>

        <div class="form-group full">

          <div style="background:#f8fafc;border:1px solid var(--line);padding:15px;border-radius:13px">

            <div class="summary-row">
              <span>Order total</span>
              <strong id="checkoutTotal">৳0</strong>
            </div>

            <small style="color:#64748b">
              Orders above ৳2,000 receive 10% discount.
            </small>

          </div>

        </div>

        <div class="form-group full">
          <button class="checkout-btn" type="submit">
            Place Order ✓
          </button>
        </div>

      </div>

    </form>

  </div>

</div>


<!-- SUCCESS MODAL -->

<div class="modal-overlay" id="successModal">

  <div class="modal">

    <div class="order-success">

      <div class="success-icon">✓</div>

      <h2>Order Confirmed!</h2>

      <p style="color:#64748b;margin:10px 0 20px">
        Thank you for shopping with Tiny Tales.
      </p>

      <div style="background:#f8fafc;padding:15px;border-radius:13px;text-align:left">

        <div class="summary-row">
          <span>Order ID</span>
          <strong id="orderId"></strong>
        </div>

        <div class="summary-row">
          <span>Total</span>
          <strong id="successTotal"></strong>
        </div>

        <div class="summary-row">
          <span>Payment</span>
          <strong id="successPayment"></strong>
        </div>

      </div>

      <button class="checkout-btn" style="margin-top:20px" onclick="closeSuccess()">
        Continue Shopping
      </button>

    </div>

  </div>

</div>


<div class="toast" id="toast"></div>


<script>

/* =========================
   PRODUCT DATABASE
========================= */

const products = [

  {
    id:1,
    name:"Minimal Desk Lamp",
    category:"Home",
    price:850,
    oldPrice:1100,
    rating:4.8,
    icon:"💡",
    discount:"23% OFF"
  },

  {
    id:2,
    name:"Cute Mini Wallet",
    category:"Accessories",
    price:490,
    oldPrice:650,
    rating:4.7,
    icon:"👛",
    discount:"25% OFF"
  },

  {
    id:3,
    name:"Reusable Water Bottle",
    category:"Lifestyle",
    price:650,
    oldPrice:800,
    rating:4.9,
    icon:"🧴",
    discount:"19% OFF"
  },

  {
    id:4,
    name:"Aesthetic Notebook",
    category:"Stationery",
    price:280,
    oldPrice:350,
    rating:4.6,
    icon:"📓",
    discount:"20% OFF"
  },

  {
    id:5,
    name:"Travel Organizer",
    category:"Accessories",
    price:750,
    oldPrice:950,
    rating:4.8,
    icon:"👜",
    discount:"21% OFF"
  },

  {
    id:6,
    name:"Mini Bluetooth Speaker",
    category:"Gadgets",
    price:1250,
    oldPrice:1500,
    rating:4.7,
    icon:"🔊",
    discount:"17% OFF"
  },

  {
    id:7,
    name:"Plant Pot Set",
    category:"Home",
    price:590,
    oldPrice:750,
    rating:4.5,
    icon:"🪴",
    discount:"21% OFF"
  },

  {
    id:8,
    name:"Daily Planner",
    category:"Stationery",
    price:420,
    oldPrice:550,
    rating:4.9,
    icon:"📔",
    discount:"24% OFF"
  },

  {
    id:9,
    name:"Phone Stand",
    category:"Gadgets",
    price:350,
    oldPrice:450,
    rating:4.7,
    icon:"📱",
    discount:"22% OFF"
  },

  {
    id:10,
    name:"Cozy Cushion",
    category:"Home",
    price:700,
    oldPrice:900,
    rating:4.6,
    icon:"🛋️",
    discount:"22% OFF"
  },

  {
    id:11,
    name:"Keychain Set",
    category:"Accessories",
    price:220,
    oldPrice:300,
    rating:4.8,
    icon:"🔑",
    discount:"27% OFF"
  },

  {
    id:12,
    name:"Wireless Mouse",
    category:"Gadgets",
    price:850,
    oldPrice:1050,
    rating:4.7,
    icon:"🖱️",
    discount:"19% OFF"
  }

];


/* =========================
   STATE
========================= */

let cart = JSON.parse(localStorage.getItem("tinyTalesCart")) || [];
let currentCategory = "All";


/* =========================
   INIT
========================= */

function init(){

  renderCategories();
  renderProducts();
  updateCart();

}

init();


/* =========================
   CATEGORIES
========================= */

function renderCategories(){

  const categories = [
    "All",
    ...new Set(products.map(p => p.category))
  ];

  document.getElementById("categories").innerHTML =
    categories.map(category => `
      <button
        class="category ${category === currentCategory ? "active":""}"
        onclick="filterCategory('${category}')">
        ${category}
      </button>
    `).join("");

}


function filterCategory(category){

  currentCategory = category;

  renderCategories();
  renderProducts();

}


/* =========================
   PRODUCTS
========================= */

function renderProducts(){

  const search =
    document.getElementById("searchInput").value
      .toLowerCase()
      .trim();

  let filtered = products.filter(product => {

    const matchesCategory =
      currentCategory === "All" ||
      product.category === currentCategory;

    const matchesSearch =
      product.name.toLowerCase().includes(search) ||
      product.category.toLowerCase().includes(search);

    return matchesCategory && matchesSearch;

  });


  const container = document.getElementById("products");


  if(!filtered.length){

    container.innerHTML = `
      <div class="empty">
        <div style="font-size:45px">🔎</div>
        <h3>No products found</h3>
        <p>Try another search or category.</p>
      </div>
    `;

    return;

  }


  container.innerHTML = filtered.map(product => `

    <article class="product">

      <div class="product-img">

        <span class="discount">${product.discount}</span>

        <span>${product.icon}</span>

      </div>

      <div class="product-body">

        <div class="product-category">
          ${product.category}
        </div>

        <h3>${product.name}</h3>

        <div class="rating">
          ★★★★★
          <span style="color:#64748b">
            ${product.rating}
          </span>
        </div>

        <div>

          <span class="price">
            ৳${product.price.toLocaleString()}
          </span>

          <span class="old-price">
            ৳${product.oldPrice.toLocaleString()}
          </span>

        </div>

        <button
          class="add-btn"
          onclick="addToCart(${product.id})">

          + Add to Cart

        </button>

      </div>

    </article>

  `).join("");

}


document
  .getElementById("searchInput")
  .addEventListener("input",renderProducts);


/* =========================
   CART
========================= */

function addToCart(id){

  const existing = cart.find(item => item.id === id);

  if(existing){
    existing.qty++;
  }else{
    cart.push({
      id:id,
      qty:1
    });
  }

  saveCart();
  updateCart();
  showToast("Added to cart ✓");

}


function removeFromCart(id){

  cart = cart.filter(item => item.id !== id);

  saveCart();
  updateCart();

}


function changeQty(id,amount){

  const item = cart.find(item => item.id === id);

  if(!item) return;

  item.qty += amount;

  if(item.qty <= 0){
    removeFromCart(id);
    return;
  }

  saveCart();
  updateCart();

}


function saveCart(){

  localStorage.setItem(
    "tinyTalesCart",
    JSON.stringify(cart)
  );

}


function getCartData(){

  return cart.map(item => {

    const product =
      products.find(p => p.id === item.id);

    return {
      ...product,
      qty:item.qty,
      lineTotal:product.price * item.qty
    };

  });

}


function calculateTotals(){

  const items = getCartData();

  const subtotal =
    items.reduce(
      (sum,item) => sum + item.lineTotal,
      0
    );

  const delivery =
    subtotal === 0 ? 0 :
    subtotal >= 1500 ? 0 : 80;

  const discount =
    subtotal >= 2000
      ? Math.round(subtotal * .10)
      : 0;

  const total =
    subtotal + delivery - discount;

  return {
    subtotal,
    delivery,
    discount,
    total
  };

}


function updateCart(){

  const items = getCartData();

  const totalQty =
    cart.reduce(
      (sum,item) => sum + item.qty,
      0
    );

  document.getElementById("cartCount").textContent =
    totalQty;


  const container =
    document.getElementById("cartItems");


  if(!items.length){

    container.innerHTML = `
      <div class="cart-empty">
        <div style="font-size:50px">🛒</div>
        <h3>Your cart is empty</h3>
        <p>Add something you love.</p>
      </div>
    `;

  }else{

    container.innerHTML =
      items.map(item => `

        <div class="cart-item">

          <div class="cart-item-img">
            ${item.icon}
          </div>

          <div class="cart-item-info">

            <h4>${item.name}</h4>

            <div class="cart-price">
              ৳${item.lineTotal.toLocaleString()}
            </div>

            <div class="qty">

              <button
                onclick="changeQty(${item.id},-1)">
                −
              </button>

              <strong>${item.qty}</strong>

              <button
                onclick="changeQty(${item.id},1)">
                +
              </button>

              <button
                class="remove"
                onclick="removeFromCart(${item.id})">
                Remove
              </button>

            </div>

          </div>

        </div>

      `).join("");

  }


  const totals = calculateTotals();

  document.getElementById("subtotal").textContent =
    "৳" + totals.subtotal.toLocaleString();

  document.getElementById("delivery").textContent =
    totals.delivery === 0
      ? "FREE"
      : "৳" + totals.delivery;

  document.getElementById("discountRow").style.display =
    totals.discount > 0 ? "flex" : "none";

  document.getElementById("discount").textContent =
    "-৳" + totals.discount.toLocaleString();

  document.getElementById("total").textContent =
    "৳" + totals.total.toLocaleString();

}


/* =========================
   CART OPEN/CLOSE
========================= */

function openCart(){

  document
    .getElementById("cart")
    .classList.add("show");

  document
    .getElementById("overlay")
    .classList.add("show");

}


function closeCart(){

  document
    .getElementById("cart")
    .classList.remove("show");

  document
    .getElementById("overlay")
    .classList.remove("show");

}


/* =========================
   CHECKOUT
========================= */

function openCheckout(){

  if(cart.length === 0){

    showToast("Your cart is empty");

    return;

  }

  const totals = calculateTotals();

  document.getElementById("checkoutTotal").textContent =
    "৳" + totals.total.toLocaleString();

  document
    .getElementById("checkoutModal")
    .classList.add("show");

}


function closeCheckout(){

  document
    .getElementById("checkoutModal")
    .classList.remove("show");

}


document
  .getElementById("checkoutForm")
  .addEventListener("submit",function(e){

    e.preventDefault();


    const totals = calculateTotals();

    const payment =
      document.querySelector(
        'input[name="payment"]:checked'
      ).value;


    const orderId =
      "TT" +
      Date.now().toString().slice(-8);


    document.getElementById("orderId").textContent =
      "#" + orderId;

    document.getElementById("successTotal").textContent =
      "৳" + totals.total.toLocaleString();

    document.getElementById("successPayment").textContent =
      payment;


    closeCheckout();
    closeCart();

    document
      .getElementById("successModal")
      .classList.add("show");


    cart = [];

    saveCart();
    updateCart();

    document.getElementById("checkoutForm").reset();

  });


function closeSuccess(){

  document
    .getElementById("successModal")
    .classList.remove("show");

}


/* =========================
   UTILITIES
========================= */

function scrollToProducts(){

  document
    .getElementById("shop")
    .scrollIntoView({
      behavior:"smooth"
    });

}


function showAbout(){

  alert(
`Tiny Tales

Little things. Big stories.

Tiny Tales is an online store focused on useful,
beautiful and affordable everyday products.

Delivery:
• Inside Dhaka: ৳80
• Orders ৳1,500+: FREE delivery
• Orders ৳2,000+: 10% OFF

Payment:
• Cash on Delivery
• bKash
• Nagad

Customer Support:
01XXXXXXXXX
hello@tinytales.com`
  );

}


let toastTimer;

function showToast(message){

  const toast =
    document.getElementById("toast");

  toast.textContent = message;

  toast.classList.add("show");

  clearTimeout(toastTimer);

  toastTimer =
    setTimeout(
      () => toast.classList.remove("show"),
      2000
    );

}


/* ESCAPE KEY */

document.addEventListener("keydown",e => {

  if(e.key === "Escape"){

    closeCart();
    closeCheckout();
    closeSuccess();

  }

});

</script>

</body>
</html>
