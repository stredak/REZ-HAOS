# Změny

## 0.8.1

- opraveno stahování místního certifikátu z Nastavení (chyba 403),
- soukromé TLS klíče zůstávají v chráněné složce,
- test stahování certifikátu přes nginx před vydáním i po restartu.

## 0.8.0

- samostatná HTTPS adresa REZ v domácí síti na portu 8090,
- vlastní přihlášení a odhlášení zařízení, ochrana dokumentů i API,
- vlastní ikona na ploše iPhonu přes Safari,
- automatické místní certifikáty a jejich stažení z Nastavení,
- zachovaný přístup přes Home Assistant i společná databáze,
- ochrana před přepsáním novějších dat z jiného zařízení,
- kontrola spuštění celého kontejneru před zveřejněním aktualizace.

## 0.7.1

- opraveno čtení konfigurace Home Assistantu,
- opraveno spuštění zabezpečené ingress brány nginx.

## 0.7.0

- lokální databáze SQLite bez Supabase,
- dokumenty uložené přímo na Home Assistantu,
- přístup přes zabezpečený Home Assistant Ingress,
- import kompletní ZIP zálohy z webové verze,
- volitelná AI analýza dokumentů s vlastním OpenAI API klíčem.
