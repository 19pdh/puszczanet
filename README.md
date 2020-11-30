![](puszczanet.png)

# puszczanet

puszczanet to bez-kontaktowy sposób komunikacji 19PDH.

Szczegółowy opis jest w [spec.md](spec.md), a poniżej jest skrócona wersja.

## Skrytki

Tak jak standardowa poczta ma skrzynki na listy, tak puszczanet ma skrytki. Każdy sam tworzy swoją skrytkę, która może mieć dowolną postać. Ważne żeby w środku zmieściła się wiadomość (zazwyczaj zwykła koperta). Skrytka musi być oznaczona symbolem [puszczanet'u](puszczanet.png).

## Adres

Aby wysłać do kogoś wiadomość trzeba znać adres jego skrytki. Adres to współrzędne geograficzne skrytki. Dla ułatwienia współrzędne powinny być przedstawione w postaci kodu QR.

Można wygenerować samemu kod QR przez skopiowanie współrzędnych z google maps itd.

Albo można użyć https://19pdh.github.io/puszczanet-addr i wskazać tam położenie skrytki.

## Wysyłanie wiadomości

Na wiadomości trzeba nakleić adres. Obok adresu należy wpisać swój pseudonim, imię lub nick (coś do rozpoznania nadawcy). Po tym można albo

- zanieść bezpośrednio do odbiorcy, albo...
- zanieść do innej osoby z drużyny - wtedy ta osoba wpisuje się obok nadawcy i przekazać wiadomość dalej. Ważne jest to że wiadomość nie może drugi raz trafić do tej samej osoby / skrytki (dlatego każda osoba pośrednia musi wpisać się na kopercie wiadomości).

## Przesyłanie plików

Pomysł na puszczanet bazuje na siecie komputerowej typu [sneakernet](https://pl.wikipedia.org/wiki/Sneakernet), więc w teorii można włożyć do koperty pendrive'a i tak przesyłać pliki. Należy jednak pamiętać, że w ten sposób łatwiej przemieszczają się wirusy komputerowe, więc nie podłączaj pendrivów od niezaufanych osób i **koniecznie** miej zainstalowanego antywirusa.
