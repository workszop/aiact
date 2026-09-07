# AI Act w praktyce
## Od ogólnych ram regulacyjnych do kwalifikacji systemu wspierającego diagnostykę

*Materiał wykładowy · podejście oparte na ryzyku · case study: Vet-View*

*Stan prawny: wrzesień 2026 – rozporządzenie (UE) 2024/1689 (AI Act) ze zmianami wprowadzonymi rozporządzeniem (UE) 2026/1744 (Digital Omnibus on AI, w mocy od 27 lipca 2026) oraz ustawa o systemach sztucznej inteligencji (w mocy od 11 sierpnia 2026).*

> **Notatka prelegenta:** Slajd otwierający. Zapowiedz logikę całości – najpierw dajemy mapę regulacji (czym jest AI Act, jak klasyfikuje systemy, kto za co odpowiada), a potem na żywym przykładzie przechodzimy całą ścieżkę subsumpcji: *czy to w ogóle system AI → do której kategorii ryzyka → jakie obowiązki*.

---

## Agenda

**Część I – AI Act ogólnie**
1. Czym jest AI Act i po co powstał
2. Definicja systemu AI
3. Piramida ryzyka – cztery kategorie
4. Role: dostawca vs podmiot stosujący
5. Obowiązki przekrojowe (AI literacy, transparentność)
6. Kalendarz stosowania, nadzór w Polsce, kary

**Część II – Case: system wspierający diagnostykę**
7. Subsumpcja: czy to system AI?
8. Kwalifikacja ryzyka – krok po kroku
9. Role i obowiązki w konkretnym wdrożeniu
10. Wnioski i pułapki rekwalifikacji

> **Notatka:** Zaznacz, że Część II nie wprowadza nowych przepisów – *stosuje* te z Części I. To ma być moment "aha": regulacja staje się operacyjna dopiero gdy ją zsubsumujemy pod konkretny produkt.

---

# CZĘŚĆ I
## AI Act – ogólne ramy regulacyjne

---

## Czym jest AI Act?

- **Rozporządzenie UE** – pierwszy na świecie kompleksowy reżim prawny dla sztucznej inteligencji
- Obowiązuje **bezpośrednio** we wszystkich państwach członkowskich (nie wymaga implementacji jak dyrektywa)
- Logika: **product safety + prawa podstawowe** – nie reguluje "AI jako takiej", lecz *ryzyko jej zastosowań*

**Kluczowa idea: podejście oparte na ryzyku (*risk-based approach*)**

Im wyższe ryzyko dla zdrowia, bezpieczeństwa i praw podstawowych, tym surowsze obowiązki. Większość systemów AI podlega obowiązkom **niewielkim albo żadnym**.

> **Notatka:** Najczęstsze nieporozumienie studentów – że AI Act "zakazuje AI" albo obciąża każdy chatbot. Przeciwnie: ciężar regulacyjny jest skoncentrowany na wąskiej grupie zastosowań wysokiego ryzyka. To dobry moment, by zapowiedzieć, że nasz case wyląduje *nisko* w piramidzie.

---

## Definicja systemu AI (art. 3 pkt 1)

System AI to **system maszynowy**, który:
- działa z **różnym poziomem autonomii**,
- może wykazywać **adaptacyjność** po wdrożeniu,
- **wnioskuje** z danych wejściowych, jak generować wyniki: *przewidywania, treści, rekomendacje lub decyzje*,
- a wyniki te mogą **wpływać na środowiska fizyczne lub wirtualne**.

**Test praktyczny – pięć pytań:**
system maszynowy? → przetwarza wejście? → generuje wynik (predykcję/treść/rekomendację)? → wynik wpływa na rzeczywistość? → zawiera komponent uczący się/wnioskujący?

> **Notatka:** Podkreśl słowo **"wnioskuje"** (*infers*) – to ono odróżnia system AI od zwykłego oprogramowania regułowego. Wytyczne Komisji w sprawie definicji systemu AI są tu źródłem interpretacyjnym, do którego wrócimy w Części II.

---

## Piramida ryzyka – cztery kategorie

| Kategoria | Co obejmuje | Skutek |
|---|---|---|
| 🔴 **Niedopuszczalne ryzyko** | praktyki zakazane (art. 5) | **zakaz** |
| 🟠 **Wysokie ryzyko** | art. 6 + Załącznik I i III | pełny reżim compliance (art. 8–17, 72) |
| 🟡 **Ograniczone ryzyko** (nazwa umowna) | systemy objęte art. 50 | **obowiązki transparentności** |
| 🟢 **Minimalne ryzyko** | reszta systemów AI | brak obowiązków szczególnych |

⚠ "Ograniczone ryzyko" to skrót dydaktyczny, nie kategoria ustawowa. Rozporządzenie zna: praktyki zakazane, systemy wysokiego ryzyka, systemy objęte art. 50 oraz modele GPAI (rozdz. V). Obowiązki z art. 50 **kumulują się** z reżimem wysokiego ryzyka, a art. 4 dotyczy wszystkich poziomów.

> **Notatka:** Narysuj to jako piramidę – góra wąska (zakazane), dół szeroki (minimalne). Komisja w wytycznych używa określenia "transparency risk". Zapowiedz, że nasz case przejdzie tę piramidę "od góry do dołu" metodą eliminacji: najpierw wykluczymy zakaz, potem wysokie ryzyko, i wylądujemy na poziomie obowiązków z art. 50.

---

## Praktyki zakazane (art. 5)

Bezwzględny zakaz – nieusuwalne ryzyko dla **godności, autonomii i praw podstawowych**:

- techniki **podprogowe** lub celowo zwodnicze, manipulacyjne, powodujące poważną szkodę (lit. a)
- wykorzystywanie **szczególnej podatności** osób (wiek, niepełnosprawność, sytuacja społeczna lub ekonomiczna) (lit. b)
- **scoring społeczny** prowadzący do nieuzasadnionego lub nieproporcjonalnego traktowania (lit. c)
- ocena ryzyka popełnienia przestępstwa **wyłącznie** na podstawie profilowania lub cech osobowości (lit. d) – nie każdy *predictive policing*
- tworzenie **baz danych twarzy** przez nieukierunkowane scrapowanie internetu lub CCTV (lit. e)
- **rozpoznawanie emocji** w miejscu pracy i w edukacji – z wyjątkiem celów medycznych i bezpieczeństwa (lit. f)
- **kategoryzacja biometryczna** wnioskująca o rasie, poglądach politycznych, przynależności związkowej, przekonaniach, życiu seksualnym lub orientacji (lit. g) – inna kategoryzacja biometryczna to wysokie ryzyko (Zał. III) + art. 50 ust. 3
- zdalna **identyfikacja biometryczna w czasie rzeczywistym** w przestrzeni publicznej **do celów ścigania przestępstw**, z wąskimi wyjątkami (lit. h) – RBI w innych celach to wysokie ryzyko
- **nowość (Omnibus 2026):** systemy, których przewidywalnym i powtarzalnym wynikiem jest generowanie treści intymnych bez zgody lub materiałów CSAM – okres przejściowy do 2 grudnia 2026

> **Notatka:** Wspólny mianownik tej listy – wszystkie dotyczą **ludzi** i ingerencji w ich prawa podstawowe. Zwróć uwagę na kwalifikatory: kilka pozycji jest zakazanych tylko w wąskim wariancie, a poza nim ląduje w wysokim ryzyku. Zapamiętajcie to, bo w case'ie weterynaryjnym brak "człowieka jako przedmiotu oceny" będzie kluczowym argumentem. Źródło interpretacji: Wytyczne Komisji w sprawie praktyk zakazanych, C(2025) 5052 final.

---

## Systemy wysokiego ryzyka (art. 6 + Zał. I i III)

System jest wysokiego ryzyka, gdy spełnia **jedną z dwóch ścieżek**:

**Ścieżka 1 – Załącznik I (produktowa), art. 6 ust. 1 – dwa warunki łącznie:**
(a) system jest **komponentem bezpieczeństwa** produktu objętego unijnym prawem harmonizacyjnym z Zał. I (np. MDR 2017/745 – wyroby medyczne, IVDR 2017/746, maszyny, zabawki, windy) **lub sam jest takim produktem**, **oraz**
(b) produkt ten podlega **ocenie zgodności przez stronę trzecią** (jednostkę notyfikowaną) na podstawie tych przepisów.

**Ścieżka 2 – Załącznik III (obszarowa), art. 6 ust. 2**
system działa w jednym z wymienionych obszarów wysokiego ryzyka dla **osób fizycznych**: biometria, infrastruktura krytyczna, edukacja, zatrudnienie, dostęp do świadczeń/kredytu/ubezpieczeń/ochrony zdrowia, ściganie, migracja, wymiar sprawiedliwości, procesy demokratyczne. Wyjątek: art. 6 ust. 3 – system z Zał. III nie jest wysokiego ryzyka, gdy nie stwarza znaczącego ryzyka (np. wykonuje wąskie zadanie proceduralne), chyba że profiluje osoby.

> **Notatka:** To najważniejszy slajd dla zrozumienia case'a. Obie ścieżki są nastawione na **ochronę ludzi**. Podkreśl, że ścieżka produktowa ma **dwa** warunki łączne – oprogramowanie medyczne klasy I bez udziału jednostki notyfikowanej nie przechodzi warunku (b). W Części II pokażemy, dlaczego oprogramowanie weterynaryjne wypada z obu – i dlaczego "technicznie mogłoby działać u ludzi" to za mało.

---

## Ograniczone ryzyko – transparentność (art. 50)

Art. 50 stosuje się **od 2 sierpnia 2026** (niezależnie od kategorii ryzyka) i nakłada obowiązki:

**Na dostawcę:**
- ust. 1 – system **przeznaczony do bezpośredniej interakcji** z osobami fizycznymi (chatboty, asystenci, agenci) → osoba ma wiedzieć, że ma do czynienia z AI, **chyba że jest to oczywiste** dla rozsądnie poinformowanego użytkownika,
- ust. 2 – system **generuje syntetyczny** obraz, dźwięk, wideo lub tekst → wynik oznaczony w formacie **maszynowo czytelnym** i wykrywalny jako wygenerowany przez AI. Wyjątki: funkcja pomocnicza przy standardowej edycji (korekta, tłumaczenie) lub brak istotnej zmiany danych wejściowych. **Streszczenia i przeredagowania generowane przez AI nie korzystają z wyjątku.**

**Na deployera:**
- ust. 3 – informowanie osób poddanych rozpoznawaniu emocji lub kategoryzacji biometrycznej,
- ust. 4 – ujawnianie **deepfake'ów** oraz tekstów generowanych przez AI publikowanych w celu informowania o sprawach publicznych.

Okres przejściowy (Omnibus): systemy generatywne obecne na rynku przed 2 sierpnia 2026 mają czas na wdrożenie oznaczania z ust. 2 do **2 grudnia 2026**. Interpretacja: Wytyczne Komisji do art. 50 (20 lipca 2026) i Kodeks postępowania ws. oznaczania treści generowanych przez AI.

> **Notatka:** Art. 50 to "miękki" reżim, ale realny i już obowiązujący. Wiele zespołów produktowych zakłada "nie jesteśmy high-risk, więc nic nas nie dotyczy" – i przeocza transparentność. Uprzedź, że w case'ie najmocniejszym punktem zaczepienia będzie **generowany opis tekstowy** (ust. 2), a nie sam interfejs.

---

## Role: dostawca vs podmiot stosujący

| | **Dostawca** (*provider*, art. 3 pkt 3) | **Podmiot stosujący** (*deployer*, art. 3 pkt 4) |
|---|---|---|
| Kto | rozwija system / zleca rozwój i **wprowadza do obrotu** pod własną marką | **używa** systemu i sprawuje nad nim **kontrolę** |
| Przykład | producent oprogramowania, SaaS | firma/klinika korzystająca z narzędzia |
| Wyłączenie | – | użycie w ramach **osobistej działalności pozazawodowej** |

**Ważne:** gdy deployerem jest osoba prawna, *poszczególni pracownicy* działający w jej ramach i pod jej kontrolą **nie są** odrębnymi deployerami (Wytyczne Komisji w sprawie praktyk zakazanych, C(2025) 5052 final, sekcja 2.4, pkt 17–18).

> **Notatka:** To rozróżnienie decyduje o tym, kto dźwiga które obowiązki. Najwięcej spoczywa na dostawcy. W case'ie precyzyjnie przypiszemy obie role.

---

## Obowiązki przekrojowe – AI literacy (art. 4)

Niezależnie od kategorii ryzyka, **dostawcy i deployerzy** podejmują środki **wspierające rozwój kompetencji AI** (*AI literacy*) swojego personelu i osób obsługujących system w ich imieniu – z uwzględnieniem wiedzy, doświadczenia i kontekstu użycia.

Brzmienie po Omnibusie (rozp. 2026/1744): obowiązek **nie wymaga zagwarantowania określonego poziomu kompetencji** u żadnej konkretnej osoby; Komisja i państwa członkowskie mają wspierać dostawców i deployerów, zwłaszcza MŚP. Wcześniejsza wersja ("zapewnić wystarczający poziom") już nie obowiązuje.

Co to znaczy w praktyce – personel powinien rozumieć:
- zasady działania i **ograniczenia** modelu,
- znaczenie **wskaźnika pewności / prawdopodobieństwa**,
- ryzyko wyników **fałszywie dodatnich i ujemnych**,
- ryzyko **automation bias** (nadmiernego zaufania do AI),
- zasady eskalacji błędów i komunikowania ograniczeń.

> **Notatka:** Art. 4 obowiązuje od 2 lutego 2025 i dotyczy **wszystkich** kategorii – także systemów objętych tylko art. 50 – i **obu ról** (klinika-deployer też). Omnibus złagodził brzmienie z obowiązku rezultatu na obowiązek starannego działania, ale nie uchylił przepisu. To częsty "ślepy punkt". Zapowiedz, że w case'ie przełożymy to na konkretny program szkoleń.

---

## Zakres zastosowania (art. 2)

AI Act stosuje się m.in. do:
- **dostawców** wprowadzających systemy AI do obrotu lub oddających je do użytku w UE, niezależnie od siedziby (art. 2 ust. 1 lit. a) – to podstawa dla dostawcy SaaS,
- **deployerów** mających siedzibę lub znajdujących się w UE (art. 2 ust. 1 lit. b),
- **producentów produktów**, którzy pod własną marką wraz ze swoim produktem wprowadzają system AI (art. 2 ust. 1 lit. e) – np. producent aparatu USG z wbudowanym modułem AI.

**Wyłączenia, które trzeba sprawdzić:**
- prywatne, nieprofesjonalne użycie,
- czynności **badawczo-rozwojowe przed** wprowadzeniem na rynek (ale **nie** testy w warunkach rzeczywistych ani komercyjne udostępnianie).

> **Notatka:** Rozróżnij lit. a (dostawca samodzielnego systemu, w tym SaaS) od lit. e (producent sprzętu, który dołącza AI do swojego produktu). Nasz case to lit. a dla Vet-View S.A. i lit. b dla klinik; lit. e wchodziłaby w grę, gdyby moduł sprzedawał producent aparatu USG.

---

## Kalendarz stosowania, nadzór w Polsce, kary

| Data | Co się stosuje |
|---|---|
| 2 lutego 2025 | praktyki zakazane (art. 5), AI literacy (art. 4), definicje |
| 2 sierpnia 2025 | modele GPAI (rozdz. V), organy nadzoru, kary (art. 99) |
| 2 sierpnia 2026 | **transparentność (art. 50)** i większość pozostałych przepisów |
| 2 grudnia 2026 | koniec okresu przejściowego na oznaczanie z art. 50 ust. 2 (systemy sprzed 2.08.2026) oraz na nowy zakaz z art. 5 |
| 2 grudnia 2027 | systemy wysokiego ryzyka z **Zał. III** (Omnibus: przesunięte z 2.08.2026) |
| 2 sierpnia 2028 | systemy wysokiego ryzyka z **Zał. I** (Omnibus: przesunięte z 2.08.2027) |

**Polska:** ustawa o systemach sztucznej inteligencji (uchwalona 3 lipca 2026, podpisana 24 lipca 2026, w mocy od **11 sierpnia 2026**). Organ nadzoru: **Komisja Rozwoju i Bezpieczeństwa Sztucznej Inteligencji (KRiBSI)** – kontrole i kary od 28 października 2026; piaskownice regulacyjne; procedura opinii przed wdrożeniem.

**Kary (art. 99):** do 35 mln EUR lub 7% obrotu (praktyki zakazane); do 15 mln EUR lub 3% (inne obowiązki, w tym art. 50); do 7,5 mln EUR lub 1% (wprowadzające w błąd informacje). Dla MŚP stosuje się niższą z kwot.

> **Notatka:** Wykład odbywa się po 2 sierpnia 2026 – art. 50 już obowiązuje, a rozpoznawanie art. 4 trwa od półtora roku. Omnibus przesunął tylko reżim wysokiego ryzyka; nasz case nie korzysta z tego odroczenia.

---

# CZĘŚĆ II
## Case: system wspierający diagnostykę
### Vet-View

*oprogramowanie AI do analizy obrazów USG w weterynarii*

> **Notatka:** Przedstaw produkt jednym zdaniem: system analizuje obraz USG nerki **psa**, lokalizuje zmianę, klasyfikuje ją, podaje prawdopodobieństwo i generuje opis tekstowy do dokumentacji. Wynik jest **pomocniczy** – decyduje lekarz weterynarii. Model ma być trenowany/walidowany na danych klientów (SaaS).

---

## Krok 0 – Czy to w ogóle system AI?

Subsumpcja pod art. 3 pkt 1 – Vet-View:
- jest **systemem maszynowym**,
- przetwarza **dane wejściowe** = obrazy USG,
- **generuje wyniki**: lokalizacja zmiany, maska, heatmapa, klasyfikacja, prawdopodobieństwo, podsumowanie tekstowe,
- wynik **wpływa** na dalszy proces diagnostyczny lekarza,
- zawiera **komponent AI** trenowany na danych.

**Wniosek: TAK – to system AI objęty AI Act.**

> **Notatka:** Pokaż, że to nie formalność – gdyby to był sztywny algorytm progowy bez wnioskowania, dyskusja byłaby inna. Dopiero pozytywna odpowiedź "to system AI" otwiera pytanie o kategorię ryzyka.

---

## Krok 1 – Czy zakazany? (art. 5)

Przechodzimy listę praktyk zakazanych:
- techniki podprogowe / manipulacja? **nie**
- scoring społeczny? **nie**
- identyfikacja / kategoryzacja biometryczna ludzi? **nie**
- rozpoznawanie emocji, predykcja przestępczości? **nie**
- generowanie treści intymnych bez zgody / CSAM (nowy zakaz 2026)? **nie**

Produkt dotyczy **obrazów USG zwierząt**, nie ingeruje w prawa podstawowe ludzi.

**Wniosek: NIE jest systemem zakazanym.**

> **Notatka:** Szybki slajd eliminacyjny. Wszystkie zakazy z art. 5 dotyczą ludzi – tu "obiektem" jest nerka psa. Schodzimy piętro niżej.

---

## Krok 2 – Czy wysokiego ryzyka? Ścieżka produktowa

Czy to **komponent bezpieczeństwa** aparatu USG (art. 3 pkt 14 + art. 6 ust. 1)? **NIE**, bo system:
- nie steruje bezpieczeństwem aparatu,
- nie zapobiega niebezpiecznej pracy urządzenia,
- nie kontroluje emisji ultradźwięków,
- jedynie **lokalizuje i klasyfikuje zmianę** – generuje informację pomocniczą.

Czy to **wyrób medyczny** (MDR/IVDR z Zał. I)? **NIE** – MDR obejmuje wyroby do stosowania **u ludzi**; to oprogramowanie do USG **wyłącznie weterynaryjnego**. Fakt, że *technicznie analogiczny* software mógłby działać u ludzi, **nie** czyni go wyrobem medycznym. Warunek (b) z art. 6 ust. 1 (ocena zgodności przez jednostkę notyfikowaną) w ogóle nie wymaga badania, bo warunek (a) nie jest spełniony.

> **Notatka:** Kluczowy moment dydaktyczny: kwalifikacja idzie za **przeznaczeniem** (*intended purpose*), nie za "teoretyczną możliwością" zastosowania. To częsty błąd w analizach.

---

## Krok 2 – Czy wysokiego ryzyka? Ścieżka obszarowa (Zał. III)

Załącznik III chroni **osoby fizyczne i ich prawa**. Vet-View:
- nie identyfikuje ani nie kategoryzuje **ludzi**,
- nie rozpoznaje emocji osób,
- nie dotyczy infrastruktury krytycznej, edukacji, zatrudnienia,
- nie decyduje o dostępie ludzi do świadczeń, kredytu, ubezpieczeń, ochrony zdrowia,
- nie jest używany przez organy ścigania, migracyjne ani sądy,
- nie wpływa na procesy demokratyczne.

System **dotyczy zwierząt** → poza zakresem Załącznika III.

**Wniosek: NIE jest systemem wysokiego ryzyka.**

> **Notatka:** Domknij obie ścieżki: produktowa (komponent bezpieczeństwa / wyrób medyczny) i obszarowa (Zał. III) – w obu negatywnie. Dopiero teraz mamy prawo zejść na poziom ograniczonego ryzyka.

---

## Krok 3 – Kwalifikacja końcowa: ograniczone ryzyko

System nie jest wysokiego ryzyka – ale **nie** jest czysto minimalnego ryzyka, bo aktualizuje się **art. 50 ust. 2**:

- **generowany opis tekstowy** wklejany do dokumentacji klinicznej to **syntetyczny tekst** – streszczenie generowane przez AI nie mieści się w wyjątku "standardowej edycji" → obowiązek maszynowo czytelnego oznaczenia (**to jest twardy punkt zaczepienia**),
- ramki, maski, heatmapy i wskaźnik prawdopodobieństwa to **wyniki analityczne** (detekcja, klasyfikacja), nie syntetyczny obraz – wytyczne Komisji i Kodeks postępowania nie traktują adnotacji jako treści syntetycznej; ich oznaczenie to **rekomendowana dobra praktyka**, nie obowiązek,
- art. 50 ust. 1 (bezpośrednia interakcja) jest przypadkiem granicznym: narzędzie obsługiwane przez lekarza w GUI to nie chatbot, a dla przeszkolonego profesjonalisty użycie AI jest **oczywiste** – informowanie w interfejsie warto utrzymać, ale nie na nim opiera się kwalifikacja.

**➡ System AI objęty obowiązkami transparentności z art. 50 ("ograniczone ryzyko").**

⚠ Dostawca musi **stale monitorować zmiany funkcjonalne** pod kątem możliwej rekwalifikacji.

> **Notatka:** To puenta całej ścieżki klasyfikacyjnej. Podkreśl, że "limited risk" to nie "brak obowiązków" – art. 50 ust. 2 jest tu sercem zgodności. Zaznacz uczciwie, że kwalifikacja wisi na generatorze tekstu: gdyby produkt zwracał tylko ramkę i klasę, byłby bliżej minimalnego ryzyka (z art. 4 nadal w mocy).

---

## Role w tym wdrożeniu

**Vet-View S.A. = DOSTAWCA** (art. 3 pkt 3), bo:
- sam rozwija moduł AI,
- oferuje produkt jako **SaaS pod własną marką**,
- udostępnia go gabinetom i klinikom w UE.

**Klienci (gabinety, lecznice, kliniki, laboratoria) = DEPLOYERZY** (art. 3 pkt 4), bo używają systemu i sprawują nad nim kontrolę.
→ Poszczególni weterynarze **nie są** odrębnymi deployerami – działają w ramach podmiotu.

> **Notatka:** Połącz to ze slajdem ról z Części I. Większość obowiązków, które omówimy dalej, spoczywa na **dostawcy** – Vet-View S.A.

---

## Obowiązki dostawcy (1/3) – AI literacy i transparentność

**AI literacy (art. 4)** – środki wspierające kompetencje: przeszkolić nie tylko R&D, ale i **sprzedaż oraz serwis**; materiały instruktażowe dla klientów i weterynarzy; aktualizacja wiedzy po każdej istotnej zmianie modelu. **Klinika-deployer ma własny obowiązek z art. 4** wobec swoich lekarzy – dostawca może go ułatwić materiałami.

**Transparentność (art. 50)** – na **trzech poziomach**:
1. **wynik tekstowy** (obowiązek, ust. 2) – opis generowany przez AI oznaczony **maszynowo czytelnie** (metadane / provenance, np. C2PA) i wykrywalny jako AI; nie znika po wklejeniu do dokumentacji,
2. **interfejs** (dobra praktyka, ust. 1 na granicy) – przy każdym wyniku: "wygenerowane przez AI, pomocnicze, nie zastępuje diagnozy, wymaga weryfikacji",
3. **dokumentacja i warstwy graficzne** (dobra praktyka) – przeznaczenie, zakres (pies / nerki / USG przezpowłokowe), ograniczenia, human oversight, zgłaszanie błędów; heatmapa i kontur jako odróżnialne **warstwy AI**.

Obowiązki deployera z art. 50 ust. 3–4 (emocje, deepfake, teksty publiczne) **nie mają zastosowania**.

> **Notatka:** Poziom 1 to bezpośrednie zastosowanie obowiązku oznaczania treści syntetycznych; poziomy 2–3 to ostrożnościowa nadwyżka. "Prawdopodobieństwo = parametr modelu, nie potwierdzenie diagnozy".

---

## Obowiązki dostawcy (2/3) – przeznaczenie systemu

**Utrzymanie prawidłowego *intended purpose* (art. 3 pkt 12)**

Pełna **spójność komunikatu** między: dokumentacją techniczną, instrukcją, regulaminem SaaS, umową, marketingiem, stroną www, prezentacjami i komunikatami w aplikacji.

🚫 **Zakazane sformułowania** (wprowadzające w błąd / przesuwające produkt w stronę wyrobu medycznego):
- "system diagnozuje choroby nerek", "automatyczna diagnoza"
- "zastępuje lekarza", "wykrywa nowotwory"
- "medyczny system AI", "dla USG" (bez dookreślenia: **weterynaryjnego**)

> **Notatka:** To pokazuje, że *język marketingu* ma skutki prawne – nieostrożny copywriting może zmienić kwalifikację produktu. Dobry punkt styku prawa z praktyką biznesową.

---

## Obowiązki dostawcy (3/3) – zarządzanie zmianami modelu

AI Act **nie** nakłada pełnego *lifecycle compliance* na systemy spoza wysokiego ryzyka – ale przy modelu **SaaS trenowanym na danych klientów** dostawca powinien prowadzić **kontrolę zmian** i dokumentować m.in.:

- wersję modelu, daty wdrożeń, zmiany architektury i zbiorów treningowych,
- zmiany progów decyzyjnych i kategorii klasyfikacji,
- wpływ na dokładność, czułość, swoistość,
- wpływ na **porównywalność wyników historycznych**, procedurę **rollback**, komunikację do klientów.

⚠ System ma umożliwiać **śledzenie historii badań w czasie** – zmiana modelu między badaniami może ograniczyć porównywalność wyników.

**GPAI:** jeśli opis tekstowy generuje zewnętrzny model ogólnego przeznaczenia (API), obowiązki z art. 53 spoczywają na **dostawcy modelu**; Vet-View S.A. pozostaje dostawcą **systemu** – chyba że istotnie zmodyfikuje model (wtedy sam staje się dostawcą GPAI).

> **Notatka:** Dobry przykład, że *dobre praktyki* wykraczają poza minimum prawne. Domknij wykład ostrzeżeniem: każda istotna zmiana funkcji może wymagać **ponownej kwalifikacji** w piramidzie ryzyka.

---

## Wnioski – czego uczy ten case

1. **Metoda zawsze ta sama:** system AI? → kategoria ryzyka (eliminacja od góry) → role → obowiązki.
2. **Kwalifikacja idzie za przeznaczeniem**, nie za technicznymi możliwościami ("mogłoby działać u ludzi" ≠ wyrób medyczny).
3. **"Ograniczone ryzyko" ≠ brak obowiązków** – transparentność (art. 50) + AI literacy (art. 4) obowiązują.
4. **Język produktu ma skutki prawne** – marketing może przesunąć produkt w górę piramidy.
5. **Kwalifikacja jest dynamiczna** – nowe funkcje (ocena ludzi, profilowanie) mogą wymagać rekwalifikacji.
6. **Odpowiedzialność cywilna idzie osobno** – dyrektywa o odpowiedzialności za AI została wycofana (luty 2025), ale nowa dyrektywa o odpowiedzialności za produkty (UE) 2024/2853 obejmuje oprogramowanie i AI od 9 grudnia 2026.

> **Notatka:** Slajd domykający. Jeśli zostaje czas – ćwiczenie: poproś studentów, by wymyślili jedną nową funkcję, która przeniosłaby Vet-View do wysokiego ryzyka lub kategorii zakazanej (np. "rozpoznawanie emocji właściciela zwierzęcia w poczekalni").
