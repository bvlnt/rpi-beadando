# RetroPie modern funkciókkal
## Fejlesztői Dokumentáció
### Mit használtunk fel
Projektünket **Raspberry Pi 2 Model B**-n készítettük el.  

A rendszer alapja a **RetroPie** nevű operációs rendszer, amely *Raspbian, EmulationStation és RetroArch* alapjaival készült.  

Szükséges hardwarek:
- Ajánlott egy Raspberry 2 vagy annál nagyobb teljesítményű
- Kijelző (HDMI-vel rendelkező)
- USB-s vagy BlueTooth-os joystick
- Micro SD kártya (minimum 8 Gb tárhelyű)
- Billentyűzet a parancssor használatához
- HDMI kábel

Elvégzett plusz feladatok a rendszerben:
- Felhasználtunk egy Scrapert (SkyScrapert) ami megjelenít egy videót a könyvtárban az adott játék mellett,
- Felhasználtunk egy témakezelőt és töltöttünk fel hozzá különböző ingyenesen elérhető témákat,
- Létrehoztunk SSH és SFTP kapcsolatot, így könnyedén távolról is hozzáadhatóak plusz játékok és további dolgok a projekthez,
### Miért ezt választottuk
Azért ezt a projektet választottuk magunknak, mert: 
- Tetszett az alapötlete a rendszernek, hogy egy ekkora méretű erőforrással játékok sokaságát vagyunk képesek játszani,
- Könnyedén elérhető, kevés perifériát használ,
- Könnyen és jól fejleszthető / tovább gondolható,
- Szórakoztató
### Kiemelt tulajdonságai a projektnek
### Fejlesztési lehetőségek
- A kész projekt Arcade Gépbe való importálása  
![Arcade Gép](https://www.tinyarcademachines.com/uploads/1/1/6/6/11664734/3004564_orig.jpg)  
- Értesítő üzenet rendszer létrehozása Python scriptek felhasználásával/kódolásával  
*például: ha elérünk egy adott Mérföldkövet akkor kapjunk egy Twitter üzenetet.*
- 
### Források
- https://retropie.org.uk/
- https://lifehacker.com/the-advanced-guide-to-setting-up-a-diy-game-console-wit-1790381861?fbclid=IwAR2iUVfynxsvxwU90BgGt9ELIIPzoQnr5UuBBZ-yuPJmNHVIcal6gvlsJiM
- https://www.youtube.com/user/Mretaprime
---
## Használati Útmutató
### Bejelentkezés a Mérdföldkövek/Eredmények (Achievement) követésére
1. Készíts felhasználót a **http://retroachievements.org/** oldalon
2. Lépj a Raspberry parancssorába **(Menu -> Quit)**
3. Írd be a következő utasítást `sudo nano /opt/retropie/configs/all/retroarch.cfg`
4. Keresd meg a fájl végén a `cheevos_username` és `cheevos_password` sort, majd töltsd ki az idézőjelek közti részt a saját felhasználói fiókod adataival.
