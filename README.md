# Rekonesans systemu SMB oraz eksploitacja z wykorzystaniem podatności typu Log Poisoning

[Przygotowanie środowiska do pracy](https://github.com/tkozl/BAWiM_proj/blob/main/Przygotowanie%20%C5%9Brodowiska.md)

## Zad. 1
Sprawdź adres IP maszyny wirtualnej, zbadaj otwarte porty oraz usługi jakie na niej działają.


<details>
  <summary>Podpowiedź 1.</summary>
    Użyj narzędzia nmap.
</details>

<!-- Użyj narzędzia nmap aby ustalić adres IP urządzenia do którego chcesz się włamać. -->



## Zad. 2
Wykorzystaj protokół SMB aby znaleźć dostępne na serwerze pliki. Przeanalizuj je i wyciągnij wnioski konieczne do włamania się do systemu. Ktoś postąpił bardzo nieodpowiedzialnie zostawiając cenne, niezabezpieczone informacje na dysku. Użyj ich aby zalogować się na konto jednego z użytkowników, nazwę którego odkryłeś podczas wykonywania polecenia `smbmap`.
Twoim celem w tym zadaniu jest znalezienie nazwy katalogu do którego możesz dostać się przez przeglądarkę.

> Przydatne narzędzia:  
> smbmap, smbclient

<details>
  <summary>Podpowiedź 1.</summary>
   Podobnie jak w przypadku FTP administratorzy często zapomninają (lub też nie chcą) ustawić hasło dla udziału anonynmous.
</details>

## Zad. 3
Jak zapewne zauważyłeś, strona internetowa do której się dostałeś została napisana w oparciu o WordPress. Przeskanuj ją używając narzędzia `wpscan`. Kto wie, może znajdziesz jakąś podatność w zainstalowanym pluginie?
> Podatności możesz szukać podpinając --api-token do wpscan, ręcznie przeszukując np. https://www.exploit-db.com/ lub używając polecenia `searchsploit`

<details>
  <summary>Podpowiedź 1.</summary>
   Konieczne może się okazać wykorzystanie przełącznika -e ap oraz --plugins-detection _aggressive_.
</details>

## Zad. 4
Odnajdź plik opisany w odnalezionej w poprzednim punkcie podatności. Następnie wykorzystaj ją, aby otworzyć plik z logami.

<details>
  <summary>Podpowiedź 1.</summary>
   Odnaleziony plugin przechowywuje logi w pliku /var/mail/"nazwa uzytkownika".
</details>
  
<details>
  <summary>Podpowiedź 2.</summary>
   Zwróć uwagę że wpisując link /h3l105/wp-content/plugins/mail-masta/inc/campaign/count_of_send.php?pl=/etc/passwd w odpowiedzi otrzymasz zawartość pliku passwd.
</details>

Wykorzystaj podatność [SMTP Log Poisoning](https://liberty-shell.com/sec/2018/05/19/poisoning/#log-poisoning-via-mail). W tym celu wstrzyknij do logów odpowiedni kod PHP, który pozwoli Ci wykonać dowolny inny kod w zapytaniu GET.

## Zad. 5
Jeśli wstrzyknąłeś już złośliwy kod, nic nie stoi na przeszkodzie aby uzyskać dostęp do terminala Linux w atakowanym serwerze. Przydatne może się okazać polecenie nc. Sprawdź dobrze zawartość serwera, być może znajdziesz tam flagę ;))

<details>
  <summary>Podpowiedź 1.</summary>
   To czego szukasz określa się frazą 'reverse shell'. DOKONCZYC
</details>

## Dla chętnych
Uzyskaj uprawnienia roota.
