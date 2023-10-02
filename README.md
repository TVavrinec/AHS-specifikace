# AHS-Specifikace

Specifikace AHS (Automatické Herní Stanoviště), nástupcem Lucerny a BlackBoxu

## Hrubý popis
Jde o statické zařízení sloužící jako herní stanoviště.
Mělo by tedy být mobilní jen natolik aby nebyl problém jej přepravovat.
Není ale cílem aby ho hráči během hry přesouvali.

## Konkrétní požadavky
- Dva LED kruhy jeden radiální a jeden axiální (tak jak na lucerně)
- Tlaková plocha (tak jak na lucerně ale asi vyměnit samotnou kontaktní plochu aby se zvýšila spolehlivost)
- Výdrž na baterii alespoň pět hodin aby bylo možné organizovat čtyřhodinovou hru s rezervou na nastavování atd.
- Elegantní zapínání (znamená ne powerbankou a kabelem!!!)
- Snadná montáž (znamená ne 16h na jeden kus)
- Základní zvuková odezva (pískle)
- Servisně snadné připojený komunikační/GPS modul uvnitř zařízení (A9, MC60 ???)
- Servisně snadné připojená dvířka a jiné moduly vně základního zařízení

## Plan realizace

### Elektrická část
Ponechat rozdělení na LedDesku a HlavníDesku
#### LedDeska

Oproti v1 přidat LED-kruh i na druhou stranu LedDesky abychom se zbavili LED-pásku a odebrat výstupní konektor.

- Přední axiální kruh z 60ti RGB LEDek
- Zadní LEDkoví kruh z 60ti RGB LEDek (buď přímo radiální [buce cca třikrát dražší] nebo axiální s odraznou plochou [radializátorem])
- LDC1614 nebo LDC1314 + čtyři snímací cívky 

#### Hlavní deska 
- ESP32-S3
- jednočlánek
- Power manager
    - zapínání
    - step-up na 5V
    - LDO na 3V3
    - nabíječka
- Interní systémy
    - dohodnutí PD
    - piezo (bez oscilátorové)
- Konektory na
    - ledDesku
    - komunikační modul
    - externí moduly (USB, CAN nebo UART ala Servio???)
    - USB-C (nabíjení a primární programování [USB přímo z ESP, nebudeme zabírat místo převodníkem])
    - zbylé piny
- mini UI
    - RESET a BOOT tlačítka
    - zapínací tlačítko
    - vypínací tlačítko bych spojil se zapínacím nebo možná s resetem (dlouhí stisk vypíná, nechci tam mít příliž mnoho tlačítek)
    - jedno dvě tlačítka a hloupí ledky?
    - podle místa kontakty na SemiSemafoří programátor     

### mechanická část

- Tělo minimálně v prototypu tisknuté
- Vyzkoušet různé provedení kontaktní plochy
    - Stejně jako na předchozí verzi FR4 ale tlustší aby se tolik nekroutila
    - PCB s hliníkovým jádrem + zalití do epoxidu nebo jiné dostatečně průsvitné hmoty
- Konektor externích modulu, USB-C a mini UI překrýt krytkou (ochrana před bordelem a náhodným mačkáním na tlačítka) 

![stack Overflow](dvirka.png)
