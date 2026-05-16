# Petetson-Custom-Baitsfrom pathlib import Path
from zipfile import ZipFile
from PIL import Image
import shutil

base = Path('/mnt/data/peterson_custom_baits_site')
base.mkdir(exist_ok=True)

# Copy logo image
src = Path('/mnt/data/92233D79-0992-408F-82B0-A5D4023806CA.jpeg')
logo_dest = base / 'logo.jpeg'
shutil.copy(src, logo_dest)

html = f"""<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Peterson Custom Baits</title>
  <link rel="stylesheet" href="styles.css"/>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;700;900&display=swap" rel="stylesheet">
</head>
<body>
  <header class="hero">
    <nav class="navbar">
      <div class="brand">Peterson Custom Baits</div>
      <ul class="nav-links">
        <li><a href="#products">Shop</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#featured">Featured</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <button class="shop-btn">Shop Now</button>
    </nav>

    <div class="hero-content">
      <div class="hero-text">
        <h1>Premium Custom Soft Plastic Lures</h1>
        <p>
          Built for serious anglers. Hand-poured custom baits designed for bass and crappie fishing with pro-level performance.
        </p>
        <div class="hero-buttons">
          <a href="#products" class="primary-btn">Explore Baits</a>
          <a href="#about" class="secondary-btn">Our Story</a>
        </div>
      </div>

      <div class="hero-image">
        <img src="logo.jpeg" alt="Peterson Custom Baits Logo"/>
      </div>
    </div>
  </header>

  <section class="featured-strip">
    <div>🔥 Tournament Tested</div>
    <div>🎣 Hand-Poured Quality</div>
    <div>🚚 Fast Shipping</div>
    <div>⭐ Trusted by Anglers</div>
  </section>

  <section id="products" class="products-section">
    <div class="section-header">
      <h2>Best Sellers</h2>
      <p>Shop our most popular custom soft plastics.</p>
    </div>

    <div class="product-grid">
      <div class="product-card">
        <img src="logo.jpeg" alt="Senko Bait">
        <h3>Classic Senko</h3>
        <p>Ultra-soft stick bait with natural fall action.</p>
        <span>$8.99</span>
        <button>Add to Cart</button>
      </div>

      <div class="product-card">
        <img src="logo.jpeg" alt="Baby Shad">
        <h3>Baby Shad</h3>
        <p>Deadly finesse bait for crappie and bass.</p>
        <span>$7.49</span>
        <button>Add to Cart</button>
      </div>

      <div class="product-card">
        <img src="logo.jpeg" alt="Swimbait">
        <h3>Pro Swimbait</h3>
        <p>Realistic paddle tail action with premium detail.</p>
        <span>$9.99</span>
        <button>Add to Cart</button>
      </div>
    </div>
  </section>

  <section id="featured" class="banner">
    <div class="banner-content">
      <h2>Built For Big Catches</h2>
      <p>Custom crafted baits engineered to outperform standard plastics on the water.</p>
      <a href="#products">Start Shopping</a>
    </div>
  </section>

  <section id="about" class="about-section">
    <div class="about-text">
      <h2>About Peterson Custom Baits</h2>
      <p>
        Peterson Custom Baits was built from a passion for fishing and creating premium soft plastics that anglers can rely on.
        Every bait is designed with attention to detail, action, and durability so you can fish with confidence.
      </p>
    </div>
  </section>

  <section class="newsletter">
    <h2>Join The Fishing Crew</h2>
    <p>Get updates on new bait drops, custom colors, and exclusive deals.</p>
    <form>
      <input type="email" placeholder="Enter your email">
      <button type="submit">Subscribe</button>
    </form>
  </section>

  <footer id="contact">
    <div class="footer-brand">Peterson Custom Baits</div>
    <p>Custom soft plastic lures for bass and crappie anglers.</p>
    <div class="footer-links">
      <a href="#">Instagram</a>
      <a href="#">Facebook</a>
      <a href="#">TikTok</a>
    </div>
  </footer>
</body>
</html>
"""

css = """
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

body{
  font-family:'Montserrat',sans-serif;
  background:#0a0a0a;
  color:white;
  line-height:1.6;
}

.navbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:25px 8%;
  position:sticky;
  top:0;
  backdrop-filter:blur(10px);
}

.brand{
  font-size:1.5rem;
  font-weight:800;
  color:#c9d46d;
}

.nav-links{
  display:flex;
  gap:30px;
  list-style:none;
}

.nav-links a{
  text-decoration:none;
  color:white;
  transition:0.3s;
}

.nav-links a:hover{
  color:#c9d46d;
}

.shop-btn,
.primary-btn,
.secondary-btn,
.product-card button,
.newsletter button,
.banner-content a{
  border:none;
  padding:14px 24px;
  border-radius:999px;
  cursor:pointer;
  text-decoration:none;
  font-weight:700;
  transition:0.3s;
}

.shop-btn,
.primary-btn,
.product-card button,
.newsletter button,
.banner-content a{
  background:#c9d46d;
  color:black;
}

.secondary-btn{
  border:2px solid #c9d46d;
  color:#c9d46d;
}

.hero{
  min-height:100vh;
  background:linear-gradient(to bottom,#0a0a0a,#111);
}

.hero-content{
  display:grid;
  grid-template-columns:1fr 1fr;
  align-items:center;
  gap:40px;
  padding:60px 8%;
}

.hero-text h1{
  font-size:4rem;
  line-height:1.1;
  margin-bottom:20px;
}

.hero-text p{
  color:#cfcfcf;
  margin-bottom:30px;
  max-width:550px;
}

.hero-buttons{
  display:flex;
  gap:15px;
}

.hero-image img{
  width:100%;
  border-radius:20px;
  box-shadow:0 20px 60px rgba(0,0,0,0.5);
}

.featured-strip{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  text-align:center;
  padding:25px;
  background:#151515;
  font-weight:700;
}

.products-section,
.about-section,
.newsletter{
  padding:90px 8%;
}

.section-header{
  text-align:center;
  margin-bottom:50px;
}

.section-header h2,
.about-text h2,
.newsletter h2,
.banner-content h2{
  font-size:2.7rem;
  margin-bottom:15px;
}

.product-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:30px;
}

.product-card{
  background:#141414;
  border:1px solid #222;
  border-radius:22px;
  overflow:hidden;
  padding:20px;
  transition:0.3s;
}

.product-card:hover{
  transform:translateY(-8px);
}

.product-card img{
  width:100%;
  border-radius:15px;
  margin-bottom:15px;
}

.product-card h3{
  margin-bottom:10px;
}

.product-card p{
  color:#cfcfcf;
  margin-bottom:15px;
}

.product-card span{
  display:block;
  margin-bottom:15px;
  font-size:1.2rem;
  font-weight:700;
}

.banner{
  padding:100px 8%;
  text-align:center;
  background:linear-gradient(135deg,#1d1d1d,#0f0f0f);
}

.banner-content{
  max-width:700px;
  margin:auto;
}

.about-section{
  background:#111;
}

.about-text{
  max-width:800px;
  margin:auto;
  text-align:center;
}

.newsletter{
  text-align:center;
}

.newsletter form{
  margin-top:20px;
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
}

.newsletter input{
  padding:14px 18px;
  width:300px;
  border-radius:999px;
  border:none;
}

footer{
  text-align:center;
  padding:40px 8%;
  border-top:1px solid #222;
}

.footer-brand{
  font-size:1.4rem;
  font-weight:800;
  color:#c9d46d;
  margin-bottom:10px;
}

.footer-links{
  margin-top:15px;
  display:flex;
  justify-content:center;
  gap:20px;
}

.footer-links a{
  color:white;
  text-decoration:none;
}

@media(max-width:900px){
  .hero-content{
    grid-template-columns:1fr;
  }

  .hero-text h1{
    font-size:2.8rem;
  }

  .featured-strip{
    grid-template-columns:1fr 1fr;
    gap:15px;
  }

  .navbar{
    flex-direction:column;
    gap:20px;
  }
}
"""

(base / 'index.html').write_text(html)
(base / 'styles.css').write_text(css)

zip_path = '/mnt/data/peterson_custom_baits_website.zip'
with ZipFile(zip_path, 'w') as zipf:
    for file in base.rglob('*'):
        zipf.write(file, arcname=file.relative_to(base))

print(f"Website package created: {zip_path}")
