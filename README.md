# Komunikator internetowy


# Opis Wymagań

Celem aplikacji jest stworzenie komunikatora na bazie serwera zapewniającego:

 - Tablicę serwera, na której członkowie serwera będą mogli  udostępniać posty i je komentować (zdjęcia/pliki)
 - Czaty grupowe
 - Czaty prywatne (między userami)
 
 >Szkice interfejsu:
 > - ![Tablica](https://github.com/Thyvenin/Specyfikacja/blob/main/PanelTablica.png =x300)
 > - ![Czaty grupowe](https://github.com/Thyvenin/Specyfikacja/blob/main/PanelGrupowy.png)
 > - ![Czaty prywatne ](https://github.com/Thyvenin/Specyfikacja/blob/main/PanelDM.png)

Poza użytkownikami, znajdują się moderatorzy  mający wgląd do tablicy/czatów systemu mogący:
- Usuwać:
	- pliki/zdjęcia z tablicy
	- wiadomości z czatów grupowych
	- użytkowników
	
# Opis architektury

Projekt jest oparty  na architekturze klient-server zaimplementowany w WCF 
Serwer korzysta z bazy danych MS SQL
Klient będzie stworzony za pomocą WPF (alternatywnie implementacja web) 
  
Mechanizm działania:
Klient wymaga połączenia z danym serwerem, po połączeniu wymagane są dane logowania (z uprzedniej rejestracji)
Po zalogowaniu klient ma dostęp do wszystkich usług danego serwera.
Dane usługi (posty na tablicy, wiadomości w czatach grupowych, wiadomości prywatne) będą przechowywane w bazie danych serwera i odpowiednio przesyłane do klienta.
Klient w celu wykonania jakiejkolwiek operacji (wysyłanie wiadomości, dodanie userów do czatu, wysłanie pliku) będzie wysyłał zapytania do serwera.
Klient będzie regularnie synchronizował wyświetlane dane z serwera.
Serwer może mieć moderatora który posiada zestaw funkcji pozwalający na usuwanie treści.

 > - ![Czaty prywatne ](https://github.com/Thyvenin/Specyfikacja/blob/main/Diagram.png)




