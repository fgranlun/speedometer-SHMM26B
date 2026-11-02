#SHMM26B - Svensk Hastighetsmätare m/26B
En svensk hastighetsmätare utan annonser eller spårning och med inbyggd offline-databas för Sverige.

Alla aktuella hastighetsgränser på svenska vägar är hämtade från den senaste offentliga vägdatabasen (trafikverket.se).
Värdena är bearbetade med ett Douglas-Peucker-filter för att göra datafilen så liten som möjligt, men mätpunktupplösningen borde
vara okej i stort sett överallt.

Eftersom databasen ligger med i APK-filen behöver du inte vara uppkopplad.

Hastigheten visas till vänster, hastighetsgränsen till höger.

Felkoder visas med inspiration från Saab CK37:

90 - Ingen GNSSS-signal
91 - Låg signalkvalitet/signalstyrka
92 - Fel på hastighetsuppdateringsfiltret (OneEuro - lågpass med adaptiv brytfrekvens)
93 - Övrigt ej kritiskt fel
99 - Kritiskt fel -> raketstol -> lämna flygplanet

Eventuell felkod blinkar intermittent med hastighetsangivelsen.

Så varför?
Det finns en miljard olika hastighetsmätarappar i appbutikerna. Samtliga kostar pengar eller är fulla av annonser och spårare.

Jag ville ha en hastighetsmätare som var gratis, som var lite skönt myndighetsträig från min barndom då allt var
antingen grön- eller ambermonokromt.

Qualcomms, Broadcoms och MediaTeks kretslösningar maxar pollingshastigheten av GNSS-data vid 1 Hz, men appen är skriven för att 
begära så hög datauppdateringshastighet som kretslösningen tillåter, så kopplar du in en extern GPS-mottagare med högre pollnings-
tak så kommer det att användas istället. (Appen anropar LocationManager.requestLocationUpdates() med parametern minTime = 0).

Uppdateringar: Appen kommer att uppdateras fyra gånger om året. Det borde räcka. Lanseringsversionen har en databas från 1 juli 2026.

Kör försiktigt!
