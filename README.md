
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --primary-gradient: linear-gradient(135deg, #1e293b 0%, #334155 100%);
            --accent-blue: #38bdf8;
            --accent-green: #10b981;
            --text-light: #f8fafc;
        }

        .hero-banner {
            font-family: 'Inter', -apple-system, sans-serif;
            background: var(--primary-gradient);
            color: var(--text-light);
            padding: 60px 20px;
            border-radius: 16px;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            margin: 20px auto;
            max-width: 1000px;
        }

        /* Animated Background Element */
        .hero-banner::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(56, 189, 248, 0.1) 0%, transparent 60%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero-tagline {
            background: rgba(56, 189, 248, 0.15);
            color: var(--accent-blue);
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 20px;
            border: 1px solid rgba(56, 189, 248, 0.3);
        }

        .hero-title {
            font-size: 2.5rem;
            font-weight: 800;
            margin: 0 0 15px 0;
            letter-spacing: -0.02em;
        }

        .hero-subtitle {
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto 30px auto;
            color: #cbd5e1;
            line-height: 1.6;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 35px;
        }

        .service-pill {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 12px;
            border-radius: 12px;
            backdrop-filter: blur(5px);
            font-size: 0.85rem;
            transition: 0.3s;
        }

        .service-pill:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: var(--accent-blue);
            transform: translateY(-3px);
        }

        .cta-button {
            background: var(--accent-blue);
            color: #0f172a;
            padding: 14px 32px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 700;
            display: inline-block;
            transition: 0.3s;
        }

        .cta-button:hover {
            background: #7dd3fc;
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
        }

        @media (max-width: 600px) {
            .hero-title { font-size: 1.8rem; }
            .hero-subtitle { font-size: 1rem; }
        }
    </style>
</head>
<body>

<section class="hero-banner">
    <div class="hero-content">
        <span class="hero-tagline">AI & DIGITAL CREATOR HUB</span>
        <h1 class="hero-title">Empowering the Next Generation of Digital Entrepreneurs</h1>
        <p class="hero-subtitle">
            Access Insights on technology, AI, and productivity. Build and manage your custom chatbots, websites, and mobile apps to help you scale your online presence.
        </p>

        <div class="services-grid">
            <div class="service-pill">🤖 Chatbot Dev</div>
            <div class="service-pill">🌐 Web Design</div>
            <div class="service-pill">📱 App Building</div>
            <div class="service-pill">📈 AI Strategy</div>
        </div>

        <a href="#contact" class="cta-button">Start Building Your Assets</a>
        
        <p style="margin-top: 25px; font-size: 0.8rem; color: #94a3b8; font-style: italic;">
            "Mastering the art of Digital design involves the iteration and innovation of templates for multiple audiences."
        </p>
    </div>
</section>

</body>
</html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Floating Sales Banner</title>
<style>
    /* 1. The Container */
    #float-banner {
        position: fixed;
        bottom: 20px;
        right: 20px;
        width: 320px;
        background-color: #ffffff; /* White background */
        box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        border-radius: 12px;
        border-left: 5px solid #ff4757; /* Accent color */
        padding: 15px;
        z-index: 9999;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        cursor: pointer;
        opacity: 0; /* Start hidden for fade-in effect */
        transform: translateY(20px);
        transition: all 0.5s ease;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    /* 2. Visible State (added by JS) */
    #float-banner.visible {
        opacity: 1;
        transform: translateY(0);
    }

    /* 3. The Content Area */
    .banner-content {
        flex-grow: 1;
        overflow: hidden;
        height: 24px; /* Fixed height for text slider */
        position: relative;
    }

    .slide-text {
        display: none; /* Hide all by default */
        font-size: 16px;
        font-weight: 600;
        color: #333;
        animation: fadeUp 0.5s ease-in-out;
    }

    .slide-text.active {
        display: block; /* Show active one */
    }

    .slide-sub {
        font-size: 12px;
        color: #666;
        font-weight: normal;
        margin-left: 5px;
    }

    /* 4. The Close Button */
    .close-btn {
        background: none;
        border: none;
        color: #999;
        font-size: 18px;
        cursor: pointer;
        padding: 0 0 0 10px;
        line-height: 1;
    }
    .close-btn:hover {
        color: #333;
    }

    /* 5. CTA Arrow */
    .cta-arrow {
        color: #ff4757;
        font-weight: bold;
        margin-right: 10px;
    }

    /* Animation Keyframes */
    @keyframes fadeUp {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    /* Mobile Tweaks */
    @media (max-width: 480px) {
        #float-banner {
            width: 90%; /* Fit screen width */
            right: 5%;
            left: 5%;
            bottom: 15px;
        }
    }
</style>
</head>
<body>

<div id="float-banner" onclick="redirectToSales()">
    <div class="banner-content">
        <div class="slide-text active">
            🔥 Limited Time Offer <span class="slide-sub">50% Off</span>
        </div>
        <div class="slide-text">
            🚀 New Arrivals <span class="slide-sub">Check them out</span>
        </div>
        <div class="slide-text">
            💎 Best Sellers <span class="slide-sub">Restocked Now</span>
        </div>
    </div>
    
    <span class="cta-arrow">→</span>
    
    <button class="close-btn" onclick="closeBanner(event)">×</button>
</div>

<script>
    const banner = document.getElementById('float-banner');
    const slides = document.querySelectorAll('.slide-text');
    let currentSlide = 0;
    const slideInterval = 3000; // Change text every 3 seconds

    // 1. Show banner after 1 second (Intro animation)
    setTimeout(() => {
        banner.classList.add('visible');
    }, 1000);

    // 2. Auto-Slide Function
    function cycleSlides() {
        // Remove active class from current
        slides[currentSlide].classList.remove('active');
        
        // Move to next slide (loop back to 0 if at end)
        currentSlide = (currentSlide + 1) % slides.length;
        
        // Add active class to new slide
        slides[currentSlide].classList.add('active');
    }

    // Start the auto-slide loop
    setInterval(cycleSlides, slideInterval);

    // 3. Redirect Function
    function redirectToSales() {
        window.location.href = "https://debeatzgh1.github.io/MB--online-/";
    }

    // 4. Close Function
    function closeBanner(event) {
        // Stop the click from bubbling up to the main banner (prevent redirect)
        event.stopPropagation();
        banner.style.display = 'none';
    }
</script>

</body>
</html>




<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Social Creator AI Product Hub</title>
<script src="https://cdn.tailwindcss.com"></script>

<style>
.badge{font-size:11px;padding:3px 10px;border-radius:999px;font-weight:600}
.card:hover{transform:translateY(-4px)}
</style>
</head>

<body class="bg-slate-100">

<!-- HEADER -->
<header class="bg-gradient-to-r from-indigo-600 to-blue-600 text-white p-6 text-center">
  <h1 class="text-3xl font-bold">Social Creator AI Hub</h1>
  <p class="text-sm mt-2 opacity-90">
    Discover creator tools, AI products & digital deals — curated for you
  </p>
</header>

<!-- CATEGORY TABS -->
<div class="flex flex-wrap justify-center gap-3 bg-white p-4 shadow sticky top-0 z-10">
  <button onclick="setInterest('tech')" class="px-4 py-2 bg-indigo-600 text-white rounded-xl">Creator Tech</button>
  <button onclick="setInterest('ai')" class="px-4 py-2 bg-indigo-100 rounded-xl">AI Tools</button>
  <button onclick="setInterest('digital')" class="px-4 py-2 bg-indigo-100 rounded-xl">Digital Products</button>
  <button onclick="setInterest('deals')" class="px-4 py-2 bg-indigo-100 rounded-xl">Hot Deals</button>
  <button onclick="setInterest('shop')" class="px-4 py-2 bg-indigo-100 rounded-xl">Affiliate Shop</button>
</div>

<!-- AI RECOMMENDER -->
<section class="p-6">
  <h2 class="text-xl font-bold mb-4">🤖 Recommended for You</h2>
  <div id="recommendations" class="grid md:grid-cols-3 gap-6"></div>
</section>

<!-- ALL PRODUCTS -->
<section class="p-6">
  <h2 class="text-xl font-bold mb-4">🛍 Explore Products</h2>
  <div id="products" class="grid md:grid-cols-3 gap-6"></div>
</section>

<!-- MOBILE NAV -->
<nav class="fixed bottom-0 inset-x-0 bg-white border-t flex justify-around p-2 md:hidden">
  <button onclick="setInterest('tech')">Tech</button>
  <button onclick="setInterest('ai')">AI</button>
  <button onclick="setInterest('digital')">Digital</button>
  <button onclick="setInterest('deals')">Deals</button>
</nav>

<script>
/* ================= PRODUCTS DATABASE ================= */
const PRODUCTS = [
  {
    title:"Creator Tech Store",
    desc:"Trending gadgets & creator tools",
    url:"https://www.socialcreator.com/techshop/?s=314037",
    tags:["tech","creator","tools"],
    badges:["Trending"]
  },
  {
    title:"AI Creator Tools",
    desc:"Automation & AI productivity tools",
    url:"https://www.socialcreator.com/techshop/?s=314038",
    tags:["ai","automation","creator"],
    badges:["AI","Hot"]
  },
  {
    title:"Digital Products Hub",
    desc:"Courses, templates & downloads",
    url:"https://www.socialcreator.com/techshop/?s=314036",
    tags:["digital","courses"],
    badges:["New"]
  },
  {
    title:"Hot Tech Deals",
    desc:"Discounted creator tools & bundles",
    url:"https://www.socialcreator.com/techshop/?s=314326",
    tags:["deals","tech"],
    badges:["Hot Deal"]
  },
  {
    title:"Affiliate Shop",
    desc:"Curated online digital products",
    url:"https://debeatzgh1.github.io/-My-Brand-Online-Digital-Products-Affiliate-Shop/",
    tags:["shop","affiliate","digital"],
    badges:["Featured"]
  }
];

/* ================= AI RECOMMENDER ================= */
let userInterest = "tech";

function setInterest(tag){
  userInterest = tag;
  render();
}

/* ================= RENDER ================= */
function render(){
  const rec = PRODUCTS.filter(p=>p.tags.includes(userInterest)).slice(0,3);
  renderCards("recommendations", rec, true);
  renderCards("products", PRODUCTS, false);
}

function renderCards(id, list, recommended){
  const el = document.getElementById(id);
  el.innerHTML = "";

  list.forEach(p=>{
    el.innerHTML += `
      <div class="card bg-white rounded-2xl shadow p-5 transition">
        <h3 class="font-bold text-lg">${p.title}</h3>
        <p class="text-sm text-gray-600 mt-1">${p.desc}</p>

        <div class="flex flex-wrap gap-2 mt-3">
          ${p.badges.map(b=>`<span class="badge bg-indigo-100 text-indigo-700">${b}</span>`).join("")}
          ${recommended ? `<span class="badge bg-green-100 text-green-700">Recommended</span>` : ""}
        </div>

        <button onclick="openNewTab('${p.url}')" 
          class="mt-4 w-full bg-indigo-600 text-white py-2 rounded-xl font-semibold">
          Open in New Tab
        </button>
      </div>
    `;
  });
}

function openNewTab(url){
  window.open(url, "_blank", "noopener,noreferrer");
}

/* INIT */
render();
</script>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Shop Catalog</title>
<script src="https://cdn.tailwindcss.com"></script>

<style>
/* ===== CAROUSEL ===== */
.carousel{
  display:flex;
  overflow-x:auto;
  scroll-snap-type:x mandatory;
  gap:14px;
  padding-bottom:12px;
  scroll-behavior:smooth;
}
.carousel::-webkit-scrollbar{display:none}

/* smaller cards */
.carousel-item{
  scroll-snap-align:start;
  flex:0 0 260px;
  background:#fff;
  border-radius:14px;
  box-shadow:0 4px 10px rgba(0,0,0,.1);
  transition:.25s ease;
}
.carousel-item:hover{
  transform:translateY(-4px);
}

/* small iframe preview */
.carousel-item iframe{
  height:150px;
}

/* pause indicator */
.carousel:hover{cursor:grab}
</style>
</head>

<body class="bg-gray-50 font-sans">

<!-- BRANDING -->
<div class="text-center py-6">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg"
       class="mx-auto w-28 h-28 rounded-full shadow-lg"/>
  <h1 class="text-2xl font-bold text-gray-800 mt-3"> Shop Catalog</h1>
  <p class="text-gray-500 text-sm">
    Premium tools, deals & digital products for creators
  </p>
</div>

<!-- CAROUSEL -->
<div id="carousel" class="carousel px-4">

  <!-- ITEM -->
  <div class="carousel-item p-3">
    <iframe src="https://stylesiai.partnerlinks.io/6da1bisqh1o8" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://stylesiai.partnerlinks.io/6da1bisqh1o8"
       class="block mt-3 text-center py-2 bg-indigo-600 text-white rounded-lg text-sm font-semibold">
      👗 AI Fashion Business
    </a>
  </div>

  <div class="carousel-item p-3">
    <iframe src="https://hosterbox.com/billing/aff.php?aff=597" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://hosterbox.com/billing/aff.php?aff=597"
       class="block mt-3 text-center py-2 bg-green-600 text-white rounded-lg text-sm font-semibold">
      🌐 Web Hosting Deals
    </a>
  </div>

  <div class="carousel-item p-3">
    <iframe src="https://appsgeyser.com/r/rnDgz" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://appsgeyser.com/r/rnDgz"
       class="block mt-3 text-center py-2 bg-pink-600 text-white rounded-lg text-sm font-semibold">
      📱 Website → App
    </a>
  </div>

  <div class="carousel-item p-3">
    <iframe src="https://adkps.me/start/?ref=111481" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://adkps.me/start/?ref=111481"
       class="block mt-3 text-center py-2 bg-yellow-600 text-white rounded-lg text-sm font-semibold">
      💵 Earn Tasks
    </a>
  </div>

  <div class="carousel-item p-3">
    <iframe src="https://www.beehiiv.com?via=D-Konsult" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://www.beehiiv.com?via=D-Konsult"
       class="block mt-3 text-center py-2 bg-blue-600 text-white rounded-lg text-sm font-semibold">
      📩 Newsletter Business
    </a>
  </div>

  <div class="carousel-item p-3">
    <iframe src="https://www.alibaba.com/x/AxMUVL?ck=activity" class="w-full rounded-lg"></iframe>
    <a target="_blank" href="https://www.alibaba.com/x/AxMUVL?ck=activity"
       class="block mt-3 text-center py-2 bg-orange-600 text-white rounded-lg text-sm font-semibold">
      🛒 Alibaba Bonus
    </a>
  </div>

</div>

<!-- AUTO SLIDE SCRIPT -->
<script>
const carousel = document.getElementById("carousel");
let autoScroll;
let scrollAmount = 0;

function startAutoSlide(){
  autoScroll = setInterval(()=>{
    carousel.scrollLeft += 1;
    if(carousel.scrollLeft + carousel.clientWidth >= carousel.scrollWidth){
      carousel.scrollLeft = 0;
    }
  },20);
}

function stopAutoSlide(){
  clearInterval(autoScroll);
}

carousel.addEventListener("mouseenter", stopAutoSlide);
carousel.addEventListener("mouseleave", startAutoSlide);

/* start */
startAutoSlide();
</script>

</body>
</html>

