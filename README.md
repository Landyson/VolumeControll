**Volume Controller**  


Desktopová aplikace pro Windows, která umožňuje hardwarově ovládat systémovou (master) i aplikační hlasitost pomocí Arduino Nano s lineárními potenciometry. Projekt je ideální pro uživatele, kteří chtějí mít fyzické ovládání hlasitosti pro konkrétní programy (Spotify, Discord, webový prohlížeč apod.).

---

## Funkce

- Ovládání systémové (master) hlasitosti  
- Ovládání hlasitosti jednotlivých běžících aplikací  
- Automatická detekce připojeného Arduino Nano  
- Uživatelské GUI pro výběr aplikací a vizualizaci aktuálních úrovní hlasitosti  
- Minimalizace do systémové lišty s možností rychlého přístupu  
- Open-source desktopová aplikace (deej.exe) v C++ a firmware v Wiring/C++

---

## Požadavky

- **Hardware:**
  - Arduino Nano  
  - 2–8 lineárních potenciometrů (dle počtu kanálů)  
  - Propojovací kabely  
  - Nepájivé pole (breadboard)

- **Software (desktop):**
  - Windows 10 nebo novější  
  - C++17-kompatibilní kompilátor (MSVC, MinGW apod.)  
  - Windows Core Audio API (WASAPI) nebo jiná knihovna pro řízení hlasitosti  
  - Konfigurační soubor `config.yaml` pro mapování potenciometrů na audio kanály

- **Firmware:**
  - Arduino IDE (Wiring/C++)

---

## Instalace

1. **Firmware (Arduino Nano):**  
   1. Připojte lineární potenciometry k analogovým pinům Arduino Nano.  
   2. Otevřete `deej-5-sliders-vanilla.ino` v Arduino IDE.  
   3. Vyberte desku "Arduino Nano" a správný port.  
   4. Nahrajte firmware.

2. **Stáhnout desktopovou aplikaci (deej.exe):**  
   ```bash
   git clone https://github.com/omriharel/deej.git
   cd deej/desktop
   mkdir build && cd build
   cmake .. && cmake --build .

---   

## Knfigurace

- Soubor `config.yaml` obsahuje mapování analogových pinů Arduino na cílové aplikace a jejich zobrazovaná jména
- Příklad `config.yaml`:
  ```bash
  slider_mapping:
  0: master
  1: 
  2: opera.exe
  3: spotify.exe
  4: discord.exe

  com_port: COM5
  baud_rate: 9600

---

## Spuštění

  1. Připojte Arduino Nano k počítači přes USB
  2. Ujistěte se, že máte správně nakonfigurovaný `config.yaml` ve stejné složce jako `deej.exe`
  3. Spusťte `deej.exe`
  4. Teď už by mělo vše fungovat

---

## Opensource
  
 https://github.com/omriharel/deej
  
