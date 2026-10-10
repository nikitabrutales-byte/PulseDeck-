# Podklady pro Google Play — PulseDeck

**Název:** PulseDeck  
**Krátký popis:** Dvoukanálový DJ přehrávač s waveformem, ekvalizérem a synchronizací tempa.  
**Plný popis:** PulseDeck je dvoukanálový DJ přehrávač pro Android v horizontálním rozložení. Umožňuje načíst hudební soubory do levé a pravé desky, sledovat průběh skladby, ovládat přehrávání, nastavovat hlasitost, gain a ekvalizér HIGH/MID/LOW a použít synchronizaci mezi deskami. Zpracování hudby probíhá lokálně v zařízení.

## Soukromí
Současná implementace neobsahuje síťové oprávnění a je navržena pro lokální zpracování skladeb. Před publikací ověřte skutečné chování výsledného APK/AAB a doplňte veřejně dostupné URL zásad ochrany soukromí, pokud je Play Console vyžádá.

## Před zveřejněním
- Vytvořit vlastní podpisový klíč a zálohovat jej bezpečně.
- Vygenerovat podepsaný Android App Bundle (`.aab`).
- Otestovat načítání MP3/WAV, zvuk na pozadí, přepínání obrazovek, EQ a SYNC na reálných zařízeních.
- Připravit ikonu, screenshoty v horizontálním režimu a klasifikaci obsahu.
- Dokončit formuláře a testovací stopu v Google Play Console.
- Odeslat ke kontrole; zveřejnění není automatické.
