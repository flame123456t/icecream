<html lang="th">    
<head>    
  <meta charset="UTF-8" />    
  <title>สูตรไอศกรีม</title>    
  <style>  
  .menu-toggle {  
  position: fixed;  
  top: 20px;  
  left: 20px;  
  z-index: 10001;  
  background-color: #28a745;  
  color: white;  
  padding: 10px 16px;  
  border: none;  
  border-radius: 8px;  
  cursor: pointer;  
}  .side-menu {
position: fixed;
top: 0;
left: -260px; /* ซ่อนอยู่ */
width: 240px;
height: 100%;
background-color: #333;
color: white;
padding: 20px;
box-shadow: 2px 0 12px rgba(0,0,0,0.3);
transition: left 0.3s ease;
z-index: 10000;
display: flex;
flex-direction: column;
}

.side-menu button {
background-color: #444;
color: white;
padding: 10px;
margin-bottom: 10px;
border: none;
border-radius: 6px;
cursor: pointer;
text-align: left;
}

.side-menu button:hover {
background-color: #555;
}

.close-btn {
align-self: flex-end;
background-color: transparent;
color: white;
font-size: 20px;
margin-bottom: 20px;
}
.menu-toggle {
position: fixed;
top: 20px;
left: 20px;
z-index: 10001;
background-color: #28a745;
color: white;
padding: 10px 16px;
border: none;
border-radius: 8px;
cursor: pointer;
}

.side-menu {
position: fixed;
top: 0;
left: -260px; /* ซ่อน */
width: 240px;
height: 100%;
background-color: #333;
color: white;
padding: 20px;
box-shadow: 2px 0 12px rgba(0,0,0,0.3);
transition: left 0.3s ease;
z-index: 10000;
display: flex;
flex-direction: column;
}

.side-menu button {
background-color: #444;
color: white;
padding: 10px;
margin-bottom: 10px;
border: none;
border-radius: 6px;
cursor: pointer;
text-align: left;
}

.side-menu button:hover {
background-color: #555;
}

.close-btn {
align-self: flex-end;
background-color: transparent;
color: white;
font-size: 20px;
margin-bottom: 20px;
}
.dark-mode {
background-color: #121212;
color: white;
}

.dark-mode .ice-cream-card {
background-color: #1e1e1e;
color: white;
border-color: #555;
}

.dark-mode .popup {
background-color: #2c2c2c;
color: white;
}

#darkModeToggle {
position: fixed;
top: 20px;
right: 20px;
background-color: #444;
color: white;
padding: 6px 12px;
border: none;
border-radius: 6px;
cursor: pointer;
z-index: 10001;
}

#darkModeToggle:hover {
background-color: #222;
}
body {
font-family: sans-serif;
text-align: center;
padding: 20px;  /* รูปพื้นหลัง */
background-image: url('https://s.isanook.com/he/0/ud/6/30093/sherbet.jpg?ip/crop/w1200h700/q80/jpg');
background-size: cover;
background-position: center;
background-repeat: no-repeat;
background-attachment: fixed;
color: #333;
position: relative;
z-index: 0;
min-height: 100vh;
}

/* ชั้นโปร่งใสครอบพื้นหลัง /
body::before {
content: "";
position: fixed;
top: 0; left: 0;
width: 100%;
height: 100%;
background-color: rgba(255,255,255,0.5); / ปรับความโปร่งใสได้ */
z-index: -1;
}

.grid-container {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 20px;
max-width: 800px;
margin: auto;
}

.ice-cream-card {
border: 1px solid #ccc;
border-radius: 10px;
padding: 10px;
box-shadow: 0 2px 6px rgba(0,0,0,0.1);
transition: transform 0.2s;
cursor: pointer;
background-color: white;
}

.ice-cream-card:hover {
transform: scale(1.03);
}

.ice-cream-img {
width: 100%;
height: 150px;
object-fit: cover;
border-radius: 8px;
}

.ice-cream-name {
margin-top: 10px;
font-weight: bold;
}

.popup {
display: none;
position: fixed;
top: 20%;
left: 50%;
transform: translate(-50%, -20%);
background-color: #fff;
padding: 20px;
border: 2px solid #aaa;
box-shadow: 0 4px 12px rgba(0,0,0,0.3);
z-index: 9999;
width: 320px;
text-align: left;
}

.popup button {
margin-top: 15px;
display: block;
margin-left: auto;
padding: 8px 12px;
cursor: pointer;
border: none;
border-radius: 5px;
background-color: #007bff;
color: white;
font-size: 14px;
transition: background-color 0.3s;
}

.popup button:hover {
background-color: #0056b3;
}

#watchVideoBtn {
margin-bottom: 10px;
}

@media (max-width: 600px) {
.grid-container {
grid-template-columns: 1fr;
}
}
#toggleFormBtn {
box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}
#addRecipeForm {
position: fixed;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
z-index: 10001; /* มากกว่า btn /
background: white;
padding: 20px;
border-radius: 10px;
box-shadow: 0 4px 12px rgba(0,0,0,0.3);
display: none; / เริ่มต้นซ่อน */
}
.dark-mode {
background-color: #121212;
color: #eee;
}

.dark-mode .ice-cream-card {
background-color: #222;
border-color: #555;
color: #eee;
}

.dark-mode #addRecipeForm {
background-color: #333;
color: #eee;
}

.dark-mode input, .dark-mode button {
background-color: #555;
color: #eee;
border: 1px solid #666;
}
</style>

</head>    
<body>  
    <!-- ปุ่มเปิดเมนู -->  
<button id="menuToggle" class="menu-toggle">☰ เมนู</button>  <div id="sideMenu" class="side-menu">  
  <button id="closeMenu" class="close-btn">✖</button>  
  <button id="toggleFormBtn">➕ เพิ่มสูตรไอศกรีม</button>  
  <button id="darkModeToggle">🌙 โหมดกลางคืน</button>  
  <button id="viewSavedBtn">⭐ ดูสูตรที่บันทึกไว้</button>  
  <button id="viewAllBtn">📋 แสดงสูตรทั้งหมด</button>  
</div>    <h2>🍨 คลิกที่ไอศกรีมเพื่อดูสูตร  
<input type="text" id="searchBox" placeholder="ค้นหาชื่อไอศกรีม..." oninput="filterIceCream()" style="padding: 8px; width: 300px; margin-bottom: 20px; border-radius: 8px;">  
!</h2>   
    <form id="addRecipeForm" style="margin-bottom: 30px; display: none;">  
  <input type="text" id="customName" placeholder="ชื่อไอศกรีม" required style="padding:8px; border-radius:8px; width:200px;">  
  <input type="text" id="customImage" placeholder="URL รูปภาพ" required style="padding:8px; border-radius:8px; width:250px;">  
  <input type="text" id="customIngredients" placeholder="ส่วนผสม (คั่นด้วย , เช่น นมสด, วานิลลา)" required style="padding:8px; border-radius:8px; width:300px;"><br><br>  
  <input type="text" id="customVideo" placeholder="ลิงก์วิดีโอ YouTube (ถ้ามี)" style="padding:8px; border-radius:8px; width:300px;">  
  <button type="submit" style="padding:8px 16px; border-radius:8px; background-color:#28a745; color:white; border:none; cursor:pointer;">เพิ่มสูตร</button>  
</form>  
<div class="grid-container">    
  <div class="ice-cream-card" onclick="showRecipe('vanilla')">    
    <img src="https://i.ytimg.com/vi/1vCnGjZzTsU/maxresdefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสวานิลลา">    
    <div class="ice-cream-name">วานิลลา</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('chocolate')">    
    <img src="https://i.ytimg.com/vi/9L0L20wqeks/sddefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสช็อกโกแลต">    
    <div class="ice-cream-name">ช็อกโกแลต</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('strawberry')">    
    <img src="https://i.ytimg.com/vi/9F6Hpy8EfLI/sddefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสสตรอว์เบอร์รี">    
    <div class="ice-cream-name">สตรอว์เบอร์รี</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('thaiTea')">    
    <img src="https://i.ytimg.com/vi/Q3B6nuYyTLs/maxresdefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสชาเย็น">    
    <div class="ice-cream-name">ชาเย็น</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('coconutMilk')">    
    <img src="https://i.ytimg.com/vi/SiglJGQ1mmM/sddefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสกะทิ">    
    <div class="ice-cream-name">กะทิ</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('youngCoconut')">    
    <img src="https://i.ytimg.com/vi/3FCev3kSQ04/sddefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสมะพร้าวอ่อน">    
    <div class="ice-cream-name">มะพร้าวอ่อน</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('lime')">    
    <img src="https://i.ytimg.com/vi/THyXzHDo_MU/maxresdefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสมะนาว">    
    <div class="ice-cream-name">มะนาว</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('greenTea')">    
    <img src="https://i.ytimg.com/vi/aP3QWOBE1mk/maxresdefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสชาเขียว">    
    <div class="ice-cream-name">ชาเขียว</div>    
  </div>    
  <div class="ice-cream-card" onclick="showRecipe('milk')">    
    <img src="https://i.ytimg.com/vi/HQZdrjtW4zU/maxresdefault.jpg" class="ice-cream-img" alt="ไอศกรีมรสนมสด">    
    <div class="ice-cream-name">นมสด</div>    
  </div>    
</div>  <div id="recipePopup" class="popup">    
  <h3 id="recipeTitle"></h3>    
  <ul id="recipeList"></ul>    
  <p id="recipeNote"></p>    
  <button id="watchVideoBtn" style="display:none;" onclick="openVideo()">ดูคลิปสอนทำ</button>    
<button id="saveRecipeBtn" onclick="toggleSaveRecipe()">บันทึกสูตร</button>    
<button onclick="hidePopup()">ปิด</button>  
</div>  
<script>  
  const recipes = {    
    vanilla: {    
      title: "สูตรไอศกรีมวานิลลา",    
      ingredients: ["นมสด 300 มล", " ครีม 250 มิลลิลิตร", "ช็อคโกแลตคูเวอร์เจอร์ 3 ออนซ์", "โกโก้ 1/3 ถ้วยตวง ", " ไข่ไก่ 1 ฟอง ",],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=1vCnGjZzTsU"    
    },    
    chocolate: {    
      title: "สูตรไอศกรีมช็อกโกแลต",    
      ingredients: [" นม 500 มิลลิลิตร", "โกโก้ 1/2 ถ้วย", "วิปครีม 1 ถ้วย", "น้ำตาล 3/4 ถ้วย", "ไข่แดง 4 ฟอง"],    
      note: "กดเพื่อดูวิธีทำนปั่น",    
      video: "https://www.youtube.com/watch?v=9L0L20wqeks"    
    },    
    strawberry: {    
      title: "สูตรไอศกรีมสตรอว์เบอร์รี",    
      ingredients: ["สตรอว์เบอร์รีสด 1 ถ้วย", "น้ำตาล 1/2 ถ้วย", "นมสด 1 ถ้วย", "วิปครีม 1 ถ้วย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=9F6Hpy8EfLI"    
    },    
    thaiTea: {    
      title: "สูตรไอศกรีมชาเย็น",    
      ingredients: ["ชาไทย 2 ช้อนโต๊ะ", "นมข้นหวาน 1/2 ถ้วย", "นมสด 1 ถ้วย", "วิปครีม 1 ถ้วย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=Q3B6nuYyTLs"    
    },    
    coconutMilk: {    
      title: "สูตรไอศกรีมกะทิ",    
      ingredients: ["กะทิ 2 ถ้วย", "น้ำตาลทราย 1 ถ้วย", "เกลือเล็กน้อย", "แป้งข้าวเจ้า 1 ช้อนโต๊ะ"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=SiglJGQ1mmM"    
    },    
    youngCoconut: {    
      title: "สูตรไอศกรีมมะพร้าวอ่อน",    
      ingredients: ["น้ำมะพร้าว 1 ถ้วย", "เนื้อมะพร้าวอ่อน 1 ถ้วย", "น้ำตาล 1/2 ถ้วย", "กะทิ 1 ถ้วย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=3FCev3kSQ04"    
    },    
    lime: {    
      title: "สูตรไอศกรีมมะนาว",    
      ingredients: ["น้ำมะนาว 1/2 ถ้วย", "นมข้นหวาน 1/2 ถ้วย", "วิปครีม 1 ถ้วย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=THyXzHDo_MU"    
    },    
    greenTea: {    
      title: "สูตรไอศกรีมชาเขียว",    
      ingredients: ["ผงมัทฉะ 2 ช้อนชา", "นมสด 2 ถ้วย", "วิปครีม 1 ถ้วย", "น้ำตาล 3/4 ถ้วย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=aP3QWOBE1mk"    
    },    
    milk: {    
      title: "สูตรไอศกรีมนมสด",    
      ingredients: ["นมสด 3 ถ้วย", "น้ำตาล 1 ถ้วย", "ไข่แดง 3 ฟอง", "วานิลลาเล็กน้อย"],    
      note: "กดเพื่อดูวิธีทำ",    
      video: "https://www.youtube.com/watch?v=HQZdrjtW4zU"    
    }    
  };    
  let currentVideoUrl = "";  
  let currentRecipeType = "";  function showRecipe(type) {
const recipe = recipes[type];
if (!recipe) return;

document.getElementById("recipeTitle").innerText = recipe.title;  
const listEl = document.getElementById("recipeList");  
listEl.innerHTML = "";  
recipe.ingredients.forEach(item => {  
  const li = document.createElement("li");  
  li.textContent = item;  
  listEl.appendChild(li);  
});  

document.getElementById("recipeNote").innerText = recipe.note;  
const videoBtn = document.getElementById("watchVideoBtn");  

if (recipe.video) {  
  currentVideoUrl = recipe.video;  
  videoBtn.style.display = "inline-block";  
} else {  
  currentVideoUrl = "";  
  videoBtn.style.display = "none";  
}  

currentRecipeType = type;  
updateSaveBtn();  

document.getElementById("saveRecipeBtn").style.display = "inline-block";  
document.getElementById("recipePopup").style.display = "block";

}

function hidePopup() {
document.getElementById("recipePopup").style.display = "none";
}

function openVideo() {
if (currentVideoUrl) window.open(currentVideoUrl, "_blank");
}

function getSavedRecipes() {
return JSON.parse(localStorage.getItem("savedRecipes") || "[]");
}

function isRecipeSaved(type) {
return getSavedRecipes().includes(type);
}

function toggleSaveRecipe() {
const saved = getSavedRecipes();
const index = saved.indexOf(currentRecipeType);

if (index === -1) {  
  saved.push(currentRecipeType);  
} else {  
  saved.splice(index, 1);  
}  

localStorage.setItem("savedRecipes", JSON.stringify(saved));  
updateSaveBtn();

}

function updateSaveBtn() {
const btn = document.getElementById("saveRecipeBtn");
if (isRecipeSaved(currentRecipeType)) {
btn.innerText = "ลบสูตรจากรายการโปรด";
} else {
btn.innerText = "บันทึกสูตร";
}
}

function filterIceCream() {
const keyword = document.getElementById("searchBox").value.toLowerCase();
const cards = document.querySelectorAll(".ice-cream-card");

cards.forEach(card => {  
  const name = card.querySelector(".ice-cream-name").innerText.toLowerCase();  
  card.style.display = name.includes(keyword) ? "block" : "none";  
});

}

function getUserRecipes() {
return JSON.parse(localStorage.getItem("userRecipes") || "[]");
}

function saveUserRecipes(recipes) {
localStorage.setItem("userRecipes", JSON.stringify(recipes));
}

function renderUserRecipes() {
const container = document.querySelector(".grid-container");
const userRecipes = getUserRecipes();

userRecipes.forEach(recipe => {  
  const card = document.createElement("div");  
  card.className = "ice-cream-card";  
  card.onclick = () => showUserRecipe(recipe);  

  card.innerHTML = `  
    <img src="${recipe.image}" class="ice-cream-img" alt="${recipe.name}">  
    <div class="ice-cream-name">${recipe.name}</div>  
  `;  

  container.appendChild(card);  
});

}

function showUserRecipe(recipe) {
document.getElementById("recipeTitle").innerText = "สูตรไอศกรีม: " + recipe.name;
const listEl = document.getElementById("recipeList");
listEl.innerHTML = "";
recipe.ingredients.forEach(item => {
const li = document.createElement("li");
li.textContent = item;
listEl.appendChild(li);
});

document.getElementById("recipeNote").innerText = "สูตรนี้สร้างโดยคุณ";  
const videoBtn = document.getElementById("watchVideoBtn");  

if (recipe.video) {  
  currentVideoUrl = recipe.video;  
  videoBtn.style.display = "inline-block";  
} else {  
  currentVideoUrl = "";  
  videoBtn.style.display = "none";  
}  

currentRecipeType = null;  
document.getElementById("saveRecipeBtn").style.display = "none";  
document.getElementById("recipePopup").style.display = "block";

}

function setDarkMode(enabled) {
if (enabled) {
document.body.classList.add("dark-mode");
document.getElementById("darkModeToggle").innerText = "☀️ โหมดกลางวัน";
localStorage.setItem("darkMode", "true");
} else {
document.body.classList.remove("dark-mode");
document.getElementById("darkModeToggle").innerText = "🌙 โหมดกลางคืน";
localStorage.setItem("darkMode", "false");
}
}

document.addEventListener("DOMContentLoaded", () => {
renderUserRecipes();

const savedMode = localStorage.getItem("darkMode") === "true";  
setDarkMode(savedMode);  

const toggleFormBtn = document.getElementById("toggleFormBtn");  
const darkModeToggle = document.getElementById("darkModeToggle");  
const form = document.getElementById("addRecipeForm");  

toggleFormBtn.addEventListener("click", () => {  
  if (form.style.display === "block") {  
    form.style.display = "none";  
    toggleFormBtn.innerText = "➕ เพิ่มสูตรไอศกรีม";  
  } else {  
    form.style.display = "block";  
    toggleFormBtn.innerText = "✖️ ปิดฟอร์มเพิ่มสูตร";  
  }  
});  
document.getElementById("viewSavedBtn").addEventListener("click", () => {

const saved = getSavedRecipes();
const container = document.querySelector(".grid-container");
const cards = container.querySelectorAll(".ice-cream-card");

// ซ่อนทั้งหมดก่อน
cards.forEach(card => {
const name = card.querySelector(".ice-cream-name").innerText.trim();
const type = Object.keys(recipes).find(key => recipes[key].title.includes(name));
if (saved.includes(type)) {
card.style.display = "block";
} else {
card.style.display = "none";
}
});

// ปิดเมนูหลังคลิก
document.getElementById("sideMenu").style.left = "-260px";
});
document.getElementById("viewAllBtn").addEventListener("click", () => {
const cards = document.querySelectorAll(".ice-cream-card");
cards.forEach(card => {
card.style.display = "block";
});

// ปิด side menu อัตโนมัติ
document.getElementById("sideMenu").style.left = "-260px";

// เคลียร์ช่องค้นหาด้วย (ถ้ามี)
document.getElementById("searchBox").value = "";
});

darkModeToggle.addEventListener("click", () => {  
  const isDark = document.body.classList.contains("dark-mode");  
  setDarkMode(!isDark);  
});  

// เมนู  
const menuToggle = document.getElementById("menuToggle");  
const sideMenu = document.getElementById("sideMenu");  
const closeMenu = document.getElementById("closeMenu");  

menuToggle.addEventListener("click", () => {  
  sideMenu.style.left = "0";  
});  

closeMenu.addEventListener("click", () => {  
  sideMenu.style.left = "-260px";  
});  

// Form submission  
document.getElementById("addRecipeForm").addEventListener("submit", function (e) {  
  e.preventDefault();  

  const name = document.getElementById("customName").value.trim();  
  const image = document.getElementById("customImage").value.trim();  
  const ingredients = document.getElementById("customIngredients").value.split(",").map(i => i.trim());  
  const video = document.getElementById("customVideo").value.trim();  

  if (!name || !image || ingredients.length === 0) return;  

  const newRecipe = { name, image, ingredients, video };  
  const existing = getUserRecipes();  
  existing.push(newRecipe);  
  saveUserRecipes(existing);  
  location.reload();  
});

});
</script>

</body>    
</html>  
