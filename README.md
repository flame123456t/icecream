<!DOCTYPE html><html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>แชร์สูตรไอศกรีม • ชมพูพาสเทล</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Thai:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      /* พาสเทลชมพู */
      --bg:#fff7fb;               /* พื้นหลังหลัก */
      --surface:#fff;              /* การ์ด/พื้นผิว */
      --text:#2b2b2b;             /* ตัวอักษร */
      --muted:#786d77;            /* ตัวอักษรรอง */
      --brand:#ff7aa2;            /* ชมพูพาสเทลหลัก */
      --brand-2:#ffc2d6;          /* ชมพูอ่อน */
      --brand-3:#ffe6ef;          /* ชมพูจาง */
      --accent:#ffd166;           /* เหลืองพาสเทล (เน้นเล็กน้อย) */
      --success:#7bd389;          /* เขียวพาสเทล */
      --danger:#ff6b6b;           /* แดงพาสเทล */
      --border:#f2e8ee;           /* เส้นขอบจาง */
      --shadow: 0 10px 30px rgba(255, 122, 162, 0.15);
    }
    body.dark{
      --bg:#1b1a1f;
      --surface:#23222a;
      --text:#f3eef3;
      --muted:#c7becb;
      --brand:#ff86b0;
      --brand-2:#3a2d36;
      --brand-3:#2a232a;
      --accent:#ffd166;
      --success:#8be09b;
      --danger:#ff8080;
      --border:#34313a;
      --shadow: 0 10px 30px rgba(0,0,0,0.25);
    }*{ box-sizing: border-box; }
html,body{ height:100%; }
body{
  margin:0; background:var(--bg); color:var(--text); font-family:'Noto Sans Thai', system-ui, sans-serif; line-height:1.4;
}

/* Header */
header{
  position:sticky; top:0; z-index:1000; backdrop-filter:saturate(140%) blur(6px);
  background:linear-gradient(180deg, rgba(255,255,255,0.75), rgba(255,255,255,0.55)) ;
}
body.dark header{ background:linear-gradient(180deg, rgba(35,34,42,0.75), rgba(35,34,42,0.55)); }
.bar{
  display:flex; align-items:center; gap:12px; padding:12px 16px; border-bottom:1px solid var(--border);
}
.menu-btn{
  appearance:none; border:0; background:var(--brand); color:#fff; padding:10px 12px; border-radius:14px; box-shadow:var(--shadow);
  display:inline-flex; align-items:center; gap:8px; cursor:pointer; font-weight:600;
}
.menu-btn .icon{ width:18px; height:2px; background:#fff; position:relative; border-radius:2px; }
.menu-btn .icon::before,.menu-btn .icon::after{ content:""; position:absolute; left:0; width:18px; height:2px; background:#fff; border-radius:2px; }
.menu-btn .icon::before{ top:-6px; } .menu-btn .icon::after{ top:6px; }

.title{ font-weight:800; letter-spacing:0.2px; }
.spacer{ flex:1; }

.theme-toggle{
  appearance:none; border:1px solid var(--border); background:var(--surface); color:var(--text); padding:10px 12px; border-radius:14px; cursor:pointer; font-weight:600;
}

/* Category Tabs */
.tabs{ display:flex; gap:8px; padding:12px 16px; overflow:auto hidden; border-bottom:1px solid var(--border); }
.tab{ background:var(--brand-3); color:#7f2d47; border:1px solid var(--border); padding:8px 14px; border-radius:999px; cursor:pointer; white-space:nowrap; font-weight:600; }
.tab.active{ background:var(--brand); color:#fff; box-shadow:var(--shadow); border-color:transparent; }

/* Layout */
.container{ padding:16px; max-width:1100px; margin:0 auto; }

/* Cards */
.grid{ display:grid; grid-template-columns:repeat(1, 1fr); gap:16px; }
@media(min-width:640px){ .grid{ grid-template-columns:repeat(2, 1fr);} }
@media(min-width:980px){ .grid{ grid-template-columns:repeat(3, 1fr);} }

.card{
  background:var(--surface); border:1px solid var(--border); border-radius:18px; overflow:hidden; box-shadow:var(--shadow);
  display:flex; flex-direction:column; min-height:280px;
}
.thumb{ position:relative; aspect-ratio:16/10; background:var(--brand-2); }
.thumb img{ width:100%; height:100%; object-fit:cover; display:block; }
.cat-chip{
  position:absolute; left:10px; top:10px; background:rgba(255,255,255,0.9); color:#7f2d47; padding:6px 10px; border-radius:999px; font-size:12px; font-weight:700; border:1px solid var(--border);
}
body.dark .cat-chip{ background:rgba(35,34,42,0.9); color:#ffd7e6; }

.card-body{ padding:12px 14px; display:flex; gap:10px; align-items:flex-start; }
.avatar{ width:40px; height:40px; border-radius:12px; background:var(--brand-3); display:grid; place-items:center; font-weight:800; color:#7f2d47; border:1px solid var(--border); }
.info{ flex:1; min-width:0; }
.name{ margin:0; font-size:16px; font-weight:800; }
.by{ margin:2px 0 0; color:var(--muted); font-size:12px; }

.heart{ appearance:none; background:transparent; border:0; cursor:pointer; font-size:20px; line-height:1; }
.heart.fav{ color:var(--danger); }

.open-btn{ margin:8px 14px 14px; padding:10px 12px; border-radius:12px; background:var(--brand); color:#fff; border:0; cursor:pointer; font-weight:700; }

/* Drawer Menu */
.drawer{
  position:fixed; inset:0; pointer-events:none; z-index:2000;
}
.drawer.show{ pointer-events:auto; }
.drawer .overlay{ position:absolute; inset:0; background:rgba(0,0,0,0.35); opacity:0; transition:opacity .2s; }
.drawer.show .overlay{ opacity:1; }
.panel{
  position:absolute; left:-320px; top:0; width:320px; height:100%; background:var(--surface); border-right:1px solid var(--border); box-shadow:var(--shadow);
  transition:transform .25s ease; transform:translateX(0);
}
.drawer.show .panel{ transform:translateX(320px); }
.panel header{ display:flex; align-items:center; gap:10px; padding:14px; border-bottom:1px solid var(--border); }
.panel h3{ margin:0; font-size:18px; font-weight:800; }
.close-drawer{ margin-left:auto; appearance:none; border:0; background:var(--brand-3); padding:8px 10px; border-radius:10px; cursor:pointer; }

.panel .section{ padding:14px; border-bottom:1px solid var(--border); }
.panel label{ display:block; font-size:12px; color:var(--muted); margin-bottom:6px; }
.panel input[type="text"], .panel input[type="search"]{
  width:100%; padding:10px 12px; border-radius:12px; border:1px solid var(--border); background:var(--surface); color:var(--text);
}
.panel .row{ display:flex; gap:10px; align-items:center; }
.panel .btn{ width:100%; appearance:none; border:0; padding:10px 12px; border-radius:12px; background:var(--brand); color:#fff; cursor:pointer; font-weight:800; box-shadow:var(--shadow); }
.panel .btn-secondary{ background:var(--brand-3); color:#7f2d47; border:1px solid var(--border); box-shadow:none; }
body.dark .panel .btn-secondary{ color:#ffd7e6; }

/* Modal */
.modal{ position:fixed; inset:0; display:none; align-items:center; justify-content:center; z-index:3000; }
.modal.show{ display:flex; }
.modal .backdrop{ position:absolute; inset:0; background:rgba(0,0,0,0.45); }
.modal .dialog{ position:relative; width:min(880px, 92vw); max-height:90vh; overflow:auto; background:var(--surface); border:1px solid var(--border); border-radius:18px; box-shadow:var(--shadow); }
.modal header{ display:flex; align-items:center; justify-content:space-between; padding:14px 16px; border-bottom:1px solid var(--border); }
.modal header h3{ margin:0; font-size:18px; font-weight:800; }
.modal .content{ padding:16px; display:grid; gap:12px; grid-template-columns: 1fr; }
@media(min-width:880px){ .modal .content{ grid-template-columns: 1fr 1fr; } }
.modal .content img{ width:100%; border-radius:12px; border:1px solid var(--border); }
.meta{ color:var(--muted); font-size:13px; }
.list{ padding-left:18px; }

/* Add Recipe Form */
.form-grid{ display:grid; gap:12px; grid-template-columns: 1fr; }
@media(min-width:720px){ .form-grid{ grid-template-columns: 1fr 1fr; } }
.field{ display:flex; flex-direction:column; gap:6px; }
.field input, .field select, .field textarea{
  padding:10px 12px; border-radius:12px; border:1px solid var(--border); background:var(--surface); color:var(--text);
}
.field textarea{ min-height:110px; resize:vertical; }
.actions{ display:flex; gap:10px; justify-content:flex-end; padding-top:8px; }
.btn{ appearance:none; border:0; background:var(--brand); color:#fff; padding:10px 12px; border-radius:12px; cursor:pointer; font-weight:800; box-shadow:var(--shadow); }
.btn.secondary{ background:var(--brand-3); color:#7f2d47; border:1px solid var(--border); box-shadow:none; }
body.dark .btn.secondary{ color:#ffd7e6; }

.empty{ text-align:center; color:var(--muted); padding:30px 10px; }

  </style>
</head>
<body>
  <!-- Drawer เมนูซ้ายบน -->
  <div class="drawer" id="drawer">
    <div class="overlay" data-close-drawer></div>
    <aside class="panel">
      <header>
        <h3>เมนู</h3>
        <button class="close-drawer" data-close-drawer>ปิด</button>
      </header><div class="section">
    <label>ชื่อผู้ใช้ (ใช้แสดงในสูตรที่โพสต์)</label>
    <div class="row">
      <input type="text" id="usernameInput" placeholder="พิมพ์ชื่อของคุณ">
    </div>
  </div>

  <div class="section">
    <label>ค้นหาสูตร</label>
    <input type="search" id="searchInput" placeholder="ค้นหาตามชื่อสูตร / ผู้โพสต์">
  </div>

  <div class="section" style="display:grid; gap:10px;">
    <button class="btn" id="openAdd">+ เพิ่มสูตรใหม่</button>
    <button class="btn btn-secondary" id="showFavs">ดูสูตรที่กดหัวใจไว้</button>
    <button class="btn btn-secondary" id="showAll">แสดงสูตรทั้งหมด</button>
  </div>
</aside>

  </div>  <!-- Header -->  <header>
    <div class="bar">
      <button class="menu-btn" id="openDrawer" title="เมนู">
        <span class="icon" aria-hidden="true"></span>
      </button>
      <div class="title">แชร์สูตรไอศกรีม</div>
      <div class="spacer"></div>
      <button class="theme-toggle" id="themeToggle">ปุ่มสว่าง/ปุ่มมืด</button>
    </div><!-- Category Tabs -->
<nav class="tabs" id="tabs">
  <button class="tab active" data-cat="all">สูตรทั้งหมด</button>
  <button class="tab" data-cat="ไอศกรีม">ไอศกรีม</button>
  <button class="tab" data-cat="เค้ก">เค้ก</button>
  <button class="tab" data-cat="คุกกี้">คุกกี้</button>
  <button class="tab" data-cat="น้ำปั่น">น้ำปั่น</button>
</nav>

  </header>  <!-- Main -->  <main class="container">
    <div id="grid" class="grid" aria-live="polite"></div>
    <div id="empty" class="empty" style="display:none;">ไม่พบสูตรตามเงื่อนไขที่เลือก</div>
  </main>  <!-- Modal: ดูรายละเอียดสูตร -->  <div class="modal" id="viewModal" aria-hidden="true">
    <div class="backdrop" data-close-modal></div>
    <div class="dialog">
      <header>
        <h3 id="viewTitle">รายละเอียดสูตร</h3>
        <button class="close-drawer" data-close-modal>ปิด</button>
      </header>
      <div class="content">
        <div>
          <img id="viewImage" alt="รูปสูตร">
          <div class="meta" id="viewMeta"></div>
          <div id="viewVideoWrap"></div>
        </div>
        <div>
          <h4>ส่วนผสม</h4>
          <ul class="list" id="viewIngredients"></ul>
          <h4>วิธีทำ</h4>
          <ol class="list" id="viewSteps"></ol>
        </div>
      </div>
    </div>
  </div>  <!-- Modal: เพิ่ม/แก้ไขสูตร -->  <div class="modal" id="addModal" aria-hidden="true">
    <div class="backdrop" data-close-add></div>
    <div class="dialog">
      <header>
        <h3>เพิ่มสูตรใหม่</h3>
        <button class="close-drawer" data-close-add>ปิด</button>
      </header>
      <div class="content">
        <form id="addForm" class="form-grid">
          <div class="field">
            <label>ชื่อสูตร *</label>
            <input type="text" name="title" required placeholder="เช่น ไอศกรีมวานิลลาโฮมเมด">
          </div>
          <div class="field">
            <label>หมวดหมู่ *</label>
            <select name="category" required>
              <option value="ไอศกรีม">ไอศกรีม</option>
              <option value="เค้ก">เค้ก</option>
              <option value="คุกกี้">คุกกี้</option>
              <option value="น้ำปั่น">น้ำปั่น</option>
            </select>
          </div><div class="field" style="grid-column:1/-1;">
        <label>ส่วนผสม (พิมพ์บรรทัดละ 1 รายการ) *</label>
        <textarea name="ingredients" required placeholder="นมสด 500 มล.\nวิปปิ้งครีม 200 มล.\nน้ำตาล 80 กรัม"></textarea>
      </div> 

            <div class="field" style="grid-column:1/-1;">
        <label>วิธีทำ (พิมพ์บรรทัดละ 1 ขั้นตอน) *</label>
        <textarea name="steps" required placeholder="ผสมส่วนผสมทั้งหมด\nแช่ช่องฟรีซ 4-6 ชม.\nคนทุก 30 นาที 2-3 ครั้ง"></textarea>
      </div>

      <div class="field">
        <label>วิดีโอสาธารณะ (ลิงก์ YouTube หรือ mp4)</label>
        <input type="text" name="videoUrl" placeholder="https://..."></input>
      </div>
      <div class="field">
        <label>อัปโหลดไฟล์วิดีโอ (ไม่บันทึกถาวร)</label>
        <input type="file" name="videoFile" accept="video/*">
      </div>

      <div class="field">
        <label>ชื่อผู้โพสต์ *</label>
        <input type="text" name="author" id="authorField" required placeholder="ชื่อคุณ">
      </div>
      <div class="field">
        <label>อัปโหลดรูปภาพ *</label>
        <input type="file" name="image" accept="image/*" required>
      </div>

      <div class="actions" style="grid-column:1/-1;">
        <button type="button" class="btn secondary" data-close-add>ยกเลิก</button>
        <button type="submit" class="btn">บันทึกสูตร</button>
      </div>
    </form>
    <div class="meta" style="grid-column:1/-1;">
      หมายเหตุ: ไฟล์วิดีโอที่อัปโหลดจะเล่นได้เฉพาะในรอบการใช้งานปัจจุบัน และจะไม่ถูกเก็บใน LocalStorage (เพื่อประสิทธิภาพ)
    </div>
  </div>
</div>

  </div>  <script>
    // ---------- Utilities ----------
    const $ = (sel, root=document) => root.querySelector(sel);
    const $$ = (sel, root=document) => Array.from(root.querySelectorAll(sel));

    const STORAGE_KEY = 'icecream_recipes_v1';
    const FAV_KEY = 'icecream_favs_v1';
    const THEME_KEY = 'icecream_theme_v1';
    const USER_KEY = 'icecream_user_v1';

    const catTH = ['ไอศกรีม','เค้ก','คุกกี้','น้ำปั่น'];

    function uid(){ return Math.random().toString(36).slice(2)+Date.now().toString(36); }

    function toBase64(file){
      return new Promise((resolve,reject)=>{
        const fr = new FileReader();
        fr.onload = () => resolve(fr.result);
        fr.onerror = reject;
        fr.readAsDataURL(file);
      });
    }

    function ytEmbed(url){
      try{
        const u = new URL(url);
        if(u.hostname.includes('youtube.com')){
          const id = u.searchParams.get('v');
          if(id) return `https://www.youtube.com/embed/${id}`;
        }
        if(u.hostname.includes('youtu.be')){
          const id = u.pathname.slice(1);
          if(id) return `https://www.youtube.com/embed/${id}`;
        }
        return url; // mp4 หรือแหล่งวิดีโออื่น
      }catch{ return null; }
    }

    // ---------- Data ----------
    /** โครงสร้าง recipe
     * { id, title, category, image, author, ingredients:[...], steps:[...], videoUrl?, _videoObjectUrl? }
     * image เก็บเป็น dataURL สำหรับความทนทาน
     */

       const seed = () => {
      const demoImg = (txt) => `https://dummyimage.com/800x500/ffc2d6/7f2d47.jpg&text=${encodeURIComponent(txt)}`;
      const YT = (id) => `https://www.youtube.com/watch?v=${id}`;
      const list = [];
      // ไอศกรีม 
      list.push({id:uid(), title:'ไอศกรีมนมสด',category:'ไอศกรีม', image:('https://i.ytimg.com/vi/HQZdrjtW4zU/maxresdefault.jpg'), author:'L', ingredients:['นมสด 500 มล.','วิปครีม 200 มล.','น้ำตาล 80 กรัม','วานิลลา 1 ช้อนชา'], steps:['ผสมนม วิปครีม น้ำตาล วานิลลา','คนจนน้ำตาลละลาย','เทใส่ภาชนะ แช่แข็ง 4-6 ชม.','ทุก 30 นาที นำออกมาคน 2-3 ครั้ง'], videoUrl:YT('https://youtu.be/HQZdrjtW4zU?si=PDR3t88XP8RoTKRH')});
      list.push({id:uid(), title:'ไอศกรีมวานิลลา', category:'ไอศกรีม', image:('https://i.ytimg.com/vi/1vCnGjZzTsU/maxresdefault.jpg'), author:'L', ingredients:['ไข่แดง 4 ฟอง','นม 400 มล.','ครีม 300 มล.','วานิลลา 1 ช้อนชา','น้ำตาล 120 กรัม'], steps:['อุ่นนม+น้ำตาล','เทลงไข่แดง คนจนข้น','ผสมครีมและวานิลลา','ปั่น/แช่แข็ง'], videoUrl:YT('https://youtu.be/1vCnGjZzTsU?si=LchKOeEAxI8u3H7Q')});
      list.push({id:uid(), title:'ไอศกรีมช็อกโกแลต', category:'ไอศกรีม', image:('https://i.ytimg.com/vi/9L0L20wqeks/sddefault.jpg'), author:'L', ingredients:['ผงโกโก้ 40 กรัม','ช็อกโกแลต 100 กรัม','ครีม 300 มล.','นม 300 มล.','น้ำตาล 100 กรัม'], steps:['อุ่นนม+ครีม','ละลายช็อกโกแลตและโกโก้','แช่ให้เย็น','ปั่น/แช่แข็ง'], videoUrl:YT('https://youtu.be/IoiiNQoBe-Y?si=rM0YbR00BOyoxBv9')});
      list.push({id:uid(), title:'ไอศกรีมทุเรียน', category:'ไอศกรีม', image:('https://i.ytimg.com/vi/O1qHjuOhgo0/maxresdefault.jpg'), author:'L', ingredients:['ทุเรียน 500 กรัม.','น้ำตาล 100 กรัม','เกลือหยิบมือ','นมจีด 500 ml '], steps:['ละลายน้ำตาลในนมจืด','เติมเกลือ','ใส่เนื้อทุเรียน','แช่แข็ง/คนระหว่างแช่'], videoUrl:YT('https://youtu.be/O1qHjuOhgo0?si=plwJznmUHvsTx28T')});
      list.push({id:uid(), title:'ไอศกรีมสตรอว์เบอร์รี', category:'ไอศกรีม', image:('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQqMi4-V-EikcgTTocWS_wkQXbWgSeoBZzv75etpsZe_in5U0mV2zUNklcX1e2dIUpGLns&usqp=CAU'), author:'Aommy', ingredients:['สตรอว์เบอร์รีบด 300 กรัม','ครีม 300 มล.','นม 200 มล.','น้ำตาล 90 กรัม'], steps:['บดสตรอว์เบอร์รี','ผสมกับครีม นม น้ำตาล','แช่เย็นจัด','ปั่น/แช่แข็ง'], videoUrl:YT('https://youtu.be/mDIsEHfG4HM?si=ahQ6zX9AAxHXsIMd')});
      // เค้ก 
      list.push({id:uid(), title:'เค้กส้มฉ่ำ', category:'เค้ก', image:('https://static.cdntap.com/tap-assets-prod/wp-content/uploads/sites/25/2022/02/orange-cake-lead.jpg'), author:'L', ingredients:['แป้งเค้ก 200 กรัม','ไข่ 3 ฟอง','น้ำส้ม 120 มล.','เนย 100 กรัม','น้ำตาล 120 กรัม'], steps:['ตีไข่กับน้ำตาล','ใส่แป้งและเนย','เติมน้ำส้ม','อบ 170°C 30-35 นาที'], videoUrl:YT('https://youtu.be/AMC6TL3tHCU?si=huKpg0OzOfQkV6Wv')});
      list.push({id:uid(), title:'ชิฟฟอนชาไทย', category:'เค้ก', image:('https://f.ptcdn.info/392/080/000/rtd62o22gbmJb6tO8I9bo-o.jpg'), author:'L', ingredients:['แป้งเค้ก 180 กรัม','ชาไทยเข้ม 150 มล.','ไข่ 4 ฟอง','น้ำตาล 130 กรัม','น้ำมัน 60 มล.'], steps:['ผสมของเหลว','ร่อนแป้ง','ตีไข่ขาวตั้งยอด','ตะล่อมรวมกัน','อบ 170°C 35 นาที'], videoUrl:YT('https://youtu.be/VWysSH5Ypm0?si=5QXzncgyIS_DEppM')});
      list.push({id:uid(), title:'เค้กช็อกโกแลตหน้านิ่ม', category:'เค้ก', image:('https://i.ytimg.com/vi/bIvRLl-R1Ho/maxresdefault.jpg'), author:'L', ingredients:['แป้ง 200 กรัม','โกโก้ 30 กรัม','นม 200 มล.','ไข่ 3 ฟอง','น้ำตาล 150 กรัม'], steps:['ผสมส่วนแห้ง','เติมของเหลว','อบ 170°C 30 นาที','ทำหน้าช็อกโกแลต เทราด'], videoUrl:YT('https://youtu.be/bIvRLl-R1Ho?si=rGTm5KYOztBAFjNh')});
      list.push({id:uid(), title:'ชีสเค้กอบ', category:'เค้ก', image:('https://recipe.sgethai.com/wp-content/uploads/2025/04/cover-basque-burnt-cheese-cake.webp'), author:'L', ingredients:['ครีมชีส 500 กรัม','น้ำตาล 120 กรัม','ไข่ 3 ฟอง','วิปครีม 150 มล.','บิสกิตบด 150 กรัม'], steps:['ทำฐานบิสกิต','ตีครีมชีสกับน้ำตาล','เติมไข่และครีม','อบ 160°C 45-55 นาที'], videoUrl:YT('https://youtu.be/xLiMoHmYR14?si=x6e_gcfk3B1Df8Jb')});
      list.push({id:uid(), title:'เค้กกล้วยหอม', category:'เค้ก', image:('https://i.ytimg.com/vi/lwXwD1WG3e4/maxresdefault.jpg'), author:'L', ingredients:['กล้วย 3 ผลสุก','แป้ง 200 กรัม','ไข่ 2 ฟอง','น้ำตาล 120 กรัม','น้ำมัน 80 มล.'], steps:['บดกล้วย','ผสมส่วนผสมทั้งหมด','อบ 175°C 35-40 นาที'], videoUrl:YT('https://youtu.be/FV47VIgvYEs?si=0qw_0Aiwl4wAI48C')});
      // น้ำปั่น 
      list.push({id:uid(), title:'สมูทตี้สตรอว์เบอร์รี-กล้วย', category:'น้ำปั่น', image:('https://today-obs.line-scdn.net/0hwMhlixjAKGJVFTxNyu1XNW1DJBNmczJrd3thDHlFIwd-OW09OnF7AXZAIU5wdz80dSFnU3IRI1t-JDtnPA/w280'), author:'L', ingredients:['สตรอว์เบอร์รี 1 ถ้วย','กล้วย 1 ผล','โยเกิร์ต 1/2 ถ้วย','น้ำผึ้ง 1 ช้อนโต๊ะ','น้ำแข็ง'], steps:['ใส่ทุกอย่างลงเครื่องปั่น','ปั่นจนเนียน เสิร์ฟทันที'], videoUrl:YT('https://youtu.be/1EjS3VR77wE?si=HtdqpbAbMZxB4RRz')});
      list.push({id:uid(), title:'มะม่วงโยเกิร์ตปั่น', category:'น้ำปั่น', image:('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT_emoKzscYjbq-q9Q848TV3hCmaS5EUvbPcw&s'), author:'L', ingredients:['มะม่วงสุก 1 ถ้วย','โยเกิร์ต 1/2 ถ้วย','นม 1/2 ถ้วย','น้ำผึ้ง 1 ช้อนโต๊ะ','น้ำแข็ง'], steps:['ปั่นทุกอย่างเข้าด้วยกัน','ชิมรส ปรับหวาน'], videoUrl:YT('https://youtu.be/R0XLH2mgsBk?si=ATwxQu-efCmEZDWL')}) 
      list.push({id:uid(), title:'แตงโมปั่นเย็นฉ่ำ', category:'น้ำปั่น', image:('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQC-JFVpW5P5AHMRgMywgI5QKV3U6lcbxWgFA&s'), author:'L', ingredients:['แตงโมหั่น 2 ถ้วย','น้ำเชื่อม 1-2 ช้อนโต๊ะ','น้ำแข็ง'], steps:['ปั่นทั้งหมด','เสิร์ฟพร้อมใบสะระแหน่'], videoUrl:YT('https://youtu.be/2ttVIkPQFwc?si=TgBhB0NQHZt_PVKY')});
      list.push({id:uid(), title:'สับปะรดมินต์ปั่น', category:'น้ำปั่น', image:('https://i.ytimg.com/vi/rerMjL21ceg/mqdefault.jpg'), author:'L', ingredients:['สับปะรด 1 ถ้วย','ใบมินต์ 6-8 ใบ','โซดา 1/2 ถ้วย','น้ำแข็ง'], steps:['ปั่นสับปะรดกับน้ำแข็ง','เทใส่แก้ว เติมโซดาและมินต์'], videoUrl:YT('https://youtu.be/LKasigS4r5c?si=iYpimpipivSM6Vbs')});
      list.push({id:uid(), title:'กาแฟปั่นคาราเมล', category:'น้ำปั่น', image:('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ5z6CKn33iksAXpE4IXpDR4lSRQy2FNHFBCw&s'), author:'L', ingredients:['เอสเปรสโซ 1 ช็อต','นม 1/2 ถ้วย','คาราเมลไซรัป 2 ช้อนโต๊ะ','น้ำแข็ง'], steps:['ปั่นทั้งหมดจนเข้ากัน','ราดคาราเมลเพิ่มได้ตามชอบ'], videoUrl:YT('https://youtu.be/HniMRESObvE?si=69Y9fFU0yIN9f5Zm')});
      // คุกกี้ 
      list.push({id:uid(), title:'คุกกี้ช็อกชิพ', category:'คุกกี้', image:('https://i.ytimg.com/vi/_7KghXqc4Qk/maxresdefault.jpg'), author:'L', ingredients:['แป้ง 220 กรัม','เนย 120 กรัม','น้ำตาล 120 กรัม','ไข่ 1 ฟอง','ช็อกชิพ 120 กรัม'], steps:['ตีเนยกับน้ำตาล','ใส่ไข่และแป้ง','ใส่ช็อกชิพ','อบ 180°C 10-12 นาที'], videoUrl:YT('https://youtu.be/dzkfeVFnV4A?si=atF2LoPo7m0jID74')});
      list.push({id:uid(), title:'คุกกี้โอ๊ตลูกเกด', category:'คุกกี้', image:('https://i.ytimg.com/vi/ZXHP-3si_hU/maxresdefault.jpg'), author:'L', ingredients:['โอ๊ต 150 กรัม','แป้ง 100 กรัม','เนย 100 กรัม','น้ำตาล 90 กรัม','ลูกเกด 80 กรัม'], steps:['ผสมส่วนผสมทั้งหมด','ตักวางถาด','อบ 175°C 12-15 นาที'], videoUrl:YT('https://youtu.be/OaQy40o7I8A?si=dNqprgWvuDpr4saW')});
      list.push({id:uid(), title:'คุกกี้งาขี้ม่อน', category:'คุกกี้', image:('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTaW1eXOfOloNq6OklSyR2m5ryFzMKrdTzbZw&s'), author:'L', ingredients:['แป้ง 200 กรัม','งาขี้ม่อน 50 กรัม','น้ำตาล 80 กรัม','เนย 120 กรัม','ไข่ 1 ฟอง'], steps:['ผสมส่วนผสม','ปั้นกดแบน','อบ 175°C 12 นาที'], videoUrl:YT('https://youtu.be/1wE_QgEF2uk?si=J6gCNqi-GJ7nA_CD')});
      list.push({id:uid(), title:'คุกกี้เนยวานิลลา', category:'คุกกี้', image:('https://i.ytimg.com/vi/I1tsliG101Y/maxresdefault.jpg'), author:'L ', ingredients:['แป้ง 220 กรัม','เนย 150 กรัม','น้ำตาลไอซิ่ง 80 กรัม','วานิลลา 1 ช้อนชา','ไข่ 1 ฟอง'], steps:['ตีเนย+ไอซิ่ง','ใส่ไข่+วานิลลา','ใส่แป้ง','อบ 170°C 12-15 นาที'], videoUrl:YT('https://youtu.be/Y9UdCT43CAA?si=VAmwnKMAwNHcNf8_')});
      list.push({id:uid(), title:'คุกกี้มัทฉะไวท์ช็อก', category:'คุกกี้', image:('https://i.ytimg.com/vi/yqR0STrOcKk/maxresdefault.jpg'), author:'L', ingredients:['แป้ง 220 กรัม','ผงมัทฉะ 10 กรัม','เนย 150 กรัม','น้ำตาล 100 กรัม','ไวท์ช็อก 120 กรัม'], steps:['ผสมแห้ง','ตีเนยกับน้ำตาล','รวมส่วนผสม','อบ 175°C 12 นาที'], videoUrl:YT('https://youtu.be/2nrwOB7DkJc?si=yzEwWBUatr2E_DmU')});
      return list.map(r=>({...r, image:r.image }));
    };


function loadRecipes(){
      const raw = localStorage.getItem(STORAGE_KEY);
      if(raw){ try{ return JSON.parse(raw); }catch{ return []; } }
      // สร้าง seed พร้อมแปลงรูปเป็น dataURL ด้วย fetch -> blob -> base64 (ข้ามเพื่อความเร็ว: ใช้ลิงก์โดยตรง)
      return seed();
    }

    function saveRecipes(){ localStorage.setItem(STORAGE_KEY, JSON.stringify(recipes)); }

    function loadFavs(){ try{ return new Set(JSON.parse(localStorage.getItem(FAV_KEY)||'[]')); }catch{ return new Set(); } }
    function saveFavs(){ localStorage.setItem(FAV_KEY, JSON.stringify([...favs])); }

    function applyTheme(initial=false){
      const mode = localStorage.getItem(THEME_KEY)||'light';
      document.body.classList.toggle('dark', mode==='dark');
      if(!initial) localStorage.setItem(THEME_KEY, mode);
    }

    // ---------- State ----------
    let recipes = loadRecipes();
    let favs = loadFavs();
    let filter = { cat:'all', q:'', favOnly:false };

    // ---------- Render ----------
    const grid = $('#grid');
    const emptyEl = $('#empty');

    function initials(name){ return (name||'?').trim().split(/\s+/).map(w=>w[0]).slice(0,2).join('').toUpperCase(); }

   function cardTemplate(r){
  const isFav = favs.has(r.id);
  return `
    <article class="card" data-id="${r.id}">
      <div class="thumb">
        <img loading="lazy" src="${r.image}" alt="${r.title}" data-open="${r.id}">
        <span class="cat-chip">${r.category}</span>
      </div>
      <div class="card-body">
        <div class="avatar">${initials(r.author)}</div>
        <div class="info">
          <h3 class="name">${r.title}</h3>
          <div class="by">โดย ${r.author}</div>
        </div>
        <button class="heart ${isFav?'fav':''}" title="กดหัวใจ" data-like>❤</button>
      </div>
    </article>
  `;
}

    function render(){
      let list = recipes.slice();
      if(filter.cat !== 'all') list = list.filter(r=>r.category===filter.cat);
      if(filter.q){
        const q = filter.q.toLowerCase();
        list = list.filter(r=> r.title.toLowerCase().includes(q) || (r.author||'').toLowerCase().includes(q));
      }
      if(filter.favOnly){ list = list.filter(r=>favs.has(r.id)); }

      grid.innerHTML = list.map(cardTemplate).join('');
      emptyEl.style.display = list.length? 'none':'block';
    }

    // ---------- Detail Modal ----------
    const viewModal = $('#viewModal');
    const viewTitle = $('#viewTitle');
    const viewImage = $('#viewImage');
    const viewMeta = $('#viewMeta');
    const viewIngredients = $('#viewIngredients');
    const viewSteps = $('#viewSteps');
    const viewVideoWrap = $('#viewVideoWrap');

    function openView(id){
      const r = recipes.find(x=>x.id===id);
      if(!r) return;
      viewTitle.textContent = r.title;
      viewImage.src = r.image;
      viewImage.alt = r.title;
      viewMeta.textContent = `หมวดหมู่: ${r.category} • โดย ${r.author}`;
      viewIngredients.innerHTML = r.ingredients.map(i=>`<li>${i}</li>`).join('');
      viewSteps.innerHTML = r.steps.map(s=>`<li>${s}</li>`).join('');

      // วิดีโอ
      viewVideoWrap.innerHTML = '';
      if(r._videoObjectUrl){
        const v = document.createElement('video');
        v.controls = true; v.src = r._videoObjectUrl; v.style.width='100%'; v.style.borderRadius='12px'; v.style.marginTop='10px';
        viewVideoWrap.appendChild(v);
      } else if(r.videoUrl){    
                const src = ytEmbed(r.videoUrl);
        if(src && src.includes('youtube.com/embed/')){
          const ifr = document.createElement('iframe');
          ifr.src = src; ifr.allow = 'accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share'; ifr.allowFullscreen = true; ifr.style.width='100%'; ifr.style.aspectRatio='16/9'; ifr.style.border='0'; ifr.style.borderRadius='12px'; ifr.style.marginTop='10px';
          viewVideoWrap.appendChild(ifr);
        }else if(src){
          const v = document.createElement('video'); v.controls = true; v.src = src; v.style.width='100%'; v.style.borderRadius='12px'; v.style.marginTop='10px'; viewVideoWrap.appendChild(v);
        }
      }

      viewModal.classList.add('show');
    }

    function closeView(){ viewModal.classList.remove('show'); }

    // ---------- Add Modal ----------
    const addModal = $('#addModal');
    const addForm = $('#addForm');

    function openAdd(){
      // เติมชื่อผู้โพสต์จาก username
      const user = localStorage.getItem(USER_KEY)||'';
      $('#authorField').value = user;
      addModal.classList.add('show');
    }
    function closeAdd(){ addModal.classList.remove('show'); addForm.reset(); }

    addForm.addEventListener('submit', async (e)=>{
      e.preventDefault();
      const fd = new FormData(addForm);
      const title = (fd.get('title')||'').toString().trim();
      const category = fd.get('category');
      const ingredients = (fd.get('ingredients')||'').toString().split(/\n+/).map(s=>s.trim()).filter(Boolean);
      const steps = (fd.get('steps')||'').toString().split(/\n+/).map(s=>s.trim()).filter(Boolean);
      const author = (fd.get('author')||'').toString().trim() || 'ผู้ใช้ไม่ระบุชื่อ';
      const videoUrl = (fd.get('videoUrl')||'').toString().trim();
      const videoFile = fd.get('videoFile');
      const imageFile = fd.get('image');

      if(!title || !category || !ingredients.length || !steps.length || !imageFile || !imageFile.size){
        alert('กรุณากรอกข้อมูลที่จำเป็นให้ครบถ้วน');
        return;
      }

      const image = await toBase64(imageFile);
      const rec = { id:uid(), title, category, author, image, ingredients, steps };
      if(videoUrl) rec.videoUrl = videoUrl;
      if(videoFile && videoFile.size){
        // ไม่เก็บถาวรใน localStorage แต่เล่นในรอบนี้ได้
        rec._videoObjectUrl = URL.createObjectURL(videoFile);
      }

      recipes.unshift(rec);
      saveRecipes();
      render();
      closeAdd();
    });

    // ---------- Events ----------
    // เปิด/ปิด Drawer
    const drawer = $('#drawer');
    $('#openDrawer').addEventListener('click', ()=> drawer.classList.add('show'));
    $$('[data-close-drawer]').forEach(el=> el.addEventListener('click', ()=> drawer.classList.remove('show')));

    // ปุ่มใน Drawer
    $('#openAdd').addEventListener('click', ()=>{ drawer.classList.remove('show'); openAdd(); });
    $('#showAll').addEventListener('click', ()=>{ filter.favOnly=false; filter.q=''; $('#searchInput').value=''; drawer.classList.remove('show'); render(); });
    $('#showFavs').addEventListener('click', ()=>{ filter.favOnly = true; drawer.classList.remove('show'); render(); });

    // ค้นหา
    $('#searchInput').addEventListener('input', (e)=>{ filter.q = e.target.value.trim(); render(); });

    // จัดการชื่อผู้ใช้
    const usernameInput = $('#usernameInput');
    usernameInput.value = localStorage.getItem(USER_KEY)||'';
    usernameInput.addEventListener('change', (e)=>{ localStorage.setItem(USER_KEY, e.target.value.trim()); });

    // Tabs หมวดหมู่
    const tabs = $('#tabs');
    tabs.addEventListener('click', (e)=>{
      const btn = e.target.closest('.tab');
      if(!btn) return;
      $$('.tab', tabs).forEach(t=>t.classList.remove('active'));
      btn.classList.add('active');
      filter.cat = btn.dataset.cat;
      filter.favOnly = false; // ออกจากโหมดโปรดเมื่อกดแท็บใหม่
      render();
    });

    // คลิกในกริด: like / open
   grid.addEventListener('click', (e) => {
  const likeBtn = e.target.closest('[data-like]');
  const img = e.target.closest('img'); // <-- เปลี่ยนจาก data-open
  const card = e.target.closest('.card');
  if (!card) return;

  const id = card.dataset.id;

  // กดหัวใจ
  if (likeBtn) {
    if (favs.has(id)) favs.delete(id);
    else favs.add(id);
    saveFavs();
    render();
    return;
  }

  // กดรูป
  if (img) {
    openView(id);
    return;
  }
});

    // ปิดโมดอล
    viewModal.addEventListener('click', (e)=>{ if(e.target.hasAttribute('data-close-modal')) closeView(); });
    addModal.addEventListener('click', (e)=>{ if(e.target.hasAttribute('data-close-add')) closeAdd(); });

    // ปุ่มธีม
    const themeToggle = $('#themeToggle');
    themeToggle.addEventListener('click', ()=>{
      const cur = localStorage.getItem(THEME_KEY)||'light';
      const next = cur==='light'? 'dark' : 'light';
      localStorage.setItem(THEME_KEY, next);
      applyTheme();
    });

    // ---------- Init ----------
    (function init(){
      applyTheme(true);
      render();
      // ฟังค์ชันทดสอบเปิดคีย์บอร์ดเข้าถึง: กด ESC ปิดโมดอล/เมนู
      window.addEventListener('keydown', (e)=>{
        if(e.key==='Escape'){
          if(addModal.classList.contains('show')) closeAdd();
          else if(viewModal.classList.contains('show')) closeView();
          else drawer.classList.remove('show');
        }
      });
    })();
 </script>
 </body>
</html>
