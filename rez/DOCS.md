# REZ pro Home Assistant OS

## Zálohy a rozpracované změny (od 0.9.0)

REZ automaticky jednou denně vytvoří kompletní ZIP evidence a dokumentů do svého úložiště `/data/backups`. Kontrola se spustí minutu po startu a potom každou hodinu. Uchovává se nejnovější úplná záloha za každý z posledních sedmi zálohovaných dnů. V Nastavení REZ je datum posledního úspěchu, případná chyba, ruční spuštění i stažení ZIPů. Pokud chybí příloha, neúplná záloha nenahradí poslední úplnou.

Zálohy na stejném disku nejsou ochranou proti poruše notebooku. Pravidelně si stáhněte kopii mimo notebook a zálohujte také celý HAOS. Volba `auto_backup` automatické zálohy vypíná nebo zapíná. Volitelná `backup_copy_to_share` navíc kopíruje ZIP do `/share/rez-backups` — je-li sdílená složka na stejném disku, stále nejde o nezávislou zálohu. Do ZIPu REZ nepatří hesla, OpenAI klíč ani soukromé certifikáty.

Text rozepsaných formulářů se uchovává sedm dní pouze v prohlížeči daného zařízení. Po obnovení stránky zvolte u rozpracovaného formuláře **Pokračovat**. Přílohy je z bezpečnostních důvodů nutné vybrat znovu. Uložením formuláře se koncept odstraní; tlačítkem **Zahodit** jej lze smazat ručně.

Při ztrátě domácí Wi-Fi REZ označí neuložené změny a pokusí se je uložit po návratu spojení. Pokud mezitím evidenci změnilo jiné zařízení, novější data nepřepíše: nabídne stažení rozpracovaných změn a načtení aktuální domácnosti. Aplikace bez VPN nefunguje mimo domácí síť a první otevření vyžaduje připojení k REZ.

## Samostatná ikona REZ (od 0.8.0)

Aktualizace zachovává databázi i dokumenty. Aplikaci neodinstalovávejte.

1. V konfiguraci aplikace nastavte `local_username` (výchozí `martin`) a `local_password` (vlastní heslo o alespoň 12 znacích). Heslo nikomu neposílejte. `local_address` ponechte `homeassistant.local`, nebo zadejte stálou lokální IP adresu bez protokolu a portu.
2. Uložte konfiguraci a restartujte REZ. Samostatný vstup je dostupný na `https://homeassistant.local:8090` (případně na zadané IP adrese). Port 8090 musí být v nastavení sítě aplikace povolený; nepřesměrovávejte ho na routeru do internetu.
3. Otevřete REZ přes Home Assistant v Safari na iPhonu. V Nastavení REZ stáhněte místní certifikát. V nastavení iPhonu otevřete Obecné → VPN a správa zařízení a certifikát nainstalujte. Potom v Obecné → Informace → Důvěryhodnost certifikátů povolte „REZ Local Home CA“. Instalujete certifikační autoritu své vlastní domácí instance; její soukromý klíč zůstává na HAOS.
4. Otevřete samostatnou HTTPS adresu v Safari, přihlaste se a zvolte Sdílet → Přidat na plochu. Ikona bude otevírat REZ bez nabídky Home Assistantu. Nepokračujte přes varování certifikátu — nejprve dokončete jeho instalaci a důvěryhodnost.

Na Windows lze stejný certifikát nainstalovat pro aktuálního uživatele do Důvěryhodných kořenových certifikačních autorit. Samostatné přihlášení vydrží 30 dní; restart aplikace nebo změna hesla vyžaduje nové přihlášení. Přístup přes Home Assistant funguje i bez nastaveného samostatného hesla.

Při zapomenutí hesla jej změňte v konfiguraci aplikace v Home Assistantu a restartujte REZ. Oba vstupy používají stejnou databázi a dokumenty, data se nekopírují. Telefon musí být ve stejné domácí síti. Vzdálený přístup lze později řešit vlastní VPN; Tailscale není vyžadovaný.

REZ běží jako soukromá aplikace uvnitř Home Assistantu. Přístup je chráněný přihlášením do Home Assistantu a aplikace neotevírá žádný veřejný port.

## První spuštění

1. Nainstalujte a spusťte aplikaci REZ.
2. Zapněte volbu **Zobrazit v postranním panelu**.
3. Otevřete REZ a v **Nastavení → Záloha REZ** zvolte **Obnovit kompletní ZIP ze staré verze**.
4. Vyberte kompletní ZIP vytvořený ve webové verzi REZ.
5. Zkontrolujte počty místností, spotřebičů a dokumentů.

Data jsou uložena v trvalé složce `/data` aplikace a jsou součástí zálohy Home Assistantu.

## AI analýza dokumentů

Pokud chcete používat rozpoznávání faktur, vložte v konfiguraci aplikace vlastní OpenAI API klíč. Klíč zůstává v konfiguraci Home Assistantu a nezapisuje se do databáze REZ.
