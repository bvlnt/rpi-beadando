# RetroPie modern funkciókkal
## Fejlesztői Dokumentáció
### Mit használtunk fel?
Projektünket **Raspberry Pi 2 Model B**-n készítettük el.  

A rendszer alapja a **RetroPie** nevű ingyenes operációs rendszer, amely *Raspbian, EmulationStation és RetroArch* alapjaival készült.  

**Szükséges hardwarek:**
- Ajánlott egy Raspberry 2 vagy annál nagyobb teljesítményű
- Kijelző (HDMI-vel rendelkező)
- USB-s vagy BlueTooth-os joystick
- Micro SD kártya (minimum 8 Gb tárhelyű)
- Billentyűzet a parancssor használatához
- HDMI kábel

Elvégzett plusz feladatok a rendszerben:  
- Feltöltöttük a rendszert a kedvenc játékainkkal ☺
- Felhasználtunk egy Scrapert (*SkyScraper*) ami megjelenít egy videót (játékmenetet) a könyvtárban az adott játék mellett,
- Felhasználtunk egy témakezelőt és töltöttünk fel hozzá különböző ingyenesen elérhető témákat,
- Beüzemeltük az *SSH és SFTP* kapcsolatot, így könnyedén távolról is dolgozhatunk a projekten (vagy adhatunk hozzá további játékokat),
### Miért ezt választottuk
Azért ezt a projektet választottuk magunknak, mert: 
- Tetszett az alapötlete a rendszernek, hogy egy ekkora méretű erőforrással játékok sokaságát vagyunk képesek játszani,
- Könnyedén elérhető, kevés perifériát használ,
- Könnyen és jól fejleszthető / tovább gondolható,
- Szórakoztató
### Kiemelt tulajdonságai a projektnek
- Sok konzol emulálását támogatja (köztük néhány: *GameBoy Advance, Nintendo 64, Nintendo SNES, Sega Genesis*)
- Nagyszínű joystick támogatás, azaz szinte bármilyen kontrollerrel működésbe hozható (teszteltük Sony Dualshock-on és Xbox One kontrollerrel is)
- Működő *motion kontrol*, a joystick fizikai mozgatásával írányíthatunk menüben, és játékban egyaránt (ha a kontroller rendelkezik vele, akkor egyszerűen beállítások nélkül működik)
- Egyszerűen programozható, fejleszthető, bővíthető
- Felhasználó barát
### Fejlesztési lehetőségek
- A kész projekt Arcade Gépbe való importálása

![Arcade Gép](https://www.tinyarcademachines.com/uploads/1/1/6/6/11664734/3004564_orig.jpg)  

- Értesítő üzenet rendszer létrehozása Python scriptek felhasználásával/kódolásával  
*például: ha elérünk egy adott Mérföldkövet akkor kapjunk egy Twitter üzenetet.*
- Többjátékos interneten való hozzáférése
### Források
- https://retropie.org.uk/
- https://lifehacker.com/the-advanced-guide-to-setting-up-a-diy-game-console-wit-1790381861?fbclid=IwAR2iUVfynxsvxwU90BgGt9ELIIPzoQnr5UuBBZ-yuPJmNHVIcal6gvlsJiM
- https://www.youtube.com/user/Mretaprime
- https://github.com/retropie/
---
## Használati Útmutató
### Az eszköz üzembe helyezése
1. Kössük áramforrásra és kijelzőre a projekttünket
2. Amennyiben indításkor új kontrollert észlel abban az esetben automatikusan felajánlja, hogy konfiguráljuk azt, egy egyszerű felhasználóbarát ablakban
3. A menüben konzolok szerint böngészhetünk, majd a kiválasztott konzolon kiválaszthatjuk a kívánt játékot
4. Jó játékot! ☺
### Játékok hozzáadása  
Ehhez két lehetőségünk adott:
- **Játékok hozzáadása hálózaton**
1. Kössük hálózatra (vagy csatlakoztassuk Wifire) a Raspberry Pi-t,
2. Nyissunk meg egy SFTP szolgáltatást nyújtó szoftvert (WinSCP),
3. Csatlakozzunk a Pi-re a következőkkel:  
Host name: `RETROPIE`   
Port number: `22`  
Username: `pi`   
Password: `raspberry`    
Ha első indításra nem fogadja el a *RETROPIE* kiszolgáló nevet, akkor indítsuk újra a Raspberry Pi-t  
4. Helyezzük el az adott játékot(játékokat) a következő helyre: `~/RetroPie/roms/$""` az idézőjelek között válasszuk ki a játék konzolját. (pl: *snes* vagy *gba*)
5. Zárjuk be a kapcsolatot a PC-ről
6. Frissítsük a rendszert F4 lenyomásával, vagy válasszuk ki azt a menüből
- **Játékok hozzáadása pendrive használatával**
1. Győzödjünk meg róla, hogy FAT32 fájlrendszerű az adathordozó
2. Hozzunk létre egy mappát `retropie` néven
3. Csatlakoztassuk a Pi-be majd várjuk meg míg befejezi a villogást
4. Csatlakoztassuk vissza a PC-nkre
5. Helyezzük a kívánt játékokat erre a helyre: `retropie/roms` (a megfelelő konzol mappájába)
6. Csatlakoztassuk a Pi-be vissza és várjuk meg a villogást
7. Húzzuk ki a pendrive-ot
8. Frissítsük a rendszert F4 lenyomásával, vagy válasszuk ki azt a menüből
### Bejelentkezés a Mérdföldkövek/Eredmények (Achievement) követésére
1. Készíts felhasználót a **http://retroachievements.org/** oldalon
2. Lépj a Raspberry parancssorába **(Menu -> Quit)**
3. Írd be a következő utasítást `sudo nano /opt/retropie/configs/all/retroarch.cfg`
4. Keresd meg a fájl végén a `cheevos_username` és `cheevos_password` sort, majd töltsd ki az idézőjelek közti részt a saját felhasználói fiókod adataival.
