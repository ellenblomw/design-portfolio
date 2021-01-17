---
Title: Load
Description: Ett projekt
Template: analysis
---

Load
=======================

### Urval
Jag har valt sajterna [Koket.se](https://www.koket.se/), [Recept.se](https://recept.se/) och [Arla.se/recept](https://www.arla.se/recept/) eftersom de verkar inom samma nisch och jag ville jämföra hur de presterar hastighetsmässigt i relation till deras placering på Google. Jag valde just receptsajter eftersom jag tänkte att de ofta innehåller mycket bilder. 

![Koket.se](../assets/img/koket.se.jpg) ![Recept.se](../assets/img/recept.se.jpg) ![Arla.se/recept](../assets/img/arla.se.jpg)  

För att hitta tre relevanta konkurrenter sökte jag på ordet "recept" och undersökte vilka som dök upp på förstasidan på Google - bortsett från de som låg med Annonser. De tre jag valt är de tre som dyker upp överst.

Notera dock att jag ej sökt på något särskilt slags recept, utan bara sökordet recept. Vidare bör det noteras att jag mätt förstasidan (det var den som kom upp när jag sökte på ordet recept), alltså inte en undersida med ett visst recept på. Dock blir Arla lite av en specialare då deras receptsida är just en undersida. De är ju huvudsakligen en matvaruproducent, inte en receptsida. Men deras native advertising-strategi har varit att inrikta sig på recept, och den var så pass lyckad att de numera är en go to-sajt för den som söker matinspiration.

### Metod
Jag började med att spara ner skärmdumpar på alla tre sidorna. Varje sida tog jag tre skärmdumpar på som jag sedan satte samman till en enda bild i Photoshop för att man ska få se en större del av sidan än bara övre delen som syns i datorn. 
Sajterna har sedan analyserats med Pagespeed Insight och Devtools Networkflik. Resultatet har jag dokumenterat i [Google Sheet](https://docs.google.com/spreadsheets/d/1KYYmqJMaQh-6o0x2i9FXdoofhtmRzmIkQEOsSFcKx70/edit?usp=sharing). 

Varje hemsida testades både mobilt och via dator. Betygen och andra mätvärden antecknades i Sheets-dokumentet. Varje test utfördes tre gånger och snittet av dessa tre undersökningar är det som jag sedan använt som slutresultat.

### Resultat
Koket.se har ett snittbetyg på 24,3 för mobil (rött) och 62 för desktop (gult). De har, enligt Pagespeed, problem med ett onödigt stort DOM-träd, ineffektiv cachelagringspolicy samt kan spara tid på att ta bort javascript som inte används och genom att läsa in resurser i förväg. Flera av de primära tipsen från verktyget handlar om att ta bort eller minimera javascript. Devtools nätverksflik visar att sidan laddar klart på i snitt 10,2 sekunder, att den har omkring 113 resurser samt att snittstorleken på sidan är 2,94 megabyte.

Recept.se har ett snittbetyg på 23,3 för mobil (rött) och 70 för dektop (gult). De har ungefär samma problem som Köket.se men i lite annorlunda prioriteringsordning. Exempelvis får de i första hand tips om att minska på javascript, ta bort onödiga sådana och att skapa en mer effektiv cachelagringspolicy. Först därefter kommer tips om att minska på DOM-trädet (som anges till ungefär hälften så stort som konkurrentens). När det kommer till mobilfliken får man också mer specifika tips kring att skicka bilder i modernt format och använda bilder med rätt storlek, samt ta bort oanvänd CSS. Devtools nätverksflik visar att sidan laddar klart på i snitt 27,4 sekunder, att den har omkring 148,7 resurser samt att snittstorleken på sidan är 5,9 megabyte.

Arla.se/recept har ett snittbetyg på 14 för mobil (rött) och 45 för desktop (rött). De skulle kunna göra en stor tidsbesparing genom att läsa in viktiga resurser i förväg och ha bilder i rätt storlek. Men de får i huvudsak kritik för att de har ett onödigt stort DOM-träd, mer än dubbelt så stort som Koket.se. Man tycker också att de bör ha en mer effektiv cachelagringspolicy samt undvika en onödigt stor nätverksbelastning. Vidare bör man rensa bort onödig CSS och ta bort javascript som inte används. Devtools nätverksflik visar att sidan laddar klart på i snitt 26,6 sekunder, att den har omkring 107,7 resurser samt att snittstorleken på sidan är 7,78 megabyte.

### Analys
Det är uppenbart att alla tre sajterna är lite av en besvikelse för Google. Dels för att samtliga mobilsajter får rött betyg (sämsta möjliga), samt att desktopversionerna är röda eller gula i betyg. Ingen av sajterna får grönt betyg. Den sajt som har bäst betyg både mobilt och desktop - om än fortfarande ett lågt sådant - är också den som har bäst placering på Google. Rangordningen på Googles startsida stämmer med hur de presterar hastighetsmässigt.

Samtliga sajter har stora DOM-träd och javascript som slöar ner dem. Två av dem får även kritik för sin bildhantering och för att de har CSS som inte används. Här finns stora förbättringsmöjligheter.

Tittar vi på Devtools resultatet ser vi att rangordningen på Google är densamma som om man skulle rangordna sajterna utifrån hur stora de är. Däremot ser man en avvikelse i form av att Recept.se har fler resurser och tar längre tid innan den är färdigladdad än vad Arla.se/recept gör, det skiljer inte jättemycket i jämförelse med hur mycket de skiljer sig åt i betyg på Google. Det jag noterade under undersökningen är att allt grundläggande laddas in på runt 15-20 sekunder hos Recept.se och att det sedan sker en rad sena förfrågningar som påverkar laddningstiden uppåt, bland annat tracking cookies och annonser som läses in väldigt segt. Detta drar upp tiden i Devtools. Kanske är det här orsaken går att finna till varför de har sämre resultat i devtools än vad arla har men ändå får bättre resultat i Googles verktyg. 

### Vinnare
Vinnaren i testet är också den som ligger etta på Google, nämligen Köket.se. Det handlar dock inte om någon storskredsseger, utan om en vinnare som har stor utvecklingspotential.

I min värld (precis som Googles) kommer sedan Recept.se. För det relevanta innehållet på sajten laddar fortare än hos Arla. Dessutom är recept.se en renodlad receptsajt medan Arla är spretigare i sitt syfte. Men det har förstås inte med hastighet att göra, utan är snarare en form av analys över vilken sajt som har mest relevant innehåll.

### Gräns
Hur snabbt en sajt laddar är ju delvis en subjektiv uppfattning. Min gräns för full laddning kanske går vid 15 sekunder. Men har sajten inte börjat visa relevant innehåll efter så lite som 1 sekund uppfattar jag den mer seg, än om en sajt skulle visa allt relevant innehåll direkt och sedan ladda in annonser, tracking cookies, innehåll som ska dyka upp när man skrollar osv senare. Så frågan här är lite kluven. 

Men om vi utgår från färdigladdad sida skulle jag säga att 10-15 sekunder känns som en rimlig tid. Speciellt eftersom man inte behöver se allt direkt, utan kommer att skrolla för att få upp mer innehåll. Utifrån detta gränsvärde är det bara Koket.se som klarar sig. De andra två är alldeles för långsamma. Dessutom visar inte Recept.se något relevant innehåll vid första anblick, det man möts av är annonser och en stor sökruta. Således måste man skrolla direkt och därmed hamnar den sist i min rangordning eftersom den sega laddningstiden då blir än mer begränsande för den sajten. Min rangordning utifrån mitt gränsvärde är därmed Köket.se, Arla.se/recept och därefter Recept.se.

Arbete av: Elina Blom