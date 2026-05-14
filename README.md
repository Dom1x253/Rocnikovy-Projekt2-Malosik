# Dokumentace k projektu: Domácí síť a konfigurace routeru
> **Autor:** Dominik Malošík  
> **Téma:** Praktické nastavení a optimalizace TP-Link Archer C6 v reálném prostředí

---

# Úvodní slovo a cíle projektu
Když jsem začínal, router pro mě byl jen "černá krabička s anténami", která prostě nějak funguje. Cílem tohoto projektu bylo podívat se pod kapotu a zkusit si celou tu věc nastavit úplně od nuly. Chtěl jsem pochopit, proč se někdy Wi-Fi seká, jaký je rozdíl mezi těmi všemi čísly v nastavení a hlavně si vyzkoušet, jestli zvládnu zabezpečit síť tak, aby byla jenom moje.

**Co jsem si od projektu sliboval:** 

* Že se naučím router správně zapojit a oživit.
* Že pochopím rozdíly mezi frekvencemi (2.4 GHz vs 5 GHz).
* Že si sám změřím, jestli moje nastavení k něčemu bylo.

---

# Hardwarové vybavení
Pro projekt jsem použil běžně dostupné vybavení, které máme doma, takže šlo o test v reálných podmínkách:
1.  **Router:** TP-Link Archer C6 (dvoupásmový gigabitový router).
2.  **Kabeláž:** Standardní Ethernet kabely (UTP Cat5e) pro propojení s internetem a počítačem.
3.  **Koncová zařízení:** Můj stolní počítač (připojen kabelem), notebook a mobilní telefon (připojeny přes Wi-Fi).

---

# Detailní postup realizace

## 1. Fyzické zapojení
Nejdřív bylo potřeba router vůbec dostat do provozu. Zapojil jsem ho do elektřiny a nastal první důležitý krok: propojení s vnějším světem. Internetový kabel, co mi vede od poskytovatele, jsem zapojil do modrého portu (WAN). Potom jsem vzal druhý kabel a propojil jeden ze žlutých portů (LAN) se svým počítačem. 


## 2. Vstup do administrace
Do adresního řádku v prohlížeči jsem naťukal adresu `192.168.0.1`. Objevila se přihlašovací stránka. Protože byl router v továrním nastavení (po resetu), musel jsem si vymyslet nové silné heslo pro správce. Tím jsem zajistil, že se do nastavení nedostane nikdo cizí.

## 3. Nastavení bezdrátových sítí (Wi-Fi)
Rozhodl jsem se, že nebudu mít jen jednu síť, ale rozdělím to na dvě pásma, abych mohl lépe řídit rychlost a dosah.

#### **Pásmo 2.4 GHz – Lepší dosah**
* **Kanál:** Zvolil jsem pevně kanál 13. Pomocí analýzy jsem zjistil, že je nejméně zarušený.
* **Šířka kanálu:** Nastavil jsem 20 MHz pro maximální stabilitu signálu.
* **Zabezpečení:** Šifrování WPA2-PSK (AES) se silným heslem.

#### **Pásmo 5 GHz – Maximální rychlost**
* **Šířka pásma:** Tady jsem nastavil 80 MHz, aby internet běžel co nejrychleji.
* **Kanál:** Nastavil jsem kanál 36 (v pásmu UNII-1).

---

# Měření rychlosti a důkaz funkčnosti
*Zde jsou výsledky mých měření, které potvrzují, že nastavení proběhlo správně.*

## Měření 1: Kabelové připojení (Referenční)
Kabel je základ. Tady jsem naměřil maximální rychlost. Je to nejstabilnější způsob připojení.
 **<img width="405" height="185" alt="Snímek obrazovky 2026-05-14 194021" src="https://github.com/user-attachments/assets/b38d4422-40f3-4825-b3a2-bec4a78c4691" />**


## Měření 2: Wi-Fi 5 GHz (V obýváku)
Tady mě překvapilo, jak blízko se rychlost blíží kabelu. Na běžnou práci i streamování je to naprosto ideální.
**<img width="405" height="185" alt="Snímek obrazovky 2026-05-14 193249" src="https://github.com/user-attachments/assets/0915e9a0-664a-41cf-abbf-04a9f754a2a9" />**


## Měření 3: Wi-Fi 2.4 GHz (V kuchyni přes stěnu)
Tady je vidět propad rychlosti kvůli vzdálenosti a překážkám, ale signál je pořád stabilní.
**<img width="442" height="184" alt="Snímek obrazovky 2026-05-14 194707" src="https://github.com/user-attachments/assets/4317a9bc-429b-4ecc-b21e-a98c34810046" />**

---

# Analýza okolních sítí (Prostředí panelového domu)
Bydlím v paneláku, takže kolem mě je spousta dalších Wi-Fi sítí. Použil jsem aplikaci **WiFi Analyzer**, abych zjistil, jak moc se moje síť "pere" s ostatními.

**<img width="733" height="354" alt="Snímek obrazovky 2026-05-14 195512" src="https://github.com/user-attachments/assets/1b0596c1-0849-4c67-88c7-a4430575568f" />


Na základě tohoto grafu jsem zjistil, že automatické nastavení kanálů nefunguje vždycky nejlépe. Ručním přepnutím na kanál 13 jsem se vyhnul největšímu rušení od sousedů, což znatelně zlepšilo odezvu (ping).

---

# Problémy, které jsem řešil
Nebylo to úplně bez chyby. Nejdřív mi na počítači vůbec nešla najít 5 GHz síť, i když na mobilu fungovala. Musel jsem v nastavení routeru změnit vysílací kanál a aktualizovat ovladače síťové karty. Také jsem bojoval s dosahem signálu v zadních místnostech bytu, což jsem vyřešil lepším natočením antén routeru.

---

# Použité zdroje a citace
Při práci jsem čerpal z těchto zdrojů:
1.  **Video návod:** [YouTube] "How to configure TP-Link Archer C6" (pomohlo mi s prvotním nastavením).
2.  **Odborné články:** Webové stránky o síťových technologiích (vysvětlení standardů 802.11ac).
3.  **Konzultace s AI (ChatGPT):** Umělá inteligence mi pomohla vysvětlit rozdíl mezi šířkou kanálu 20 MHz a 80 MHz a doporučila vhodné zabezpečení.

---

# Sebereflexe a závěr
Tento projekt pro mě byl hodně přínosný. Předtím jsem jen věděl, že v rohu místnosti bliká nějaká krabička, ale teď už vím, jak ji ovládat. 

**Porozuměl jsem díky tomu spoustě nových věcí:**
* Už vím, jaký je rozdíl mezi tím, když se připojím kabelem a vzduchem.
* Naučil jsem se, že Wi-Fi není jen jedna, ale že existují různá pásma, která se hodí na něco jiného.
* Zjistil jsem, jak důležité je zabezpečení a že výběr správného kanálu může reálně zrychlit internet.

Celkově jsem rád, že jsem si to vyzkoušel sám "na vlastní kůži". Teď už se nebojím, že kdyby internet vypadl, nebudu si vědět rady.
