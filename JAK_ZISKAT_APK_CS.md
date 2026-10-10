# Jak získat skutečný APK pro testování

V tomto chatu není dostupný Android SDK ani Gradle a internetové stahování SDK je zablokované, proto tu nemohu APK zkompilovat přímo. Projekt ale obsahuje GitHub Actions automatizaci, která APK sestaví na GitHub serveru.

1. Na GitHubu vytvoř nový prázdný repozitář, například `PulseDeck`.
2. Nahraj do něj obsah této složky (všechny soubory a složky v ZIPu, včetně `.github`).
3. Otevři v repozitáři záložku **Actions** a spusť **Build PulseDeck Android** (nebo počkej na dokončení buildu po nahrání do `main`).
4. Po dokončení otevři běh workflow a v části **Artifacts** stáhni `PulseDeck-Android-build.zip`.
5. Rozbal ZIP. Soubor `app-debug.apk` nainstaluješ na Android pro testování. Android může požádat o povolení instalace z daného zdroje.
6. Build automaticky kontroluje zdrojový kód a testuje odhad 138 BPM / první úder na syntetickém rytmu. To nenahrazuje poslechový test na telefonu.

## Pozor
- APK je testovací debug build.
- Workflow vytváří také `.aab`, ale `bundleRelease` je nepodepsaný. Google Play vyžaduje podepsaný release AAB. Před publikací musíš nastavit svůj soukromý upload/signing klíč; ten neposílej do veřejného repozitáře.
- Build v cloudu ještě nebyl spuštěn, takže zatím nemohu tvrdit, že APK úspěšně vznikl nebo prošel testem.

## Automatické testy

Před sestavením workflow spustí `scripts/verify_pulsedeck.py`, syntetický test BPM (`scripts/test_dsp.js`) a browser smoke test (`scripts/test_browser.js`). Ten v Chromiu načte testovací stereo WAV a zkontroluje BPM, první úder, přehrávání, EQ, synchronizaci a přepnutí DESKY/MIXER. Nejde o náhradu testu na fyzickém Androidu.
