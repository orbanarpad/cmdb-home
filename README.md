A beadott projektem neve: cmdb-home, egy egyszerű konfigurációkezelő alkalmazás, amit otthoni felhasználásra terveztem.

A rendszer célja, hogy egy felhasználó nyilvántarthassa a saját számítástechnikai eszközeit – például laptopokat, szoftvereket, előfizetéseket.

A rendszer webes felületen érhető el, reszponzív kialakítással, így számítógépen és mobilon is jól használható.

A háttérben SQLite adatbázis fut, amit egy Node.js + Express API kezel.

A felhasználók saját eszközeiket látják, míg az admin felhasználó minden adatot elér.

A forráskód egyszerű, jól kommentált, a dokumentációban minden szükséges technikai részlet szerepel.

A rendszer saját gépen futtatható, és beadásra kész.

Rendszertechnikai áttekintés
Frontend: HTML + Bootstrap + JavaScript
Backend: Node.js + Express
Adatbázis: SQLite3 (fájl alapú)

REST végpontok:
Módszer	Útvonal	Leírás
POST	/login	Bejelentkezés
GET	/devices	Saját eszközök lekérdezése
POST	/devices	Új eszköz mentése
GET	/admin/devices	Összes eszköz (admin)
DELETE	/devices/:id	Eszköz törlése (opcionális)

Futtatás lépései:
Telepíts Node.js-t

Parancssorban:
cd backend
npm install
node server.js

Böngészőből nyisd meg: frontend/index.html

CMDB-Home – Felhasználói dokumentáció
Cél:
A rendszer lehetővé teszi otthoni felhasználók számára, hogy eszközeiket nyilvántartsák.

Bejelentkezés:
Indítsd el a rendszert (Node.js és SQLite szükséges).

Böngészőben nyisd meg az index.html fájlt.

Jelentkezz be a következő adatokkal:

Felhasználó: teszt / teszt123

Admin: admin / admin123

Eszköz hozzáadása:
Töltsd ki az eszköz nevét, típusát, vételárát, vásárlás dátumát és tárolási helyét.

Nyomd meg a "Hozzáadás" gombot.

Az eszköz megjelenik a listában.

Lista:
A felhasználó csak a saját eszközeit látja.

Az admin az összes eszközt látja.

Adatbázisstruktúra:
users:
| id | username | password | role  |
| -- | -------- | -------- | ----- |
| 1  | admin    | admin123 | admin |
| 2  | teszt    | teszt123 | user  |

devices:
| id |  user_id | name   | type     |  purchase_date | price  | location  |
| -- | -------- | ------ | -------- | -------------- | ------ | --------- |
| 1  | 2        | Laptop | hardver  | 2023-01-01     | 250000 | Otthon    |
| 2  | 2        | Office | szoftver | 2024-01-01     | 35000  | Munkahely |

'''Fájlstruktúra'''
cmdb-home/
├── backend/
│   ├── server.js
│   ├── db.js
│   └── auth.js
├── frontend/
│   ├── index.html
│   ├── dashboard.html
│   └── script.js
├── database/
│   └── cmdb.sqlite
└── docs/
    ├── dokumentáció.txt (leírás lásd lent)
    ├── readme.txt (kódmagyarázat itt)
'''    └── prezi_short.txt (rövid prezentáció)'''
