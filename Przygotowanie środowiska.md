# Przygotowanie środowiska do pracy

Zalecamy wykonać to laboratorium na systemie Kali Linux. Konieczna będzie również maszyna wirtualna VirtualBox z serwerem. Celem laboratorium jest włamanie się do niniejszego serwera.

Link do maszyny wirtualnej: https://download.vulnhub.com/symfonos/symfonos1.7z

Instalacja VirtualBoxa na Kalim:
```
sudo apt-get install virtualbox
```

## 1. Importowanie
1.1. Uruchom aplikację VirtualBox

1.2. Plik > Importuj urządzenie wirtualne

1.3. Wybierarz plik symfonos.ovf w celu zaimportowania maszyny

1.4. Nie zmieniaj ustawień, kliknij Importuj

## 2. Konfiguracja maszyny

2.1. Prawy klawisz myszy na maszynę vm > Ustawienia

![](img/maszyna.png)

2.2. Wejdź w sieć i ustaw jak poniżej (host-only)

![](img/siec.png)

2.3. Plik > Host Network Manager

![](img/hnm.png)

2.4. Ustawiamy adresacje, np. jak poniżej (karta oraz serwer DHCP)

![](img/karta.png)

![](img/dhcp.png)

W tej chwili 192.168.2.2 jest adresem adaptera wirtualnego po stronie hosta a 192.168.2.1 zostaje przypisany jako serwer DHCP VirtualBox’a. w VirtualBox Host-Only Ethernet Adapter będzie używana sieć 192.168.2.0/24.

# Gotowe! Zapraszamy do wykonania [laboratorium](https://github.com/tkozl/BAWiM_proj#readme) :)
