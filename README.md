# Bezpieczeństwo - rosnące zagrożenia dla aplikacji WWW (CHWYTYLIWY TEMAT?)
Praca licencjacka

### Wstęp ( DO SKRÓCENIA I ULEPSZENIA )
W erze Internetu rośnie ilość i znaczenie aplikacji WWW oraz danych przez nie zarządzanych. Wraz ze złożonością systemów rosną też potencjalne zagrożenia oraz ich skutki. Niestety ogólna świadomość wagi tej dziedziny jest zaniedbywana z wielu względów. Nie poprawia też stanu rzeczy niewielka ilość aktualnych pozycji naukowych ponieważ ze względu na częste zmiany szybko stają się nieadekwatne do realiów.

Istnieją normy bezpieczeństwa (PN-ISO/IEC 27001:2014-12) jednak w praktyce rzadko kiedy możemy ich doświadczyć. Tak samo sprawa wygląda z metodykami, które istnieją (opracowane na przykład przez SANS czy OWASP), ale prawie nieznane w środowisku programistycznym. Istnienie problemu może jednak wykazywać działanie specjalnych instytucji jak Ministerstwo Cyfryzacji czy CERT Polska, które zajmują się bezpieczeństwem sieci.

Z wielu warstw internetu (serwery, węzły wymiany danych, bazy danych) to właśnie aplikacje WWW są w ostatnim czasie najbardziej zaniedbywane pod względem bezpieczeństwa. Dzieje się tak przez brak świadomości gnającego postępu i potrzeby udoskonalania zabezpieczeń, zwykłe cięcia budżetowe czy zbyt duża ufność w gotowe rozwiązania programistyczne.  Często też jest to bagatelizowane ponieważ nie pojawiają się natychmiastowe i bezpośrednie szkody. Mimo tego skutki mogą doprowadzić od zwykłego ośmieszenia (twórcy czy właściciela), przez straty finansowe po konsekwencje karne. 

Skupiając się tylko na jednej technologii jaką jest PHP możemy wyróżnić klika rodzajów ataków na aplikacje WWW: 
SQL Injection
Cross Site Scripting (XSS)
Cross Site Request Forgery
Directory Traversal
XPATH Injection
JavaScript Injection
Remote File Inclusion

Lista ta z dnia na dzień się zmienia ponieważ na niektóre ataki znajdują się rozwiązania uniwersalne, co jakiś czas pojawiają się nowe, a niektóre cały czas są zagrożeniem właśnie ze względu na niską świadomość społeczności programistycznej o ich powszechności.

W dziedzinie bezpieczeństwa aplikacji WWW cały czas następuje rozwój samej technologii jak i zmian społecznych generujących niebezpieczeństwa (takie jak terroryzm, straty finansowe) wpływających na wszystkie sfery życia. Stąd konieczność ciągłego rozwoju nauki i prawa w tej kwestii.

Opierając się na moim doświadczeniu zawodowym, które pozwala mi stykać się z tym problemem na co dzień chciałbym bliżej opisać ten stan rzeczy i możliwości jego poprawy. Będę miał możliwość praktycznego podejścia do sprawy względem testów penetracyjnych jak i naprawy luk bezpieczeństwa.


### Keywords
bezpieczeństwo, aplikacje WWW, PHP, swiadomosc, SQL, JS, luki bezpieczeństwa, programowanie



## Pytania
1. Na czym się lepiej skupić? Rozpoznanie luk bezpieczeństwa występujace w sieci czy może jak zabezpieczać takie luki?
1. Czy warto wchodzić w aspekty prawne? Np. Certyfikaty ISO czy GIODO
1. Na którym z ataków najlepiej się skupić?
