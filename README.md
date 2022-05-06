# CeneoScraper

## struktura opinii w serwisie [Ceneo.PL](https://www.ceneo.pl/)

|Składowa opinii|Selektor|Nazwa zmiennej|Typ danych|
|---------------|--------|--------------|----------|
|opinia|div.js_product-review|opinion||
|identyfikator opinii|div.js_product-review\["data-entry-id"\]|opinion_id||
|autor opinii|span.user-post__author-name|author||
|rekomendacja autora|span.user-post__author-recomendation > em|recomendation||
|liczba gwaizdek|span.user-post__score-count|stars||
|treść opinii|div.user-post__text|content||
|lista zalet|div\[class$=positives\] ~ div.review_feature__item|pros||
|lista wad|div\[class$=negatives\] ~ div.review_feature__item|cons||
|dla ilu osób przydatna|button.vote-yes > span|useful||
|dla ilu odób nieprzydatna|button.vote-no > span|useless||
|data wystawienia opinii|span.user-post__published > time:nth-child(1)\["datetime"\]|published||
|data zakupu produktu|span.user-post__published > time:nth-child(2)\["datetime"\]|purchased||

## Etapy pracy nad projektem
1. Pobranie elementów pojedynczej opinii do niezależnych zmiennych
2. Zapisanie wszystkich elementów pojedynczej opinni do jedneh zmiennej \(słownik\)
3. Pobranie wszystkich opinii z pojedynczej strony do słowników i dodanie ich do listy
4. Pobranie wszystkich opinii o produkcie z wszystkich stron i zapisanie ich do pliku json
5. Dodanie możliwości podania id produktu przez użytkowanika za pomocą klawiatury
6. Refraktoryzacja (optymalizacja) kodu:
    a. utworzenie funkcji do pobierania składowuch strony HTML
    b. utworzenie słownika opisującego struktorę opinii wraz z selektorami poszczególnych elementów
    c. zamiana instrukcji pobierających składowe opinii do pojedynczych zmiennych i tworzących z nich słownik na wyrażenie słownikowe \(disctonary comprehencion\) tworzący słownik reprezentujący pojedynczą opinię na podstawie słownika selektorów.
