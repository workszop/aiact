# Jak AI Act wpływa na projekt AI – studium przypadku

## Przykład: weterynaryjny system Vet-View

> **Charakter materiału.** Poniższy tekst jest dydaktycznym studium przypadku. Na przykładzie projektu *Vet-View* pokazuje, jak krok po kroku przeprowadzić analizę zgodności konkretnego systemu z rozporządzeniem (UE) 2024/1689 – *AI Act*. Nazwa produktu i spółki są przykładowe; celem jest pokazanie **metody rozumowania**, a nie wydanie opinii dotyczącej rzeczywistego podmiotu.
>
> **Stan prawny:** wrzesień 2026 – AI Act ze zmianami wprowadzonymi rozporządzeniem (UE) 2026/1744 (Digital Omnibus on AI, w mocy od 27 lipca 2026) oraz polska ustawa o systemach sztucznej inteligencji (w mocy od 11 sierpnia 2026).

---

### Cele dydaktyczne

Po przeanalizowaniu przykładu czytelnik powinien umieć:

1. ustalić, czy dane oprogramowanie jest **„systemem AI"** w rozumieniu art. 3 pkt 1 AI Act;
2. zaklasyfikować system do właściwej **kategorii ryzyka** (zakazane / wysokie / ograniczone / minimalne);
3. rozpoznać **role** podmiotów na gruncie AI Act (dostawca vs podmiot stosujący);
4. ocenić, czy i w jakim **zakresie** AI Act znajduje zastosowanie;
5. wyprowadzić **konkretne obowiązki** prawne z przyjętej kwalifikacji;
6. umiejscowić analizę w **kalendarzu stosowania** AI Act i wskazać organ nadzoru w Polsce.

---

### Opis przykładowego projektu

**Vet-View** to oprogramowanie oferowane w modelu **SaaS** przez spółkę **Vet-View S.A.**, wspierające lekarzy weterynarii w analizie obrazów USG. Na podstawie obrazu ultrasonograficznego system:

- lokalizuje badany obszar / zmianę (na etapie POC – ramka; docelowo maska segmentacyjna, kontur lub heatmapa);
- proponuje **klasyfikację** zmiany;
- podaje **prawdopodobieństwo** / wskaźnik pewności;
- generuje **podsumowanie tekstowe** możliwe do wklejenia do dokumentacji klinicznej.

**Zakres przeznaczenia** (w analizowanej wersji): gatunek – pies; narząd – nerki; badanie – USG przezpowłokowe. Producent zamierza **trenować, testować i walidować** model na danych klientów, a system ma umożliwiać śledzenie historii badań i porównywanie wyników w czasie.

Mając te fakty, przechodzimy do analizy.

---

## KROK 1 – Czy Vet-View jest „systemem AI"?

**Podstawa prawna:** art. 3 pkt 1 AI Act.

**Definicja.** „System AI" oznacza system maszynowy zaprojektowany do działania z różnym poziomem autonomii, który może wykazywać adaptacyjność po wdrożeniu i który – dla celów wyraźnych lub dorozumianych – wnioskuje z otrzymanych danych wejściowych, jak generować wyniki (przewidywania, treści, rekomendacje lub decyzje) mogące wpływać na środowiska fizyczne lub wirtualne.

**Analiza.** Vet-View spełnia kryteria tej definicji, ponieważ:

- jest systemem maszynowym;
- przetwarza dane wejściowe w postaci obrazów USG;
- generuje wyniki w postaci lokalizacji zmiany, maski, heatmapy, klasyfikacji, prawdopodobieństwa i podsumowania tekstowego;
- jego wynik wpływa na dalszy proces diagnostyczny prowadzony przez lekarza weterynarii;
- wykorzystuje komponent AI, a producent zamierza trenować, testować i walidować model na danych klientów.

**Wniosek:** ✅ Vet-View jest systemem AI w rozumieniu AI Act. Konieczne jest zatem zakwalifikowanie go do właściwej kategorii ryzyka.

---

## KROK 2 – Do jakiej kategorii ryzyka należy?

AI Act buduje obowiązki na ocenie ryzyka. Kolejność analizy: najpierw sprawdzamy, czy system nie jest **zakazany**, następnie czy nie jest **wysokiego ryzyka**, a dopiero potem ustalamy łagodniejszą kategorię.

### 2a. Czy to praktyka zakazana? (art. 5 AI Act)

Bezwzględnie zakazane są systemy o nieakceptowalnym poziomie ingerencji w chronione wartości, m.in.:

- wykorzystujące techniki podprogowe lub celowo zwodnicze techniki manipulacyjne, powodujące poważną szkodę (art. 5 ust. 1 lit. a);
- wykorzystujące szczególną podatność osób fizycznych ze względu na wiek, niepełnosprawność lub sytuację społeczną/ekonomiczną (lit. b);
- służące do oceny społecznej (*social scoring*) prowadzącej do nieuzasadnionego lub nieproporcjonalnego traktowania (lit. c);
- oceniające ryzyko popełnienia przestępstwa **wyłącznie** na podstawie profilowania lub cech osobowości (lit. d) – nie każda analityka predykcyjna organów ścigania;
- tworzące bazy danych rozpoznawania twarzy przez nieukierunkowane scrapowanie internetu lub nagrań CCTV (lit. e);
- rozpoznające emocje w miejscu pracy i w edukacji, z wyjątkiem celów medycznych i bezpieczeństwa (lit. f);
- kategoryzujące biometrycznie w celu wnioskowania o rasie, poglądach politycznych, przynależności związkowej, przekonaniach religijnych lub światopoglądowych, życiu seksualnym lub orientacji seksualnej (lit. g) – inna kategoryzacja biometryczna jest systemem wysokiego ryzyka (Zał. III pkt 1) i podlega art. 50 ust. 3;
- zdalnej identyfikacji biometrycznej w czasie rzeczywistym w przestrzeni publicznej **do celów ścigania przestępstw**, z wąskimi wyjątkami (lit. h) – RBI w innych celach jest systemem wysokiego ryzyka;
- **nowość po Omnibusie 2026:** systemy, których przewidywalnym i powtarzalnym wynikiem jest generowanie treści intymnych bez zgody lub materiałów przedstawiających wykorzystywanie seksualne dzieci (okres przejściowy do 2 grudnia 2026).

Interpretacja: Wytyczne Komisji w sprawie praktyk zakazanych, C(2025) 5052 final z 29 lipca 2025.

**Wniosek:** Vet-View nie realizuje żadnej z tych praktyk → **nie jest systemem zakazanym.**

### 2b. Czy to system wysokiego ryzyka? (art. 6 oraz Załączniki I i III AI Act)

Analiza prowadzi do **wniosku negatywnego**, ponieważ Vet-View:

- **ścieżka produktowa (art. 6 ust. 1) wymaga dwóch warunków łącznie:** (a) system jest komponentem bezpieczeństwa produktu objętego prawem harmonizacyjnym z Załącznika I albo sam takim produktem, **oraz** (b) produkt ten podlega ocenie zgodności przez stronę trzecią. Warunek (a) nie jest spełniony, więc warunku (b) nie trzeba badać;
- **nie jest komponentem bezpieczeństwa aparatu USG** (art. 3 pkt 14) – nie steruje bezpieczeństwem urządzenia, nie zapobiega niebezpiecznej pracy sprzętu, nie kontroluje parametrów emisji ultradźwięków, nie jest funkcją bezpieczeństwa sprzętu; lokalizuje i klasyfikuje zmiany w nerce psa oraz generuje wyłącznie informację pomocniczą dla lekarza;
- **nie jest wyrobem medycznym** – Załącznik I obejmuje m.in. rozporządzenia MDR 2017/745 i IVDR 2017/746, które dotyczą wyrobów stosowanych **u ludzi** (art. 1 MDR); oprogramowanie weterynaryjne nie wchodzi w ten zakres tylko dlatego, że technicznie analogiczne rozwiązanie mogłoby działać w aparacie USG dla ludzi;
- **nie mieści się w kategoriach Załącznika III** (art. 6 ust. 2; obszary ryzyka wobec osób fizycznych i praw podstawowych ludzi), bo dotyczy zwierząt – nie służy identyfikacji ani kategoryzacji biometrycznej ludzi, nie rozpoznaje emocji, nie działa w infrastrukturze krytycznej, nie dotyczy edukacji ani zatrudnienia, nie decyduje o dostępie osób fizycznych do świadczeń, kredytu, ubezpieczenia czy opieki zdrowotnej, nie jest używany przez organy ścigania, migracyjne ani sądy i nie wpływa na procesy demokratyczne. Filtr z art. 6 ust. 3 nie jest więc nawet potrzebny.

**Wniosek:** Vet-View **nie jest systemem wysokiego ryzyka.**

### 2c. Która kategoria łagodniejsza? (art. 50 AI Act)

Uwaga terminologiczna: „ograniczone ryzyko" to skrót dydaktyczny, nie kategoria ustawowa. Rozporządzenie zna praktyki zakazane, systemy wysokiego ryzyka, systemy objęte obowiązkami z art. 50 oraz modele GPAI; obowiązki z art. 50 kumulują się także z reżimem wysokiego ryzyka. Wytyczne Komisji mówią o „transparency risk".

Vet-View nie jest systemem wysokiego ryzyka, ale **nie jest** czystym systemem minimalnego ryzyka, ponieważ spełnia przesłankę z **art. 50 ust. 2**:

- **generuje syntetyczny tekst** – podsumowanie wstawiane do dokumentacji klinicznej jest treścią wygenerowaną przez AI; wytyczne Komisji do art. 50 (20 lipca 2026) wskazują, że streszczenia i przeredagowania generowane przez AI **nie** korzystają z wyjątku „funkcji pomocniczej przy standardowej edycji". To jest rozstrzygający punkt zaczepienia;
- ramki, maski, heatmapy i wskaźnik prawdopodobieństwa są **wynikami analitycznymi** (detekcja, klasyfikacja), a nie syntetycznym obrazem w rozumieniu ust. 2 – ani wytyczne, ani Kodeks postępowania w sprawie oznaczania treści generowanych przez AI nie obejmują adnotacji obrazu; ich oznaczanie należy traktować jako **rekomendowaną dobrą praktykę**, nie obowiązek;
- art. 50 ust. 1 (systemy przeznaczone do bezpośredniej interakcji z osobami fizycznymi) celuje w chatboty, asystentów i agentów. Narzędzie obsługiwane przez lekarza przez interfejs graficzny jest przypadkiem granicznym, a dla przeszkolonego profesjonalisty fakt użycia AI jest **oczywisty** w rozumieniu wyjątku z ust. 1 – informacja w interfejsie pozostaje dobrą praktyką, ale nie na niej opiera się kwalifikacja.

**Wniosek:** ✅ Vet-View należy kwalifikować jako system objęty **obowiązkami transparentności z art. 50** („ograniczone ryzyko"). Kwalifikacja zależy od generatora opisu tekstowego: produkt zwracający wyłącznie ramkę i klasę byłby bliżej minimalnego ryzyka (z art. 4 nadal w mocy). Dostawca musi **stale monitorować zmiany funkcjonalne** pod kątem możliwej rekwalifikacji.

> 🎯 **Lekcja z Kroku 2:** rozstrzygający okazał się kontekst – *zwierzęta, nie ludzie*. Ta sama architektura modelu zastosowana w USG dla ludzi prowadziłaby do zupełnie innej kwalifikacji (wyrób medyczny → potencjalnie wysokie ryzyko).

---

## KROK 3 – Kto jest kim? Role na gruncie AI Act

Obowiązki zależą nie tylko od kategorii ryzyka, lecz także od **roli** podmiotu.

### Dostawca – Vet-View S.A. (art. 3 pkt 3)

„Dostawca" to podmiot, który rozwija system AI (lub zleca jego rozwój) i wprowadza go do obrotu albo oddaje do używania pod własną nazwą lub znakiem towarowym, odpłatnie lub nieodpłatnie. Vet-View S.A. jest dostawcą, ponieważ:

- sam rozwija moduł AI;
- oferuje produkt jako SaaS pod własną marką;
- udostępnia go gabinetom, lecznicom, klinikom i laboratoriom weterynaryjnym w UE.

### Podmioty stosujące (*deployers*) – klienci (art. 3 pkt 4)

„Podmiot stosujący" to podmiot, który wykorzystuje system AI pod swoją kontrolą (poza osobistą działalnością pozazawodową). Gabinety, przychodnie, lecznice, kliniki i laboratoria weterynaryjne będą co do zasady **deployerami**.

**Niuans:** gdy podmiotem stosującym jest osoba prawna sprawująca kontrolę nad wykorzystaniem systemu (klinika), za podmiot stosujący **nie** uznaje się poszczególnych pracowników (weterynarzy) działających w ramach procedur i pod kontrolą tego podmiotu (zob. Wytyczne Komisji w sprawie praktyk zakazanych, C(2025) 5052 final, sekcja 2.4 „Personal scope: responsible actors", pkt 17–18).

---

## KROK 4 – Czy AI Act w ogóle ma zastosowanie?

**Podstawa:** art. 2 ust. 1 lit. a AI Act – rozporządzenie stosuje się do dostawców wprowadzających do obrotu lub oddających do użytku systemy AI w Unii, niezależnie od ich siedziby. To dokładnie sytuacja Vet-View S.A. jako dostawcy SaaS. Kliniki-deployerzy podlegają rozporządzeniu na podstawie art. 2 ust. 1 lit. b (siedziba w Unii).

Częsty błąd: wskazywanie lit. e (producenci produktów, którzy pod własną marką wraz ze swoim produktem wprowadzają system AI). Ta podstawa dotyczy np. producenta aparatu USG z wbudowanym modułem AI – Vet-View S.A. nie wytwarza żadnego produktu fizycznego, więc lit. e nie ma tu zastosowania.

**Czy zadziała któreś z wyłączeń? Nie:**

- **prywatne, nieprofesjonalne użycie** – wyłączenie nie działa, bo produkt jest używany przez przedsiębiorców w ramach profesjonalnej działalności weterynaryjnej;
- **badania i rozwój przed wprowadzeniem do obrotu** – wyłączenie nie działa, bo analiza dotyczy produktu oferowanego komercyjnie; AI Act nie obejmuje tym wyłączeniem testowania w warunkach rzeczywistych ani komercyjnego udostępniania systemu.

**Wniosek:** ✅ AI Act znajduje zastosowanie do Vet-View.

---

## KROK 5 – Jakie obowiązki z tego wynikają?

Z kwalifikacji *„system ograniczonego ryzyka + rola dostawcy"* wynika następujący zestaw obowiązków.

### 5.1. Kompetencje w zakresie AI (*AI literacy*) – art. 4

Po Omnibusie (rozp. 2026/1744) art. 4 stanowi, że dostawcy i deployerzy **podejmują środki wspierające rozwój kompetencji AI** swojego personelu i osób obsługujących system w ich imieniu, z uwzględnieniem ich wiedzy, doświadczenia, wykształcenia i kontekstu użycia; przepis wprost **nie wymaga zagwarantowania określonego poziomu** kompetencji u konkretnej osoby. Wcześniejsze brzmienie („zapewniają wystarczający poziom") nie obowiązuje. Obowiązek pozostaje w mocy od 2 lutego 2025 i dotyczy **obu ról** – klinika jako deployer ma własny obowiązek z art. 4 wobec swoich lekarzy.

Dla Vet-View S.A. oznacza to, że osoby zaangażowane w projektowanie, rozwój, walidację, **sprzedaż, wsparcie techniczne i obsługę reklamacji** powinny rozumieć co najmniej:

- a) podstawowe zasady działania modułu AI;
- b) ograniczenia modelu;
- c) znaczenie prawdopodobieństwa / wskaźnika pewności;
- d) ryzyko wyników fałszywie dodatnich i fałszywie ujemnych;
- e) ryzyko *automation bias* po stronie lekarzy;
- f) ograniczenie przeznaczenia do psów, nerek i USG przezpowłokowego;
- g) zakaz sugerowania użycia u ludzi;
- h) zasady eskalacji błędów modelu;
- i) zasady komunikowania klientom ograniczeń systemu.

*Wdrożenie:* szkolenia wewnętrzne (także dla działów sprzedaży i serwisu), materiały instruktażowe dla klientów i weterynarzy (które ułatwiają klinikom wykonanie ich własnego obowiązku z art. 4), interfejs opatrzony ostrzeżeniami oraz procedura aktualizacji wiedzy po każdej istotnej zmianie modelu.

### 5.2. Transparentność – art. 50 (i motyw 132)

Art. 50 stosuje się od 2 sierpnia 2026. Dostawca systemu generującego syntetyczny tekst, obraz, dźwięk lub wideo ma zapewnić, że wyniki są oznaczone w formacie maszynowo czytelnym i wykrywalne jako wygenerowane przez AI (ust. 2); systemy przeznaczone do bezpośredniej interakcji z osobami fizycznymi mają być tak zaprojektowane, aby osoby te wiedziały, że wchodzą w interakcję z AI, chyba że jest to oczywiste (ust. 1). Dla systemów generatywnych obecnych na rynku przed 2 sierpnia 2026 Omnibus przewidział okres przejściowy na oznaczanie z ust. 2 do **2 grudnia 2026**. Praktyczne wskazówki: Wytyczne Komisji do art. 50 (20 lipca 2026) i Kodeks postępowania w sprawie oznaczania treści generowanych przez AI, uznany przez Komisję za adekwatny.

Vet-View powinien zapewnić transparentność na **trzech poziomach**, o różnej mocy prawnej:

- **w treści wyniku tekstowego** (obowiązek, art. 50 ust. 2) – generowany opis tekstowy ma być oznaczony w formacie maszynowo czytelnym i wykrywalnym jako wygenerowany przez AI (np. metadane pochodzenia w standardzie C2PA, oznaczenie w strukturze dokumentu), tak aby oznaczenie nie znikało po wklejeniu do dokumentacji klinicznej; prawdopodobieństwo należy opisywać jako parametr modelu – nie potwierdzenie diagnozy;
- **w interfejsie** (dobra praktyka; ust. 1 jest tu przypadkiem granicznym) – przy każdym wyniku należy wskazać, że został wygenerowany przez AI, ma charakter pomocniczy, nie jest samodzielną diagnozą, wymaga weryfikacji przez lekarza, jego jakość zależy od jakości obrazu wejściowego, a prawdopodobieństwo nie jest równoznaczne z pewnością diagnostyczną;
- **w dokumentacji i warstwach graficznych** (dobra praktyka) – instrukcja używania powinna opisywać przeznaczenie (jednoznacznie: produkt dla zwierząt, nie dla ludzi), zakres gatunkowy (pies), anatomiczny (nerki) i badania (USG przezpowłokowe), obsługiwane formaty i minimalną jakość obrazu, ograniczenia skuteczności, znane przypadki gorszego działania, interpretację wskaźnika pewności, zasady nadzoru człowieka (*human oversight*) oraz sposób zgłaszania błędów; heatmapa i kontur powinny być odróżnialnymi warstwami AI, choć jako wyniki analityczne nie są „syntetycznym obrazem" w rozumieniu ust. 2.

Obowiązki deployera z art. 50 ust. 3 (rozpoznawanie emocji, kategoryzacja biometryczna) i ust. 4 (deepfake, teksty publikowane w celu informowania o sprawach publicznych) **nie mają zastosowania** do klinik używających Vet-View.

### 5.3. Utrzymanie prawidłowego przeznaczenia (*intended purpose*) – art. 3 pkt 12

„Intended purpose" to użycie, do którego dostawca przeznaczył system, określone w instrukcjach, materiałach promocyjnych i dokumentacji. Wymaga to **spójności** między: dokumentacją techniczną, instrukcją używania, regulaminem SaaS, umową z klientem, materiałami marketingowymi, stroną WWW, prezentacjami sprzedażowymi, komunikatami w aplikacji i szkoleniami.

⚠️ **Zakaz sformułowań mylących**, np.: „system diagnozuje choroby nerek", „automatyczna diagnoza", „zastępuje lekarza", „wykrywa nowotwory", „medyczny system AI", „dla USG" bez zaznaczenia, że chodzi wyłącznie o USG **weterynaryjne**.

### 5.4. Niestosowanie zakazanych praktyk – art. 5

Obecnie Vet-View nie wykazuje cech praktyki zakazanej, ale produkt nie powinien być w przyszłości rozszerzany o funkcje typu: ocena lekarzy, rankingowanie pracowników klinik, predykcja zachowań klientów czy profilowanie właścicieli zwierząt – mogłoby to przesunąć go ku kategorii zakazanej lub wysokiego ryzyka.

### 5.5. Zarządzanie zmianami modelu

AI Act **nie** ustanawia uniwersalnego obowiązku zgodności „lifecycle-based"; jest to centralny element reżimu wyłącznie dla systemów wysokiego ryzyka (art. 8–17, art. 72). Mimo to – z uwagi na charakter SaaS i zamiar trenowania modelu na danych klientów – rekomendowana jest procedura kontroli zmian, obejmująca dokumentowanie:

1. wersji modelu; 2. dat wdrożeń; 3. zmian architektury; 4. zmian zbiorów treningowych; 5. zmian kategorii klasyfikacji; 6. zmian progów decyzyjnych; 7. wpływu na dokładność, czułość i swoistość; 8. wpływu na interpretację historycznych wyników; 9. procedury rollback; 10. komunikowania klientom istotnych aktualizacji.

To istotne, bo system ma umożliwiać porównywanie wyników w czasie: jeśli model zmieni się między pierwszym a kolejnym badaniem, **porównywalność wyników może być ograniczona**.

### 5.6. Modele ogólnego przeznaczenia (GPAI) – art. 53

Jeśli opis tekstowy generuje zewnętrzny model ogólnego przeznaczenia udostępniany przez API, obowiązki dostawcy modelu GPAI (dokumentacja, polityka praw autorskich, streszczenie danych treningowych) spoczywają na **dostawcy tego modelu**, nie na Vet-View S.A. Vet-View pozostaje dostawcą **systemu AI** i odpowiada za jego zgodność, w tym za oznaczanie wyników z art. 50 ust. 2. Sytuacja zmienia się, gdyby Vet-View istotnie zmodyfikował model (np. przez rozległe dotrenowanie) – wtedy sam mógłby stać się dostawcą modelu GPAI.

---

## KROK 6 – Kiedy to obowiązuje i kto egzekwuje?

| Data | Co się stosuje |
|------|----------------|
| 2 lutego 2025 | praktyki zakazane (art. 5), AI literacy (art. 4), przepisy ogólne |
| 2 sierpnia 2025 | modele GPAI (rozdz. V), organy nadzoru, kary (art. 99) |
| 2 sierpnia 2026 | **transparentność (art. 50)** i większość pozostałych przepisów |
| 2 grudnia 2026 | koniec okresu przejściowego na oznaczanie z art. 50 ust. 2 (systemy sprzed 2.08.2026) oraz na nowy zakaz z art. 5 |
| 2 grudnia 2027 | systemy wysokiego ryzyka z Załącznika III (Omnibus: przesunięte z 2.08.2026) |
| 2 sierpnia 2028 | systemy wysokiego ryzyka z Załącznika I (Omnibus: przesunięte z 2.08.2027) |

Dla Vet-View oznacza to, że obowiązki z art. 4 i art. 50 **już obowiązują**; odroczenia z Omnibusu dotyczą wyłącznie reżimu wysokiego ryzyka, z którego produkt i tak wypadł.

**Polska.** Ustawa o systemach sztucznej inteligencji (uchwalona 3 lipca 2026, podpisana 24 lipca 2026, ogłoszona 27 lipca 2026) weszła w życie **11 sierpnia 2026**. Tworzy **Komisję Rozwoju i Bezpieczeństwa Sztucznej Inteligencji (KRiBSI)** jako organ nadzoru rynku, przewiduje piaskownice regulacyjne oraz procedurę uzyskania opinii przed wdrożeniem; kontrole i kary KRiBSI od 28 października 2026.

**Kary (art. 99 AI Act):** do 35 mln EUR lub 7% światowego obrotu za praktyki zakazane; do 15 mln EUR lub 3% za naruszenie innych obowiązków (w tym art. 50); do 7,5 mln EUR lub 1% za nieprawdziwe lub wprowadzające w błąd informacje. Dla MŚP stosuje się niższą z kwot.

---

## Podsumowanie analizy

| Krok | Pytanie | Podstawa prawna | Wniosek |
|------|---------|-----------------|---------|
| 1 | Czy to system AI? | art. 3 pkt 1 | **Tak** |
| 2a | Czy zakazany? | art. 5 | Nie |
| 2b | Czy wysokiego ryzyka? | art. 6, zał. I i III | Nie |
| 2c | Która kategoria? | art. 50 ust. 2 | **Obowiązki transparentności („ograniczone ryzyko")** |
| 3 | Kto jest kim? | art. 3 pkt 3 i 4 | Dostawca = Vet-View S.A.; deployer = klinika |
| 4 | Czy AI Act ma zastosowanie? | art. 2 ust. 1 lit. a (dostawca), lit. b (deployer) | **Tak**, bez wyłączeń |
| 5 | Jakie obowiązki? | art. 4, 50 ust. 2, 3 pkt 12, 53 | Literacy (obie role), oznaczanie tekstu AI, intended purpose, kontrola zmian |
| 6 | Od kiedy i kto nadzoruje? | art. 113, 99; ustawa o systemach AI | art. 4 od 2.02.2025, art. 50 od 2.08.2026; KRiBSI |

---

## Czego uczy ten przykład – wnioski dydaktyczne

1. **Kwalifikacja ryzyka wyznacza zakres obowiązków.** Najpierw ustalamy kategorię, potem dopiero obowiązki – nie odwrotnie.
2. **Kontekst potrafi być rozstrzygający.** „Zwierzęta vs ludzie" zadecydowało o wyjściu poza reżim wyrobu medycznego i Załącznika III.
3. **„Ograniczone ryzyko" ≠ „brak obowiązków".** Transparentność i AI literacy obowiązują również tutaj.
4. **Język marketingu ma skutki prawne.** Sposób opisu produktu współtworzy jego *intended purpose*.
5. **Kwalifikacja jest dynamiczna.** Nowe funkcje mogą zmienić kategorię – compliance to proces, nie jednorazowa czynność.
6. **Kwalifikacja wisi na konkretnym wyniku.** To generator opisu tekstowego, a nie ramki i heatmapy, uruchamia art. 50 ust. 2 – warto wiedzieć, który element produktu „ciągnie" obowiązki.

---

## Pytania do dyskusji

1. Co zmieniłoby się w analizie, gdyby Vet-View był przeznaczony dla **ludzi** (USG medyczne)?
2. Jakie konkretne funkcje przesunęłyby produkt do kategorii **wysokiego ryzyka** lub **zakazanej**?
3. Trenowanie modelu na danych klientów – jakie obowiązki rodzi to dodatkowo na gruncie **RODO**, niezależnie od AI Act?
4. Jak w praktyce technicznie oznaczyć opis tekstowy (obowiązek) i heatmapę (dobra praktyka) jako **treść wygenerowaną przez AI** w formacie maszynowo czytelnym, tak aby oznaczenie przetrwało wklejenie do systemu dokumentacji kliniki?
5. Kto ponosi odpowiedzialność, gdy lekarz bezkrytycznie zaufa błędnemu wynikowi (*automation bias*) – dostawca czy podmiot stosujący? Wskazówka: dyrektywa o odpowiedzialności za AI została wycofana w lutym 2025, ale nowa dyrektywa o odpowiedzialności za produkty (UE) 2024/2853 obejmuje oprogramowanie i AI od 9 grudnia 2026.
6. Gdyby Vet-View zwracał wyłącznie ramkę i klasę zmiany, bez opisu tekstowego – czy art. 50 nadal miałby zastosowanie? Które obowiązki by pozostały?

---

*Materiał dydaktyczny. Stan prawny: wrzesień 2026 – rozporządzenie (UE) 2024/1689 (AI Act) ze zmianami z rozporządzenia (UE) 2026/1744, ustawa o systemach sztucznej inteligencji. Przykład ma charakter ilustracyjny i nie stanowi porady prawnej.*
