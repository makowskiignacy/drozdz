## Proponowany wstępny temat pracy doktorskiej
Identyfikacja biomarkerów nowotworowych z wykorzystaniem wyjaśnialnego uczenia maszynowego

---

## Cel naukowy projektu
Projekt skupia się na opracowaniu wyjaśnialnych algorytmów analizy obrazu, zdolnych do wnioskowania o defektach mechanizmów naprawy DNA i sygnaturach mutacyjnych na podstawie preparatów histopatologicznych raka jelita grubego barwionych hematoksyliną i eozyną (H&E). Docelowa architektura zostanie wybrana na podstawie ewaluacji wiodących modeli referencyjnych dla patologii obliczeniowej. Zostaną one poddane ustandaryzowanemu porównaniu pod kątem stabilności uczenia na zintegrowanych zbiorach danych. Ostatecznie wyłonione modele przejdą walidację na niezależnej kohorcie zewnętrznej. Zakłada się również możliwość zbadania skuteczności detekcji szlaków naprawczych w odniesieniu do profili genomowych algorytmu RePrint [1], a potencjalne interakcje wyekstrahowanych cech wpływających na przeżycie pacjentów mogłyby być analizowane metodą SurvSHAP-IQ [2]. Zrozumienie opisanych zależności ma na celu precyzyjną imputację cech molekularnych na podstawie obrazów morfologicznych.

[1] D. Wójtowicz et al., "Toward identification of common DNA repair process in mutational signatures," bioRxiv, 2026.
[2] S. Langbein et al., "Functional decomposition and shapley interactions for interpreting survival models," arXiv, 2026.

---

## Uzasadnienie podjęcia tematu pracy doktorskiej w kontekście dotychczasowego stanu wiedzy
Nowotwory o fenotypie hipermutacyjnym wykazują wrażliwość na leczenie stymulujące odpowiedź układu odpornościowego. Zalicza się do nich guzy charakteryzujące się niestabilnością mikrosatelitarną (MSI). Zjawisko to dotyczy nie tylko MSI, ale także guzów posiadających patogenne mutacje w genie POLE, stanowiących około 1% przypadków raka jelita grubego. Identyfikacja tych defektów wymaga obecnie kosztownego profilowania molekularnego. Każdy z procesów patofizjologicznych przejawia się występowaniem określonych wzorców podstawień nukleotydowych – tzw. sygnatur mutacyjnych. Niedobór POLE koreluje z sygnaturami SBS10a i SBS10b, natomiast dysfunkcja systemu MMR m.in. z sygnaturami SBS6 i SBS14. Ponieważ opisane mechanizmy wywołują zbieżne wzorce histopatologiczne (jak nasilony naciek limfocytarny), preparaty H&E mogą pełnić rolę markerów zastępczych. Skuteczność diagnozowania tego fenotypu morfologicznego przy użyciu sztucznej inteligencji została już udowodniona [3], co stanowi punkt wyjścia do poszukiwań rozwiązań łączących różne typy danych. Modele multimodalne postrzegane są jako szansa na dodatkowe poprawienie wyników klasyfikacji, a jednocześnie dają możliwość zbadania, które informacje są zachowane pomiędzy poszczególnymi modalnościami. Architektury takie jak TransSurv z powodzeniem łączą skany H&E z profilami transkryptomicznymi (RNA-seq) i analizą zmienności liczby kopii (CNV), optymalizując w ten sposób predykcję czasu przeżycia pacjentów [4]. Predykcje w proponowanym projekcie opierają się na przestrzennej analizie cech histologicznych i ich matematycznej reprezentacji tkankowej. Niezbędna do tego weryfikacja biologicznej poprawności tych reprezentacji (map atencji) odbędzie się na multimodalnym zbiorze danych IMMUcan, umożliwiając ścisłą korelację wyników z wielokrotną immunofluorescencją.

[3] M. Gustav et al., "Deep learning for dual detection of microsatellite instability and POLE mutations in colorectal cancer histopathology," npj Precis. Oncol., vol. 8, no. 1, p. 115, 2024.
[4] D. Gharaie Amirabadi et al., "Multimodal foundation models in colorectal cancer," Brief Bioinform, 2026.

---

## Zakres planowanych prac badawczych, proponowana metodyka badań
Projekt zakłada adaptację architektur sztucznej inteligencji typu weakly-supervised, zaczynając od modeli CLAM oraz UNI, zoptymalizowanych do analizy wirtualnych preparatów mikroskopowych (WSI). Wybrane modele wizyjne zostaną wytrenowane na obszernej puli ponad 3500 zintegrowanych skanów H&E, agregującej zestawy danych z czterech międzynarodowych kohort klinicznych (DACHS, TCGA, APHP, SurGen). Aby wyeliminować zjawisko przeuczenia sieci na specyfikę sprzętową jednego laboratorium, ewaluacja generalizacji zewnętrznej zostanie przeprowadzona na odrębnej kohorcie testowej IMMUcan. 

Interpretowalność decyzji modelu będzie realizowana poprzez wygenerowanie topograficznych map uwagi. Wskażą one subregiony tkanki decydujące o predykcji konkretnych sygnatur deficytów naprawczych, w dużej mierze zastępując manualne i kosztowne adnotacje patomorfologów [5]. W końcowym etapie, za pomocą metodyki SurvSHAP-IQ, wykonana zostanie dekompozycja cech. Umożliwi to kwantyfikację interakcji występujących między wyekstrahowanymi deficytami mechanizmów naprawy DNA a parametrami przeżycia pacjentów, pozwalając na analizę wpływu poszczególnych zmiennych na przebieg choroby.

[5] M. Y. Lu et al., "Data-efficient and weakly supervised computational pathology on whole-slide images," Nat. Biomed. Eng., vol. 5, no. 6, pp. 555-570, 2021.

---

## Oczekiwane rezultaty naukowo-badawcze i znaczenie projektu
Proponowane badania skupiają się na zastosowaniu algorytmów uczenia głębokiego do wnikliwej analizy preparatów histopatologicznych (H&E). Do głównych oczekiwanych rezultatów projektu należy ustandaryzowana ocena wiodących modeli referencyjnych z dziedziny patologii obliczeniowej w celu wyłonienia architektury gwarantującej optymalną zdolność do generalizacji. Równie istotnym aspektem będzie predykcja sygnatur mutacyjnych, w tym specyficznych wzorców SBS10a/b przypisanych do szlaku POLE oraz SBS6 i SBS14 wskazujących na deficyty MMR, prowadzona z wykorzystaniem danych obrazowych. Oprócz tego zaplanowano podjęcie próby oceny jakości wyjaśnialności (explainability) testowanych modeli na drodze weryfikacji generowanych przestrzennych map uwagi z biologicznym rozkładem struktur uwidocznionych dzięki metodzie immunofluorescencji. Całość prac zmierza do weryfikacji założenia, że fenotyp morfologiczny zawiera ukryte dane molekularne, co z kolei dostarczy fundamentów pod projektowanie bardziej precyzyjnych algorytmów wielomodalnych nowej generacji.
