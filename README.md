# SmartDealZone
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Low&SmartZone – Best Low Price Deals</title>

<style>
body{margin:0;font-family:Arial;background:#f2f4f7}
.header{background:#0f172a;color:#fff;padding:16px;text-align:center;font-size:20px;font-weight:bold}
.sub{font-size:13px;color:#cbd5e1}
.search{margin:15px}
.search input{width:100%;padding:12px;border-radius:10px;border:1px solid #ccc}
.categories{display:flex;gap:10px;padding:0 15px}
.cat{flex:1;text-align:center;background:#e0e7ff;padding:10px;border-radius:10px;font-size:13px;font-weight:bold;cursor:pointer}
.cat.active{background:#2563eb;color:#fff}
.card{background:#fff;margin:15px;padding:15px;border-radius:12px;box-shadow:0 4px 10px rgba(0,0,0,0.08)}
.card h3{margin:0 0 8px 0;font-size:16px}
.price{color:#16a34a;font-weight:bold}
.btn{display:block;text-align:center;background:#2563eb;color:#fff;padding:12px;border-radius:8px;text-decoration:none;margin-top:10px}
.social{display:flex;gap:10px;padding:15px}
.social a{flex:1;text-align:center;padding:12px;border-radius:8px;color:#fff;text-decoration:none;font-weight:bold}
.telegram{background:#229ED9}
.instagram{background:#E1306C}
.footer{text-align:center;font-size:12px;color:#64748b;padding:20px}
</style>
</head>

<body>

<div class="header">
  Low&SmartZone
  <div class="sub">Best Low Price Deals Online</div>
</div>

<div class="search">
  <input type="text" id="searchInput" placeholder="Search low price deals..." onkeyup="searchItems()">
</div>

<div class="categories">
  <div class="cat active" onclick="filterCategory('all',this)">All</div>
  <div class="cat" onclick="filterCategory('electronics',this)">Electronics</div>
  <div class="cat" onclick="filterCategory('fashion',this)">Fashion</div>
  <div class="cat" onclick="filterCategory('home',this)">Home</div>
</div>

<!-- PRODUCTS -->
<div class="card" data-category="electronics">
  <h3>Wireless Earbuds</h3>
  <p class="price">Under ₹499</p>
  <a class="btn" href="#">Buy Now</a>
</div>

<div class="card" data-category="fashion">
  <h3>Men Solid T-Shirt</h3>
  <p class="price">Flat 60% OFF</p>
  <a class="btn" href="#">Buy Now</a>
</div>

<div class="card" data-category="electronics">
  <h3>Power Bank 10000mAh</h3>
  <p class="price">Lowest Price Today</p>
  <a class="btn" href="#">Buy Now</a>
</div>

<div class="card" data-category="fashion">
  <h3>Women Cotton Kurti</h3>
  <p class="price">Starting ₹399</p>
  <a class="btn" href="#">Buy Now</a>
</div>

<div class="card" data-category="home">
  <h3>LED Bulb</h3>
  <p class="price">Pack of 2 – Best Price</p>
  <a class="btn" href="#">Buy Now</a>
</div>

<div class="social">
  <a class="telegram" href="#">Join Telegram</a>
  <a class="instagram" href="#">Follow Instagram</a>
</div>

<div class="footer">
  © 2026 Low&SmartZone  
  <br>Affiliate Disclosure: We may earn commission from purchases.
</div>

<script>
function searchItems(){
  let input=document.getElementById("searchInput").value.toLowerCase();
  let cards=document.getElementsByClassName("card");
  for(let i=0;i<cards.length;i++){
    let text=cards[i].innerText.toLowerCase();
    cards[i].style.display = text.includes(input) ? "block" : "none";
  }
}

function filterCategory(category,el){
  let cards=document.getElementsByClassName("card");
  let cats=document.getElementsByClassName("cat");
  for(let c of cats){c.classList.remove("active")}
  el.classList.add("active");

  for(let i=0;i<cards.length;i++){
    if(category==="all" || cards[i].dataset.category===category){
      cards[i].style.display="block";
    }else{
      cards[i].style.display="none";
    }
  }
}
</script>

</body>
</html>
