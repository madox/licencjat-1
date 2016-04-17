Rosnące zagrożenia dla aplikacji WWW {#rosnące-zagrożenia-dla-aplikacji-www .western}
====================================

Praca licencjacka

[]()Keywords {#keywords .western}
------------

bezpieczeństwo, aplikacje WWW, PHP, świadomość, SQL, JS, luki
bezpieczeństwa, programowanie

\
\

[]()Wprowadzenie {#wprowadzenie .western}
----------------

W dzisiejszych czasach internet rozwija się w bardzo dynamicznym tempie,
szczególnie w zakresie aplikacji WWW, za którym większość firm je
wytwarzających nie jest w stanie nadążyć. O ile w kwestii wyglądu,
funkcjonalności, czy zwykłego UX niesie to tylko ograniczone
konsekwencje o tyle w dziedzinie bezpieczeństwa jest to bardzo kosztowne
w dłuższej perspektywie czasu. Ciągle rośnie ilość usług udostępnianych
poprzez WWW, a także ich istotność dla interesów firm. Drastycznie
rośnie ich poziom zaawansowania technologicznego i tempo zmian
potrzebnych dla dostosowania ich do potrzeb rynku. Z tych przesłanek
wynika coraz większe ryzyko naruszeń bezpieczeństwa oraz strat
spowodowanych tymi naruszeniami. W raporcie bezpieczeństwa Rządowego
Zespołu Reagowania na Incydenty Komputerowe CERT.GOV.PL
^[^1^](#sdfootnote1sym){.sdfootnoteanc}^ wynika, że aż 18% z
przebadanych 34 witryn różnych instytucji państwowych posiada krytyczną
podatność serwera WWW. Tego typu podatności mogą prowadzić nie tylko do
strat finansowych (np. 4 mln złotych oszacowanych strat w wyniku
włamania do Plus Banku[^2^](#sdfootnote2sym){.sdfootnoteanc}), ale
również do zagrożenia bezpieczeństwa Państwa (w przypadku ważnych
instytucji państwowych nawet deface strony może katastrofalne skutki).
Dla przykładu atak na infrastrukturę państwową Estonii w 2007 roku:

„<span style="font-style: normal"><span style="font-weight: normal">fala
cyberataków na infrastrukturę informatyczną nasilała się,
unieruchamiając strony internetowe parlamentu, ministerstw obrony i
sprawiedliwości, partii politycznych, policji, a nawet szkół
publicznych. Cyberataki osiągnęły apogeum 9 maja (rosyjski Dzień
Zwycięstwa), gdy ich celem stał się też sektor prywatny. Sytuacja
zaczęła przypominać powieść science fiction: dwa największe banki,
Hansapank i SEB Ühispank, musiały zawiesić usługi on-line i wstrzymać
transakcje zagraniczne. Zamarła też strona największego dziennika
„Postimees”.</span></span>”[^3^](#sdfootnote3sym){.sdfootnoteanc}

Aspekt bezpieczeństwa aplikacji WWW jest tylko drobną częścią tzw.
„cyberbezpieczeństwa”, ale warto się tym zająć bo jest często
zaniedbywane, a po drugie może być pierwszym krokiem (wektorem) ataku na
dane wykorzystywane później do elewacji dostępu do reszty
infrastruktury. Na przykład opisany w raporcie „Data breach
digest”[^4^](#sdfootnote4sym){.sdfootnoteanc} atak typu „CMS compromise”
służący do wykradzenia danych autentykacyjnych służących do kolejnych
ataków.

\

Rozdział I {#rozdział-i .western}
----------

### 1. Początki WWW, brak idei bezpieczeństwa {#początki-www-brak-idei-bezpieczeństwa .western}

Gdy idea stron WWW powstawała w CERN w 1991 roku było to ograniczone
tylko dla środowisk naukowych i nikt nie przejmował się kwestią
bezpieczeństwa ponieważ wszyscy użytkownicy (naukowcy) sobie ufali. Tak
wielkiego rozwoju terytorialnego (z początku tylko kilka ośrodków
naukowych, a według ITU na rok 2014 dostęp do internetu posiada 2 937
mln ludzi na całym świecie[^5^](#sdfootnote5sym){.sdfootnoteanc}), ani
ilości publikowanych danych (według CISCO VNI Forecasts w roku 2014
przez internet przepływało 59,9 EB danych na
miesiąc[^6^](#sdfootnote6sym){.sdfootnoteanc}) nikt nie przewidywał więc
nikt nie myślał wtedy o zabezpieczeniach. Nie istniały jeszcze sieci
społecznościowe, które aktualnie są jednym ze źródeł zagrożeń. Sam
protokół HTTP jest bezstanowy (tzn. działa w trybie
pytanie-odpowiedź-porzucenie sesji) ze względu na zmniejszenie
obciążenia serwerów i na początkowy brak potrzeby np. identyfikacji
użytkownika. Dlatego wszystkie strony były statyczny co uniemożliwiało
jakiekolwiek próby ataku przez nie (nadal pozostawały możliwości ataku
na sam serwer), a zabezpieczenia tych danych można było łatwo wykonać
przez zablokowanie możliwości zapisu w całym folderze. Z czasem powstały
technologie typu klient-serwer jak np. cookies, które przechowują dane w
przeglądarce klienta, ale są wykorzystywane przez serwer do jego
identyfikacji. Przeglądarki internetowe nie posiadały żadnych
mechanizmów bezpieczeństwa i tylko parsowały kod HTML w czysty sposób.
Powstawały kolejne coraz bardziej rozbudowane standardy HTML które
pozwalały na coraz większą interakcję z użytkownikami. Formularze danych
pozwalały wysłać na serwer użytkownikowi swój tekst, a potem nawet
pliki. Kolejnym krokiem była możliwość uruchamiania na stronach kodu JS
który posiadał dostęp bezpośrednio do zasobów użytkownika, często
wychodząc poza zakres samej przeglądarki. Wzrosła nie tylko ilość kodu
źródłowego przez co trudniej jest wychwytywać błędy, ale też ilość
wykorzystywanego przez programistów gotowego oprogramowania i bibliotek
podczas tworzenia aplikacji WWW.

\
\

\
\

### 2. Najważniejsze wydarzenia dla Aplikacji WWW {#najważniejsze-wydarzenia-dla-aplikacji-www .western}

Dopiero w dalszym etapie rozwoju pojawiły się rozbudowane przeglądarki
WWW typu Mosaic (1992 rok) czy Netscape Navigator (1994) dające całe
pakiety nowych funkcji które miały na celu poszerzać interakcję z
użytkownikiem. W 1995 wprowadzono CGI które pozwalało na uruchomienie po
stronie serwera programów i tym samym generowanie dynamicznych stron
WWW. Do wsparcia tego systemu został wprowadzony system zarządzania
relacyjnymi bazami danych – MySQL, który ułatwiał w znaczący sposób
przechowywanie i zarządzanie skomplikowanymi strukturami danych.
Powstała też technologia Javascript która umożliwiała wykonywanie
dynamiczne akcje, ale już po stronie klienta. Rok później pojawiła się
technologia Flash z którą były wiązane duże nadzieje ze względu na spory
wachlarz możliwości. W 1997 został wymyślony standard HTML 3.2 i
wprowadzony w przeglądarce IE 4, a także najpopularniejszy obecnie język
skryptowy do obsługi aplikacji WWW - PHP/FI 2.0. PHP z wersji na wersję
stawało się coraz bardziej popularne wśród WebDeveloperow – już w roku
2004 20% wszystkich stron działało pod kontrolą tego języka.
Współcześnie według Web Technology Surveys język PHP jest używany na
82,3% serwerów na całym świecie[^7^](#sdfootnote7sym){.sdfootnoteanc}.
Powstawały nowe formaty przekazywania danych jak XML (1996 rok) czy JSON
(2006 rok) które usprawniały komunikację.

\
\

### 3. Pierwsze problemy z bezpieczeństwem {#pierwsze-problemy-z-bezpieczeństwem .western}

Sam język HTML nie dawał możliwości wykonywania poleceń przez co był sam
w sobie bardzo bezpieczny. Ataki mogły dotyczyć tylko samych serwerów.
Już w 1995 pojawiła się technologia CGI umożliwiająca wykonywanie kodu
programu po stronie serwera co pozwalało na dynamiczne tworzenie
wyświetlanych dokumentów, ale niestety wniosło nowe zagrożenia w postaci
danych wprowadzanych przez użytkowników stron. Taka możliwość
wprowadzania danych do bazy zapoczątkowała problemy związane z
zagrożeniem typu Injection czyli ataku wykorzystującego lukę w aplikacji
polegającą na braku filtrowania (i typowania) danych przekazywanych do
zapytań i zapisów w bazie. Dzięki temu jest możliwość pełnego dostępu do
bazy przez użytkowników, a nawet usunięcia bazy (np. DROP DATABASE
prace\_licencjackie). Kolejnym powszechnie występującym błędem jest też
podatność typu XSS (Cross-site scripting). Pozwala ona na osadzeniu w
treści atakowanej strony niebezpiecznego kodu (najczęściej JS), który
będzie wykonywany na komputerach wszystkich odwiedzających użytkowników.
Można dzięki tej metodzie wykraść ciasteczka użytkownika (np. do
późniejszego wykorzystania ich we włamaniu na konta użytkownika) czy
inne szkodliwe akcje. Ze względu na wady mechanizmów bezpieczeństwa w
JavaScript, trudność rozróżnienia kodu od znaczników kontrolujących
prezentację widoku i szeregową strukturę języka HTML tego typu
zagrożenia bardzo często występują we współczesnych aplikacjach WWW, a
poprawa tych luk wymaga dużych nakładów pracy.

### 4. Pomysły poprawy bezpieczeństwa {#pomysły-poprawy-bezpieczeństwa .western}

Twórcy przeglądarek będąc jedną z bardziej świadomych grup
developerskich pod względem bezpieczeństwa cały czas aktualizują
zabezpieczenia popularnych luk. Odnosi się to zarówno do zabezpieczeń
typowo po stronie przeglądarki gdzie dla przykładu <span
style="font-style: normal"><span style="font-weight: normal">Internet
Explorer 3 pozwalał wykonać na komputerze użytkownika dowolny program z
sieci lub </span></span><span style="font-style: normal"><span
style="font-weight: normal">wysyłał dane takie jak nazwa użytkownika,
hasło użytkownika i nazwa grupy roboczej na żądanie dowolnego serwera
sieciowego[^8^](#sdfootnote8sym){.sdfootnoteanc}, ale też zabezpieczeń
samych technologii jak możliwość otwierania nowych okien przez JS czy
kontrola dostępu do ciasteczek. Poprawa w tej kwestii jest też napędzana
silną konkurencja o użytkowników którzy zaczynają coraz bardziej zwracać
uwagę na kwestię bezpieczeństwa. </span></span>

<span style="font-style: normal"><span style="font-weight: normal">
Powstają specjalne protokoły jak SSL i jego następca TLS odpowiedzialne
za szyfrowanie danych przesyłanych za pomocą HTTP. Pozwala ona
zabezpieczyć wszystkie dane użytkownika która są wysyłane od niego na
serwer (np. hasła) oraz powrotem (dane wrażliwe użytkownika). Mimo
długiego czasu istnienia tej metody nie jest ona ciągle powszechnie
stosowana ze względów finansowych.</span></span>

<span style="font-style: normal"><span style="font-weight: normal">
Pojawił się też cały wachlarz gotowych rozwiązań programistycznych jakim
są gotowe Frameworki do tworzenia aplikacji WWW (np. Zend, Symofony).
Mają one wbudowane zabezpieczenia przed popularnymi typami ataku na
strony co pozwala programistom skupić się na samej funkcjonalności.
Często jest to dobre rozwiązanie dla początkujących developerów,
ponieważ daje to niskiego poziomu, ale jednak jakieś zabezpieczenia.
Oczywiście jest też druga strona medalu, która wykazuje wady takiego
rozwiązania. Przez transparentność logiki kodu łatwiej znaleźć
atakującym nowe metody włamania, które zazwyczaj są nie do uniknięcia.
Pełne zdanie się na gotowe rozwiązania też obniża czujność programistów
co prowadzi do sytuacji w której żadne odgórne zabezpieczenia nie
pomogą.</span></span>

<span style="font-style: normal"><span style="font-weight: normal"> W
kursach i książkach na temat tworzenia aplikacji WWW już coraz częściej
traktuje się bezpieczeństwo jako obowiązkowy element procesu tworzenia.
Na najbardziej popularne sposoby ataku można znaleźć szereg rozwiązań
programistycznych. Sam język PHP w nowszych wersjach blokuje
niebezpieczne metody łączenia z bazą i wykonywania pytań wysoce
wrażliwych na ataki typu Injection. </span></span>

<span style="font-style: normal"><span style="font-weight: normal">
Powstaje wiele firm które specjalizują się w testach penetracyjnych
czyli metodzie nadzorowanego ataku na aplikację WWW w celu wykrycia
możliwych luk bezpieczeństwa które mogłyby być wykorzystane w
przyszłości przez osoby niepożądane. Zaczyna się takie testy od
wstępnego badania czyli sprawdzenia kodu w celu znalezienia typowych
błędów krytycznych umożliwiających przejęcie kontroli nad systemem.
Drugim etapem jest mapowanie aplikacji czyli ustalanie technologii i
zapoznawanie się z logiką całego systemu. Ostatnim etapem są typowe
ataki które dzięki znajomości oprogramowania potrafią wykazać wiele luk
bezpieczeństwa o niskiej wykrywalności. Ciągle rosnąca liczba takich
firm na rynku jest dowodem na coraz większe zapotrzebowanie specjalistów
z tej dziedziny.</span></span>

<span style="font-style: normal"><span style="font-weight: normal">
OWSAP (</span></span>Open Web Application Security Project<span
style="font-style: normal"><span style="font-weight: normal">) to
stowarzyszenie które powstawało między innymi w celu poprawy
bezpieczeństwa aplikacji webowych. Grupa profesjonalistów z całego
świata działająca non-profit, która stara się możliwie obiektywnie
przekazywać informacje na temat praktyk z dziedziny zabezpieczeń
oprogramowania. Przygotowali takie dokumenty jak na przykład
</span></span>„OWASP Guide” opisujący sposoby projektowania, tworzenia i
wdrażania systemów bezpieczeństwa w aplikacjach WWW. Wytyczne traktują o
standardowych lukach typu Injection, ale też o tych nowszych jak CRSF,
phishing, karty płatnicze czy session fixation. Co jest przydatne to
praktyczne wskazówki w znanych językach jak ASP.NET czy PHP z gotowymi
przykładami rozwiązań. Poza dokumentacją wydają oprogramowanie do testów
i pisania oprogramowania. Dla przykładu framework XSSer do łatwego
wykrywania luk XSS w pisanych usługach webowych.

\
\

\

Rozdział II {#rozdział-ii .western}
-----------

### 1. Opracowanie diagramu na podstawie danych {#opracowanie-diagramu-na-podstawie-danych .western}

### 2. Analiza skuteczności wprowadzonych zabezpieczeń {#analiza-skuteczności-wprowadzonych-zabezpieczeń .western}

### 3. Świadomość środowiska IT na temat bezpieczeństwa {#świadomość-środowiska-it-na-temat-bezpieczeństwa .western}

### 4. Aktualny stan bezpieczeństwa Aplikacji WWW {#aktualny-stan-bezpieczeństwa-aplikacji-www .western}

\
\

![](LicencjatRobo_html_m5e11c3aa.jpg){width="643"
height="319"}**Statystyka wykrytych podatności w witrynach WWW
należących do administracji publicznych,**

**według poziomu zagrożenia**

\

\

\

Spis treści (plan) {#spis-treści-plan .western}
------------------

\

1.  Streszczenie

2.  Wstęp

3.  Wprowadzenie

4.  Rozdział I

    1.  Początki WWW, brak idei bezpieczeństwa

    2.  Najważniejsze wydarzenia dla Aplikacji WWW

    3.  Pierwszy problem z bezpieczeństwem

    4.  Pomysły poprawy bezpieczeństwa

5.  Rozdział II

    1.  Opracowanie diagramu na podstawie danych

    2.  Analiza skuteczności wprowadzonych zabezpieczeń

    3.  Świadomość środowiska programistów na temat bezpieczeństwa

    4.  Aktualny stan bezpieczeństwa Aplikacji WWW

6.  Zakończenie

7.  Bibliografia

\

\

<div id="Spis treści1" dir="LTR">

<div id="Spis treści1_Head" dir="LTR">

**Spis treści**

</div>

Rosnące zagrożenia dla aplikacji WWW 1

Keywords 1

Wprowadzenie 1

Rozdział I 2

1\. Początki WWW, brak idei bezpieczeństwa 2

2\. Najważniejsze wydarzenia dla Aplikacji WWW 2

3\. Pierwsze problemy z bezpieczeństwem 3

4\. Pomysły poprawy bezpieczeństwa 3

Rozdział II 4

1\. Opracowanie diagramu na podstawie danych 4

2\. Analiza skuteczności wprowadzonych zabezpieczeń 4

3\. Świadomość środowiska programistów na temat bezpieczeństwa 4

4\. Aktualny stan bezpieczeństwa Aplikacji WWW 4

Spis treści (plan) 4

</div>

\

<div id="sdfootnote1">

[1](#sdfootnote1anc){.sdfootnotesym} *Raport o stanie bezpieczeństwa
cyberprzestrzeni RP w 2014 roku*, CERT.GOV.PL,
<http://www.cert.gov.pl/download/3/172/RaportostaniebezpieczenstwacyberprzestrzeniRPw2014roku.pdf>
(dostęp: 14 kwietnia 2016 r.).

</div>

<div id="sdfootnote2">

[2](#sdfootnote2anc){.sdfootnotesym}<http://www.bankier.pl/wiadomosc/Policja-zatrzymala-hakera-ktory-wlamal-sie-do-Plus-Banku-7281790.html>
(dostęp: 13 kwietnia 2016 r.).

</div>

<div id="sdfootnote3">

[3](#sdfootnote3anc){.sdfootnotesym}<http://www.eesti.pl/dni-ktore-wstrzasnely-estonia-11963.html>
<span style="font-weight: normal">(dostęp: 14 kwietnia 2016 r.).</span>

</div>

<div id="sdfootnote4">

[4](#sdfootnote4anc){.sdfootnotesym}<http://www.verizonenterprise.com/resources/reports/rp_data-breach-digest_xg_en.pdf>
(dostęp: 15 kwietnia 2016 r.).

</div>

<div id="sdfootnote5">

[5](#sdfootnote5anc){.sdfootnotesym}*<span
style="font-weight: normal">International Telecommunication
Union</span>*
<https://www.itu.int/en/ITU-D/Statistics/Documents/statistics/2015/ITU_Key_2005-2015_ICT_data.xls>
(dostęp: 16 kwietnia 2016 r.).

</div>

<div id="sdfootnote6">

[6](#sdfootnote6anc){.sdfootnotesym}The Zettabyte Era—Trends and
Analysis
<http://www.cisco.com/c/en/us/solutions/collateral/service-provider/visual-networking-index-vni/VNI_Hyperconnectivity_WP.html>
(dostęp: 16 kwietnia 2016 r.).

</div>

<div id="sdfootnote7">

[7](#sdfootnote7anc){.sdfootnotesym}<http://w3techs.com/technologies/overview/programming_language/all>
(dostęp: 17 kwietnia 2016 r.).

</div>

<div id="sdfootnote8">

[8](#sdfootnote8anc){.sdfootnotesym}Książka „Internet Agresja i Ochrona”
str. 305

</div>
