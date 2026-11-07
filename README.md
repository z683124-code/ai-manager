# AI MANAGER — O'zbekiston Bizneslari Uchun Virtual Xodimlar SaaS Platformasi

> **AI MANAGER** — do'konlar, restoranlar, xizmat ko'rsatish shoxobchalari va korxonalar uchun 24/7 ishlaydigan professional sun'iy intellekt virtual operatori, buyurtma qabul qilish, omborxona va kassa tahlili platformasi.

---

## 🌟 Asosiy Imkoniyatlar (Key Features)

### 1. Multi-Tenant SaaS Arxitekturasi
- Har bir biznes (tenant) o'zining mustaqil hisobi, tovarlar katalogi, ombor qoldiqlari, mijozlar bazasi (CRM), AI sozlamalari va obuna rejasiga ega.
- Ma'lumotlar to'liq izolyatsiya qilingan (Tenant isolation). Bir korxona boshqa korxona ma'lumotlarini aslo ko'ra olmaydi.

### 2. O'zbekiston Lokalizatsiyasi
- **O'zbek tili (birlamchi)** va **Rus tili** to'liq qo'llab-quvvatlanadi.
- Milliy valyuta: **O'zbekiston so'mi (UZS)** formatlash (`250 000 so'm`).
- **+998** telefon raqamlar formati va validatsiyasi.
- O'zbekiston sana va vaqt mintaqasi (`Asia/Tashkent`).
- Mahalliy to'lov tizimlari: **Click.uz, Payme, Uzum Bank**.
- Mahalliy telefoniya va SIP provayderlari (Eskiz.uz, PlayMobile, Beeline Business SIP).

### 3. AI Virtual Receptionist & Qat'iy 0% Uydirma Qoidasi (No Hallucination)
- Tabiiy o'zbek tili fonetikasiga moslashgan ovozlar (`uz-UZ-MadinaNeural`, `uz-UZ-SardorNeural`).
- **Grounded RAG Engine**: AI faqat korxona tomonidan tasdiqlangan tovarlar katalogi, real ombor qoldig'i, ish vaqti va rasmiy FAQ bilimlar bazasiga tayanadi.
- **Uydirmalar taqiqlangan**: Narxlar, mavjud bo'lmagan tovarlar yoki yetkazib berish shartlari o'zidan to'qib chiqarilmaydi.
- Telefon orqali avtomatik buyurtma qabul qilish va tizimda rasmiylashtirish (`ORD-...`).

### 4. Tariflar va Ruxsatlar Matritsasi (Plan Permissions)
- **FREE (0 so'm)**: Cheklangan demo, 20 tagacha tovar, oyiga 50 ta qo'ng'iroq.
- **GO (490 000 so'm/oy)**: AI telefon javob berish, ish vaqti va biznes ma'lumoti, tovar narxi va qoldig'i, 100 ta tovar.
- **PLUS (1 290 000 so'm/oy)**: Barcha GO imkoniyatlari + **Telefon orqali buyurtma qabul qilish**, mijozlar bazasi (CRM), Telegram bot integratsiyasi, 1 000 ta tovar.
- **PRO (2 890 000 so'm/oy)**: Barcha PLUS imkoniyatlari + **Omborxona harakatlari jurnali (Kirim/Chiqim)**, kassa va savdo analitikasi, marketing AI, ko'p filialli tizim (Multi-branch), 10 000 ta tovar.
- Qimmat PRO imkoniyatlari pastki tariflarga berilmaydi va tizim darajasida tekshiriladi.
- Tarif limitlari Super Admin panelidan o'zgartiriladi.

### 5. Foydalanuvchi va Administrator Panellari
- **Biznes Boshqaruv Paneli (`/dashboard`)**:
  - Umumiy ko'rinish (KPI, savdo tushumi so'mda, qo'ng'iroqlar, kutilayotgan buyurtmalar)
  - AI Virtual Xodim sozlamalari va Jonli Ovozli Test Simulyatori
  - Mahsulotlar katalogi (SKU, narxlar, qoldiqlar)
  - Omborxona (Kirim/Chiqim — PRO tarifida)
  - Buyurtmalar boshqaruvi va holatlarini o'zgartirish
  - Mijozlar bazasi (CRM)
  - Qo'ng'iroqlar jurnali, audio yozuvlar va stenogrammalar
  - Muloqotlar (Chatlar)
  - Kassa va moliya tahlillari
  - Obuna va to'lovlar (Click / Payme)
  - Jamoa a'zolari va rollar
  - Biznes rekvizitlari va sozlamalari
- **Super Admin Paneli (`/admin`)**:
  - Platforma umumiy MRR daromadi
  - Korxonalar hisoblarini boshqarish, vaqtincha bloklash (Suspend) va qayta tiklash (Restore)
  - Tarif rejalari va limitlarni tahrirlash
  - AI tokenlari sarfi va tannarx tahlili
  - Tizim va telefoniya webhook sozlamalari
  - Xavfsizlik va audit jurnali

---

## 🛠 Texnologiyalar Steki

- **Frontend / Framework**: Next.js 14 (App Router, JavaScript)
- **Styling**: Tailwind CSS, PostCSS, Autoprefixer (Dark navy & Clean white dizayn)
- **Icons**: Lucide React
- **Ma'lumotlar bazasi**: PostgreSQL / SQLite (`prisma/schema.prisma`)
- **ORM**: Prisma ORM v5
- **Autentifikatsiya**: JSON Web Token (JWT) + HTTP-only Secure Cookies + Bcrypt password hashing
- **Lokalizatsiya**: O'zbek tili (`uz-UZ`), UZS valyuta formati, +998 telefon formati

---

## 📁 Loyiha Tuzilmasi (Project Structure)

```
MASTER PROMPT/
├── prisma/
│   ├── schema.prisma       # Multi-tenant ma'lumotlar bazasi modeli
│   └── seed.js             # O'zbekiston real demo ma'lumotlari (Do'kon, Restoran, Admin)
├── src/
│   ├── app/
│   │   ├── page.js                 # Asosiy sahifa (Homepage + Jonli AI Ovozli Vidjet)
│   │   ├── features/page.js        # Imkoniyatlar sahifasi
│   │   ├── pricing/page.js         # Tariflar sahifasi (FREE, GO, PLUS, PRO)
│   │   ├── about/page.js           # Biz haqimizda sahifasi
│   │   ├── contact/page.js         # Bog'lanish sahifasi
│   │   ├── login/page.js           # Kirish (Tezkor demo hisoblar bilan)
│   │   ├── register/page.js        # Biznes ro'yxatdan o'tish
│   │   ├── dashboard/              # Biznes boshqaruv paneli
│   │   │   ├── layout.js           # Himoyalangan dashboard layout + Bloklanganlik tekshiruvi
│   │   │   ├── page.js             # Umumiy ko'rinish (KPI lar, tushum, qo'ng'iroqlar)
│   │   │   ├── ai-manager/page.js  # AI Virtual xodim sozlamalari & Jonli Audio Simulyator
│   │   │   ├── products/page.js    # Mahsulotlar katalogi
│   │   │   ├── inventory/page.js   # Omborxona (Kirim/Chiqim - PRO tarifida)
│   │   │   ├── marketing/page.js   # AI Marketing & Reklama (Eskiz SMS, Instagram, Telegram)
│   │   │   ├── orders/page.js      # Buyurtmalar boshqaruvi & Chek chiqarish (Print)
│   │   │   ├── customers/page.js   # Mijozlar bazasi (CRM)
│   │   │   ├── calls/page.js       # Qo'ng'iroqlar jurnali va stenogrammalar
│   │   │   ├── conversations/page.js# Muloqotlar
│   │   │   ├── analytics/page.js   # Biznes va kassa tahlili
│   │   │   ├── billing/page.js     # Obuna va to'lovlar (Click/Payme)
│   │   │   ├── team/page.js        # Jamoa xodimlari
│   │   │   └── settings/page.js    # Biznes rekvizitlari va sozlamalari
│   │   ├── admin/                  # Super Admin paneli
│   │   │   ├── layout.js           # Super Admin huquqi tekshiruvi
│   │   │   ├── page.js             # Platforma MRR va umumiy ko'rinish
│   │   │   ├── businesses/page.js  # Korxonalarni boshqarish & Bloklash / Tiklash
│   │   │   ├── plans/page.js       # Tariflar va limitlarni sozlash
│   │   │   ├── usage/page.js       # AI xarajatlari va tokenlar statistikasi
│   │   │   ├── revenue/page.js     # Platforma tushumlari tahlili
│   │   │   ├── settings/page.js    # Tizim va telefoniya sozlamalari
│   │   │   └── audit/page.js       # Xavfsizlik audit jurnali
│   │   └── api/                    # Backend API yo'nalishlari
│   │       ├── auth/               # Login, Register, Me, Logout
│   │       ├── ai/receptionist/    # Grounded AI Virtual Operator & Simulyator
│   │       ├── products/           # Mahsulotlar CRUD
│   │       ├── orders/             # Buyurtmalar CRUD
│   │       ├── inventory/          # Ombor harakatlari (PRO plan gating)
│   │       ├── customers/          # CRM
│   │       ├── calls/              # Qo'ng'iroqlar
│   │       ├── dashboard/stats/    # Biznes KPI statistikasi
│   │       ├── business/settings/  # Biznes va AI sozlamalari
│   │       ├── admin/              # Super Admin API lari
│   │       └── webhooks/           # Telephony, Click.uz, Payme.uz, Telegram
│   ├── components/
│   │   ├── public/                 # Navbar, Footer, LiveDemoWidget
│   │   ├── dashboard/              # Sidebar, Header
│   │   └── admin/                  # AdminSidebar
│   └── lib/
│       ├── prisma.js               # Prisma Client singleton
│       ├── auth.js                 # JWT, Password hash, Cookie session
│       ├── permissions.js          # Plan limitlari va ruxsatlar tekshiruvi
│       ├── eskiz.js                # Eskiz.uz SMS provayderi
│       ├── uzbekistan.js           # UZS valyuta, +998 telefon, sana formatlash
│       └── ai-engine.js            # Grounded AI logic, 0% uydirma qoidasi
├── .env.example
├── package.json
└── jsconfig.json
```

---

## ⚡️ O'rnatish va Ishga Tushirish (Setup Instructions)

### 1. Bog'liqliklarni o'rnatish
```bash
npm install
```

### 2. Ma'lumotlar bazasini sinxronlash va to'ldirish
```bash
# Prisma Client yaratish
npx prisma generate

# Bazani sinxronlash (dev.db yaratiladi)
node_modules/.bin/prisma db push

# Demo ma'lumotlar bilan to'ldirish
node prisma/seed.js
```

### 3. Dasturni ishga tushirish
```bash
npm run dev
# yoki production rejimda:
npm run build
npm run start
```
Brauzerda oching: `http://localhost:3000`

---

## 🔑 Tayyor Demo Hisoblar (Test Credentials)

Tizimga kirish sahifasida (`/login`) bir marta bosish orqali avtomatik to'ldiriladigan demo hisoblar:

| Rol | Kompaniya | Email | Parol | Tarif |
|---|---|---|---|---|
| **Super Admin** | Platforma Egasi | `admin@aimanager.uz` | `AdminPassword2026!` | Super Admin |
| **Biznes Egasi** | SmartElectronics Tashkent | `sardor@smartelectronics.uz` | `Password123!` | PLUS |
| **Biznes Egasi** | Osh Markazi Samarqand | `alisher@oshmarkazi.uz` | `Password123!` | PRO |

---

## ⚙️ Muhit O'zgaruvchilari (Environment Variables)

`.env` faylida quyidagi parametrlar mavjud:

```env
# Database
DATABASE_URL="file:./dev.db"
# PostgreSQL uchun: postgresql://USER:PASSWORD@HOST:5432/ai_manager?schema=public

# Authentication
JWT_SECRET="ai-manager-uz-super-secret-production-jwt-key-2026"
NEXT_PUBLIC_APP_URL="http://localhost:3000"

# AI Voice & LLM
OPENAI_API_KEY="sk-..."
AI_VOICE_MODEL="gpt-4o-realtime-preview"
DEFAULT_AI_VOICE="uz-UZ-MadinaNeural"

# O'zbekiston Telefoniya (Eskiz / PlayMobile / Beeline Business SIP)
TELEPHONY_WEBHOOK_SECRET="uz_telephony_secret_hash_2026"

# O'zbekiston To'lov Shlyuzlari
CLICK_MERCHANT_ID="12345"
CLICK_SERVICE_ID="67890"
CLICK_SECRET_KEY="click_secret_sample"
PAYME_MERCHANT_ID="payme_merchant_sample"
PAYME_SECRET_KEY="payme_secret_sample"

# Telegram Bot
TELEGRAM_BOT_TOKEN="123456789:ABCDefghIJKlmnoPQRstuvWXyz"
```

---

## 📞 Telefoniya va To'lov Webhook Integratsiyalari

- **Telefoniya Webhook**: `POST /api/webhooks/telephony` — mahalliy SIP provayder (Eskiz, PlayMobile) dan kiruvchi qo'ng'iroq va ovozni qabul qilib, o'zbek tilida tayyor TTS javob qaytaradi.
- **Click.uz Webhook**: `POST /api/webhooks/click` — `Prepare` (0) va `Complete` (1) amallarini qo'llab-quvvatlaydi, obunani avtomatik uzaytiradi.
- **Payme.uz Webhook**: `POST /api/webhooks/payme` — merchant tranzaksiyalari integratsiyasi uchun tayyorlangan.

# ai-manager
