![](puszczanet.png)

# puszczanet

![v0.1a](https://img.shields.io/badge/puszczanet-v0.1a-green)

puszczanet to rozproszona sieć typu [sneakernet](https://pl.wikipedia.org/wiki/Sneakernet) stworzona w celu stworzenia prywatnego, bez-kontaktowego sposobu komunikacji i wymiany zasobów cyfrowych w 19 PDH Puszcza.

## Adresacja

Cel wiadomości wyznaczają współrzędne geograficzne przedstawione w formacie kodu QR. Współrzędne wskazują na kryjówkę, skrzynkę do której ma zostać dostarczona wiadomość. Skrytka musi mieć na sobie symbol puszczanet-u.

### Format

Współrzędne geograficzne powinny być zapisane w standardzie EPSG:4326 (WGS84) i oddzielone przecinkiem. Przykład:

  52.42571469318589, 16.89852874238232

Przykłady kodowania:

```sh
export LAT=52.406376 LON=16.925167
echo "($LAN, $LON)" | qrencode -o qr.png
```

## Wysyłanie wiadomości

Aby wysłać wiadomość trzeba zakodować współrzędne skrytki docelowej aby miała formę [adresu](#adresacja). Następnie należy przymocować kod qr do nośnika danych (uniwersalnym sposobem jest włożenie nośnika do koperty i naklejenie/nadrukowanie adresu na kopercie).

Przygotowaną wiadomość należy zanieść do znanej skrytki innego harcerza użytkującego z sieci.

## Skrytki

Skrytki muszą być oznaczone znakiem puszczanet-u.

## Wyznaczanie drogi (routing)

Wiadomość zanim trafi do punktu docelowego, może przejść przez kilka adresów pośrednich. Droga wiadomości jest zapisywana na kopercie/wiadomości, aby znać poszczególne punkty, które już odwiedziła wiadomość. Droga musi być znana, ponieważ wiadomość nie może trafić 2 razy do tej samej skrytki.

Droga wiadomości jest wyznaczana przez algorytm "chęci":

1. Harcerz sprawdza swoją prywatnę skrytkę.
2. Jeśli w skrytce znajduje się wiadomść, należy odczytać lokalizacje.
3. Następnie sprawdzana jest droga wiadomości, czy jest prawidłowa.
4. Jeżeli droga jest prawidłowa, to harcerz może dostarczyć wiadomość do adresu docelowego, lub jeśli zna adres, który nie był jeszcze wymieniony w drodze wiadomości, to w zależności od **chęci** może dostraczyć wiadomość do kolejnego punktu pośredniego.
5. Do drogi wiadomości harcerz dopisuje siebie.

### Przerywanie transmisji

W przypadku jeżeli droga wiadomości nie jest prawidłowa, albo odbiorca wiadomości nie ufa pośrednikom wiadomości wymienionymi w drodze, wtedy można przerwać transmisję wiadomości. Należy odesłać wiadomość do skrzynki początkowej z odpowiednią wiadomością tłumaczącą powód przerwania.
