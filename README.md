# Handlelista

En delt handleliste for mobilen. Varene sorteres etter avdeling i butikken, og endringer vises med en gang på alle telefoner som har lenken.

- Skriv «2 melk», «to brød», «brød 2» eller «tre x egg» for antall
- Flere varer på én gang: skill med komma, f.eks. «melk, brød, ost»
- Forslag mens du skriver, basert på det dere har kjøpt før
- Trykk på blyanten for å endre navn, antall eller avdeling
- Initialene AW og IS viser hvem som la til varen (velges én gang per telefon)
- Virker også uten dekning; endringene sendes når nettet er tilbake

Lagringen skjer i Firebase (Firestore) i prosjektet `handleliste-472b1`.

## Filer

| Fil | Hva den er |
|---|---|
| `index.html` | Hele appen |
| `icon.png` | Ikonet på hjemskjermen |
| `firestore.rules` | Tilgangsreglene. Ligger her som sikkerhetskopi; de må limes inn i Firebase-konsollen |

## Oppsett

### 1. Firebase (gjøres én gang)

1. Gå til [console.firebase.google.com](https://console.firebase.google.com) og åpne prosjektet **Handleliste**.
2. **Databases & Storage → Firestore → Create database.** Velg Standard, en europeisk lokasjon (f.eks. europe-north1) og *Start in production mode*.
3. Gå til fanen **Rules**, erstatt alt med innholdet i `firestore.rules`, og trykk **Publish**.

Innstillingene for prosjektet (`firebaseConfig`) står allerede i `index.html`. De er ikke hemmelige; det er reglene som beskytter dataene.

### 2. GitHub Pages

1. Lag et nytt repo på GitHub, f.eks. `handleliste`.
2. Last opp `index.html`, `icon.png`, `firestore.rules` og `README.md` (Add file → Upload files → Commit).
3. **Settings → Pages.** Under *Branch* velger du `main` og `/ (root)`, og trykker **Save**.
4. Etter et minutt eller to ligger appen på `https://<brukernavn>.github.io/handleliste/`.

### 3. Første gang på telefonen

1. Åpne adressen og trykk **Lag ny liste**. Adressen får da en lang kode bak `#`. Det er den som er lista.
2. Trykk **Del** øverst og send lenken til den andre.
3. Begge åpner lenken i Safari (iPhone) eller Chrome (Android), velger **AW** eller **IS**, og legger appen på hjemskjermen via **Del → Legg til på Hjem-skjerm**.

Legg til på hjemskjermen *etter* at lenken med koden er åpnet, så husker ikonet hvilken liste det er.

## Sikkerhet

Lista er beskyttet med koden i lenken, ikke med innlogging. Alle som har lenken kan se og endre lista, så ikke del den bredt. Har lenken kommet på avveie: lag en ny liste og del den nye lenken.

## Gratiskvote

Firebase Spark-planen er gratis og krever ikke betalingskort. Kvoten (50 000 lesinger og 20 000 skrivinger per dag) er langt mer enn en handleliste for en husstand bruker.
