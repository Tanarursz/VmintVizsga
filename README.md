# **PR - Hivatalos Vizsgafeladat**

## **Bevezetés**

A feladat egy középvállalati informatikai rendszer tervezését és konfigurálását szimulálja. A **Robbanas** egy dinamikusan fejlődő vállalat, amely modern IT infrastruktúrát kíván létrehozni egy új irodai központ számára. A cég célja egy stabil és biztonságos szerverrendszer kiépítése, amely támogatja az alkalmazottak napi munkáját, miközben megfelelő hálózati és biztonsági irányelveket alkalmaz.

A projekt során egy Windows-alapú szerverkörnyezetet kell kialakítani, amely tartalmaz egy tartományvezérlőt, DHCP szolgáltatást, nyomtatószervert, és egy központi biztonsági mentési megoldást.

**Tantárgy:** Szerverek és felhőszolgáltatások

**Vizsgázó neve:**  _______________________________

**Dátum:**  _______________________________

**Instrukciók:**

- A dolgozat során csak a megadott hálózati tartományt és konfigurációs beállításokat használja.
- A vizsga teljes időtartama: korlátlan az órák végéig

---

## **Feladatok és követelmények:**

### **1. VirtualBox konfiguráció (1 pont)**
- Hozzon létre egy virtuális környezetet, amely biztosítja a szerver és a kliensgépek megfelelő működését. (meghajtók, hálókátyák)

### **2. Alapvető kliensbeállítások (3 pont)**
- Állítsa be a megfelelő hálózati interfészeket. (2p)
- A számítógép azonosító neve legyen: „kliens”. (1p)
- A kliens DNS-kiszolgálója a szerver IP-címe legyen.


### **3. Alapvető szerverbeállítások (9 pont)**
- Állítsa be a megfelelő hálózati interfészeket. (1p)
- A szerver IP-címe a hálózat utolsó kiosztható címe legyen. (2p)
- A szerver neve legyen: „szerver”. (1p)
- Telepítse a szükséges szoftvereket és szolgáltatásokat. (3p)
- A szerveren az elsődleges DNS a 8.8.8.8, a másodlagos DNS pedig 1.1.1.1 harmadlagosnak 8.8.4.4

### **4. Active Directory tartományvezérlő telepítése és konfigurálása (3 pont)**
- A tartomány neve legyen: „robbanas.hu”. (1p)
- A jelszó **Aa1234** legyen
- Hozza létre a "dolgozok" és "adminok" csoportokat.
- Adja hozzá a következő felhasználókat: (1p)
- Mindegyik felhasználónak **Aa1234.** legyen a jelszava

| Teljes név             | Belépési név | Csoport  |
| ---------------------- | ------------ | -------- |
| Vickes Viktor          | vickes       | dolgozok |
| Szorgalmas Szebasztián | szorgalmas   | dolgozok |
| Dolgozó Olga           | dolgozo      | adminok  |

- Hozzon létre egy megosztott mappát, amely csak **olvasási** joggal rendelkezik és automatikusan felcsatolásra kerül. (1p)

### **7. Távoli asztal elérés konfigurálása és tesztelése (1 pont)**
- Engedélyezze a távoli asztali kapcsolatot és ellenőrizze annak működését.

### **9. RAID (2 pont)**
- Hozzon létre egy meghajtókat (5 db, a tárhely kapacitása szabadon választható)

---

## **Hálózati kiosztás 192.168.10.0/28 (255.255.255.240)**

| Eszköz              | IP-cím        | Megjegyzés                      |
| ------------------- | ------------- | ------------------------------- |
| Tiltott IP 1        | 192.168.10.1  | Tiltott IP-cím                  |
| Tiltott IP 2        | 192.168.10.2  | Tiltott IP-cím                  |
| Tiltott IP 3        | 192.168.10.3  | Tiltott IP-cím                  |
| FeladatK (kliens)   | DHCP          | Kliensgép a feladat szerint     |
| FeladatSZ (szerver) | 192.168.10.14 | Szerver az utolsó kiosztott cím |

---

**Megjegyzések és értékelés:**

| Feladat                  | Max. Pont | Elért Pont |
| ------------------------ | --------- | ---------- |
| VirtualBox konfiguráció  | 1         |       1    |
| Kliensbeállítások        | 3         |       3    |
| Szerverbeállítások       | 9         |       9    |
| AD tartományvezérlő      | 3         |       3    |
| Tartományba léptetés     | 2         |       2    |
| DHCP konfigurálása       | 3         |       3    |
| Távoli asztal beállítása | 1         |       1    |
| Nyomtatószerver          | 2         |       2    |
| Windows Server Backup    | 2         |       2    |
| **Összesen**             | **26**    | **/26**      |

**Vizsgáztató aláírása:** _______________________________

**Megjegyzések:**

---

A vizsga befejezése után kérjük, hogy adja le a dokumentációt és az ellenőrzési jegyzőkönyvet a vizsgáztatónak.



# **Ubuntu Szerver Vizsgafeladat**

---

## **Feladatok és követelmények:**

### **1. Rendszerindítás és GRUB konfiguráció (2 pont)**
- Tekintse meg és szerkessze a GRUB konfigurációt úgy, hogy az időzítés 5 másodpercre legyen állítva. (1p)
- Frissítse a GRUB beállításokat. (1p)


---

### **2. Futási szintek és systemd konfiguráció (2 pont)**
- Állítsa be a szervert úgy, hogy mindig multi-user.target állapotban induljon. (2p)


---

### **3. Statikus IP-cím beállítása (3 pont)**
- Nyissa meg és szerkessze a Netplan konfigurációt. (1p)
- Állítsa be az IP-címet 192.168.1.69/24-re. (1p)
- Alkalmazza a beállításokat és ellenőrizze az új IP-címet. (1p)


---

### **4. Fájlrendszer és particionálás (3 pont)**
- Listázza ki a csatlakoztatott meghajtókat. (1p)
- Hozzon létre egy új partíciót a `/dev/sdb` meghajtón. (1p)
- Formázza azt **ext4** fájlrendszerre. (1p)

---

---

---

### **7. DHCP szerver beállítása (4 pont)**
- Telepítse és konfigurálja az **ISC DHCP szervert**. (1p)
- Állítsa be a DHCP hatókört **192.168.1.100-192.168.1.200** tartományban. (1p)
- Állítsa be az alapértelmezett átjárót 192.168.1.69-re. (1p)
- Engedélyezze és indítsa el a DHCP szolgáltatást. (1p)

---

### **8. Apache webkiszolgáló telepítése (2 pont)**
- Telepítse az **Apache** webkiszolgálót. (1p)
- Indítsa el és ellenőrizze a működését. (1p)

---

---

---

## **Értékelés**

| Feladat                  | Max. Pont | Elért Pont |
| ------------------------ | --------- | ---------- |
| Rendszerindítás és GRUB  | 2         |            |
| Futási szintek beállítása | 2         |            |
| Statikus IP beállítása    | 3         |            |
| Particionálás és fájlrendszer | 3   |            |
| Linkek kezelése          | 2         |            |
| Fájlhozzáférések         | 3         |            |
| DHCP szerver konfigurálás | 4        |            |
| Apache webkiszolgáló     | 2         |            |
| MySQL szerver beállítása | 3         |            |
| Tűzfal beállítások       | 3         |            |
| **Összesen**             | **27**    | **/**      |

---

**Vizsgáztató aláírása:** _______________________________

A vizsga befejezése után kérjük, hogy adja le a dokumentációt és az ellenőrzési jegyzőkönyvet a vizsgáztatónak.
