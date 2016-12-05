Utvärdera webbplats
===================


##DN

| Mätningar          | [Startsida](http://www.dn.se/) | [Ekonomi](http://www.dn.se/ekonomi/) | [Sport](http://www.dn.se/sport/) |
| ------------------ | ------------------------------ | ------------------------------------ | -------------------------------- |
| Hastighet          | 57/100                         | 58/100                               | 56/100                           |
| Användarupplevelse | 99/100                         | 99/100                               | 99/100                           |
| Förslagsöversikt   | 63/100                         | 60/100                               | 67/100                           |
| Laddningstid       | 3.73 s                         | 4.16 s                               | 3.02 s                           |
| Antal resurser     | 469                            | 442                                  | 437                              |
| Total storlek      | 7 MB                           | 6.3 MB                               | 5.5 MB                           |


###Förbättringar
Några Javascript- och CSS-resurser behöver läsas in innan den övre delen av sidan kan renderas. Detta går att lösa genom att antingen skjuta upp inläsningen av resurserna, läsa in dem asynkront
eller att skriva in de viktigaste delarna av resurserna direkt i HTML-koden.

Bilder och Javascript-kod kan komprimeras för att minska storleken på filerna.

##GOG

| Mätningar          | [Startsida](https://www.gog.com/) | [Movies](https://www.gog.com/movies?sort=bestselling&page=1) | [Support](https://www.gog.com/support) |
| ------------------ | --------------------------------- | ------------------------------------------------------------ | -------------------------------------- |
| Hastighet          | 54/100                            | 59/100                                                       | 65/100                                 |
| Användarupplevelse | 95/100                            | 99/100                                                       | 67/100                                 |
| Förslagsöversikt   | 83/100                            | 81/100                                                       | 82/100                                 |
| Laddningstid       | 1.76 s                            | 1.12 s                                                       | 1.32 s                                 |
| Antal resurser     | 153                               | 90                                                           | 58                                     |
| Total storlek      | 132 kB                            | 825 kB                                                       | 441 kB                                 |


###Förbättringar
Innan den övre delen av sidan kan renderas behöver några Javascript- och CSS-resurser läsa in. Några sätt för att snabba på renderingen kan vara att skjuta upp inläsningen av resurserna, läsa in dem asynkront
eller att skriva in de viktigaste delarna av resurserna direkt i HTML-koden.

Det går att minska storleken bild-filerna genom korrekt komprimering och formatering.


##SVTPlay

| Mätningar          | [Startsida](http://www.svtplay.se/) | [Program](http://www.svtplay.se/program) | [Dokumentär](http://www.svtplay.se/genre/dokumentar) |
| ------------------ | ----------------------------------- | ---------------------------------------- | ---------------------------------------------------- |
| Hastighet          | 59/100                              | 58/100                                   | 57/100                                               |
| Användarupplevelse | 99/100                              | 99/100                                   | 99/100                                               |
| Förslagsöversikt   | 53/100                              | 75/100                                   | 73/100                                               |
| Laddningstid       | 1.31 s                              | 1.18 s                                   | 1.79 s                                               |
| Antal resurser     | 85                                  | 37                                       | 189                                                  |
| Total storlek      | 4.5 MB                              | 3.8 MB                                   | 7.2 MB                                               |

###Förbättringar
Det finns JavaScript- och CSS-kod som förhindrar innehåll ovanför mitten att renderas innan
andra resurser lästs in, så man kan testa skjuta upp inläsningen av de andra resurserna, eller
läsa in dem asynkront.

Resurser kan komprimeras med gzip eller deflate för att minska antalet byte som skickas via nätverket.

##Loading

| Mätningar          | [Startsida](http://loading.se/) | [Nyhetsartikel](http://loading.se/news.php?pub_id=42842) | [Forumtråd](http://loading.se/forum.php?thread_id=35458) |
| ------------------ | ------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| Hastighet          | 56/100                          | 51/100                                                   | 57/100                                                   |
| Användarupplevelse | 66/100                          | 64/100                                                   | 64/100                                                   |
| Förslagsöversikt   | 56/100                          | 62/100                                                   | 72/100                                                   |
| Laddningstid       | 3.13 s                          | 3.57 s                                                   | 2.46 s                                                   |
| Antal resurser     | 200                             | 207                                                      | 213                                                      |
| Total storlek      | 3.6 MB                          | 8.8 MB                                                   | 2.4 MB                                                   |

###Förbättringar
Många byte kan sparas genom att formatera och komprimera bilder.

Cachelagring kan utnyttjas genom att ange ett utgångsdatum eller en högsta ålder
i HTTP-rubrikerna för statiska resurser.


##Sammanfattning
Det första vi noterar från mätningarna är att tre av webbplatserna får mycket bättre betyg i Användarupplevelse än i Hastighet och Förslagsöversikt. Detta kan tyda på att
det antingen är enklare att optimera användarupplevelsen, eller att utveklarna prioriterar det högre än de andra områdena.

Vi märker att den totala storleken på sidorna och laddningstiden inte har någon koppling när man jämför webbplatser med varandra. Jämför vi t.ex. GOG och SVTPlay ser vi att
de har i princip lika långa laddningstider, medan storleken på respektive sidor skiljer sig anmärkningsvärt. 

De vanligaste potentiella förbättringsåtgärderna är att: ta bort Javscript- och CSS-kod som blockerar rendering från innehåll ovanför mitten, optimera bilder för att förminska
storleken på dem, utnyttja cachelagring i webbläsare, minska svarstiden från servern och aktivera komprimering av resurser med hjälp av t.ex. gzip eller deflate. 

##Gräns för absolut laddningstid
På de stationära datorer vi använder upplever vi inte någon av dessa webbplatser som långsam. Så 3--4 sekunders laddningstid ser vi inte som något problem. Dock vill vi tillägga
att DN känns väldigt långsam till mobila enheter. Man kan egentligen börja använda sidan relativt snabbt, men t.ex. bilder tar tid att renderas vilket gör att sidan känns långsam.

Laddningstiderna som vi mätt upp stämmer inte överens med den upplevda laddningstiden, då man väldigt fort som användare kan börja navigera på sidan även om allt inte är riktigt
klart. Därför har vi svårt att säga en exakt laddningstid som vi upplever som en gräns. Men som en gissning säger vi att när laddningstiden överstiger 5--6 sekunder så känns det nog 
långsamt.

##Gruppmedlem
Thomas Hedlund