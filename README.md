
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
<title>Affiliate Shop Catalog</title>
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
  <h1 class="text-2xl font-bold text-gray-800 mt-3">Affiliate Shop Catalog</h1>
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

