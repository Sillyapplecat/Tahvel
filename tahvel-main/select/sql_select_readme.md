# 📘 SQL SELECT Päringute Harjutus

## 🎯 Eesmärk
Koosta **6 kasulikku SELECT-päringut** oma andmebaasiskeema kohta, mis annavad rakenduse kasutajale või administraatorile olulist infot.  
Kõik päringud on salvestatud faili **`SELECT.sql`**, mille tulemused saab suunata faili **`tulemused.txt`**.

---

## ⚙️ Paigaldus ja käivitamine

### 1. Laadi projekt alla
```bash
git clone https://github.com/Sillyapplecat/Tahvel.git
cd Tahvel/tahvel-main/select

```

### 2. Veendu, et Docker töötab
Kontrolli, kas konteiner nimega **tahvel_mariadb** on aktiivne:
```bash
doas docker ps
```

Kui konteinerit ei ole, käivita see:
```bash
doas docker start tahvel_mariadb
```

### 3. Käivita SQL-päringud
Failis **`SELECT.sql`** olevad päringud käivitatakse järgmise käsuga:
```bash
doas docker exec -i tahvel_mariadb mysql -ustudent -pPassw0rd < SELECT.sql
```

### 4. Salvesta tulemused faili
Kui soovid väljundit salvestada faili **`tulemused.txt`**, kasuta:
```bash
doas docker exec -i tahvel_mariadb mysql -ustudent -pPassw0rd < SELECT.sql > tulemused.txt
```

---

## 📂 Failid

| Fail | Kirjeldus |
|------|------------|
| `SELECT.sql` | Sisaldab 6 ülesandele vastavat SELECT-päringut. |
| `tulemused.txt` | Siia salvestatakse päringute tulemused. |
| `README.md` | Ülesande kirjeldus, käsud ja juhised. |

---

## 🧩 Ülesande kirjeldus ja kriteeriumid

Kõik päringud peavad:
- ✅ töötama (tagastama vähemalt 1 rea);
- ✅ kasutama projekti andmebaasiskeemi välju ja seoseid;
- ✅ olema äriliselt kasulikud (õpetajale, õpilasele või administraatorile);
- ✅ sisaldama vähemalt:
  - `WHERE` tingimust
  - `JOIN` (vähemalt 1 INNER või LEFT JOIN)
  - agregeerimisfunktsiooni (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`)
  - `GROUP BY`
  - `HAVING`
  - `ORDER BY`
  - `LIMIT` (vajadusel)

Iga päring peab olema kommenteeritud (eesmärk + oodatav tulemus).

---

## 🧠 Päringute ülevaade

| Nr | Teema | Kasutatud SQL elemendid | Eesmärk |
|----|-------|--------------------------|----------|
| 1 | Lähinädala kodutööd | `WHERE`, `ORDER BY`, `LIMIT` | Näitab, millised kodutööd tuleb esitada järgmisel nädalal. |
| 2 | Õpilaste puudumised | `JOIN 3 tabelit`, `WHERE` | Kuvab viimase nädala puudujad koos tundide teemadega. |
| 3 | Klasside suurused | `GROUP BY`, `COUNT` | Kuvab iga klassi õpilaste arvu. |
| 4 | Õpetajate tunnid | `GROUP BY`, `WHERE`, `HAVING` | Kuvab iga õpetaja antud tundide arvu viimase kuu jooksul. |
| 5 | Hindamata tööd | `LEFT JOIN`, `WHERE`, `ORDER BY` | Kuvab esitamised, mis ootavad hindamist. |
| 6 | Ainete keskmised hinded | `AVG`, `GROUP BY`, `HAVING` | Kuvab iga aine keskmise hinde. |

---

## ✅ Kokkuvõte

Kõik päringud:
- on loogilised ja kasulikud;
- töötavad ilma vigadeta;
- vastavad kõikidele ülesande kriteeriumidele;
- on kommenteeritud ja struktureeritud eesti keeles.
