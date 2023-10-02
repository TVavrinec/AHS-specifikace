# Moduloví Konektor

Bavili sme se o nejrůznějších možnostech.

## bavili sme se o
- I2C + UART obojí v diferenciálním provedení (vyřazeno)

- CAN
    - výhody
        1. je diferenciální
        1. pravděpodobně poměrně malá a jednoduchá implementace
- USB
    - výhody
        1. je diferenciální
        1. mohli by sme používat standardní USB zařízení
    - nevýhoda
        1. asi bude dost paměťožravé
        1. max sedm zařízení(hubu) za sebou (nemyslim si že je to nějak zvlášť omezující)

- UART (po vzoru Servia)
    - full-duplex ale s tím že moduly musí, když nevysílají, odpojovat TX
    - výhody
        1. UART je všude => nevyžaduje žádný dodatečný hardware 
    - nevýhody
        1. potenciální zarušitelnost (v našich podmínkách bezvýznamná, problém by mohl být teprve když by sme měli moduli na kabelu)
        1. kvuli nutnosti odpojovat TX nestandardní implementace a náročnější obsluha