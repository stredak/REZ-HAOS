# REZ pro Home Assistant OS

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
