# REZ pro Home Assistant OS

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
