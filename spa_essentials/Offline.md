Ask:
```text
create a local offline webpage similar to https://spa-disposables--7pertgha.preview.emergentagent.com/ using html, css, javascript and python

on clicking a product from main page, there should be a provision to view product details and Similar products list as per following page create a local website similar to https://spa-disposables--7pertgha.preview.emergentagent.com/product/airloom-bouffant-head-cap 

To build this complete offline e-commerce site with a main page, detailed product pages, and a "Similar Products" section, you will use Flask (Python) for the backend and standard HTML/CSS/JS for the frontend.

Because this needs to work completely offline, all visual elements will use system fonts, CSS styling, and emoji-based product placeholders so no internet connection is required to load external images or fonts.

Project Structure
Create a new folder called spa_offline and set up the exact structure below:

spa_offline/
├── app.py
├── static/
│   ├── style.css
│   └── script.js
└── templates/
    ├── index.html
    └── product.html
```

## 1. Python Backend (app.py)
This serves your web pages and handles the logic for finding "similar products."

```python
from flask import Flask, render_template, jsonify, abort

app = Flask(__name__)

# Offline product database
PRODUCTS = [
    {
        "id": 1, 
        "name": "Airloom Bouffant Head Cap", 
        "price": 14.99, 
        "image": "🧑‍⚕️", 
        "desc": "Breathable, spunbond polypropylene bouffant caps.",
        "long_desc": "Keep your spa environment sanitary with our premium Airloom Bouffant Head Caps. Made from lightweight, breathable spunbond polypropylene, these caps provide excellent barrier protection while remaining comfortable for extended wear. The gentle elastic band ensures a secure fit without leaving marks.",
        "specs": ["Material: Spunbond Polypropylene", "Size: 21 inches", "Latex-free elastic", "Color: White", "Pack Size: 100 pieces"]
    },
    {
        "id": 2, 
        "name": "Disposable Massage Bed Covers", 
        "price": 24.99, 
        "image": "🛏️", 
        "desc": "Pack of 50 non-woven waterproof bed sheets.",
        "long_desc": "Protect your massage tables and ensure maximum hygiene for every client. Our non-woven bed covers are waterproof, oil-resistant, and tear-proof, providing a clean and professional surface for every treatment.",
        "specs": ["Material: Non-woven fabric + PE film", "Size: 31 x 70 inches", "Waterproof & Oil-resistant", "Pack Size: 50 pieces"]
    },
    {
        "id": 3, 
        "name": "Eco-Friendly Spa Slippers", 
        "price": 19.99, 
        "image": "🩴", 
        "desc": "Pack of 20 pairs, closed-toe comfort.",
        "long_desc": "Provide maximum comfort from the moment your clients arrive. These closed-toe disposable slippers feature a padded sole and soft fabric upper, perfect for walking around wet or dry spa areas.",
        "specs": ["Material: Cotton blend", "Sole: 5mm EVA non-slip", "Size: Universal Adult", "Pack Size: 20 pairs"]
    },
    {
        "id": 4, 
        "name": "Disposable Spa Towels", 
        "price": 29.99, 
        "image": "🧖", 
        "desc": "Pack of 50 ultra-absorbent towels.",
        "long_desc": "Eliminate laundry costs and maintain perfect hygiene with our ultra-absorbent disposable towels. Soft enough for facial use, yet durable enough for body treatments.",
        "specs": ["Material: 100% Biodegradable Wood Pulp", "Size: 16 x 31 inches", "Absorbency: High", "Pack Size: 50 pieces"]
    }
]

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/product/<int:product_id>')
def product_page(product_id):
    product = next((p for p in PRODUCTS if p["id"] == product_id), None)
    if not product:
        abort(404)
        
    # Get 3 other products to display as "Similar Products"
    similar_products = [p for p in PRODUCTS if p["id"] != product_id][:3]
    
    return render_template('product.html', product=product, similar=similar_products)

@app.route('/api/products')
def get_products():
    return jsonify(PRODUCTS)

if __name__ == '__main__':
    app.run(debug=True, port=5000)
```

## 2. Main Page (templates/index.html)

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spa Disposables | Premium Offline Shop</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <header>
        <div class="logo"><a href="/">🌿 SpaDisposables</a></div>
        <nav>
            <ul>
                <li><a href="/">Home</a></li>
                <li><a href="#products">Shop</a></li>
                <li class="cart-icon">🛒 Cart (<span id="cart-count">0</span>)</li>
            </ul>
        </nav>
    </header>

    <section class="hero">
        <h1>Premium Quality Disposables for Your Spa</h1>
        <p>Hygienic, comfortable, and eco-friendly supplies for salons, spas, and massage therapy.</p>
        <a href="#products" class="btn">Shop Now</a>
    </section>

    <main id="products" class="container">
        <h2>Our Products</h2>
        <div class="product-grid" id="product-list"></div>
    </main>

    <footer>
        <p>&copy; 2026 Spa Disposables. Running Locally.</p>
    </footer>

    <script src="{{ url_for('static', filename='script.js') }}"></script>
</body>
</html>
```

## 3. Product Details Page (templates/product.html)

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ product.name }} | Spa Disposables</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <header>
        <div class="logo"><a href="/">🌿 SpaDisposables</a></div>
        <nav>
            <ul>
                <li><a href="/">Home</a></li>
                <li><a href="/#products">Shop</a></li>
                <li class="cart-icon">🛒 Cart (<span id="cart-count">0</span>)</li>
            </ul>
        </nav>
    </header>

    <main class="container">
        <!-- Breadcrumbs -->
        <nav class="breadcrumbs">
            <a href="/">Home</a> &gt; <a href="/#products">Products</a> &gt; <span>{{ product.name }}</span>
        </nav>

        <!-- Product Details -->
        <div class="product-layout">
            <div class="product-gallery">
                <div class="main-image">{{ product.image }}</div>
            </div>

            <div class="product-details">
                <h1 class="product-title-large">{{ product.name }}</h1>
                <p class="product-price-large">${{ "%.2f"|format(product.price) }}</p>
                <p class="product-description">{{ product.long_desc }}</p>

                <div class="purchase-actions">
                    <div class="quantity-selector">
                        <button type="button" class="qty-btn" onclick="updateQty(-1)">-</button>
                        <input type="number" id="qty-input" value="1" min="1">
                        <button type="button" class="qty-btn" onclick="updateQty(1)">+</button>
                    </div>
                    <button class="btn add-to-cart-large" onclick="addToCart()">Add to Cart</button>
                </div>

                <div class="product-specs">
                    <h3>Specifications</h3>
                    <ul>
                        {% for spec in product.specs %}
                            <li>{{ spec }}</li>
                        {% endfor %}
                    </ul>
                </div>
            </div>
        </div>

        <!-- Similar Products Section -->
        <section class="similar-products">
            <h2>Similar Products</h2>
            <div class="product-grid">
                {% for item in similar %}
                <div class="product-card" onclick="window.location.href='/product/{{ item.id }}'">
                    <div class="product-icon">{{ item.image }}</div>
                    <h3 class="product-title">{{ item.name }}</h3>
                    <div class="product-price">${{ "%.2f"|format(item.price) }}</div>
                    <button class="add-to-cart" onclick="addToCart(1, event)">Add to Cart</button>
                </div>
                {% endfor %}
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Spa Disposables. Running Locally.</p>
    </footer>

    <script src="{{ url_for('static', filename='script.js') }}"></script>
</body>
</html>
```

## 4. Styles (static/style.css)
This CSS uses a soft green color palette without relying on external background images.

```css
:root {
    --primary: #5c8d89;
    --secondary: #74b49b;
    --bg-color: #f4f9f4;
    --text-color: #333;
    --white: #ffffff;
}

* { margin: 0; padding: 0; box-sizing: border-box; font-family: system-ui, -apple-system, sans-serif; }
body { background-color: var(--bg-color); color: var(--text-color); }

header {
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.5rem 5%; background-color: var(--white); box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}
.logo a { font-size: 1.5rem; font-weight: bold; color: var(--primary); text-decoration: none; }
nav ul { list-style: none; display: flex; gap: 2rem; }
nav a { text-decoration: none; color: var(--text-color); font-weight: 500; }
.cart-icon { font-weight: bold; cursor: pointer; transition: transform 0.2s; }

.hero {
    text-align: center; padding: 6rem 2rem; 
    background: linear-gradient(135deg, #e0ece0 0%, #c4dcd4 100%);
}
.hero h1 { font-size: 3rem; margin-bottom: 1rem; color: #2c3e50; }
.hero p { font-size: 1.2rem; margin-bottom: 2rem; color: #555; }

.btn {
    padding: 0.8rem 2rem; background-color: var(--primary); color: var(--white);
    text-decoration: none; border-radius: 5px; font-weight: bold; cursor: pointer; border: none;
}
.btn:hover { background-color: #4a7571; }

.container { padding: 4rem 5%; }
h2 { text-align: center; margin-bottom: 3rem; font-size: 2.2rem; color: var(--primary); }

.product-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; }
.product-card {
    background: var(--white); border-radius: 10px; padding: 1.5rem; text-align: center;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05); transition: transform 0.2s; cursor: pointer;
}
.product-card:hover { transform: translateY(-5px); }
.product-icon { font-size: 4rem; margin-bottom: 1rem; }
.product-title { font-size: 1.2rem; margin-bottom: 0.5rem; }
.product-desc { font-size: 0.9rem; color: #666; margin-bottom: 1rem; min-height: 40px;}
.product-price { font-size: 1.3rem; font-weight: bold; color: var(--primary); margin-bottom: 1rem; }

.add-to-cart { background: var(--secondary); color: var(--white); border: none; padding: 0.7rem 1rem; border-radius: 5px; width: 100%; font-size: 1rem; cursor: pointer; }
.add-to-cart:hover { background: var(--primary); }

/* Product Page Specific */
.breadcrumbs { margin-bottom: 2rem; font-size: 0.9rem; color: #666; }
.breadcrumbs a { color: var(--primary); text-decoration: none; }

.product-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start; }
@media (max-width: 768px) { .product-layout { grid-template-columns: 1fr; gap: 2rem; } }

.main-image {
    background: var(--white); border-radius: 12px; height: 400px;
    display: flex; align-items: center; justify-content: center; font-size: 10rem;
    box-shadow: 0 4px 15px rgba(0,0,0,0.05);
}

.product-title-large { font-size: 2.5rem; color: #2c3e50; margin-bottom: 1rem; }
.product-price-large { font-size: 2rem; font-weight: bold; color: var(--primary); margin-bottom: 1.5rem; }
.product-description { font-size: 1.1rem; line-height: 1.6; color: #555; margin-bottom: 2rem; }

.purchase-actions { display: flex; gap: 1rem; margin-bottom: 3rem; }
.quantity-selector { display: flex; align-items: center; border: 2px solid #ddd; border-radius: 5px; }
.qty-btn { background: var(--bg-color); border: none; padding: 0 1rem; font-size: 1.2rem; cursor: pointer; height: 100%; }
#qty-input { width: 60px; text-align: center; border: none; font-size: 1.1rem; outline: none; }
.add-to-cart-large { flex-grow: 1; font-size: 1.1rem; }

.product-specs { background: var(--white); padding: 2rem; border-radius: 10px; }
.product-specs h3 { margin-bottom: 1rem; border-bottom: 2px solid var(--bg-color); padding-bottom: 0.5rem; }
.product-specs ul { list-style-position: inside; color: #555; line-height: 1.8; }

.similar-products { margin-top: 5rem; padding-top: 3rem; border-top: 1px solid #ddd; }

footer { text-align: center; padding: 2rem; background-color: var(--white); margin-top: 2rem; }
```

## 5. Logic (static/script.js)

```javascript
let cartCount = parseInt(localStorage.getItem('cartCount')) || 0;

document.addEventListener('DOMContentLoaded', () => {
    document.getElementById('cart-count').innerText = cartCount;

    // Load Main Page Grid dynamically if we are on index.html
    const productList = document.getElementById('product-list');
    if (productList) {
        fetch('/api/products')
            .then(res => res.json())
            .then(products => {
                products.forEach(product => {
                    const card = document.createElement('div');
                    card.className = 'product-card';
                    card.onclick = () => window.location.href = `/product/${product.id}`;
                    
                    card.innerHTML = `
                        <div class="product-icon">${product.image}</div>
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-desc">${product.desc}</p>
                        <div class="product-price">$${product.price.toFixed(2)}</div>
                        <button class="add-to-cart" onclick="addToCart(1, event)">Add to Cart</button>
                    `;
                    productList.appendChild(card);
                });
            });
    }
});

function updateQty(change) {
    const qtyInput = document.getElementById('qty-input');
    let newVal = parseInt(qtyInput.value) + change;
    if (newVal >= 1) qtyInput.value = newVal;
}

function addToCart(amount = null, event = null) {
    if (event) event.stopPropagation(); // Prevents navigating to product page when clicking "Add to Cart" on a card
    if (!amount) amount = parseInt(document.getElementById('qty-input').value) || 1;

    cartCount += amount;
    localStorage.setItem('cartCount', cartCount);
    document.getElementById('cart-count').innerText = cartCount;
    
    const cartIcon = document.querySelector('.cart-icon');
    cartIcon.style.transform = 'scale(1.3)';
    setTimeout(() => cartIcon.style.transform = 'scale(1)', 150);
}
```

## Execution
Open terminal in the spa_offline folder.

Run pip install flask.

Run python app.py.

Open a browser to [http://127.0.0.1:5000](http://127.0.0.1:5000). You can freely disconnect from the internet and navigate the store, add items to the cart, and view the Similar Products lists.

