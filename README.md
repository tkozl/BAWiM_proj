# Rekonesans systemu SMB oraz eksploitacja z wykorzystaniem podatności typu Log Poisoning

## Zad. 1
Użyj narzędzia nmap aby ustalić adres IP urządzenia do którego chcesz się włamać.

## Zad. 2
Wykorzystaj protokół SMB aby znaleźć dostępne na serwerze pliki. Przeanalizuj je i wyciągnij wnioski konieczne do włamania się do systemu. Ktoś postąpił bardzo nieodpowiedzialnie zostawiając cenne, niezabezpieczone informacje na dysku. Użyj ich aby zalogować się na konto użytkownika helios.
Twoim celem w tym zadaniu jest znalezienie nazwy katalogu do którego możesz dostać się przez przeglądarkę.

Przydatne narzędzia:  
> nmap, smbmap, smbclient

## Zad. 3
Jak zapewne zauważyłeś, strona internetowa do której się dostałeś została napisana w oparciu o WordPress. Przeskanuj ją używając narzędzia wpscan. Kto wie, może znajdziesz jakąś podatność w zainstalowanym pluginie?
> Podatności możesz szukać podpinając --api-token do wpscan lub ręcznie przeszukując np. https://www.exploit-db.com/

## Zad. 4
Wykorzystaj podatność [SMTP Log Poisoning](https://liberty-shell.com/sec/2018/05/19/poisoning/). W tym celu wstrzyknij do logów odpowiedni kod PHP, który pozwoli Ci wykonać dowolny inny kod w zapytaniu GET.

Przykładowy kod:  
> echo system($_GET[„cmd”]);

## Zad. 5
Jeśli wstrzyknąłeś już złośliwy kod, nic nie stoi na przeszkodzie aby uzyskać dostęp do terminala Linux w atakowanym serwerze. Przydatne może się okazać polecenie nc.
