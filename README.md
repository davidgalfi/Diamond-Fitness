# 💎 Diamond Fitness Management System

> Kis csoportos fitness stúdió menedzsment rendszer mobil-first megközelítéssel.

[![Railway](https://img.shields.io/badge/Deploy-Railway-blueviolet)](https://railway.app)
[![Node.js](https://img.shields.io/badge/Node.js-v18+-green)](https://nodejs.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 📖 Tartalomjegyzék

- [Projekt Céljai](#-projekt-céljai)
- [Főbb Funkciók](#-főbb-funkciók)
- [Technológiai Stack](#️-technológiai-stack)
- [Gyors Start](#-gyors-start)
- [Projekt Struktúra](#-projekt-struktúra)
- [Dokumentáció](#-dokumentáció)
- [Képernyőképek](#-képernyőképek)
- [Deployment Railway-re](#-deployment-railway-re)
- [Költségoptimalizálás](#-költségoptimalizálás)
- [Biztonság & GDPR](#-biztonság--gdpr)
- [Többnyelvűség](#-többnyelvűség)
- [Licensz](#-licensz)
- [Kapcsolat](#-kapcsolat)

---

## 🎯 Projekt Céljai

A **Diamond Fitness** egy teljes körű webes alkalmazás, amely **kis létszámú (max 40-50 fős)** fitness stúdiók számára készült. A rendszer célja egyszerű, barátságos kezelés biztosítása mind az adminok (akik nem tech-savvy-k), mind a tagok (jellemzően idősebb korosztály, mobil eszközökről) számára.

### Miért készült?

- ✅ **Mobil-first design** - 99% mobilhasználat
- ✅ **Egyszerű kezelés** - Boomer-friendly admin felület
- ✅ **Motivációs rendszer** - Kitűzők, XP, streak
- ✅ **Minimális költség** - Railway ingyenes/olcsó tier
- ✅ **GDPR compliance** - Minimális adatgyűjtés
- ✅ **3 nyelvű** - Magyar, Szerb, Angol

---

## ⭐ Főbb Funkciók

### 👤 Tagok részére
* ✅ **Regisztráció & Bejelentkezés** 
* 📅 **Edzések böngészése** és jelentkezés 
* 📊 **Személyes statisztikák** megtekintése 
* 💪 **BMI követés & célkitűzések** beállítása 
* 🏅 **Kitűzők & XP rendszer** (Gamification) 
* 🔥 **Streak (sorozat)** követés
*  ⚖️ **Súly frissítés & grafikon** 
* 📧 **Email értesítések** (opcionális) 
* 🌐 **3 nyelvű felület** váltása

### 🧑‍💼 Adminok részére
* 👥 **Tagok jóváhagyása/elutasítása** (Pending státusz)
*  📅 **Edzések létrehozása/szerkesztése**
*  💾 **Edzés sablonok mentése** (gyors létrehozás) 
* 👤 **Tagok kezelése** (kirúgás, elnémítás) 
* ⚠️ **Figyelmeztetési rendszer** kezelése 
* 📊 **Közösségi statisztikák** 
* 📥 **Jelenléti ív export** (PDF/CSV) 
* 💰 **Árak szerkesztése** 
* 🖼️ **Galéria kezelés** 
* ⚙️ **Rendszer beállítások**

### 🔐 Jóváhagyási folyamat

Új tag regisztrációja után:

```mermaid 
graph TD 
A[Tag kitölti a regisztrációs űrlapot] --> B[PENDING állapot (Nem tud belépni)] 
B --> C{Admin döntés} 
C -- Jóváhagyás --> D[Tag bejelentkezhet] 
C -- Elutasítás --> E[Adatok törlődnek (GDPR)]
```
**Szöveges verzió:**
1. Tag kitölti a regisztrációs űrlapot 
2. PENDING állapot (nem tud belépni) 
3. Admin jóváhagyja VAGY elutasítja 
4. Ha jóváhagyva → Tag bejelentkezhet 
5. Ha elutasítva → Adatok törlődnek (GDPR)

### 🏅 Motivációs rendszer
#### Kitűzők (20 db) 
- **Első lépés** 1 edzés 
- **Heti hős** - 3 edzés/hét 
- **10-es klub** - 10 edzés 
- **Holdszakasz** - 30 napos sorozat 
- **Célba érő** - célsúly elérve - _...és még 15 további!_ 

#### Streak rendszer 
- **Aktív:** 2 héten belül edzés 
- **Szünetel:** 2 hét kihagyás (de nem törlődik!) 
- **Törlődik:** 3 hét kihagyás 

#### XP rendszer 
- Edzések: **+10 XP** 
- Súly frissítés: **+5 XP** 
- Kitűzők: **+10-1000 XP** 
- Level up jutalmak

### ⚠️ Figyelmeztetési rendszer (opcionális)

Admin bekapcsolhatja: 
- Késői lemondás → **+1 pont** Meg nem jelenés → **+2 pont** 
- 3 pont után → **1 hét blokkolás** 
- Pontok automatikusan törlődnek **30 nap** után


---

## 🛠️ Technológiai Stack

### Backend
- 📦 **Node.js** v18+ 
- ⚡ **Express.js** (REST API) 
- 🗄️ **Prisma ORM** 
- 💾 **SQLite** (kezdésnek) / **PostgreSQL** (később) 
- 🔐 **JWT** (autentikáció) 
- 🔒 **bcrypt** (jelszó titkosítás) 
- 🌐 **i18next** (többnyelvűség)

### Frontend
- 🎨 **HTML5** + **CSS3** + **Vanilla JavaScript** 
- 💨 **Tailwind CSS** (styling) 
- 🏔️ **Alpine.js** (opcionális, könnyű interaktivitás) 
- 📊 **Chart.js** (grafikonok)

### Deployment
- 🚂 **Railway** (hosting) 
- 🔄 **GitHub** (verziókezelés) 
- ☁️ **Cloudinary** (képek tárolása, opcionális)

---

## 🚀 Gyors Start

### Követelmények

- **Node.js** v18 vagy újabb
- **Git**
- **SQLite** (beépített) vagy **PostgreSQL**

### Telepítés lépésről-lépésre

#### 1. Repository klónozása
```bash
git clone [https://github.com/your-username/diamond-fitness.git](https://github.com/your-username/diamond-fitness.git)
cd diamond-fitness
```
#### 2. Függőségek telepítése
```bash
npm install
```

#### 3. Környezeti változók beállítása
```bash
cp .env.example .env
```
Szerkeszd a `.env` fájlt:
```
NODE_ENV=development
PORT=3000
DATABASE_URL="file:./prisma/dev.db"
JWT_SECRET=valami_nagyon_titkos_kulcs_ide
APP_URL=http://localhost:3000
```

#### 4. Adatbázis migráció
```bash
npx prisma migrate dev
npx prisma generate
```

#### 5. Seed adatok (opcionális)
```bash
npm run seed
```

Ez létrehoz:
- 1 admin felhasználót (username: `admin`, jelszó: `admin123`)
- Néhány példa edzést
- Példa tagokat

#### 6. Fejlesztői szerver indítása
```bash
npm run dev
```

A szerver elérhető: [**http://localhost:3000**](http://localhost:3000)

---

## 📁 Projekt Struktúra

```
diamond-fitness/
│
├── backend/
│   ├── config/
│   │   └── badges.json       # Kitűzők definíciója (JSON)
│   ├── controllers/          # Üzleti logika (Auth, Event, User, Badge, Stats)
│   ├── middleware/           # Auth, Validation, ErrorHandling
│   ├── models/               # (Prisma generálja)
│   ├── routes/               # API végpontok definíciói
│   ├── utils/                # Helper funkciók (BadgeChecker, EmailSender)
│   └── locales/              # Fordítási JSON fájlok (hu, sr, en)
│
├── frontend/
│   ├── public/
│   │   ├── css/              # Tailwind + custom styles.css
│   │   ├── js/               # Main, Auth, Dashboard, Admin szkriptek
│   │   └── images/           # Statikus képek, ikonok
│   └── pages/
│       ├── index.html        # Főoldal
│       ├── login.html        # Bejelentkezés / Regisztráció
│       ├── dashboard.html    # Tag dashboard
│       ├── admin.html        # Admin felület
│       └── ...               # Egyéb oldalak (stats, profile, badges)
│
├── prisma/
│   ├── schema.prisma         # Adatbázis séma definíció
│   ├── seed.js               # Seed adatok betöltése
│   └── dev.db                # SQLite adatbázis (gitignore!)
│
├── docs/                     # Részletes dokumentáció (.md fájlok)
├── .env.example
├── package.json
├── railway.toml              # Railway deployment config
└── server.js                 # Belépési pont
```

---

## 📚 Dokumentáció

Részletes dokumentáció a `/docs` mappában található:

| Dokumentum | Leírás |
|------------|--------|
| [📋 Projekt Áttekintő](docs/01-PROJECT-OVERVIEW.md) | Teljes projekt leírás, célok, scope |
| [⭐ Funkciók](docs/02-FEATURES.md) | Összes funkció részletesen |
| [🏗️ Architektúra](docs/03-ARCHITECTURE.md) | Rendszer felépítés, komponensek |
| [🗄️ Adatbázis Séma](docs/04-DATABASE-SCHEMA.md) | Táblák, relációk, indexek |
| [🔌 API Dokumentáció](docs/05-API-DOCUMENTATION.md) | REST API végpontok |
| [👥 Felhasználói Folyamatok](docs/06-USER-FLOWS.md) | UX flow diagramok |
| [🧑‍💼 Admin Útmutató](docs/07-ADMIN-GUIDE.md) | Admin funkciók használata |
| [🚂 Deployment](docs/08-DEPLOYMENT.md) | Railway-re telepítés lépésről-lépésre |
| [💻 Fejlesztői Útmutató](docs/09-DEVELOPMENT-GUIDE.md) | Kód struktúra, best practices |
| [🏅 Badge Kezelés](docs/10-BADGES-MANAGEMENT.md) | Kitűzők hozzáadása/módosítása |
| [🌐 Többnyelvűség](docs/11-MULTILANGUAGE.md) | Fordítások kezelése |
| [🔒 Biztonság & GDPR](docs/12-SECURITY-GDPR.md) | Biztonsági gyakorlatok |
| [🔧 Hibaelhárítás](docs/13-TROUBLESHOOTING.md) | Gyakori problémák megoldása |

---

## 📱 Képernyőképek

### Mobil nézet (elsődleges - 99% használat)

```
┌────────────────────────────────────────────────┐
│ 💎 Diamond Fitness              🌐 Magyar ▼    │
├─────────┬──────────────────────────────────────┤
│    🏠   │  👋 Szia Anna!                       │
│  Főoldal│  🔥 12 napos sorozat                 │
│    📅   │  💪 Még 3 kg a célig                 │
│  Naptár │                                      │
│    📊   │  ┌──────────────────────────┐        │
│   Stat. │  │ 📅 MAI EDZÉSEK           │        │
│    🏅   │  │ 10:00 - Reggeli Cardio   │        │
│ Kitűzők │  │ 👤 Edző: Kovács Éva      │        │
│    👤   │  │ 👥 12/15 fő              │        │
│  Profil │  │ [JELENTKEZEM]            │        │
│         │  └──────────────────────────┘        │
│    🚪   │                                      │
│  Kilépés│  ┌──────────────────────────┐        │
│         │  │ 🏅 LEGÚJABB KITŰZŐK      │        │
│         │  │ 🏅 Heti hős (+25 XP)     │        │
│         │  └──────────────────────────┘        │
└─────────┴──────────────────────────────────────┘
```

### Desktop nézet (ritkább, de támogatott)

**Sidebar navigáció:** 
- 🏠 Főoldal 
- 📅 Naptár 
- 📊 Statisztika 
- 🏅 Kitűzők 
- 👤 Profil 
- 🚪 Kilépés 

**Főterület:** 
- Üdvözlő widget (sorozat, cél, stb.) 
- Mai edzések lista 
- Legújabb kitűzők


### Admin nézet (egyszerű, vizuális)

```
┌─────────────────────────────────────┐
│ 👤 ÚJ JELENTKEZŐK (3)               │ ← Piros pont jelzi az akciót
│ [Elfogadás] vagy [Elutasítás]       │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│ 📅 EDZÉSEK KEZELÉSE                 │
│ Új edzés létrehozása, módosítás     │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│ 👥 TAGOK KEZELÉSE                   │
│ Tagok listája, kirúgás, elnémítás   │
└─────────────────────────────────────┘
```

---

## 🚂 Deployment Railway-re

### Gyors Deploy

1. **Fork/Clone** a repót
2. **Regisztrálj** Railway-n: https://railway.app
3. **New Project** → **Deploy from GitHub**
4. Válaszd ki a `diamond-fitness` repót
5. **Add változók**: Settings → Variables:
	```
	NODE_ENV=production  
	DATABASE_URL=file:./prisma/dev.db  
	JWT_SECRET=your_secret_here  
	APP_URL=[https://your-app.up.railway.app](https://your-app.up.railway.app/)
	```
6. **Deploy** → Automatikusan indul!

Részletes útmutató: [docs/08-DEPLOYMENT.md](docs/08-DEPLOYMENT.md)

---

## 💰 Költségoptimalizálás

### Railway Free Tier (elég a projekthez!)
**Ingyen minden hónapban:** 
- $5 kredit 
- ~500 óra futásidő 
- 1 GB RAM 
- 1 GB Storage 
- Automatikus SSL 
- Egy projekt (backend + frontend együtt!) 

**Optimalizálások:** 
- SQLite használata (nincs külön DB szerver) 
- Képek Cloudinary-n (10GB ingyen) 
- Cache middleware 
- Keep-alive (UptimeRobot ingyen)

### Várható költség
**40 fős stúdió esetén:** 
- Havi forgalom: ~100 MB 
- RAM használat: ~200 MB 
- Storage: ~50 MB (SQLite) 

**KÖLTSÉG: $0-2/hó** (ingyen tier elég!) 
**Maximum: $5/hó** (ha túllépném, ritka)

---

## 🔒 Biztonság & GDPR

### Biztonsági intézkedések

- ✅ Jelszavak **bcrypt hashelt** tárolása (10 rounds)
- ✅ **JWT token** alapú autentikáció
- ✅ **SQL injection védelem** (Prisma ORM)
- ✅ **XSS védelem** (input sanitization)
- ✅ **Rate limiting** (túl sok próbálkozás blokkolása)
- ✅ **HTTPS** (Railway automatikusan)
- ✅ **Environment variables** (érzékeny adatok)

### GDPR Compliance

- ✅ **Minimális adatgyűjtés** (csak ami feltétlenül szükséges)
- ✅ **Adattörlés** (tag kérheti, admin jóváhagyás után)
- ✅ **Cookie banner** (tájékoztatás)
- ✅ **Adatvédelmi nyilatkozat** (magyar nyelven)
- ✅ **Email opcionális** (tag dönt)
- ✅ **Soft delete** (30 napos törlési időzítő)

Részletek: [docs/12-SECURITY-GDPR.md](docs/12-SECURITY-GDPR.md)

---

## 🌐 Többnyelvűség

Támogatott nyelvek:
- 🇭🇺 **Magyar** (alapértelmezett)
- 🇷🇸 **Szerb**
- 🇬🇧 **Angol**

### Nyelvváltás

**Dektop verzió**:
```
🌐 [Magyar ▼]  
Szerb  
Angol
```
**Mobil verzió:**
```
🌐 HU | SR | EN
```

### Fordítási fájlok

```
backend/locales/  
├── hu.json # Magyar fordítások  
├── sr.json # Szerb fordítások  
└── en.json # Angol fordítások
```

Részletek: [docs/11-MULTILANGUAGE.md](docs/11-MULTILANGUAGE.md)

---

## 👥 Felhasználói Szerepkörök

| Szerepkör | Jogosultságok |
|-----------|---------------|
| **Tag** | Edzésre jelentkezés, saját statisztikák, profil szerkesztés, súly frissítés |
| **Admin/Edző** | Teljes hozzáférés: tagok jóváhagyása/kirúgása/elnémítása, edzések létrehozása/szerkesztése, sablonok kezelése, jelenléti ív export, árak szerkesztése, galéria kezelés, rendszer beállítások, közösségi statisztikák, elfelejtett jelszó visszaállítás |

---

## 🎨 Design Színpaletta (Diamond téma)
A felület "Sötét rózsaszín" (Dark Pink) témát használ, amely nőies, de modern és sportos.
```css
:root {
  /* TÉMASZÍNEK */
  --primary:    #C75B7A; /* Fő szín (gombok, kiemelések) */
  --secondary:  #F9E0E5; /* Világos háttér */
  --accent:     #9B4D6B; /* Mélyebb árnyalat (hover) */
  --background: #FFFFFF; /* Fehér háttér */
  --text:       #2D2D2D; /* Sötét szürke szöveg */
  
  /* ÁLLAPOT SZÍNEK */
  --success:    #22C55E; /* Zöld (jóváhagyás) */
  --warning:    #F59E0B; /* Sárga (figyelmeztetés) */
  --danger:     #EF4444; /* Piros (hiba, törlés) */
}
```

---

## 🤝 Közreműködés

Ez egy privát projekt, de javítások, új funkciók ötleteit szívesen fogadom!

### Hogyan?

1. **Fork-old** a repót
2. Készíts egy **feature branch-et**: `git checkout -b feature/AwesomeFeature`
3. **Commit-old**: `git commit -m 'Add some AwesomeFeature'`
4. **Push-old**: `git push origin feature/AwesomeFeature`
5. Nyiss egy **Pull Request-et**

---

## 🐛 Hibabejelentés

Ha hibát találsz:
1. Ellenőrizd a [Hibaelhárítás](docs/13-TROUBLESHOOTING.md) dokumentumot
2. Nyiss egy **GitHub Issue-t** részletes leírással
3. Vagy írj email-t: info@diamond-fitness.hu

---

## 📝 Licensz

Ez a projekt **MIT licensz** alatt áll. Szabadon használható, módosítható, terjeszthető.

Lásd: [LICENSE](LICENSE)

---

## 📧 Kapcsolat

**Diamond Fitness**
- 🌐 Website: https://diamond-fitness.hu (még nem biztos)
- 📧 Email: info@diamond-fitness.hu (ez is csak próba)
- 📞 Telefon: +36 30 123 4567 (ez egy példa szám)
- 📍 Cím: Esbjerg, Dánia (Ez sem igaz)

**Projekt készítő:**
- 👤 Név: Dávid Zsolt Gálfi
- 📧 Email: galfidavid314@gmail.com
- 💼 GitHub: [@davidgalfi](https://github.com/davidgalfi)

---

## 🙏 Köszönet

Külön köszönet:
- **Railway** - Kiváló hosting platform
- **Tailwind CSS** - Modern styling framework
- **Prisma** - Egyszerű ORM
- **Chart.js** - Szép grafikonok
- **i18next** - Többnyelvűség támogatás

---

## 📅 Changelog

### v1.0.0 (2025.12.07.)
- ✨ Első stabil verzió
- ✅ Teljes tag és admin felület
- ✅ Kitűző & XP rendszer
- ✅ Streak követés
- ✅ BMI & súly követés
- ✅ 3 nyelvű támogatás
- ✅ Figyelmeztetési rendszer
- ✅ Railway deployment

---

**Készítve ❤️-tel Esbjergben, 2025-ben**

---

**Utolsó frissítés:** 2025.12.07.
**Verzió:** 1.0.0
