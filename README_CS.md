# PulseDeck pro Android — projekt 1.0.0

Toto je nativní Android Studio projekt pro aplikaci PulseDeck. Schválená verze PulseDeck 2.4 je zabalena uvnitř aplikace v `app/src/main/assets/index.html`; uživatel nemusí HTML soubor ručně otevírat.

## Co projekt obsahuje
- Aplikace Android s názvem PulseDeck a vlastní ikonou.
- Na šířku orientovaná obrazovka.
- Dvě obrazovky DESKY / MIXER z verze 2.4.
- Výběr hudebních souborů přes systémový výběr Androidu.
- JavaScript/Web Audio běží uvnitř Android WebView; zvukové buffery se zpracovávají lokálně a audio graf zachovává stereo kanály.
- Kontrola zdrojů a syntetický test beatgridu jsou v `scripts/verify_pulsedeck.py` a `scripts/test_dsp.js`. Browser smoke test `scripts/test_browser.js` v Chromiu načítá skutečný testovací stereo WAV a ověřuje dekódování 2 kanálů, odhad BPM/beat offsetu, spuštění obou desek, EQ, synchronizaci a přepnutí obrazovek. Tyto testy běží v cloud buildu.
- Identifikátor balíčku: `com.pulsedeck.dj`.
- Verze: `1.0.0`, versionCode `1`.

## Jak vytvořit instalovatelnou aplikaci
1. Nainstaluj Android Studio a Android SDK Platform 36.
2. Otevři v Android Studiu složku `PulseDeckAndroid`.
3. Nech doběhnout Gradle Sync.
4. Pro instalaci do telefonu zvol **Build → Build APK(s)**. APK bude v `app/build/outputs/apk/debug/`.
5. Před vydáním na Google Play nastav vlastní podpisový klíč a v Android Studiu zvol **Build → Generate Signed Bundle / APK → Android App Bundle**. Výsledný `.aab` nahraj přes svůj účet Google Play Console.

## Důležité
V tomto prostředí nebyl dostupný Android SDK ani Gradle, takže zde nebylo možné APK/AAB zkompilovat ani otestovat na skutečném telefonu. Projekt je připravený pro sestavení v Android Studiu, ale není to již zkompilovaný APK a aplikace zatím není zveřejněná v Google Play. Browser smoke test ověřuje Web Audio v Chromiu, nikoli fyzický Android telefon. Po vytvoření APK je stále nutný test instalace, výběru souborů a zvuku na reálném zařízení.
