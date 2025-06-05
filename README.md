# PS2-NAN - Dispozitiv de detectare a umidității 🌧️📡

Proiect realizat cu **Arduino IoT Cloud** pentru detectarea umidității și trimiterea de alerte prin email în timp real.

## 🔧 Ce face acest proiect

- Monitorizează prezența umidității printr-un senzor digital.
- Trimite automat un email de alertă atunci când este detectată umiditate.
- Afișează temperatura curentă în Dashboard-ul Arduino IoT Cloud.
- Permite programarea unui LED printr-un scheduler online.
- Păstrează în EEPROM istoricul mesajelor și al alertelor cu dată și oră.

## 🧰 Hardware folosit

- Arduino R4 WIFI
- Buton care simuleaza detectarea umidității (digital, pe pinul D4)
- Senzor de temperatură analogic LM35 (pe A0)
- LED (pe pinul D2)
- EEPROM intern

## ☁️ Integrare cu Arduino IoT Cloud

Variabile utilizate:
- `mesaj` (String) – mesaj citit din interfața Web și afișat în Serial Monitor și salvat în EEPROM
- `led` (CloudLight) – control LED
- `temperature` (CloudTemperatureSensor) – temperatura senzorului
- `orar` (CloudSchedule) – scheduler pentru LED
- `afiseazaMesaj` (bool) – trigger pentru afișarea mesajului

## 📬 Trimitere Email

Folosim SMTP2GO pentru trimiterea alertelor:

- Server: `mail.smtp2go.com`
- Port: `2525`
- Autentificare: `base64(username)` și `base64(password)`
- Email trimis către: `pichler.gabriel2@gmail.com`

> ⚠️ Asigură-te că ai cont SMTP2GO și că ai activat autentificarea de tip SMTP.

## 💾 Salvare locală (EEPROM)

- Ultimele 10 mesaje și alerte cu timestamp sunt salvate în EEPROM.
- Fiecare intrare are o lungime maximă de 30 caractere.

## 🖥️ Cum rulezi proiectul

1. Descarcă codul din acest repository
2. Deschide fișierul `.ino` în Arduino IDE
3. Asigură-te că ai biblioteca `ArduinoIoTCloud` și `WiFi` instalate
4. Configurează datele de autentificare în `thingProperties.h`
5. Încarcă pe placă (Arduino R4 WIFI)
6. Monitorizează via Serial Monitor și Dashboard

## 📸 Capturi de ecran

- Dashboard Arduino IoT Cloud
  
![image](https://github.com/user-attachments/assets/165e1ff2-b844-427e-ae6d-840e9c75af1a)
- Montaj circuit
  
![image](https://github.com/user-attachments/assets/02e052af-ee16-4db2-9886-e8475ba16382)


## 👨‍💻 Autori

- **Adelin-Sebastian Sima** - student la Universitatea Politehnica Timișoara, Facultatea de Automatică și Calculatoare, specializarea Ingineria Sistemelor, anul 3
- **Viorel-Gabriel Pichler** - student la Universitatea Politehnica Timișoara, Facultatea de Automatică și Calculatoare, specializarea Ingineria Sistemelor, anul 3

## 📜 Licenta

Proiect făcut pentru a servi la proiectul sincretic 2 din anul 3 de facultate, publicat cu scop educațional. Poți folosi liber codul pentru învățare sau proiecte personale.

---

