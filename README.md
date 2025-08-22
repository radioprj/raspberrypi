Eksperymentalny obraz hotspota FM  Raspberry PI

**To jest projekt hobbystyczny i rozwija się w autora własnym tempie**

**Obraz przygotowany na bazie Raspberry PI v4**  Obraz na bazie 32 bitowej wersji Raspbian Debian 12 Bookworm powinien działać na wszystkich modelach RPI włącznie z RPI v5

Uwaga użytkownicy Pi 5. Aby serial port na GPIO 14 i 15 (ttyAMA0) był dostępny do programowania SA818 dla tej wersji PI należy 

**plik config.txt znajdujący się w /boot//firmware musi zostać zmodyfikowany poprzez usunięcie dtoverlay=disable-bt
i dodanie dtparam=uart0  (na końcu pliku)**

_Informacja o definicji ttyAMA0 dla PI 5 pochodzi z dokumentacji SHARI_

Obraz o nazwie [hotspotfm-rpi.img.xz](https://github.com/radioprj/raspberrypi/releases/download/v1.0/hotspotfm-rpi.img.xz) nagrać na kartę microSD przy pomocy: https://etcher.balena.io/

Jeśli masz problem zapisać skompresowany obraz .xz na kartę microSD możesz go dekompresować darmowym narzędziem [7-zip](http://www.e7z.org/free-download.htm) Rozpakowany obraz możesz też zapisać na kartę microSD programem [Win32Image](https://sourceforge.net/projects/win32diskimager/files/Archive/)

Login do konsoli via ssh:

user: pi

hasło: fmpoland

Zalecana zmiana hasła poleceniem: passwd

Przejście na użytkownika root poleceniem:

sudo -s

Dostęp do dashboard:

http://hotspotfm.local/

lub

http://ip_adres

IP adres możesz znaleźć przy pomocy darmowego narzędzia: https://www.advanced-ip-scanner.com/pl/

**UWAGA:** wgranie pliku wpa_supplicant.conf do konfiguracji sieci WIFI do katalog /boot może spowodować wyłączenie usługi Networ Manager. 

Konfiguracja via Dashboard, należy wybrać z menu "Admin" i następnie:

W pierwszej kolejności sprawdź poprawne ustawienia obsługi SQL i PTT w menu

**SQL PTT**

Po sprawdzeniu / ustawieniu SQL / PTT dopiero wtedy możesz przejść do konfiguracji:

**SVXCnf** - konfiguracja konta 

**NodeInfo** - Informacje o stacji

**WEBCnf** - konfiguracja Dashboard

oraz inne opcje stosownie do potrzeb

**CZYTAJ** uważnie informacje umieszczone w każdym oknie z serii administracyjnych
w których są istotne informacje do dostępnych ustawień

![AdminMenu](https://github.com/radioprj/raspberrypi/blob/main/admin-menu.png)

Obraz ten można używać z produktami SHARI i SHARI PiHat https://kits4hams.com/shari lub HotSpotRadio https://hotspotradios.com/purchase-parts lub USB-RMI https://www.repeater-builder.com/products/usb-rim-lite.html
Można używać z kartą dźwiękową CM108 modyfikowana lub bez modyfikacji z dowolnym radiem patrz [Budowa hotspota](https://fm-poland.pl/budowa-hotspota/)

Jeśli dashboard będzie dostępny z zewnątrz ( **nierekomendowane z powodów bezpieczeństwa** - należy przemyśleć to czy jest to ci niezbędne czy jest to ci niezbędne) to aby dostać się do menu ADMIN należy w Admin -> WebCnf w opcji REMOTEIP zamiast adresu 127.0.0.1 wpisać zdalny zaufany IP adres (ZALECANE: można skorzystać z VPN [Tailscale](https://tailscale.com/) wersja personal zawiera darmową obsługę 3 userów/100 urządzeń). Można też dostać z publicznego adresu do strony dashboard po linkiem

http://ipadresdashboard/svxc/

po podaniu użytkownika i hasła gdzie można wyłączyć lub włączyć zdalnie odbiornik SVXLINK. Jak założyć użytkownika i dla niego hasło patrz opis na swoim hotspot w pliku /etc/svxlink/SVXControl.txt

![AdminMenu](https://github.com/radioprj/raspberrypi/blob/main/hotspot-login.png)


![AdminMenu](https://github.com/radioprj/raspberrypi/blob/main/displays-svx.png)

Możesz podłączyć wyświetlacze  OLED SSD1306, SH1106 patrze w katalog /opt/fmpoland/oledsvx/

w katalogach tych jest plik opis.txt z informacjami jak podłączyć i uruchomić wyświetlacz

Możesz skorzystać z Remote Display zamiast podłączać bezpośrednio do hotspota:

https://github.com/radioprj/remoteoled

https://github.com/radioprj/remotelcd

Instalacja pakietów i konfiguracja wyświetlaczy poprzez użytkownika root. Przejście na użytkownika root poleceniem:

**sudo -s**


**Ustawienia programu WinSCP, aby przenosić pliki do hotspota w katalogi systemowe:** https://www.luisllamas.es/en/winscp-transfer-files-between-windows-and-raspberry-pi/


**Eksperymentalny obraz używasz na własną odpowiedzialność i autor nie ponosi odpowiedzialności za wykorzystane rozwiązanie i wynikające z niego skutki.**
