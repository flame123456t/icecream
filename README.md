<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <title>สูตรไอศกรีม</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding: 20px;
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
  </style>
</head>
<body>

<h2>🍨 คลิกที่ไอศกรีมเพื่อดูสูตร!</h2>

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
</div>

<!-- Popup -->
<div id="recipePopup" class="popup">
  <h3 id="recipeTitle"></h3>
  <ul id="recipeList"></ul>
  <p id="recipeNote"></p>
  <button id="watchVideoBtn" style="display:none;" onclick="openVideo()">ดูคลิปสอนทำ</button>
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

  function showRecipe(type) {
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

    document.getElementById("recipePopup").style.display = "block";
  }

  function hidePopup() {
    document.getElementById("recipePopup").style.display = "none";
  }

  function openVideo() {
    if (currentVideoUrl) {
      window.open(currentVideoUrl, "_blank");
    }
  }
</script>

</body>
</html>
