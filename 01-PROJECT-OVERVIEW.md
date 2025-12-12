# 📋 Projekt Áttekintő - Diamond Fitness Management System

> Részletes projekt dokumentáció - Célok, Scope, Döntések

**Verzió:** 1.0.0  
**Utolsó frissítés:** 2025.12.07.  
**Készítette:** Gálfi Dávid Zsolt

---

## 📖 Tartalomjegyzék

- [Executive Summary](#executive-summary)
- [Projekt Háttér](#projekt-háttér)
- [Célok és Követelmények](#célok-és-követelmények)
- [Scope (Hatókör)](#scope-hatókör)
- [Target Audience (Célközönség)](#target-audience-célközönség)
- [Technológiai Döntések](#technológiai-döntések)
- [Fejlesztési Ütemterv](#fejlesztési-ütemterv)
- [Kockázatok és Kihívások](#kockázatok-és-kihívások)
- [Sikermutatók (KPI-k)](#sikermutatók-kpi-k)

---

## Executive Summary

A **Diamond Fitness Management System** egy **mobil-first webes alkalmazás**, amely kis létszámú (max 40-50 fős) fitness stúdiók napi működését támogatja. A rendszer fő céljai:

- ✅ **Egyszerű használat** - Tech-savvy nélküli adminok és idősebb tagok számára
- ✅ **Motiváció növelése** - Gamification elemek (kitűzők, XP, streak)
- ✅ **Költséghatékonyság** - Ingyenes/olcsó hosting (Railway)
- ✅ **GDPR megfelelés** - Minimális adatgyűjtés
- ✅ **Többnyelvűség** - Magyar, Szerb, Angol

### Kulcsstatisztikák

| Metrika | Érték |
|---------|-------|
| **Max felhasználók** | 50 fő (40 tag + 10 admin/edző) |
| **Havi edzések** | ~120-150 alkalom |
| **Várható költség** | $0-5/hó (Railway) |
| **Fejlesztési idő** | 4-6 hét (MVP) |
| **Támogatott nyelvek** | 3 (HU, SR, EN) |

---

## Projekt Háttér

### Miért készült?

A **Diamond Fitness** egy kis, családias fitneszstúdió Esbjergben (Dánia), ahol:

1. **Adminok nem tech-savvy-k** - Nehezen boldogulnak bonyolult rendszerekkel
2. **Tagok idősebb korosztályból** - Egyszerű, nagyméretű gombok, minimális scrolling szükséges
3. **99% mobilhasználat** - A tagok kizárólag telefonról érik el az oldalt
4. **Kis létszám** - Max 40-50 fő, nincs szükség enterprise megoldásra
5. **Minimális költségvetés** - Ingyen vagy nagyon olcsó hosting

### Problémák meglévő megoldásokkal

| Meglévő megoldás | Probléma |
|------------------|----------|
| **Papír alapú nyilvántartás** | Kézzel írott listák, nehezen követhető, elvesznek |
| **Excel táblázatok** | Nincs valós idejű frissítés, nehéz mobil használat |
| **Mindbody / Gymmaster** | Túl drága ($50-200/hó), túl bonyolult |
| **Facebook csoport** | Kaotikus, nincs statisztika, nem professzionális |

### Megoldás

Egy **egyedi fejlesztésű webalkalmazás**, amely:
- ✅ Pontosan a stúdió igényeihez igazodik
- ✅ Egyszerű, barátságos felület (mobil-first)
- ✅ Olcsó/ingyenes üzemeltetés (Railway)
- ✅ Gamification elemekkel motivál
- ✅ GDPR-nak megfelelő adatkezelés

---

## Célok és Követelmények

### Üzleti Célok

1. **Adminisztráció egyszerűsítése**
   - Tag jelentkezések automatikus kezelése
   - Edzések gyors létrehozása (sablonok)
   - Jelenléti ív PDF/CSV export

2. **Tagok motiválása**
   - Kitűzők és XP rendszer (gamification)
   - Sorozat (streak) követés
   - Személyre szabott célok

3. **Költségcsökkentés**
   - Ingyenes/olcsó hosting
   - Minimális karbantartás
   - Skálázható architektúra

4. **GDPR megfelelés**
   - Minimális adatgyűjtés
   - Adatok törlése igény szerint
   - Átlátható adatkezelés

### Funkcionális Követelmények

#### Must Have (MVP)

- ✅ Regisztráció és bejelentkezés (username-based)
- ✅ Admin jóváhagyási folyamat (pending státusz)
- ✅ Edzések létrehozása és böngészése
- ✅ Edzésre jelentkezés/lemondás
- ✅ Személyes statisztikák (edzések száma, kalória)
- ✅ BMI számítás és célkitűzések
- ✅ Súly frissítés és grafikon
- ✅ Kitűzők és XP rendszer (20 db badge)
- ✅ Streak követés
- ✅ 3 nyelvű felület (HU, SR, EN)
- ✅ Admin dashboard (egyszerű, nagy gombok)

#### Should Have (V1.1)

- 🔄 Email értesítések (opcionális)
- 🔄 Figyelmeztetési rendszer (lemondási büntetés)
- 🔄 Árlista kezelés
- 🔄 Galéria modul
- 🔄 Jelenléti ív export (PDF/CSV)
- 🔄 Kapcsolat oldal (térkép)

#### Could Have (Későbbi verziók)

- ⏳ Receptek modul (kommentelés)
- ⏳ Előtte-utána fotók
- ⏳ Push értesítések (PWA)
- ⏳ Mobil app (React Native)
- ⏳ Fizetési integráció (Stripe)

#### Won't Have (Nem célunk)

- ❌ Közösségi funkciók (chat, fórum)
- ❌ Video edzések tárolása
- ❌ AI-alapú személyre szabás
- ❌ Multi-location support (több stúdió)

### Nem-funkcionális Követelmények

| Követelmény | Célérték |
|-------------|----------|
| **Teljesítmény** | < 2 mp oldalbetöltés (3G) |
| **Uptime** | 99.5% (Railway) |
| **Biztonság** | HTTPS, JWT, bcrypt, rate limiting |
| **Mobil támogatás** | 100% funkció mobil eszközökön |
| **Hozzáférhetőség** | WCAG 2.1 AA szint (nagy betűk, kontrasztok) |
| **Skálázhatóság** | 50-100 fő támogatása (extra díj nélkül) |

---

## Scope (Hatókör)

### In Scope (Benne van)

✅ **Tagok kezelése**
- Regisztráció, jóváhagyás, bejelentkezés
- Profil szerkesztés
- Súly követés, BMI számítás

✅ **Edzések kezelése**
- Edzések létrehozása, szerkesztése
- Sablonok mentése
- Résztvevők listája
- Jelenléti ív export

✅ **Motivációs rendszer**
- 20 db kitűző
- XP és level rendszer
- Streak követés

✅ **Adminisztráció**
- Tag jóváhagyás/elutasítás
- Figyelmeztetési rendszer
- Közösségi statisztikák

✅ **Többnyelvűség**
- Magyar, Szerb, Angol

✅ **Deployment**
- Railway hosting
- SQLite/PostgreSQL
- Automatikus deploy (GitHub)

### Out of Scope (Nincs benne)

❌ **Fizetési rendszer** (készpénzes fizetés helyszínen)  
❌ **Video streaming** (edzések videói)  
❌ **Közösségi funkciók** (chat, fórum)  
❌ **Multi-tenant** (több stúdió kezelése)  
❌ **Natív mobilapp** (első verzióban PWA elég)  
❌ **AI javaslatok** (túl komplex kis projekthez)  

---

## Target Audience (Célközönség)

### Primer Felhasználók: Tagok

**Demográfia:**
- **Életkor:** 35-65 év (boomer korosztály)
- **Tech tudás:** Alacsony-közepes
- **Eszköz:** 99% mobil telefon (kis képernyők)
- **Nyelv:** Magyar, Szerb (multi-kulti közösség)

**Igények:**
- 📱 Nagy gombok, egyszerű navigáció
- 🔤 Nagy betűk, jó kontraszt
- 🚫 Minimális scrolling
- 💪 Motiváció (látható fejlődés)
- 🎯 Egyszerű célkitűzés

**Pain points:**
- Nehezen boldogulnak bonyolult felületekkel
- Rosszabb látás (idősebb korosztály)
- Nem szívesen adnak meg túl sok adatot

### Szekunder Felhasználók: Adminok/Edzők

**Demográfia:**
- **Életkor:** 25-45 év
- **Tech tudás:** Alapszintű (nem tudnak copy-paste-elni!)
- **Eszköz:** Laptop/asztali gép (desktop nézet fontos)
- **Szerepkör:** 2-3 személy kezeli az egész stúdiót

**Igények:**
- 🖱️ Nagy gombok, vizuális segítség
- 📋 Wizard-style folyamatok (lépésről-lépésre)
- 📊 Gyors statisztikák
- 📥 Export funkciók (PDF/CSV)
- ⚙️ Egyszerű beállítások

**Pain points:**
- Túlterhelt admin felületek
- Túl sok kattintás egyszerű feladatokhoz
- Nehezen értik a tech terminológiát

---

## Technológiai Döntések

### Miért Node.js + Express?

| Előny | Indoklás |
|-------|----------|
| **Egyszerűség** | Kis learning curve, gyors fejlesztés |
| **JavaScript mindenhol** | Frontend és backend is JS |
| **Nagy közösség** | Rengeteg tutorial, library |
| **Railway támogatás** | Natív Node.js support |

### Miért Prisma ORM?

- ✅ Típusbiztos adatbázis műveletek
- ✅ Egyszerű migráció kezelés
- ✅ SQL injection védelem beépített
- ✅ SQLite és PostgreSQL support

### Miért SQLite kezdésnek?

- ✅ **Ingyenes** (nincs külön DB szerver)
- ✅ **Elég 50 fő kezelésére** (kis projektek ideálisak)
- ✅ **Egyszerű backup** (egy fájl)
- ✅ **Később átváltható** PostgreSQL-re (Prisma miatt)

### Miért Tailwind CSS?

- ✅ Gyors prototípus készítés
- ✅ Reszponzív design utility-kkel
- ✅ Kis bundle size (purge CSS)
- ✅ Könnyen testreszabható (diamond téma)

### Miért Railway?

- ✅ **$5/hó ingyen kredit** (elég kis projekthez)
- ✅ **Automatikus deploy** GitHub-ról
- ✅ **SSL ingyen** (HTTPS automatikus)
- ✅ **Egyszerű setup** (Heroku-szerű)
- ✅ **Nincs alvó mód** (Heroku-val ellentétben)

---

## Fejlesztési Ütemterv

### Fázis 1: MVP (4 hét)

**Hét 1-2: Backend alapok**
- ✅ Prisma setup, adatbázis séma
- ✅ Auth rendszer (JWT, bcrypt)
- ✅ API végpontok (events, users, auth)
- ✅ Badge rendszer (JSON-based)

**Hét 3-4: Frontend és integráció**
- ✅ HTML oldalak (login, dashboard, admin)
- ✅ Tailwind CSS styling (diamond téma)
- ✅ API kapcsolódás (fetch)
- ✅ Többnyelvűség (i18next)

**Hét 4: Deploy és teszt**
- ✅ Railway setup
- ✅ Manuális teszt (adminok + tagok)
- ✅ Bug fixes

### Fázis 2: Fejlesztések (2 hét)

**Hét 5:**
- 🔄 Email értesítések
- 🔄 Figyelmeztetési rendszer
- 🔄 PDF/CSV export

**Hét 6:**
- 🔄 Galéria modul
- 🔄 Árlista kezelés
- 🔄 Polishing (UX javítások)

### Fázis 3: Opcionális (később)

- ⏳ Receptek modul
- ⏳ PWA funkciók (push notifications)
- ⏳ Analytics (Google Analytics)

---

## Kockázatok és Kihívások

### Technikai Kockázatok

| Kockázat | Valószínűség | Hatás | Mitigálás |
|----------|--------------|-------|-----------|
| **Railway költség túllépés** | Alacsony | Közepes | Monitoring, cache, SQLite |
| **SQLite limit elérése** | Alacsony | Magas | Prisma → PostgreSQL migráció kész |
| **Biztonsági rés** | Közepes | Magas | Penetration test, rate limiting |
| **Adatvesztés** | Alacsony | Magas | Napi backup, Railway snapshot |

### Üzleti Kockázatok

| Kockázat | Valószínűség | Hatás | Mitigálás |
|----------|--------------|-------|-----------|
| **Adminok nem használják** | Közepes | Magas | Egyszerű UI, wizard-style, képzés |
| **Tagok ellenállnak** | Alacsony | Közepes | Gamification, vizuális motiváció |
| **GDPR probléma** | Alacsony | Magas | Minimális adatgyűjtés, legal review |

### UX Kihívások

1. **Idősebb korosztály** → Nagy gombok, egyszerű navigáció, tooltipek
2. **Mobil optimalizálás** → Mobil-first design, egyszerű layout
3. **Boomer adminok** → Wizard-style folyamatok, vizuális segítség, videók

---

## Sikermutatók (KPI-k)

### Technikai KPI-k

| Mutató | Célérték | Mérési módszer |
|--------|----------|----------------|
| **Oldalbetöltési idő** | < 2 sec | Lighthouse audit |
| **Uptime** | > 99.5% | UptimeRobot |
| **Havi költség** | < $5 | Railway dashboard |
| **Mobile responsive** | 100% | Manual testing |

### Üzleti KPI-k

| Mutató | Célérték (3 hónap után) | Mérési módszer |
|--------|----------|----------------|
| **Aktív tagok** | > 80% (32/40 fő) | Database query |
| **Havi edzések** | > 100 alkalom | Events count |
| **Admin elégedettség** | > 4/5 | Survey |
| **Tag elégedettség** | > 4/5 | Survey |

### Felhasználói KPI-k

| Mutató | Célérték | Mérési módszer |
|--------|----------|----------------|
| **Átlagos bejelentkezések** | > 2/hét/tag | User analytics |
| **Badge unlock rate** | > 50% (10/20 badge) | Badge analytics |
| **Streak átlag** | > 5 edzés | Streak tracking |
| **Súly frissítés** | > 1/hét/tag | Weight log count |

---

## Következő Lépések

1. ✅ **README.md elkészítése** → Kész
2. ✅ **PROJECT-OVERVIEW.md elkészítése** → Ez a dokumentum
3. 🔄 **DATABASE-SCHEMA.md** → Adatbázis séma részletezése
4. 🔄 **API-DOCUMENTATION.md** → REST API végpontok
5. 🔄 **DEPLOYMENT.md** → Railway deployment lépések
6. 🔄 **Fejlesztés indítása** → Backend setup

---

## Kapcsolat & Támogatás

**Projekt Owner:** Gálfi Dávid Zsolt  
**Email:** galfidavid314@gmail.com  
**GitHub:** [@davidgalfi](https://github.com/davidgalfi)

**Diamond Fitness:**  
**Email:** info@diamond-fitness.hu  
**Telefon:** +36 30 123 4567

---

**Utolsó frissítés:** 2025.12.07.  
**Verzió:** 1.0.0
