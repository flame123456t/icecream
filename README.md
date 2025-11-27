<!doctype html>
<html lang="th">
 <head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>ร้านค้าออนไลน์หน้าเดียว</title><!-- Tailwind via CDN -->
  <script src="https://cdn.tailwindcss.com"></script><!-- Canva SDKs -->
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    body {
      box-sizing: border-box;
    }
    html, body {
      height: 100%;
      width: 100%;
    }
    /* Simple focus ring for accessibility */
    :focus-visible {
      outline: 2px solid #fbbf24;
      outline-offset: 2px;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="w-full h-full m-0 antialiased">
  <div id="app-root" class="w-full h-full bg-[#0f172a] flex justify-center">
   <div id="app-shell" class="w-full max-w-md h-full flex flex-col bg-[#0b1220] text-white"><!-- HEADER -->
    <header class="flex items-center justify-between px-4 py-3 bg-[#0ea5e9] text-white shadow-md">
     <div class="flex items-center gap-2"><!-- Simple store icon -->
      <div class="w-8 h-8 rounded-lg bg-white/20 flex items-center justify-center" aria-hidden="true">
       <svg class="w-5 h-5 text-white" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M4 10L5 5H19L20 10" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <path d="M4 10H20V19C20 20.1046 19.1046 21 18 21H6C4.89543 21 4 20.1046 4 19V10Z" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <path d="M9 14H15" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" />
       </svg>
      </div>
      <div class="flex flex-col">
       <h1 id="shop-title" class="text-sm font-semibold leading-tight">ร้านค้าออนไลน์</h1>
       <p id="shop-tagline" class="text-[11px] text-white/80 leading-tight">เลือกสินค้า ใส่ตะกร้า และชำระเงินในหน้าเดียว</p>
      </div>
     </div>
     <div class="flex items-center gap-2"><button id="home-icon-btn" type="button" class="flex flex-col items-center gap-0.5 text-xs font-semibold" aria-label="หน้าหลัก">
       <svg class="w-5 h-5" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M3 9L12 2L21 9V20C21 20.5304 20.7893 21.0391 20.4142 21.4142C20.0391 21.7893 19.5304 22 19 22H5C4.46957 22 3.96086 21.7893 3.58579 21.4142C3.21071 21.0391 3 20.5304 3 20V9Z" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <path d="M9 22V12H15V22" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
       </svg><span class="text-[10px]">HOME</span> </button> <button id="cart-icon-btn" type="button" class="relative flex flex-col items-center gap-0.5 text-xs font-semibold" aria-label="ดูตะกร้าสินค้า">
       <svg class="w-5 h-5" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M4 4H6L7.5 15H18L20 8H8" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <circle cx="10" cy="19" r="1" fill="currentColor" /> <circle cx="17" cy="19" r="1" fill="currentColor" />
       </svg><span class="text-[10px]">ตะกร้��</span> <span id="cart-count-badge" class="absolute -top-1 -right-1 inline-flex min-w-[16px] h-[16px] items-center justify-center rounded-full bg-[#f97316] px-1 text-[10px] font-bold" aria-label="จำนวนสินค้าในตะกร้า"> 0 </span> </button> <button id="profile-icon-btn" type="button" class="flex flex-col items-center gap-0.5 text-xs font-semibold" aria-label="โปรไฟล์">
       <svg class="w-5 h-5" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M20 21V19C20 17.9391 19.5786 16.9217 18.8284 16.1716C18.0783 15.4214 17.0609 15 16 15H8C6.93913 15 5.92172 15.4214 5.17157 16.1716C4.42143 16.9217 4 17.9391 4 19V21" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
       </svg><span class="text-[10px]">โปรไฟล์</span> </button>
     </div>
    </header><!-- MAIN CONTENT -->
    <main id="main-content" class="flex-1 overflow-y-auto px-3 pt-3 pb-20" role="main"><!-- SECTION: PRODUCT LIST -->
     <section id="section-home" class="space-y-3" aria-label="รายการสินค้า">
      <header class="px-1">
       <h2 id="home-heading" class="text-base font-semibold text-[#7dd3fc] mb-0.5">สินค้าแ���ะนำ</h2>
       <p class="text-xs text-slate-300">แตะที่สินค้าเพื่อดูรายละเอียด หรือเพิ่มลงตะกร้าได้ทันที</p>
      </header>
      <div id="product-grid" class="grid grid-cols-2 gap-3"><!-- Product cards will be injected here -->
      </div>
     </section><!-- SECTION: PRODUCT DETAIL -->
     <section id="section-detail" class="hidden space-y-4" aria-label="รายละเอียดสินค้า"><button id="back-to-home-from-detail" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปหน้าสินค้า</span> </button>
      <article class="rounded-2xl bg-[#020617] border border-sky-900/40 shadow-lg overflow-hidden">
       <div id="detail-visual" class="h-40 flex items-center justify-center bg-gradient-to-br from-sky-500/40 via-sky-700/40 to-sky-900/60" aria-hidden="true"><span id="detail-emoji" class="text-5xl"> ⭐ </span>
       </div>
       <div class="p-4 space-y-2">
        <div class="flex items-start justify-between gap-3">
         <div>
          <h2 id="detail-name" class="text-base font-semibold text-white">ชื่อสินค้า</h2>
          <p id="detail-short" class="text-xs text-slate-300 mt-1">คำอธิบายสั้น ๆ ของสินค้า</p>
         </div>
         <p id="detail-price" class="text-sm font-bold text-sky-300">฿0</p>
        </div>
        <p id="detail-long" class="mt-1 text-xs text-slate-300">รายละเอียดสินค้าแบบเต็มจะแสดงที่นี่</p>
        <div class="mt-3 flex items-center justify-between gap-3">
         <div class="text-xs text-slate-400"><span>สถานะ: </span> <span class="font-semibold text-emerald-300">พร้อมส่ง</span>
         </div><button id="detail-add-to-cart" type="button" class="inline-flex flex-1 justify-center items-center gap-1 rounded-xl bg-[#0ea5e9] px-3 py-2 text-xs font-semibold text-white hover:bg-[#0284c7] transition-colors"> + ใส่ในตะกร้า </button>
        </div>
       </div>
      </article>
     </section><!-- SECTION: CART -->
     <section id="section-cart" class="hidden space-y-4" aria-label="ตะกร้าสินค้า">
      <div class="flex items-center justify-between"><button id="back-to-home-from-cart" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>เลือกสินค้าต่อ</span> </button>
       <p class="text-xs text-slate-300">ในตะกร้า: <span id="cart-item-count-text">0 รายการ</span></p>
      </div>
      <div id="cart-empty-state" class="rounded-2xl border border-dashed border-sky-800 bg-slate-900/40 px-4 py-6 text-center text-xs text-slate-300">
       <p>ยังไม่มีสินค้าในตะกร้า</p>
       <p class="mt-1 text-[11px] text-slate-400">เลือกสินค้าจากหน้าหลักแล้วกด "เพิ่มในต���กร้า"</p>
      </div>
      <div id="cart-list" class="space-y-3"><!-- Cart items will be injected here -->
      </div>
      <div id="cart-actions" class="hidden space-y-3">
       <div class="rounded-2xl bg-[#020617] border border-sky-900/70 px-4 py-3">
        <div class="flex items-center justify-between text-sm"><span class="text-slate-300">ยอดรวมทั้งหมด</span> <span id="cart-total-price" class="text-lg font-bold text-sky-300">฿0</span>
        </div>
       </div><button id="proceed-to-checkout-btn" type="button" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-3 text-sm font-semibold text-white hover:bg-[#0284c7]"> ดำเนินการชำระเงิน </button>
      </div>
     </section><!-- SECTION: LOGIN -->
     <section id="section-login" class="hidden space-y-4" aria-label="เข้าสู่ระบบ">
      <header class="space-y-1 text-center">
       <h2 class="text-lg font-semibold text-[#7dd3fc]">เข้าสู่ระบบ</h2>
       <p class="text-xs text-slate-300">ยินดีต้อนรับกลับมา! กรุณาเข้าสู่ระบบเพื่อดำเนินการต่อ</p>
      </header>
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-4 space-y-4">
       <form id="login-form" class="space-y-3">
        <div><label for="login_email" class="block text-xs text-slate-300 mb-1"> อีเมล </label> <input id="login_email" name="login_email" type="email" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="example@email.com" required>
        </div>
        <div><label for="login_password" class="block text-xs text-slate-300 mb-1"> รหัสผ่าน </label> <input id="login_password" name="login_password" type="password" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="••••••••" required>
        </div><button type="submit" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-2.5 text-sm font-semibold text-white hover:bg-[#0284c7]"> เข้าสู่ระบบ </button>
       </form>
       <div class="text-center space-y-2">
        <p class="text-xs text-slate-400">ยังไม่มีบัญชี? <button id="go-to-register" type="button" class="text-sky-300 hover:text-sky-200 font-semibold"> สมัครสมาชิก </button></p>
        <p class="text-xs text-slate-400">หรือ <button id="go-to-seller-register" type="button" class="text-emerald-300 hover:text-emerald-200 font-semibold"> สมัครเป็นผู้ขาย </button></p>
       </div>
       <div class="mt-4 pt-3 border-t border-sky-900/40">
        <p class="text-center text-[11px] text-slate-400 mb-2">สำหรับผู้ดูแลระบบ</p>
        <div class="rounded-xl border border-amber-900/60 bg-amber-950/30 px-3 py-2">
         <p class="text-[11px] text-amber-200"><span class="font-semibold">🔐 เข้าสู่ระบบแอดมิน:</span></p>
         <p class="text-[11px] text-amber-300 mt-1">อีเมล: admin@shop.com<br>
           รหัสผ่าน: admin123</p>
        </div>
       </div>
      </article>
     </section><!-- SECTION: REGISTER -->
     <section id="section-register" class="hidden space-y-4" aria-label="สมัครสมาชิก">
      <header class="space-y-1 text-center">
       <h2 class="text-lg font-semibold text-[#7dd3fc]">สมัครสมาชิก</h2>
       <p class="text-xs text-slate-300">สร้างบัญชีใหม่เพื่อเริ่มต้นใช้งาน</p>
      </header>
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-4 space-y-4">
       <form id="register-form" class="space-y-3">
        <div><label for="register_name" class="block text-xs text-slate-300 mb-1"> ชื่อ-นามสกุล </label> <input id="register_name" name="register_name" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="เช่น สมชาย ใจดี" required>
        </div>
        <div><label for="register_email" class="block text-xs text-slate-300 mb-1"> อีเมล </label> <input id="register_email" name="register_email" type="email" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="example@email.com" required>
        </div>
        <div><label for="register_phone" class="block text-xs text-slate-300 mb-1"> เบอร์โทร </label> <input id="register_phone" name="register_phone" type="tel" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="08x-xxx-xxxx" required>
        </div>
        <div><label for="register_password" class="block text-xs text-slate-300 mb-1"> รหัสผ่าน </label> <input id="register_password" name="register_password" type="password" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="••••••••" required>
        </div>
        <div><label for="register_confirm_password" class="block text-xs text-slate-300 mb-1"> ยืนยันรหัสผ่าน </label> <input id="register_confirm_password" name="register_confirm_password" type="password" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="••••••••" required>
        </div><button type="submit" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-2.5 text-sm font-semibold text-white hover:bg-[#0284c7]"> สมัครสมาชิก </button>
       </form>
       <div class="text-center">
        <p class="text-xs text-slate-400">มีบัญชีอยู่แล้ว? <button id="go-to-login" type="button" class="text-sky-300 hover:text-sky-200 font-semibold"> เข้าสู่ระบบ </button></p>
       </div>
      </article>
     </section><!-- SECTION: SELLER REGISTER -->
     <section id="section-seller-register" class="hidden space-y-4" aria-label="สมัครเป็นผู้ข���ย"><button id="back-to-login-from-seller" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปหน้าเข้าสู่ระบบ</span> </button>
      <header class="space-y-1 text-center">
       <h2 class="text-lg font-semibold text-[#7dd3fc]">สมัครเป็นผู้ขาย</h2>
       <p class="text-xs text-slate-300">เปิดร้านค้าออนไลน์ของคุณเอง</p>
      </header>
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-4 space-y-4">
       <form id="seller-register-form" class="space-y-3">
        <div><label for="seller_shop_name" class="block text-xs text-slate-300 mb-1"> ชื่อร้านค้า </label> <input id="seller_shop_name" name="seller_shop_name" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="เช่น ร้านของดีมีคุณภาพ" required>
        </div>
        <div><label for="seller_name" class="block text-xs text-slate-300 mb-1"> ชื่อ-นามสกุล (เจ้าของร้าน) </label> <input id="seller_name" name="seller_name" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="เช่น สมชาย ใจดี" required>
        </div>
        <div><label for="seller_email" class="block text-xs text-slate-300 mb-1"> อีเมล </label> <input id="seller_email" name="seller_email" type="email" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="example@email.com" required>
        </div>
        <div><label for="seller_phone" class="block text-xs text-slate-300 mb-1"> ���บอร์โทรศัพท์ </label> <input id="seller_phone" name="seller_phone" type="tel" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="08x-xxx-xxxx" required>
        </div>
        <div><label for="seller_address" class="block text-xs text-slate-300 mb-1"> ที่อยู่ร้านค้า </label> <textarea id="seller_address" name="seller_address" rows="3" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="ระบุที่อยู่ร้านค้าอย่างละเอียด" required></textarea>
        </div>
        <div><label for="seller_tax_id" class="block text-xs text-slate-300 mb-1"> เลขประจำตัวผู้เสียภาษี (ถ้ามี) </label> <input id="seller_tax_id" name="seller_tax_id" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="13 หลัก (ไม่บังคับ)">
        </div>
        <div><label for="seller_password" class="block text-xs text-slate-300 mb-1"> รหัสผ่าน </label> <input id="seller_password" name="seller_password" type="password" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="••••••••" required>
        </div>
        <div><label for="seller_confirm_password" class="block text-xs text-slate-300 mb-1"> ยืนยันรหัสผ่าน </label> <input id="seller_confirm_password" name="seller_confirm_password" type="password" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="••••••••" required>
        </div>
        <div class="rounded-xl border border-emerald-900/60 bg-emerald-950/30 px-3 py-2">
         <p class="text-[11px] text-emerald-200"><span class="font-semibold">💡 สิทธิประโยชน์ผู้ขาย:</span></p>
         <ul class="mt-1 text-[11px] text-emerald-300 space-y-0.5 list-disc list-inside">
          <li>เปิดร้านค้าออนไลน์ฟรี</li>
          <li>จัดการสินค้าและคำสั่งซื้อ</li>
          <li>ระบบรายงานยอดขาย</li>
          <li>รับเงินตรงเข้าบัญชี</li>
         </ul>
        </div><button type="submit" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-2.5 text-sm font-semibold text-white hover:bg-[#0284c7]"> สมัครเป็นผู้ขาย </button>
       </form>
       <div class="text-center">
        <p class="text-xs text-slate-400">มีบัญชีอยู่แล้ว? <button id="go-to-login-from-seller" type="button" class="text-sky-300 hover:text-sky-200 font-semibold"> เข้าสู่ระบบ </button></p>
       </div>
      </article>
     </section><!-- SECTION: PROFILE (LOGGED IN) -->
     <section id="section-profile" class="hidden space-y-4" aria-label="โปรไฟล์">
      <header class="space-y-1">
       <h2 class="text-base font-semibold text-[#7dd3fc]">โปรไฟล์ของฉัน</h2>
       <p class="text-xs text-slate-300">ข้อมูลส่วนตัวและการตั้งค่าบัญชี</p>
      </header><!-- Profile Card -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-4 space-y-4">
       <div class="flex items-center gap-3">
        <div class="w-16 h-16 rounded-full bg-gradient-to-br from-sky-500/40 via-sky-700/40 to-sky-900/60 flex items-center justify-center"><span class="text-3xl">👤</span>
        </div>
        <div class="flex-1">
         <h3 id="profile-name" class="text-sm font-semibold text-white">ผู้ใช้งาน</h3>
         <p id="profile-email" class="text-xs text-slate-300 mt-0.5">user@example.com</p>
        </div>
       </div>
       <div class="space-y-2">
        <div class="flex items-center justify-between py-2 border-b border-sky-900/40"><span class="text-xs text-slate-300">ชื่อ-นามสกุล</span> <span id="profile-fullname" class="text-xs text-white font-medium">ยังไม่ได้ระบุ</span>
        </div>
        <div class="flex items-center justify-between py-2 border-b border-sky-900/40"><span class="text-xs text-slate-300">เบอร์โทร</span> <span id="profile-phone" class="text-xs text-white font-medium">ยังไม่ได้ระบุ</span>
        </div>
       </div><button id="edit-profile-btn" type="button" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-2 text-xs font-semibold text-white hover:bg-[#0284c7]"> แก้ไขข้อมูล </button>
      </article><!-- Saved Addresses -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <div class="flex items-center justify-between">
        <h3 class="text-xs font-semibold text-sky-200">ที่อยู่ที่บันทึกไว้</h3><button id="add-address-btn" type="button" class="text-xs text-sky-300 hover:text-sky-200 font-semibold"> + เพิ่มที่อยู่ </button>
       </div>
       <div id="saved-addresses-list" class="space-y-2">
        <div class="text-center py-4">
         <p class="text-xs text-slate-300">ยังไม่มีที่อยู่ที่บันทึกไว้</p>
         <p class="text-[11px] text-slate-400 mt-1">เพิ่มที่อยู่��พื่อความสะดวกในการสั่งซื้อ</p>
        </div>
       </div>
      </article><!-- Order History -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <h3 class="text-xs font-semibold text-sky-200">ประวัติการสั่งซื้อ</h3>
       <div class="text-center py-4">
        <p class="text-xs text-slate-300">ยังไม่มีประวัติการสั่งซื้อ</p>
        <p class="text-[11px] text-slate-400 mt-1">เมื่อคุณสั่งซื้อสินค้า ประวัติจะแสดงที่นี่</p>
       </div>
      </article><!-- Settings -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <h3 class="text-xs font-semibold text-sky-200">การตั้งค่า</h3>
       <div class="space-y-2"><button type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>การแจ้งเตือน</span> <span>›</span> </button> <button type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>ความเป็นส่วนตัว</span> <span>›</span> </button> <button type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>ช่วยเหลือและสนับสนุน</span> <span>›</span> </button> <button id="logout-btn" type="button" class="w-full flex items-center justify-between py-2 text-xs text-rose-300 hover:text-rose-200"> <span>ออกจากระบบ</span> <span>›</span> </button>
       </div>
      </article>
     </section><!-- SECTION: ADD/EDIT ADDRESS -->
     <section id="section-address-form" class="hidden space-y-4" aria-label="เพิ่มที่อยู่"><button id="back-to-profile-from-address" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปโปรไฟล์</span> </button>
      <header class="space-y-1">
       <h2 id="address-form-title" class="text-base font-semibold text-[#7dd3fc]">เพิ่มที่อยู่ใหม่</h2>
       <p class="text-xs text-slate-300">กรอกข้อมูลที่อยู่เพื่อความสะดวกในการสั่งซื้อ</p>
      </header>
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-4 space-y-4">
       <form id="address-form" class="space-y-3">
        <div><label for="address_label" class="block text-xs text-slate-300 mb-1"> ชื่อที่อยู่ (เช่น บ้าน, ที่ทำงาน) </label> <input id="address_label" name="address_label" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="เช่น บ้าน" required>
        </div>
        <div><label for="address_name" class="block text-xs text-slate-300 mb-1"> ชื่อผู้รับ </label> <input id="address_name" name="address_name" type="text" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="เช่�� สมชาย ใจดี" required>
        </div>
        <div><label for="address_phone" class="block text-xs text-slate-300 mb-1"> เบอร์โทร </label> <input id="address_phone" name="address_phone" type="tel" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="08x-xxx-xxxx" required>
        </div>
        <div><label for="address_detail" class="block text-xs text-slate-300 mb-1"> ที่อยู่ (บ้านเลขที่, ถนน, เขต/อำเภอ, จังหวั��, รหัสไปรษณีย์) </label> <textarea id="address_detail" name="address_detail" rows="4" class="w-full rounded-xl border border-sky-900/70 bg-slate-900/60 px-3 py-2 text-xs text-white placeholder:text-slate-500 focus:border-sky-400 focus:ring-0" placeholder="ระบุที่อยู่อย่างละเอียด" required></textarea>
        </div>
        <div class="flex gap-2"><button id="cancel-address-btn" type="button" class="flex-1 rounded-xl border border-sky-800 bg-slate-900/60 px-4 py-2.5 text-sm font-semibold text-sky-200 hover:bg-slate-900"> ยกเลิก </button> <button type="submit" class="flex-1 rounded-xl bg-[#0ea5e9] px-4 py-2.5 text-sm font-semibold text-white hover:bg-[#0284c7]"> บันทึกที่อยู่ </button>
        </div>
       </form>
      </article>
     </section><!-- SECTION: ADMIN DASHBOARD -->
     <section id="section-admin" class="hidden space-y-4" aria-label="แดชบอร์ดแอดมิน">
      <header class="space-y-1">
       <h2 class="text-base font-semibold text-[#7dd3fc]">แดชบอร์ดแอดมิน</h2>
       <p class="text-xs text-slate-300">จัดการสินค้า คำสั่งซื้อ และผู้ใช้งาน</p>
      </header><!-- Stats Cards -->
      <div class="grid grid-cols-2 gap-3">
       <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3">
        <div class="flex items-center gap-2"><span class="text-2xl">📦</span>
         <div>
          <p class="text-xs text-slate-300">สินค้าทั้งหมด</p>
          <p id="admin-total-products" class="text-lg font-bold text-sky-300">30</p>
         </div>
        </div>
       </article>
       <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3">
        <div class="flex items-center gap-2"><span class="text-2xl">🛒</span>
         <div>
          <p class="text-xs text-slate-300">คำสั่งซื้อ</p>
          <p id="admin-total-orders" class="text-lg font-bold text-emerald-300">0</p>
         </div>
        </div>
       </article>
       <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3">
        <div class="flex items-center gap-2"><span class="text-2xl">👥</span>
         <div>
          <p class="text-xs text-slate-300">ผู้ใช้งาน</p>
          <p id="admin-total-users" class="text-lg font-bold text-purple-300">0</p>
         </div>
        </div>
       </article>
       <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3">
        <div class="flex items-center gap-2"><span class="text-2xl">💰</span>
         <div>
          <p class="text-xs text-slate-300">ยอดขาย</p>
          <p id="admin-total-revenue" class="text-lg font-bold text-amber-300">฿0</p>
         </div>
        </div>
       </article>
      </div><!-- Quick Actions -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <h3 class="text-xs font-semibold text-sky-200">การจัดการ</h3>
       <div class="space-y-2"><button id="admin-manage-products-btn" type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>📦 จัดการสินค้า</span> <span>›</span> </button> <button id="admin-manage-orders-btn" type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>🛒 จัดการคำสั่งซื้อ</span> <span>›</span> </button> <button id="admin-manage-users-btn" type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>👥 จัดการผู้ใช้งาน</span> <span>›</span> </button> <button id="admin-settings-btn" type="button" class="w-full flex items-center justify-between py-2 text-xs text-slate-200 hover:text-white"> <span>⚙️ ตั้งค่าระบบ</span> <span>›</span> </button>
       </div>
      </article><!-- Recent Activity -->
      <article class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <h3 class="text-xs font-semibold text-sky-200">กิจกรรมล่าสุด</h3>
       <div id="admin-recent-activity" class="space-y-2">
        <div class="text-center py-4">
         <p class="text-xs text-slate-300">ยังไม่มีกิจกรรม</p>
        </div>
       </div>
      </article><button id="admin-logout-btn" type="button" class="w-full rounded-xl border border-rose-800 bg-rose-900/20 px-4 py-2.5 text-sm font-semibold text-rose-300 hover:bg-rose-900/40"> ออกจากระบบแอดมิน </button>
     </section><!-- SECTION: ADMIN MANAGE PRODUCTS -->
     <section id="section-admin-products" class="hidden space-y-4" aria-label="จัดการสินค้า"><button id="back-to-admin-from-products" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปแดชบอร์ด</span> </button>
      <header class="flex items-center justify-between">
       <div>
        <h2 class="text-base font-semibold text-[#7dd3fc]">จัดการสินค้า</h2>
        <p class="text-xs text-slate-300">แก้ไข เพิ่ม หรือลบสินค้า</p>
       </div><button id="admin-add-product-btn" type="button" class="rounded-xl bg-[#0ea5e9] px-3 py-2 text-xs font-semibold text-white hover:bg-[#0284c7]"> + เพิ่มสินค้า </button>
      </header>
      <div id="admin-products-list" class="space-y-3"><!-- Products will be rendered here -->
      </div>
     </section><!-- SECTION: ADMIN MANAGE ORDERS -->
     <section id="section-admin-orders" class="hidden space-y-4" aria-label="จัดการคำสั่งซื้อ"><button id="back-to-admin-from-orders" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปแดชบอร์ด</span> </button>
      <header>
       <h2 class="text-base font-semibold text-[#7dd3fc]">จัดการคำสั่งซื้อ</h2>
       <p class="text-xs text-slate-300">ดูและจัดการคำสั่งซื้อทั้งหมด</p>
      </header>
      <div id="admin-orders-list" class="space-y-3">
       <div class="text-center py-8 rounded-2xl bg-[#020617] border border-sky-900/60">
        <p class="text-xs text-slate-300">ยังไม่มีคำสั่งซื้อ</p>
        <p class="text-[11px] text-slate-400 mt-1">คำสั่งซื้อจะแสดงที่นี่เมื่อมีลูกค้าสั่งซื้อสินค้า</p>
       </div>
      </div>
     </section><!-- SECTION: ADMIN MANAGE USERS -->
     <section id="section-admin-users" class="hidden space-y-4" aria-label="จัดการผู้ใช้งาน"><button id="back-to-admin-from-users" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปแดชบอร์ด</span> </button>
      <header>
       <h2 class="text-base font-semibold text-[#7dd3fc]">จัดการผู้ใช้งาน</h2>
       <p class="text-xs text-slate-300">ดูและจัดการผู้ใช้งานทั้งหมด</p>
      </header>
      <div id="admin-users-list" class="space-y-3">
       <div class="text-center py-8 rounded-2xl bg-[#020617] border border-sky-900/60">
        <p class="text-xs text-slate-300">ยังไม่มีผู้ใช้งาน</p>
        <p class="text-[11px] text-slate-400 mt-1">ผู้ใช้งานที่สมัครจะแสดงที่นี่</p>
       </div>
      </div>
     </section><!-- SECTION: CHECKOUT -->
     <section id="section-checkout" class="hidden space-y-4" aria-label="เช็คเอาต์"><button id="back-to-cart-from-checkout" type="button" class="inline-flex items-center gap-1 text-xs text-sky-300 hover:text-sky-200"> <span class="inline-block rotate-180">➜</span> <span>กลับไปตะกร้า</span> </button>
      <header class="space-y-1">
       <h2 id="checkout-heading" class="text-base font-semibold text-[#7dd3fc]">เช็คเอาต์ &amp; ชำระเงิน (ตัวอย่าง)</h2>
       <p id="checkout-subheading" class="text-xs text-slate-300">เลือกที่อยู่จัดส่งและยืนยันคำสั่งซื้อ (ไม่มีการชำระเงินจริง)</p>
      </header><!-- Select Address -->
      <section class="rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 space-y-3">
       <div class="flex items-center justify-between">
        <h3 class="text-xs font-semibold text-sky-200">เลือกที่อยู่จัดส่ง</h3><button id="add-address-from-checkout-btn" type="button" class="text-xs text-sky-300 hover:text-sky-200 font-semibold"> + เพิ่มที่อยู�� </button>
       </div>
       <div id="checkout-address-list" class="space-y-2">
        <div class="text-center py-4">
         <p class="text-xs text-slate-300">ยังไม่มีที่อยู่ที่บันทึกไว้</p>
         <p class="text-[11px] text-slate-400 mt-1">กรุณาเพิ่มที่อยู่เพื่อดำเนินการต่อ</p>
        </div>
       </div>
      </section><!-- Order summary -->
      <section class="rounded-2xl bg-[#020617] border border-sky-900/70 px-4 py-3 space-y-3">
       <h3 id="order-summary-label" class="text-xs font-semibold text-sky-200">สรุปคำสั่งซื้อ</h3>
       <div id="checkout-summary-items" class="space-y-2 text-xs text-slate-200"><!-- summary lines -->
       </div>
       <div class="mt-2 flex items-center justify-between text-xs font-semibold"><span class="text-slate-300">ยอดรวมทั้งหมด</span> <span id="checkout-total" class="text-sky-300"> ฿0 </span>
       </div>
       <div class="mt-2 rounded-xl border border-dashed border-sky-900 px-3 py-2 text-[11px] text-slate-300">
        <p class="font-semibold text-sky-200">ชำระเงิน (ตัวอย่าง)</p>
        <p class="mt-1 text-[11px] text-slate-400">ส่วนนี้เป็นการจำลองขั้นตอนการชำระเงินเท่านั้น ไม่มีการตัดบัตรหรือโอนเงินจริงใด ๆ</p>
       </div><button id="place-order-btn" type="button" class="w-full rounded-xl bg-[#0ea5e9] px-4 py-3 text-sm font-semibold text-white hover:bg-[#0284c7]"> ยืนยันคำสั่งซื้อ (ตัวอย่าง) </button>
      </section>
     </section>
    </main><!-- FOOTER FIXED NAV BAR -->
    <footer id="footer-bar" class="fixed left-1/2 bottom-3 -translate-x-1/2 w-full max-w-md px-3">
     <div class="flex items-center justify-center gap-3 rounded-2xl bg-[#020617]/95 border border-sky-900/70 px-4 py-3 shadow-[0_18px_45px_rgba(0,0,0,0.7)] backdrop-blur"><button id="footer-home-btn" type="button" class="flex-1 flex flex-col items-center gap-1 text-sky-300 hover:text-sky-200">
       <svg class="w-6 h-6" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M3 9L12 2L21 9V20C21 20.5304 20.7893 21.0391 20.4142 21.4142C20.0391 21.7893 19.5304 22 19 22H5C4.46957 22 3.96086 21.7893 3.58579 21.4142C3.21071 21.0391 3 20.5304 3 20V9Z" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <path d="M9 22V12H15V22" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
       </svg><span class="text-xs font-semibold">HOME</span> </button> <button id="footer-profile-btn" type="button" class="flex-1 flex flex-col items-center gap-1 text-sky-300 hover:text-sky-200">
       <svg class="w-6 h-6" viewbox="0 0 24 24" fill="none" aria-hidden="true"><path d="M20 21V19C20 17.9391 19.5786 16.9217 18.8284 16.1716C18.0783 15.4214 17.0609 15 16 15H8C6.93913 15 5.92172 15.4214 5.17157 16.1716C4.42143 16.9217 4 17.9391 4 19V21" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" /> <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
       </svg><span class="text-xs font-semibold">โปรไฟล์</span> </button>
     </div>
    </footer><!-- TOAST / INLINE MESSAGE -->
    <div id="toast" class="pointer-events-none fixed inset-x-0 bottom-20 flex justify-center px-4 opacity-0 transition-opacity duration-200" aria-live="polite">
     <div id="toast-inner" class="max-w-xs rounded-xl bg-slate-900/95 px-3 py-2 text-[11px] text-slate-50 shadow-lg border border-sky-700/70"><!-- text set via JS -->
     </div>
    </div>
   </div>
  </div>
  <script>
    // ------- CONFIG & ELEMENT SDK SETUP --------
    const defaultConfig = {
      background_color: "#0b1220",
      surface_color: "#020617",
      text_color: "#e5e7eb",
      primary_action_color: "#0ea5e9",
      secondary_action_color: "#f97316",
      font_family: "Segoe UI",
      font_size: 14,

      shop_title: "ร้านค้าออนไลน์",
      shop_tagline: "เลือกสินค้า ใส่ตะกร้า และชำระเงินในหน้าเดียว",
      home_heading: "สินค้าแนะนำ",
      checkout_heading: "เช็คเอาต์ & ชำระเงิน (ตัวอย่าง)",
      checkout_subheading:
        "เลือกที่อยู่จัดส่งและยืนยันคำสั่งซื้อ (ไม่มีการชำระเงินจริง)",
      customer_info_label: "ข้อมูลลูกค้า",
      shipping_info_label: "ที่อยู่จัดส่ง",
      order_summary_label: "สรุปคำสั่งซื้อ",
      place_order_button_text: "ยืนยันคำสั่งซื้อ (ตัวอย่าง)",
      footer_note: "ส่วนนี้เป็นตัวอย่างหน้าร้านค้าออนไลน์เท่านั้น"
    };

    function applyConfigToUI(config) {
      const cfg = Object.assign({}, defaultConfig, config || {});
      const root = document.getElementById("app-shell");

      const baseFontStack = "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif";
      const fontFamily = cfg.font_family || defaultConfig.font_family;
      const baseSize = cfg.font_size || defaultConfig.font_size;

      if (root) {
        root.style.backgroundColor =
          cfg.background_color || defaultConfig.background_color;
        root.style.color = cfg.text_color || defaultConfig.text_color;
        root.style.fontFamily = fontFamily + ", " + baseFontStack;
        root.style.fontSize = baseSize + "px";
      }

      const appRoot = document.getElementById("app-root");
      if (appRoot) {
        appRoot.style.backgroundColor =
          cfg.background_color || defaultConfig.background_color;
      }

      const surfaces = document.querySelectorAll(
        ".bg-surface-dynamic, .surface-panel"
      );
      surfaces.forEach((el) => {
        el.style.backgroundColor = cfg.surface_color || defaultConfig.surface_color;
      });

      const header = document.querySelector("header");
      if (header) {
        header.style.backgroundColor =
          cfg.primary_action_color || defaultConfig.primary_action_color;
      }

      const textEls = document.querySelectorAll(".dynamic-text");
      textEls.forEach((el) => {
        el.style.color = cfg.text_color || defaultConfig.text_color;
      });

      const primaryButtons = document.querySelectorAll(".btn-primary-main");
      primaryButtons.forEach((btn) => {
        btn.style.backgroundColor =
          cfg.primary_action_color || defaultConfig.primary_action_color;
      });

      const secondaryEls = document.querySelectorAll(".accent-secondary");
      secondaryEls.forEach((el) => {
        el.style.backgroundColor =
          cfg.secondary_action_color ||
          defaultConfig.secondary_action_color;
      });

      const titleEl = document.getElementById("shop-title");
      const taglineEl = document.getElementById("shop-tagline");
      const homeHeadingEl = document.getElementById("home-heading");
      const checkoutHeadingEl = document.getElementById("checkout-heading");

      if (titleEl) titleEl.style.fontSize = baseSize * 1.1 + "px";
      if (taglineEl) taglineEl.style.fontSize = baseSize * 0.75 + "px";
      if (homeHeadingEl) homeHeadingEl.style.fontSize = baseSize * 1.1 + "px";
      if (checkoutHeadingEl)
        checkoutHeadingEl.style.fontSize = baseSize * 1.1 + "px";

      const smallLabels = document.querySelectorAll(".text-xs, .text-[11px]");
      smallLabels.forEach((el) => {
        el.style.fontSize = baseSize * 0.8 + "px";
      });

      const bodyText = document.querySelectorAll(".body-text");
      bodyText.forEach((el) => {
        el.style.fontSize = baseSize + "px";
      });

      const textMap = {
        "shop-title": "shop_title",
        "shop-tagline": "shop_tagline",
        "home-heading": "home_heading",
        "checkout-heading": "checkout_heading",
        "checkout-subheading": "checkout_subheading",
        "customer-info-label": "customer_info_label",
        "shipping-info-label": "shipping_info_label",
        "order-summary-label": "order_summary_label"
      };

      Object.keys(textMap).forEach((id) => {
        const key = textMap[id];
        const el = document.getElementById(id);
        if (el) {
          el.textContent = cfg[key] || defaultConfig[key];
        }
      });

      const placeOrderBtn = document.getElementById("place-order-btn");
      if (placeOrderBtn) {
        placeOrderBtn.textContent =
          cfg.place_order_button_text ||
          defaultConfig.place_order_button_text;
      }
    }

    (function initElementSdk() {
      if (!window.elementSdk) {
        applyConfigToUI(defaultConfig);
        return;
      }

      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (config) => {
          applyConfigToUI(config);
        },
        mapToCapabilities: (config) => {
          const cfg = config || defaultConfig;

          const recolorables = [
            {
              get: () => cfg.background_color || defaultConfig.background_color,
              set: (value) => {
                cfg.background_color = value;
                window.elementSdk.setConfig({ background_color: value });
              }
            },
            {
              get: () => cfg.surface_color || defaultConfig.surface_color,
              set: (value) => {
                cfg.surface_color = value;
                window.elementSdk.setConfig({ surface_color: value });
              }
            },
            {
              get: () => cfg.text_color || defaultConfig.text_color,
              set: (value) => {
                cfg.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () =>
                cfg.primary_action_color ||
                defaultConfig.primary_action_color,
              set: (value) => {
                cfg.primary_action_color = value;
                window.elementSdk.setConfig({
                  primary_action_color: value
                });
              }
            },
            {
              get: () =>
                cfg.secondary_action_color ||
                defaultConfig.secondary_action_color,
              set: (value) => {
                cfg.secondary_action_color = value;
                window.elementSdk.setConfig({
                  secondary_action_color: value
                });
              }
            }
          ];

          const fontEditable = {
            get: () => cfg.font_family || defaultConfig.font_family,
            set: (value) => {
              cfg.font_family = value;
              window.elementSdk.setConfig({ font_family: value });
            }
          };

          const fontSizeable = {
            get: () => cfg.font_size || defaultConfig.font_size,
            set: (value) => {
              cfg.font_size = value;
              window.elementSdk.setConfig({ font_size: value });
            }
          };

          return {
            recolorables,
            borderables: [],
            fontEditable,
            fontSizeable
          };
        },
        mapToEditPanelValues: (config) => {
          const cfg = Object.assign({}, defaultConfig, config || {});
          return new Map([
            ["shop_title", cfg.shop_title],
            ["shop_tagline", cfg.shop_tagline],
            ["home_heading", cfg.home_heading],
            ["checkout_heading", cfg.checkout_heading],
            ["checkout_subheading", cfg.checkout_subheading],
            ["customer_info_label", cfg.customer_info_label],
            ["shipping_info_label", cfg.shipping_info_label],
            ["order_summary_label", cfg.order_summary_label],
            ["place_order_button_text", cfg.place_order_button_text],
            ["footer_note", cfg.footer_note]
          ]);
        }
      });
    })();

    // ------- APP STATE --------
    let isLoggedIn = false;
    let currentUser = null;
    let savedAddresses = [];
    let selectedAddressId = null;
    let editingAddressId = null;
    let isAdmin = false;

    // Admin credentials (for demo purposes)
    const ADMIN_EMAIL = "admin@shop.com";
    const ADMIN_PASSWORD = "admin123";

    const products = [
      {
        id: "p1",
        name: "แก้วน้ำสเตนเลสมินิมอล",
        short: "เก็บอุณหภูมิได้ยาวนาน ดีไซน์เรียบหรู",
        long: "แก้วน้ำสเตนเลสขนาด 420 มล. ฝาปิดซิลิโคนเกรดอาหาร เก็บความเย็นได้นานถึง 8 ชม. และความร้อนได้นานถึง 4 ชม.",
        price: 290,
        emoji: "🥤"
      },
      {
        id: "p2",
        name: "สมุดโน้ตปกผ้า",
        short: "กระดาษเนื้อดี เขียนไม่ซึม",
        long: "สมุดโน้ตปกผ้าขนาด A5 จำนวน 160 หน้า เย็บเล่มแบบด้าย เปิดกางแล้วไม่เด���ง เหมาะสำหรับจดงานหรือ bullet journal",
        price: 180,
        emoji: "📓"
      },
      {
        id: "p3",
        name: "เทียนหอมกลิ่นลาเวนเดอร์",
        short: "ให้ความผ่อนคลายก่อนนอน",
        long: "เทียนหอมทำจากขี้ผึ้งธรรมชาติ กลิ่นลาเวนเดอร์จากน้ำมันหอมระเหยธรรมชาติ ให้กลิ่นหอมละมุน ไม่แสบจมูก",
        price: 220,
        emoji: "🕯️"
      },
      {
        id: "p4",
        name: "ถุงผ้ารักษ์โลก",
        short: "เหนียว ทน พับเก็บง่าย",
        long: "ถุงผ้าคอตตอนลายเรียบ น้ำหนักเบา รับน้ำหนักได้ถึง 10 กิโลกรัม ซักทำความสะอาดได้ ใช้ซ้ำได้หลายครั้ง",
        price: 150,
        emoji: "🛍️"
      },
      {
        id: "p5",
        name: "หูฟังบลูทูธไร้สาย",
        short: "เสียงใส คุณภาพสูง ใช้งานได้นาน",
        long: "หูฟังบลูทูธ 5.0 เสียงคุณภาพ HD พร้อมระบบตัดเสียงรบกวน แบตเตอรี่ใช้งานได้ 20 ชั่วโมง กันน้ำ IPX5",
        price: 890,
        emoji: "🎧"
      },
      {
        id: "p6",
        name: "��ระเป๋าสะพายหนัง PU",
        short: "ดีไซน์เรียบหรู จุของได้เยอะ",
        long: "กระเป๋าสะพายหนัง PU คุณภาพดี มีช่องใส่ของหลายช่อง ขนาดกำลังดี เหมาะกับการใช้งานประจำวัน",
        price: 650,
        emoji: "👜"
      },
      {
        id: "p7",
        name: "แว่นกันแดด UV400",
        short: "ป้องกันแสง UV ได้ 100%",
        long: "แว่นกันแดดเลนส์โพลาไรซ์ กรองแสง UV400 กรอบแข็งแรง น้ำหนักเบา สวมใส่สบาย พร้อมกล่องและผ้าเช็ด",
        price: 450,
        emoji: "🕶️"
      },
      {
        id: "p8",
        name: "ลำ��พงบลูทูธพกพา",
        short: "เสียงดัง ชัด เบสหนัก",
        long: "ลำโพ��บลูทูธกันน้ำ IPX7 กำลังขับ 10W เสียงเบสหนัก แบตเตอรี่ใช้งาน 12 ชั่วโมง เชื่อมต่อได้ 2 เครื่อง",
        price: 790,
        emoji: "🔊"
      },
      {
        id: "p9",
        name: "นาฬิกาข้อมือสมาร์ทวอทช์",
        short: "วัดชีพจร นับก้าว แจ้งเตือนข้อความ",
        long: "สมาร์ทวอทช์จอสัมผัส 1.4 นิ้ว วัดอัตราการเต้นหัวใจ นับก้าว วัดแคลอรี่ กันน้ำ IP68 แบตเตอรี่ 7 วัน",
        price: 1290,
        emoji: "⌚"
      },
      {
        id: "p10",
        name: "เมาส์ไร้สายเงียบ",
        short: "คลิกเงียบ ไม่รบกวน ใช้งานสบาย",
        long: "เมาส์ไร้สาย 2.4GHz ระบบคลิกเงียบ DPI ปรับได้ 800-1600 ประหยัดพลังงาน ใช้แบตเตอรี่��ด้นาน 12 เดือน",
        price: 320,
        emoji: "🖱️"
      },
      {
        id: "p11",
        name: "คีย์บอร์ดเมคคานิคอล",
        short: "สวิตช์ Blue ตอบสนองเร็ว เสียงคลิกชัด",
        long: "คีย์บอร์ดเมคคานิคอล 87 คีย์ สวิตช์ Blue ไฟ RGB ปรับได้หลายโหมด สายถอดได้ เหมาะสำหรับเกมและทำงาน",
        price: 1590,
        emoji: "⌨️"
      },
      {
        id: "p12",
        name: "แท่นชาร์จไร้สาย 3in1",
        short: "ชาร์จมือถือ นาฬิกา หูฟัง พร้อมกัน",
        long: "แท่นชาร์จไร้สาย 3 in 1 รองรับ iPhone, Apple Watch, AirPods ชาร์จเร็ว 15W ป��องกันความร้อนเกิน",
        price: 890,
        emoji: "🔌"
      },
      {
        id: "p13",
        name: "กระบอกน้ำแก้วสูญญากาศ",
        short: "เก็บความเย็น 24 ชม. ความร้อน 12 ชม.",
        long: "กระบอกน้ำแก้วสองชั้นสูญญากาศ ขนาด 750ml ปากกว้างใส่น้ำแข็งได้ ฝาเกลียวแน่น ไม่รั่วซึม",
        price: 390,
        emoji: "🍶"
      },
      {
        id: "p14",
        name: "หมอนหนุนคอเมมโมรี่โฟม",
        short: "รองรับทรงคอ นอนสบาย ลดอาการปว��คอ",
        long: "หมอนหนุนเมมโมรี่โฟมคุณภาพสูง ออกแบบตามหลักสรี���ะ ช่วยลดอาการปวดคอ ปลอกหมอนถอดซักได้",
        price: 590,
        emoji: "🛏️"
      },
      {
        id: "p15",
        name: "ไฟ LED แบบพกพา",
        short: "ปรับความสว่างได้ ชาร์จ USB",
        long: "��ฟ LED แบบพกพา 3 โหมดแสง ปรับความสว่างได้ แบตเตอรี่ในตัว ชาร์จ USB ใช้งานได้ 8 ชั่วโมง",
        price: 250,
        emoji: "💡"
      },
      {
        id: "p16",
        name: "ชุดแปรงแต่งหน้า 12 ชิ้น",
        short: "ขนนุ่ม ไม่ระคายผิว พร้อมกระเป๋า",
        long: "ชุดแปรงแต่งหน้าครบเซ็ต 12 ชิ้น ขนสังเคราะห์คุณภาพสูง นุ่มนวล ไม่ระคายผิว พร้อมกระเป๋าใส���แปรง",
        price: 490,
        emoji: "💄"
      },
      {
        id: "p17",
        name: "เครื่องชงกาแฟแบบพกพา",
        short: "ชงกาแฟได้ทุกที่ ไม่ต้องใช้ไฟฟ้า",
        long: "เครื่องชงกาแฟแบบกดมือ ขนาดพกพา ชงได้ทุกที่ ไม่ต้องใช้ไฟฟ้า วัสดุคุณภาพดี ทำความสะอาดง่าย",
        price: 680,
        emoji: "☕"
      },
      {
        id: "p18",
        name: "พัดลมมินิ USB",
        short: "เย็นสบาย เสียงเงียบ พกพาสะดวก",
        long: "พัดลมมินิ USB 3 ความเร็ว แบตเตอรี่ในตัว 2000mAh ใช้งานได้ 6 ชั่วโมง ปรับมุมได��� 360 องศา",
        price: 280,
        emoji: "🌀"
      },
      {
        id: "p19",
        name: "กล่องใส่อาหารสูญญากาศ",
        short: "เก็บอาหารสด ไม่ร���่วซึม ล้างง่าย",
        long: "กล่องใส่อาหารสูญญากาศ 3 ชิ้น ขนาด 500ml, 800ml, 1200ml ฝาล็อคแน่น ไม่รั่วซึม ใช้ไมโครเวฟได้",
        price: 420,
        emoji: "🍱"
      },
      {
        id: "p20",
        name: "ที่นอนโยคะ TPE",
        short: "หนา 6mm กันลื่น ไม่มีกลิ่น",
        long: "ที่นอนโยคะ TPE หนา 6mm พื้น��ิวกันลื่น ไม่มีกลิ่น น้ำหนักเบา พับเก็บง่าย พร้อมสายรัด",
        price: 590,
        emoji: "🧘"
      },
      {
        id: "p21",
        name: "ขาตั้งมือถือแบบยืดหยุ่น",
        short: "��รับมุมได้ 360 องศา ตั้งโต๊ะหรือหนีบได้",
        long: "ขาตั้งมือถือแบบยืดหยุ่น ปรับมุมได้รอบทิศทาง หนีบได้แน่น รองรับมือถือ 4-7 นิ้ว เหมาะสำหรับถ่ายคลิป",
        price: 350,
        emoji: "📱"
      },
      {
        id: "p22",
        name: "หมวกกันน็อคจักรยาน",
        short: "น้ำหนักเบา ระบายอากาศดี ปรับ���นาดได้",
        long: "หมวกกันน็อคจักรยาน มาตรฐาน CE ระบายอากาศดี น้ำหนักเบา ปรับขนาดได้ พร้อมไฟ LED ด้านหลัง",
        price: 890,
        emoji: "🚴"
      },
      {
        id: "p23",
        name: "กระติกน้ำร้อนสูญญากาศ",
        short: "เก็บความร้อน 24 ชม. ขนาด 1 ลิตร",
        long: "กระติกน้ำร้อนสูญญากาศ ขนาด 1 ลิตร เก็บความร้อนได้นาน 24 ชั่วโมง ฝาเป็นถ้วย เทสะดวก",
        price: 490,
        emoji: "🫖"
      },
      {
        id: "p24",
        name: "ชุดไขควงอเนกประสงค์",
        short: "ครบชุด 25 หัว พกพาสะ���วก",
        long: "ชุดไขควงอเนกประสงค์ 25 หัว เหมาะสำหรับซ่อมมือถือ แท็บเล็ต แล็ปท็อป วัสดุคุณภาพดี พร้อมกล่องเก็บ",
        price: 380,
        emoji: "🔧"
      },
      {
        id: "p25",
        name: "กระเป๋าเป้กันน้ำ",
        short: "จุของได้เยอะ มีช่อง USB ชาร์จมือถือ",
        long: "กระเป๋าเป้กันน้ำ ความจุ 30 ลิตร มีช่อง USB ชาร์จมือถือ ช่องใส่โน้ตบุ๊ค 15.6 นิ้ว สายสะพายนุ่ม",
        price: 890,
        emoji: "🎒"
      },
      {
        id: "p26",
        name: "เครื่องวัดความดันโลหิต",
        short: "วัดแม่นยำ จอใหญ่ อ่านง่าย",
        long: "เครื่องวัดความดันโลหิตดิจ��ตอล วัดแม่นยำ จอ LCD ใหญ่ บันทึกค่าได้ 99 ครั้ง พร้อมกระเป๋าใส่",
        price: 1290,
        emoji: "🩺"
      },
      {
        id: "p27",
        name: "ตาชั่งดิจิตอลครั���",
        short: "ชั่งได้ถึง 5 กก. แม่นยำ 1 กรัม",
        long: "ตาชั่งดิจิตอลครัว ชั่งได้ 5 กก. แม่นยำ 1 กรัม จอ LCD ใหญ่ ฟังก์ชันชั่งน้ำหนักสุทธิ ปิดอัตโนมัติ",
        price: 290,
        emoji: "⚖️"
      },
      {
        id: "p28",
        name: "ไฟฉายแบบชาร์จไฟได้",
        short: "แสงสว่างสูง 1000 ลูเมน กันน้ำ",
        long: "ไฟฉาย LED แสงสว่าง 1000 ลูเมน ชาร์จ USB ได้ กันน้ำ IPX6 ปรับโฟกัสได้ แบตเตอรี่ใช้งาน 10 ชั่วโมง",
        price: 590,
        emoji: "🔦"
      },
      {
        id: "p29",
        name: "หูฟังเกมมิ่ง RGB",
        short: "เสียงเซอร์ราวด์ 7.1 ไมค์ตัดเสียงรบกวน",
        long: "หูฟังเกมมิ่ง เสียงเซอร์ราวด์ 7.1 ไฟ RGB ปรับได้ ไมค์ตัดเสียงรบกวน น้ำหนักเบา สวมใส่สบาย",
        price: 1190,
        emoji: "🎮"
      },
      {
        id: "p30",
        name: "แผ่นรองเมาส์ขนาดใหญ่",
        short: "ขนาด 80x40cm พื้นผิวเรียบ ขอบเย็บ",
        long: "แผ่นรองเมาส์ขนาดใหญ่ 80x40cm พื้นผิวเรียบลื่น ฐานยางกันลื่น ขอบเย็บแน่น ทนทาน ล้างทำความสะอาดได้",
        price: 390,
        emoji: "🖥️"
      }
    ];

    let cart = [];
    let currentDetailId = null;

    function formatCurrency(num) {
      return "฿" + num.toLocaleString("th-TH");
    }

    function showSection(id) {
      const sections = [
        "section-home",
        "section-detail",
        "section-cart",
        "section-login",
        "section-register",
        "section-seller-register",
        "section-profile",
        "section-address-form",
        "section-checkout",
        "section-admin",
        "section-admin-products",
        "section-admin-orders",
        "section-admin-users"
      ];
      sections.forEach((sid) => {
        const el = document.getElementById(sid);
        if (!el) return;
        if (sid === id) {
          el.classList.remove("hidden");
        } else {
          el.classList.add("hidden");
        }
      });
    }

    function showToast(msg) {
      const toast = document.getElementById("toast");
      const inner = document.getElementById("toast-inner");
      if (!toast || !inner) return;
      inner.textContent = msg;
      toast.style.opacity = "1";
      setTimeout(() => {
        toast.style.opacity = "0";
      }, 1800);
    }

    function renderProducts() {
      const grid = document.getElementById("product-grid");
      if (!grid) return;
      grid.innerHTML = "";

      products.forEach((p) => {
        const card = document.createElement("article");
        card.className =
          "rounded-2xl bg-[#020617] border border-sky-900/60 shadow-lg overflow-hidden flex flex-col text-xs";
        card.setAttribute("data-id", p.id);

        const visual = document.createElement("div");
        visual.className =
          "h-28 flex items-center justify-center bg-gradient-to-br from-sky-500/40 via-sky-700/40 to-sky-900/60";
        visual.setAttribute("aria-hidden", "true");
        const emojiSpan = document.createElement("span");
        emojiSpan.textContent = p.emoji;
        emojiSpan.className = "text-4xl";
        visual.appendChild(emojiSpan);

        const body = document.createElement("div");
        body.className = "flex-1 p-3 flex flex-col gap-1";

        const nameRow = document.createElement("div");
        nameRow.className = "flex items-start justify-between gap-2";

        const nameEl = document.createElement("h3");
        nameEl.className = "text-[13px] font-semibold text-white";
        nameEl.textContent = p.name;

        const priceEl = document.createElement("p");
        priceEl.className = "text-xs font-bold text-sky-300";
        priceEl.textContent = formatCurrency(p.price);

        nameRow.appendChild(nameEl);
        nameRow.appendChild(priceEl);

        const shortEl = document.createElement("p");
        shortEl.className = "text-[11px] text-slate-300 line-clamp-2";
        shortEl.textContent = p.short;

        const btnRow = document.createElement("div");
        btnRow.className =
          "mt-2 flex items-center justify-between gap-2 text-[11px]";

        const detailBtn = document.createElement("button");
        detailBtn.type = "button";
        detailBtn.className =
          "flex-1 rounded-xl border border-sky-800 bg-slate-900/60 px-2 py-1 text-[11px] text-sky-200 hover:bg-slate-900";
        detailBtn.textContent = "ดูรายละเอียด";

        const addBtn = document.createElement("button");
        addBtn.type = "button";
        addBtn.className =
          "flex-1 rounded-xl bg-[#0ea5e9] px-2 py-1 text-[11px] font-semibold text-white hover:bg-[#0284c7]";
        addBtn.textContent = "+ เพิ่มลงตะกร้า";

        detailBtn.addEventListener("click", () => {
          openDetail(p.id);
        });
        addBtn.addEventListener("click", () => {
          addToCart(p.id);
          showToast("เพิ่ม \"" + p.name + "\" ลงในตะกร้าแล้ว");
        });

        btnRow.appendChild(detailBtn);
        btnRow.appendChild(addBtn);

        body.appendChild(nameRow);
        body.appendChild(shortEl);
        body.appendChild(btnRow);

        card.appendChild(visual);
        card.appendChild(body);

        grid.appendChild(card);
      });
    }

    function addToCart(productId) {
      const item = cart.find((c) => c.id === productId);
      if (item) {
        item.qty += 1;
      } else {
        cart.push({ id: productId, qty: 1 });
      }
      updateCartUI();
    }

    function updateCartItem(productId, delta) {
      const item = cart.find((c) => c.id === productId);
      if (!item) return;
      item.qty += delta;
      if (item.qty <= 0) {
        cart = cart.filter((c) => c.id !== productId);
      }
      updateCartUI();
    }

    function getCartStats() {
      let totalQty = 0;
      let totalPrice = 0;
      cart.forEach((item) => {
        const p = products.find((x) => x.id === item.id);
        if (!p) return;
        totalQty += item.qty;
        totalPrice += p.price * item.qty;
      });
      return { totalQty, totalPrice };
    }

    function updateCartUI() {
      const { totalQty, totalPrice } = getCartStats();

      const badge = document.getElementById("cart-count-badge");
      if (badge) badge.textContent = totalQty;

      const emptyState = document.getElementById("cart-empty-state");
      const cartList = document.getElementById("cart-list");
      const cartActions = document.getElementById("cart-actions");
      const cartTotalPrice = document.getElementById("cart-total-price");

      if (!emptyState || !cartList) return;

      if (totalQty === 0) {
        emptyState.classList.remove("hidden");
        cartList.innerHTML = "";
        if (cartActions) cartActions.classList.add("hidden");
      } else {
        emptyState.classList.add("hidden");
        if (cartActions) cartActions.classList.remove("hidden");
        if (cartTotalPrice) cartTotalPrice.textContent = formatCurrency(totalPrice);

        cartList.innerHTML = "";

        cart.forEach((item) => {
          const p = products.find((x) => x.id === item.id);
          if (!p) return;

          const row = document.createElement("article");
          row.className =
            "rounded-2xl bg-[#020617] border border-sky-900/60 px-3 py-3 flex items-start gap-3 text-xs";

          const visual = document.createElement("div");
          visual.className =
            "w-10 h-10 rounded-xl bg-gradient-to-br from-sky-500/40 via-sky-700/40 to-sky-900/60 flex items-center justify-center flex-shrink-0";
          const emojiSpan = document.createElement("span");
          emojiSpan.textContent = p.emoji;
          emojiSpan.className = "text-2xl";
          visual.appendChild(emojiSpan);

          const info = document.createElement("div");
          info.className = "flex-1 flex flex-col gap-1";

          const topRow = document.createElement("div");
          topRow.className = "flex items-start justify-between gap-2";

          const namePrice = document.createElement("div");
          namePrice.className = "flex flex-col gap-0.5";

          const nameEl = document.createElement("p");
          nameEl.className = "text-[13px] font-semibold text-white";
          nameEl.textContent = p.name;

          const priceEl = document.createElement("p");
          priceEl.className = "text-[11px] text-sky-300";
          priceEl.textContent = formatCurrency(p.price);

          namePrice.appendChild(nameEl);
          namePrice.appendChild(priceEl);

          const lineTotal = document.createElement("p");
          lineTotal.className = "text-[11px] font-semibold text-sky-200";
          lineTotal.textContent = formatCurrency(p.price * item.qty);

          topRow.appendChild(namePrice);
          topRow.appendChild(lineTotal);

          const qtyRow = document.createElement("div");
          qtyRow.className =
            "mt-1 flex items-center justify-between gap-2 text-[11px]";

          const qtyControls = document.createElement("div");
          qtyControls.className =
            "inline-flex items-center gap-1 rounded-full bg-slate-900/70 px-1 py-0.5";

          const minusBtn = document.createElement("button");
          minusBtn.type = "button";
          minusBtn.className =
            "w-6 h-6 flex items-center justify-center rounded-full text-slate-100 hover:bg-slate-800";
          minusBtn.textContent = "−";

          const qtyText = document.createElement("span");
          qtyText.className = "min-w-[18px] text-center";
          qtyText.textContent = item.qty;

          const plusBtn = document.createElement("button");
          plusBtn.type = "button";
          plusBtn.className =
            "w-6 h-6 flex items-center justify-center rounded-full text-slate-100 hover:bg-slate-800";
          plusBtn.textContent = "+";

          minusBtn.addEventListener("click", () => {
            updateCartItem(p.id, -1);
          });
          plusBtn.addEventListener("click", () => {
            updateCartItem(p.id, 1);
          });

          qtyControls.appendChild(minusBtn);
          qtyControls.appendChild(qtyText);
          qtyControls.appendChild(plusBtn);

          const removeBtn = document.createElement("button");
          removeBtn.type = "button";
          removeBtn.className =
            "text-[11px] text-rose-300 hover:text-rose-200";
          removeBtn.textContent = "ลบออก";
          removeBtn.addEventListener("click", () => {
            cart = cart.filter((c) => c.id !== p.id);
            updateCartUI();
          });

          qtyRow.appendChild(qtyControls);
          qtyRow.appendChild(removeBtn);

          info.appendChild(topRow);
          info.appendChild(qtyRow);

          row.appendChild(visual);
          row.appendChild(info);

          cartList.appendChild(row);
        });
      }

      renderCheckoutSummary();
    }

    function openDetail(productId) {
      const p = products.find((x) => x.id === productId);
      if (!p) return;
      currentDetailId = p.id;
      const nameEl = document.getElementById("detail-name");
      const shortEl = document.getElementById("detail-short");
      const longEl = document.getElementById("detail-long");
      const priceEl = document.getElementById("detail-price");
      const emojiEl = document.getElementById("detail-emoji");

      if (nameEl) nameEl.textContent = p.name;
      if (shortEl) shortEl.textContent = p.short;
      if (longEl) longEl.textContent = p.long;
      if (priceEl) priceEl.textContent = formatCurrency(p.price);
      if (emojiEl) emojiEl.textContent = p.emoji;

      showSection("section-detail");
    }

    function renderCheckoutSummary() {
      const container = document.getElementById("checkout-summary-items");
      const totalEl = document.getElementById("checkout-total");
      if (!container || !totalEl) return;

      const { totalQty, totalPrice } = getCartStats();
      container.innerHTML = "";

      if (totalQty === 0) {
        const p = document.createElement("p");
        p.className = "text-xs text-slate-300";
        p.textContent = "ยังไม่มีสินค้าในตะกร้า";
        container.appendChild(p);
        totalEl.textContent = formatCurrency(0);
        return;
      }

      cart.forEach((item) => {
        const prod = products.find((x) => x.id === item.id);
        if (!prod) return;
        const row = document.createElement("div");
        row.className = "flex items-center justify-between gap-2";

        const nameQty = document.createElement("div");
        nameQty.className = "flex items-center gap-2";

        const dot = document.createElement("span");
        dot.className = "text-[13px]";
        dot.textContent = "•";

        const label = document.createElement("span");
        label.className = "text-xs text-slate-200";
        label.textContent = prod.name + " × " + item.qty;

        nameQty.appendChild(dot);
        nameQty.appendChild(label);

        const lineTotal = document.createElement("span");
        lineTotal.className = "text-xs text-sky-300";
        lineTotal.textContent = formatCurrency(prod.price * item.qty);

        row.appendChild(nameQty);
        row.appendChild(lineTotal);

        container.appendChild(row);
      });

      totalEl.textContent = formatCurrency(totalPrice);
    }

    function handleLogin(e) {
      e.preventDefault();
      const form = e.target;
      const email = form.login_email.value.trim();
      const password = form.login_password.value.trim();

      if (!email || !password) {
        showToast("กรุณากรอกอีเมลและรหัสผ่าน");
        return;
      }

      // Check if admin login
      if (email === ADMIN_EMAIL && password === ADMIN_PASSWORD) {
        isLoggedIn = true;
        isAdmin = true;
        currentUser = {
          name: "ผู้ดูแลระบบ",
          email: email,
          phone: "",
          fullname: "Admin"
        };
        showSection("section-admin");
        showToast("เข้าสู่ระบบแอดมินสำเร็จ!");
        form.reset();
        renderAdminProducts();
        return;
      }

      // Simulate regular user login
      isLoggedIn = true;
      isAdmin = false;
      currentUser = {
        name: "ผู้ใช้งาน",
        email: email,
        phone: "",
        fullname: ""
      };

      updateProfileUI();
      showSection("section-profile");
      showToast("เข้าสู่ระบบสำเร็จ!");
      form.reset();
    }

    function handleRegister(e) {
      e.preventDefault();
      const form = e.target;
      const name = form.register_name.value.trim();
      const email = form.register_email.value.trim();
      const phone = form.register_phone.value.trim();
      const password = form.register_password.value.trim();
      const confirmPassword = form.register_confirm_password.value.trim();

      if (!name || !email || !phone || !password || !confirmPassword) {
        showToast("กรุณากรอกข้อมูลให้ครบทุกช่อง");
        return;
      }

      if (password !== confirmPassword) {
        showToast("รหัสผ่านไม่ตรงกัน");
        return;
      }

      // Simulate registration
      isLoggedIn = true;
      currentUser = {
        name: name,
        email: email,
        phone: phone,
        fullname: name
      };

      updateProfileUI();
      showSection("section-profile");
      showToast("สมัครสมาชิกส��เร็จ!");
      form.reset();
    }

    function handleSellerRegister(e) {
      e.preventDefault();
      const form = e.target;
      const shopName = form.seller_shop_name.value.trim();
      const name = form.seller_name.value.trim();
      const email = form.seller_email.value.trim();
      const phone = form.seller_phone.value.trim();
      const address = form.seller_address.value.trim();
      const password = form.seller_password.value.trim();
      const confirmPassword = form.seller_confirm_password.value.trim();

      if (!shopName || !name || !email || !phone || !address || !password || !confirmPassword) {
        showToast("กรุณากรอกข้อมูลให้ครบทุกช่อง");
        return;
      }

      if (password !== confirmPassword) {
        showToast("รหัสผ่านไม่ตรงกัน");
        return;
      }

      // Simulate seller registration
      showToast("สมัครเป็นผู้ขายสำเร็จ! กำลังตรวจสอบข้อมูล...");
      form.reset();
      
      setTimeout(() => {
        showSection("section-login");
        showToast("ระบบจะแจ้งผลการอนุมัติภายใน 1-2 วันทำการ");
      }, 2000);
    }

    function handleLogout() {
      isLoggedIn = false;
      isAdmin = false;
      currentUser = null;
      savedAddresses = [];
      selectedAddressId = null;
      showSection("section-login");
      showToast("ออกจากระบบแล้ว");
    }

    function renderAdminProducts() {
      const container = document.getElementById("admin-products-list");
      if (!container) return;

      container.innerHTML = "";

      products.forEach((p) => {
        const card = document.createElement("article");
        card.className = "rounded-2xl bg-[#020617] border border-sky-900/60 px-4 py-3 flex items-start gap-3";

        const visual = document.createElement("div");
        visual.className = "w-12 h-12 rounded-xl bg-gradient-to-br from-sky-500/40 via-sky-700/40 to-sky-900/60 flex items-center justify-center flex-shrink-0";
        const emojiSpan = document.createElement("span");
        emojiSpan.textContent = p.emoji;
        emojiSpan.className = "text-2xl";
        visual.appendChild(emojiSpan);

        const info = document.createElement("div");
        info.className = "flex-1 space-y-1";

        const nameRow = document.createElement("div");
        nameRow.className = "flex items-start justify-between gap-2";

        const name = document.createElement("p");
        name.className = "text-xs font-semibold text-white";
        name.textContent = p.name;

        const price = document.createElement("p");
        price.className = "text-xs font-bold text-sky-300";
        price.textContent = formatCurrency(p.price);

        nameRow.appendChild(name);
        nameRow.appendChild(price);

        const short = document.createElement("p");
        short.className = "text-[11px] text-slate-300";
        short.textContent = p.short;

        const actions = document.createElement("div");
        actions.className = "mt-2 flex items-center gap-2";

        const editBtn = document.createElement("button");
        editBtn.type = "button";
        editBtn.className = "flex-1 rounded-xl border border-sky-800 bg-slate-900/60 px-3 py-1.5 text-[11px] text-sky-200 hover:bg-slate-900";
        editBtn.textContent = "แก้ไข";
        editBtn.addEventListener("click", () => {
          showToast("ฟีเจอร์แก้ไขสินค้า (ตัวอย่าง)");
        });

        const deleteBtn = document.createElement("button");
        deleteBtn.type = "button";
        deleteBtn.className = "flex-1 rounded-xl border border-rose-800 bg-rose-900/20 px-3 py-1.5 text-[11px] text-rose-300 hover:bg-rose-900/40";
        deleteBtn.textContent = "ลบ";
        deleteBtn.addEventListener("click", () => {
          showToast("ฟีเจอร์ลบสินค้า (ตัวอย่าง)");
        });

        actions.appendChild(editBtn);
        actions.appendChild(deleteBtn);

        info.appendChild(nameRow);
        info.appendChild(short);
        info.appendChild(actions);

        card.appendChild(visual);
        card.appendChild(info);

        container.appendChild(card);
      });
    }

    function updateProfileUI() {
      if (!currentUser) return;

      const profileName = document.getElementById("profile-name");
      const profileEmail = document.getElementById("profile-email");
      const profileFullname = document.getElementById("profile-fullname");
      const profilePhone = document.getElementById("profile-phone");

      if (profileName) profileName.textContent = currentUser.name || "ผู้ใช้งาน";
      if (profileEmail) profileEmail.textContent = currentUser.email || "";
      if (profileFullname) profileFullname.textContent = currentUser.fullname || "ยังไม่ได้ระบุ";
      if (profilePhone) profilePhone.textContent = currentUser.phone || "ยังไม่ได้ระบุ";

      renderSavedAddresses();
    }

    function renderSavedAddresses() {
      const container = document.getElementById("saved-addresses-list");
      if (!container) return;

      container.innerHTML = "";

      if (savedAddresses.length === 0) {
        const empty = document.createElement("div");
        empty.className = "text-center py-4";
        empty.innerHTML = `
          <p class="text-xs text-slate-300">ยังไม่มีที่อยู่ที่บันทึกไว้</p>
          <p class="text-[11px] text-slate-400 mt-1">เพิ่มที่อยู่เพื่อความสะดวกในการสั่งซื้อ</p>
        `;
        container.appendChild(empty);
        return;
      }

      savedAddresses.forEach((addr) => {
        const card = document.createElement("div");
        card.className = "rounded-xl border border-sky-900/60 bg-slate-900/40 px-3 py-2 space-y-1";

        const header = document.createElement("div");
        header.className = "flex items-center justify-between";

        const label = document.createElement("p");
        label.className = "text-xs font-semibold text-sky-200";
        label.textContent = addr.label;

        const actions = document.createElement("div");
        actions.className = "flex items-center gap-2";

        const editBtn = document.createElement("button");
        editBtn.type = "button";
        editBtn.className = "text-[11px] text-sky-300 hover:text-sky-200";
        editBtn.textContent = "แก้ไข";
        editBtn.addEventListener("click", () => {
          openAddressForm(addr.id);
        });

        const deleteBtn = document.createElement("button");
        deleteBtn.type = "button";
        deleteBtn.className = "text-[11px] text-rose-300 hover:text-rose-200";
        deleteBtn.textContent = "ลบ";
        deleteBtn.addEventListener("click", () => {
          deleteAddress(addr.id);
        });

        actions.appendChild(editBtn);
        actions.appendChild(deleteBtn);

        header.appendChild(label);
        header.appendChild(actions);

        const name = document.createElement("p");
        name.className = "text-[11px] text-slate-200";
        name.textContent = addr.name;

        const phone = document.createElement("p");
        phone.className = "text-[11px] text-slate-300";
        phone.textContent = addr.phone;

        const detail = document.createElement("p");
        detail.className = "text-[11px] text-slate-300";
        detail.textContent = addr.detail;

        card.appendChild(header);
        card.appendChild(name);
        card.appendChild(phone);
        card.appendChild(detail);

        container.appendChild(card);
      });
    }

    function renderCheckoutAddresses() {
      const container = document.getElementById("checkout-address-list");
      if (!container) return;

      container.innerHTML = "";

      if (savedAddresses.length === 0) {
        const empty = document.createElement("div");
        empty.className = "text-center py-4";
        empty.innerHTML = `
          <p class="text-xs text-slate-300">ยังไม่มีที่อยู่ที่บันทึกไว้</p>
          <p class="text-[11px] text-slate-400 mt-1">กรุณาเพิ่มที่อยู่เพื่อดำเนินการต่อ</p>
        `;
        container.appendChild(empty);
        return;
      }

      savedAddresses.forEach((addr) => {
        const card = document.createElement("button");
        card.type = "button";
        card.className = "w-full text-left rounded-xl border px-3 py-2 space-y-1 transition-colors";
        
        if (selectedAddressId === addr.id) {
          card.className += " border-sky-400 bg-sky-900/30";
        } else {
          card.className += " border-sky-900/60 bg-slate-900/40 hover:border-sky-700";
        }

        card.addEventListener("click", () => {
          selectedAddressId = addr.id;
          renderCheckoutAddresses();
        });

        const label = document.createElement("p");
        label.className = "text-xs font-semibold text-sky-200";
        label.textContent = addr.label;

        const name = document.createElement("p");
        name.className = "text-[11px] text-slate-200";
        name.textContent = addr.name;

        const phone = document.createElement("p");
        phone.className = "text-[11px] text-slate-300";
        phone.textContent = addr.phone;

        const detail = document.createElement("p");
        detail.className = "text-[11px] text-slate-300";
        detail.textContent = addr.detail;

        card.appendChild(label);
        card.appendChild(name);
        card.appendChild(phone);
        card.appendChild(detail);

        container.appendChild(card);
      });
    }

    function openAddressForm(addressId = null) {
      editingAddressId = addressId;
      const form = document.getElementById("address-form");
      const title = document.getElementById("address-form-title");

      if (addressId) {
        const addr = savedAddresses.find((a) => a.id === addressId);
        if (addr) {
          title.textContent = "แก้ไขที่อยู่";
          form.address_label.value = addr.label;
          form.address_name.value = addr.name;
          form.address_phone.value = addr.phone;
          form.address_detail.value = addr.detail;
        }
      } else {
        title.textContent = "เพิ่มที่อยู่ใหม่";
        form.reset();
      }

      showSection("section-address-form");
    }

    function handleAddressSubmit(e) {
      e.preventDefault();
      const form = e.target;
      const label = form.address_label.value.trim();
      const name = form.address_name.value.trim();
      const phone = form.address_phone.value.trim();
      const detail = form.address_detail.value.trim();

      if (!label || !name || !phone || !detail) {
        showToast("กรุณากรอกข้อมูลให้ครบทุกช่อง");
        return;
      }

      if (editingAddressId) {
        // Edit existing
        const addr = savedAddresses.find((a) => a.id === editingAddressId);
        if (addr) {
          addr.label = label;
          addr.name = name;
          addr.phone = phone;
          addr.detail = detail;
          showToast("แก้ไขที่อยู่สำเร็จ!");
        }
      } else {
        // Add new
        const newAddr = {
          id: "addr_" + Date.now(),
          label,
          name,
          phone,
          detail
        };
        savedAddresses.push(newAddr);
        showToast("เพิ่มที่อยู่สำเร็จ!");
      }

      editingAddressId = null;
      form.reset();
      renderSavedAddresses();
      showSection("section-profile");
    }

    function deleteAddress(addressId) {
      savedAddresses = savedAddresses.filter((a) => a.id !== addressId);
      if (selectedAddressId === addressId) {
        selectedAddressId = null;
      }
      renderSavedAddresses();
      showToast("ลบที่อยู่แล้ว");
    }

    function handleFakeOrderSubmit() {
      if (!selectedAddressId) {
        showToast("กรุณาเลือกที่อยู่จัดส่ง");
        return;
      }

      const { totalQty } = getCartStats();
      if (totalQty === 0) {
        showToast("ยังไม่มีสินค้าในตะกร้า");
        return;
      }

      showToast("ระบบบันทึกคำสั่งซื้อ (ตัวอย่าง) เรียบร้อยแล้ว");
      cart = [];
      selectedAddressId = null;
      updateCartUI();
      showSection("section-home");
    }

    function initEvents() {
      const homeIcon = document.getElementById("home-icon-btn");
      const cartIcon = document.getElementById("cart-icon-btn");
      const profileIcon = document.getElementById("profile-icon-btn");
      const backDetail = document.getElementById("back-to-home-from-detail");
      const backCart = document.getElementById("back-to-home-from-cart");
      const backFromCheckout = document.getElementById("back-to-cart-from-checkout");
      const backFromAddress = document.getElementById("back-to-profile-from-address");
      const backFromSeller = document.getElementById("back-to-login-from-seller");

      const footerHomeBtn = document.getElementById("footer-home-btn");
      const footerProfileBtn = document.getElementById("footer-profile-btn");

      const proceedToCheckoutBtn = document.getElementById("proceed-to-checkout-btn");
      const placeOrderBtn = document.getElementById("place-order-btn");

      const goToRegister = document.getElementById("go-to-register");
      const goToSellerRegister = document.getElementById("go-to-seller-register");
      const goToLogin = document.getElementById("go-to-login");
      const goToLoginFromSeller = document.getElementById("go-to-login-from-seller");
      const logoutBtn = document.getElementById("logout-btn");

      const loginForm = document.getElementById("login-form");
      const registerForm = document.getElementById("register-form");
      const sellerRegisterForm = document.getElementById("seller-register-form");
      const addressForm = document.getElementById("address-form");

      const addAddressBtn = document.getElementById("add-address-btn");
      const addAddressFromCheckoutBtn = document.getElementById("add-address-from-checkout-btn");
      const cancelAddressBtn = document.getElementById("cancel-address-btn");

      // Admin buttons
      const adminManageProductsBtn = document.getElementById("admin-manage-products-btn");
      const adminManageOrdersBtn = document.getElementById("admin-manage-orders-btn");
      const adminManageUsersBtn = document.getElementById("admin-manage-users-btn");
      const adminSettingsBtn = document.getElementById("admin-settings-btn");
      const adminLogoutBtn = document.getElementById("admin-logout-btn");
      const adminAddProductBtn = document.getElementById("admin-add-product-btn");
      const backToAdminFromProducts = document.getElementById("back-to-admin-from-products");
      const backToAdminFromOrders = document.getElementById("back-to-admin-from-orders");
      const backToAdminFromUsers = document.getElementById("back-to-admin-from-users");

      if (homeIcon) {
        homeIcon.addEventListener("click", () => {
          showSection("section-home");
        });
      }
      if (cartIcon) {
        cartIcon.addEventListener("click", () => {
          showSection("section-cart");
        });
      }
      if (profileIcon) {
        profileIcon.addEventListener("click", () => {
          if (isLoggedIn) {
            showSection("section-profile");
          } else {
            showSection("section-login");
          }
        });
      }
      if (backDetail) {
        backDetail.addEventListener("click", () => {
          showSection("section-home");
        });
      }
      if (backCart) {
        backCart.addEventListener("click", () => {
          showSection("section-home");
        });
      }
      if (backFromCheckout) {
        backFromCheckout.addEventListener("click", () => {
          showSection("section-cart");
        });
      }
      if (backFromAddress) {
        backFromAddress.addEventListener("click", () => {
          showSection("section-profile");
        });
      }
      if (backFromSeller) {
        backFromSeller.addEventListener("click", () => {
          showSection("section-login");
        });
      }

      if (footerHomeBtn) {
        footerHomeBtn.addEventListener("click", () => {
          showSection("section-home");
        });
      }
      if (footerProfileBtn) {
        footerProfileBtn.addEventListener("click", () => {
          if (isLoggedIn) {
            showSection("section-profile");
          } else {
            showSection("section-login");
          }
        });
      }

      if (proceedToCheckoutBtn) {
        proceedToCheckoutBtn.addEventListener("click", () => {
          if (!isLoggedIn) {
            showToast("กรุณาเข้าสู่ระบบก่อนชำระเงิน");
            showSection("section-login");
            return;
          }
          renderCheckoutAddresses();
          showSection("section-checkout");
        });
      }

      if (placeOrderBtn) {
        placeOrderBtn.addEventListener("click", () => {
          handleFakeOrderSubmit();
        });
      }

      const detailAddBtn = document.getElementById("detail-add-to-cart");
      if (detailAddBtn) {
        detailAddBtn.addEventListener("click", () => {
          if (!currentDetailId) return;
          const prod = products.find((p) => p.id === currentDetailId);
          addToCart(currentDetailId);
          if (prod) {
            showToast("เพิ่ม \"" + prod.name + "\" ลงในตะกร้าแล้ว");
          }
        });
      }

      if (goToRegister) {
        goToRegister.addEventListener("click", () => {
          showSection("section-register");
        });
      }

      if (goToSellerRegister) {
        goToSellerRegister.addEventListener("click", () => {
          showSection("section-seller-register");
        });
      }

      if (goToLogin) {
        goToLogin.addEventListener("click", () => {
          showSection("section-login");
        });
      }

      if (goToLoginFromSeller) {
        goToLoginFromSeller.addEventListener("click", () => {
          showSection("section-login");
        });
      }

      if (logoutBtn) {
        logoutBtn.addEventListener("click", () => {
          handleLogout();
        });
      }

      if (loginForm) {
        loginForm.addEventListener("submit", handleLogin);
      }

      if (registerForm) {
        registerForm.addEventListener("submit", handleRegister);
      }

      if (sellerRegisterForm) {
        sellerRegisterForm.addEventListener("submit", handleSellerRegister);
      }

      if (addressForm) {
        addressForm.addEventListener("submit", handleAddressSubmit);
      }

      if (addAddressBtn) {
        addAddressBtn.addEventListener("click", () => {
          openAddressForm();
        });
      }

      if (addAddressFromCheckoutBtn) {
        addAddressFromCheckoutBtn.addEventListener("click", () => {
          openAddressForm();
        });
      }

      if (cancelAddressBtn) {
        cancelAddressBtn.addEventListener("click", () => {
          showSection("section-profile");
        });
      }

      // Admin event listeners
      if (adminManageProductsBtn) {
        adminManageProductsBtn.addEventListener("click", () => {
          renderAdminProducts();
          showSection("section-admin-products");
        });
      }

      if (adminManageOrdersBtn) {
        adminManageOrdersBtn.addEventListener("click", () => {
          showSection("section-admin-orders");
        });
      }

      if (adminManageUsersBtn) {
        adminManageUsersBtn.addEventListener("click", () => {
          showSection("section-admin-users");
        });
      }

      if (adminSettingsBtn) {
        adminSettingsBtn.addEventListener("click", () => {
          showToast("ฟีเจอร์ตั้งค่าระบบ (ตัวอย่าง)");
        });
      }

      if (adminLogoutBtn) {
        adminLogoutBtn.addEventListener("click", () => {
          handleLogout();
        });
      }

      if (adminAddProductBtn) {
        adminAddProductBtn.addEventListener("click", () => {
          showToast("ฟีเจอร์เพิ่มสินค้า (ตัวอย่าง)");
        });
      }

      if (backToAdminFromProducts) {
        backToAdminFromProducts.addEventListener("click", () => {
          showSection("section-admin");
        });
      }

      if (backToAdminFromOrders) {
        backToAdminFromOrders.addEventListener("click", () => {
          showSection("section-admin");
        });
      }

      if (backToAdminFromUsers) {
        backToAdminFromUsers.addEventListener("click", () => {
          showSection("section-admin");
        });
      }
    }

    // Initialize view
    renderProducts();
    updateCartUI();
    initEvents();
    applyConfigToUI(defaultConfig);
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a4ddf9473888829',t:'MTc2NDIwNzE2NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
