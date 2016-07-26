# Rosnące zagrożenia dla aplikacji WWW
Praca licencjacka


### Keywords
bezpieczeństwo, aplikacje WWW, PHP, swiadomosc, SQL, JS, luki bezpieczeństwa, programowanie


### Wstęp
W dzisiejszych czasach internet rozwija się w bardzo dynamicznym tempie, szczególnie w zakresie aplikacji WWW, za którym większość firm je wytwarzających nie jest w stanie nadążyć. O ile w kwestii wyglądu, funkcjonalności, czy zwykłego UX niesie to tylko ograniczone konsekwencje o tyle w dziedzinie bezpieczeństwa jest to bardzo kosztowne w dłuższej perspektywie czasu. Ciągle rośnie ilość usług udostępnianych poprzez WWW, a także ich istotność dla interesów firm. Drastycznie podnosi się ich poziom zaawansowania technologicznego i tempo zmian potrzebnych dla dostosowania ich do potrzeb rynku. Z tych przesłanek wynika coraz większe ryzyko naruszeń bezpieczeństwa oraz strat spowodowanych tymi naruszeniami. W raporcie bezpieczeństwa Rządowego Zespołu Reagowania na Incydenty Komputerowe CERT.GOV.PL 1 wynika, że aż 18% z przebadanych 34 witryn różnych instytucji państwowych posiada krytyczną podatność serwera WWW. Tego typu podatności mogą prowadzić nie tylko do strat finansowych (np. 4 mln złotych oszacowanych strat w wyniku włamania do Plus Banku2), ale również do zagrożenia bezpieczeństwa Państwa (w przypadku ważnych instytucji państwowych nawet deface strony może katastrofalne skutki). Dla przykładu atak na infrastrukturę państwową Estonii w 2007 roku: 
„fala cyberataków na infrastrukturę informatyczną nasilała się, unieruchamiając strony internetowe parlamentu, ministerstw obrony i sprawiedliwości, partii politycznych, policji, a nawet szkół publicznych. Cyberataki osiągnęły apogeum 9 maja (rosyjski Dzień Zwycięstwa), gdy ich celem stał się też sektor prywatny. Sytuacja zaczęła przypominać powieść science fiction: dwa największe banki, Hansapank i SEB Ühispank, musiały zawiesić usługi on-line i wstrzymać transakcje zagraniczne. Zamarła też strona największego dziennika „Postimees”.”3
Aspekt bezpieczeństwa aplikacji WWW jest tylko drobną częścią tzw. „cyberbezpieczeństwa”, ale warto się tym zająć bo jest często zaniedbywane, a po drugie może być pierwszym krokiem (wektorem) ataku na dane wykorzystywane później  do elewacji dostępu do reszty infrastruktury. Na przykład opisany w raporcie „Data breach digest”4 atak typu „CMS compromise” służący do wykradzenia danych autentykacyjnych wykorzystywany jest do wykorzystania kolejnych luk bezpieczeństwa.
Z wielu warstw internetu (serwery, węzły wymiany danych, bazy danych) to właśnie aplikacje WWW są w ostatnim czasie najbardziej zaniedbywane pod względem bezpieczeństwa. Dzieje się tak przez brak świadomości gnającego postępu i potrzeby udoskonalania zabezpieczeń, zwykłe cięcia budżetowe czy zbyt duża ufność w gotowe rozwiązania programistyczne.  Często też jest to bagatelizowane ponieważ nie pojawiają się natychmiastowe i bezpośrednie szkody. Mimo tego skutki mogą doprowadzić od zwykłego ośmieszenia (twórcy czy właściciela), przez straty finansowe po konsekwencje karne.

###Spis treści
* Rosnące zagrożenia dla aplikacji WWW
* Keywords
* Wprowadzenie
* Rozdział I
  1. Początki WWW, brak idei bezpieczeństwa	
  2. Najważniejsze wydarzenia dla Aplikacji WWW
  3. Pierwsze problemy z bezpieczeństwem	
  4. Pomysły poprawy bezpieczeństwa 
* Rozdział II
  1. Opracowanie diagramu na podstawie danych	
  2. Analiza skuteczności wprowadzonych zabezpieczeń
  3. Świadomość środowiska programistów na temat bezpieczeństwa
  4. Aktualny stan bezpieczeństwa Aplikacji WWW
