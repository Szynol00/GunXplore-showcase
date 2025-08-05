# Portal społecznościowy dla pasjonatów militariów z modułem edukacyjnym o budowie broni

[English version (Wersja angielska)](README.md)

> **Note:** **To repozytorium zawiera wyłącznie materiały demonstracyjne projektu "GunXplore" - zrzuty ekranu, filmy i opisy funkcjonalności. Kod źródłowy nie jest dostępny, gdyż aplikacja powstała w ramach pracy inżynierskiej.**

## Spis treści

1. [Opis projektu](#opis-projektu)
2. [Technologie](#technologie)
3. [Przegląd platformy](#przegląd-platformy)
4. [Doświadczenie użytkownika krok po kroku](#doświadczenie-użytkownika-krok-po-kroku)
5. [Funkcje społecznościowe](#funkcje-społecznościowe)
6. [Moduł edukacyjny o budowie broni](#moduł-edukacyjny-o-budowie-broni)
7. [Funkcje dla poszczególnych ról użytkowników](#funkcje-dla-poszczególnych-ról-użytkowników)
8. [Responsywność i motywy](#responsywność-i-motywy)
9. [Materiały wizualne](#materiały-wizualne)
10. [Informacje kontaktowe](#informacje-kontaktowe)

## Opis projektu

Celem projektu było stworzenie aplikacji internetowej typu REST API, łączącej funkcje społecznościowe z interaktywnym modułem edukacyjnym z modelami 3D dla pasjonatów militariów. Backend oparto na Laravel 11 z autoryzacją przez Laravel Sanctum, a frontend zbudowano w React z TypeScript, wykorzystując React Three Fiber do renderowania modeli 3D oraz Tailwind CSS i DaisyUI do stylizacji.

Aplikacja składa się z dwóch kluczowych modułów:
- **Moduł edukacyjny** umożliwia interakcję z realistycznymi modelami 3D broni, które można oglądać, animować i eksplorować, klikając poszczególne części, by zobaczyć ich funkcję i opis. System zawiera także szczegółowe dane techniczne, historię broni oraz schematy konserwacji.
- **Moduł społecznościowy** wykorzystuje mechanizmy Laravel Gates i Policies do zarządzania uprawnieniami użytkowników. Oferuje rejestrację, logowanie, polubienia, komentowanie, obserwowanie oraz powiadomienia o interakcjach. Aplikacja zapewnia również funkcjonalność prywatnego chatu między użytkownikami.

Podczas realizacji projektu autor zmierzył się z wyzwaniami związanymi z optymalizacją modeli 3D pod kątem wydajności przeglądarki, synchronizacją interakcji użytkowników oraz integracją systemu powiadomień i chatu. Projekt wpisuje się w rosnące zainteresowanie tematyką militariów, oferując nowoczesne narzędzie edukacyjne zintegrowane z funkcjami społecznościowymi.

## Technologie

### Backend
- 🖥️ **Język**: PHP 8.2.4
- 🛠️ **Framework**: Laravel 11
- 🔒 **Uwierzytelnianie**: Laravel Sanctum
- 💾 **Baza danych**: MySQL/MariaDB 10.4.28
- 🔑 **Autoryzacja**: Laravel Gates & Policies

### Frontend
- ⚛️ **Framework**: React z TypeScript
- 🎮 **Renderowanie 3D**: React Three Fiber
- 🎨 **Stylizacja**: Tailwind CSS, DaisyUI oraz FlowBite

### Modelowanie 3D
- 🧊 **Modelowanie**: Blender
- 🖌️ **Tekstury**: Niestandardowe mapy Diffuse, Normal i Roughness
- 📦 **Export**: Format GLB

## Przegląd platformy

### Strona główna dla różnych typów użytkowników

<p align="center">
  <img src="assets/images/home-logged-out.png" width="48%" alt="Strona główna dla niezalogowanych">
  <img src="assets/images/home-logged-in.png" width="48%" alt="Strona główna dla zalogowanych">
  <br>
  <em>Strona główna: widok dla użytkownika niezalogowanego (po lewej) i zalogowanego (po prawej)</em>
</p>

Niezalogowany użytkownik ma ograniczony dostęp do funkcjonalności systemu, obejmujący jedynie przeglądanie publicznych modeli 3D oraz 30 najpopularniejszych postów tygodnia, podczas gdy zalogowany użytkownik ma pełny dostęp do wszystkich funkcji społecznościowych i edukacyjnych platformy.

### Główne moduły platformy

<p align="center">
  <img src="assets/images/posts-logged-out.png" width="48%" alt="Posty dla niezalogowanego">
  <img src="assets/images/posts-logged-in.png" width="48%" alt="Posty dla zalogowanego">
  <br>
  <em>Widok postów dla użytkownika niezalogowanego (po lewej) i zalogowanego (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/guns-logged-out.png" width="48%" alt="Modele dla niezalogowanego">
  <img src="assets/images/guns-logged-in.png" width="48%" alt="Modele dla zalogowanego">
  <br>
  <em>Widok modeli 3D dla użytkownika niezalogowanego (po lewej) i zalogowanego (po prawej)</em>
</p>

Platforma składa się z dwóch głównych modułów:
- **Moduł społecznościowy** - umożliwia publikowanie postów, komentowanie, likowanie i interakcję z innymi użytkownikami. Dla niezalogowanych użytkowników dostępne jest tylko 30 najpopularniejszych postów tygodnia, podczas gdy zalogowani mają pełny dostęp do wszystkich treści z możliwością filtrowania.
- **Moduł edukacyjny** - udostępnia interaktywne modele 3D broni z szczegółowymi opisami, animacjami i danymi technicznymi. Niezalogowani użytkownicy widzą tylko publiczne modele, a zalogowani mają dostęp do wszystkich modeli poza roboczymi.

## Doświadczenie użytkownika krok po kroku

### 1. Rejestracja i logowanie

<p align="center">
  <img src="assets/images/registration-form.png" width="48%" alt="Rejestracja">
  <img src="assets/images/login-form.png" width="48%" alt="Logowanie">
  <br>
  <em>Proces rejestracji (po lewej) i logowania (po prawej)</em>
</p>

Niezalogowany użytkownik może rozszerzyć dostępne funkcje poprzez zalogowanie się do istniejącego konta lub utworzenie nowego konta. System przeprowadza użytkownika przez intuicyjny proces rejestracji wymagający podania podstawowych danych osobowych oraz spełniającego wymogi bezpieczeństwa hasła.

### 2. Weryfikacja email

<p align="center">
  <img src="assets/images/email-verification.png" width="48%" alt="Status weryfikacji email w profilu">
  <img src="assets/images/email-verification-message.png" width="48%" alt="Wiadomość email z linkiem weryfikacyjnym">
  <br>
  <em>Weryfikacji email (po lewej) i rzeczywista wiadomość email z linkiem weryfikacyjnym (po prawej)</em>
</p>

Po rejestracji użytkownik może zweryfikować swój adres e-mail poprzez kliknięcie w link aktywacyjny przesłany na podany adres. W profilu użytkownika wyświetlana jest informacja o statusie weryfikacji, a system wysyła rzeczywistą wiadomość email zawierającą spersonalizowany link weryfikacyjny.

### 3. Resetowanie hasła

<p align="center">
  <img src="assets/images/password-reset-form.png" width="48%" alt="Formularz resetowania hasła">
  <img src="assets/images/password-reset-email.png" width="48%" alt="Email z tokenem do resetowania hasła">
  <br>
  <em>Formularz resetowania hasła (po lewej) i wiadomość email z tokenem zabezpieczającym (po prawej)</em>
</p>

System resetowania hasła umożliwia odzyskanie dostępu do konta przez kliknięcie przycisku "Zapomniałeś hasła?" w formularzu logowania. Po podaniu adresu email, system wysyła wiadomość zawierającą unikalny token zabezpieczający oraz link przekierowujący do formularza zmiany hasła. Po wprowadzeniu nowego hasła, konto jest aktualizowane, a użytkownik może się zalogować.

### 4. Personalizacja profilu

<p align="center">
  <img src="assets/images/profile-view-full.png" width="48%" alt="Widok profilu">
  <img src="assets/images/profile-edit.png" width="48%" alt="Edycja profilu">
  <br>
  <em>Widok profilu użytkownika (po lewej) i edycja profilu (po prawej)</em>
</p>

Profil użytkownika prezentuje zdjęcie profilowe, zdjęcie w tle, dane osobowe, listę postów i status weryfikacji email. Dostępny po kliknięciu zdjęcia profilowego w menu nawigacyjnym, umożliwia edycję danych, zarządzanie zdjęciami oraz korzystanie z funkcji społecznościowych.

## Funkcje społecznościowe

### Tworzenie i przeglądanie postów

<p align="center">
  <img src="assets/images/post-creation.png" width="48%" alt="Tworzenie posta">
  <img src="assets/images/posts-logged-in.png" width="48%" alt="Lista postów">
  <br>
  <em>Formularz tworzenia posta (po lewej) i przeglądanie listy postów (po prawej)</em>
</p>

System posiada funkcję wyświetlania postów z możliwością filtrowania według kategorii tematycznych. Platforma oferuje intuicyjny formularz dodawania postów, wyposażony w edytor tekstu z rozszerzonymi możliwościami formatowania.


https://github.com/user-attachments/assets/48ed74f4-8fee-49a4-8d84-c03485940e00


### Zarządzanie własnymi postami

<p align="center">
  <img src="assets/images/post-menu.png" width="30%" alt="Menu zarządzania postem">
  <img src="assets/images/post-edit-form.png" width="30%" alt="Formularz edycji posta">
  <img src="assets/images/post-edited.png" width="30%" alt="Post po edycji">
  <br>
  <em>Menu zarządzania własnym postem (po lewej), formularz edycji (środek) i post z informacją o edycji (po prawej)</em>
</p>

Autor posta ma dostęp do menu kontekstowego po kliknięciu ikony trzech kropek, które umożliwia edycję lub usunięcie treści. Formularz edycji wykorzystuje ten sam interfejs co przy tworzeniu postów, automatycznie wypełniony dotychczasowymi danymi. Po edycji system automatycznie oznacza post stosowną informacją o czasie modyfikacji i osobie edytującej.

### Zgłaszanie treści

<p align="center">
  <img src="assets/images/report-menu.png" width="48%" alt="Menu zgłaszania postu">
  <img src="assets/images/report-form.png" width="48%" alt="Formularz zgłoszenia">
  <br>
  <em>Menu zgłaszania cudzego postu (po lewej) i formularz zgłoszenia treści (po prawej)</em>
</p>

Użytkownicy mogą zgłaszać nieodpowiednie treści poprzez kliknięcie ikony trzech kropek przy postach innych użytkowników. System wyświetla wtedy formularz zgłoszenia z możliwością wyboru powodu oraz dodania dodatkowego opisu.

### System komentarzy (posty i modele broni)

<p align="center">
  <img src="assets/images/comment-creation.png" width="48%" alt="Tworzenie komentarza">
  <img src="assets/images/comment-reply.png" width="48%" alt="Odpowiadanie na komentarz">
  <br>
  <em>Tworzenie komentarza (po lewej) i odpowiadanie na komentarz (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/comment-edit.png" width="30%" alt="Edycja komentarza">
  <img src="assets/images/comment-edited.png" width="30%" alt="Komentarz po edycji">
  <img src="assets/images/comment-report.png" width="30%" alt="Zgłaszanie komentarza">
  <br>
  <em>Edycja komentarza (po lewej), komentarz po edycji (środek) i zgłaszanie komentarza (po prawej)</em>
</p>

System komentarzy jest uniwersalny i działa identycznie zarówno dla postów społecznościowych, jak i dla modeli broni w module edukacyjnym. Użytkownicy mogą komentować posty i modele 3D oraz odpowiadać na komentarze innych. Przy własnych komentarzach widoczne są przyciski edycji i usuwania, natomiast przy komentarzach innych użytkowników - przycisk zgłoszenia. System automatycznie oznacza edytowane komentarze odpowiednią informacją wraz z datą aktualizacji.

### Obserwowanie użytkowników i wyszukiwanie

<p align="center">
  <img src="assets/images/following-system.png" width="48%" alt="System obserwowania">
  <img src="assets/images/user-search.png" width="48%" alt="Wyszukiwanie użytkowników">
  <br>
  <em>System obserwowania użytkowników (po lewej) i wyszukiwarka użytkowników (po prawej)</em>
</p>

System obserwacji użytkowników działa intuicyjnie - po najechaniu kursorem na imię lub zdjęcie profilowe pojawia się podgląd profilu z przyciskiem obserwacji. Platforma oferuje również zaawansowany system wyszukiwania użytkowników, dostępny po kliknięciu przycisku "Wyszukaj osoby" w panelu bocznym.

### System powiadomień

<p align="center">
  <img src="assets/images/notifications-center.png" width="48%" alt="Centrum powiadomień">
  <img src="assets/images/notification-redirect.png" width="48%" alt="Przekierowanie z powiadomienia">
  <br>
  <em>Okno powiadomień (po lewej) i widok po kliknięciu w powiadomienie o polubionym komentarzu (po prawej)</em>
</p>

System powiadomień informuje użytkowników o nowych obserwujących, polubieniach i komentarzach. Kliknięcie w powiadomienie przekierowuje użytkownika do odpowiedniej treści z wyraźnym podświetleniem elementu.

### System komunikacji

<p align="center">
  <img src="assets/images/chat-dropdown.png" width="48%" alt="Menu czatu">
  <img src="assets/images/chat-modal.png" width="48%" alt="Okno konwersacji">
  <br>
  <em>Menu czatu w nawigacji (po lewej) i okno konwersacji (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/chat-fullscreen.png"  width="48%" alt="Czat pełnoekranowy">
  <img src="assets/images/new-conversation.png"  width="48%" alt="Tworzenie nowej konwersacji">
  <br>
  <em>Pełnoekranowy widok wiadomości (po lewej) i interfejs tworzenia nowej konwersacji (po prawej) </em>
</p>

System czatu dostępny jest z dwóch poziomów interfejsu: rozwijane menu w pasku nawigacyjnym oraz pełnoekranowa strona wiadomości. Oba interfejsy implementują dynamiczne doładowywanie starszych wiadomości podczas przewijania w górę. Tworzenie nowych konwersacji odbywa się przez dedykowany widok, umożliwiający wyszukiwanie i filtrowanie użytkowników.

## Moduł edukacyjny o budowie broni

### Szczegóły modelu i podstawowe informacje

<p align="center">
  <img src="assets/images/gun-overview.png" width="48%" alt="Przegląd broni">
  <img src="assets/images/gun-contents-history.png" width="48%" alt="Spis treści i historia">
  <br>
  <em>Krótki opis broni ze spisem treści (po lewej) i szczegółowa historia z rozszerzonym opisem (po prawej)</em>
</p>

### Dane techniczne i konserwacja

<p align="center">
  <img src="assets/images/gun-technical-data.png" width="48%" alt="Dane techniczne">
  <img src="assets/images/gun-maintenance-scheme.png" width="48%" alt="Schemat konserwacji">
  <br>
  <em>Dane techniczne broni (po lewej) i schemat konserwacji (po prawej)</em>
</p>

### Elementy broni

<p align="center">
  <img src="assets/images/gun-parts-collection.png" width="100%" alt="Kolekcje części broni">
  <br>
  <em>Interaktywny system części broni z podziałem na kolekcje</em>
</p>

### Rendery i model 3D

<p align="center">
  <img src="assets/images/gun-renders.png" width="48%" alt="Rendery broni">
  <img src="assets/images/gun-3d-model-viewer.png" width="48%" alt="Podgląd modelu 3D">
  <br>
  <em>Rendery broni (po lewej) i Modeli 3D broni (po prawej)</em>
</p>

### Model 3D (broń złożona) i kliknięcie w część

<p align="center">
  <img src="assets/images/gun-3d-model-part-click.png" alt="Kliknięcie w element">
  <br>
  <em>Kliknięcie w wybrany element broni</em>
</p>

### Model 3D - animacja rozkładania i lista części

<p align="center">
  <img src="assets/images/gun-3d-model-animation.png" width="48%" alt="Animacja rozkładania">
  <img src="assets/images/gun-3d-model-disassembled.png" width="48%" alt="Broń rozłożona z listą części">
  <br>
  <em>Animacja rozkładania broni (po lewej) i broń rozłożona z wyborem części z listy (po prawej)</em>
</p>

### Źródła i komentarze

<p align="center">
  <img src="assets/images/gun-sources-comments-start.png" width="48%" alt="Źródła i początek komentarzy">
  <img src="assets/images/gun-comments-continuation.png" width="48%" alt="Ciąg dalszy komentarzy">
  <br>
  <em>Sekcja źródeł z początkiem komentarzy (po lewej) i ciąg dalszy komentarzy (po prawej)</em>
</p>

---

Moduł edukacyjny łączy interaktywne modele 3D z kompleksowymi informacjami o broni, oferując użytkownikom możliwość eksploracji zarówno przez kliknięcia w części modelu, jak i animacje rozkładania. System umożliwia także wymianę wiedzy poprzez komentarze i dostęp do źródeł informacji.

https://github.com/user-attachments/assets/9d66ce95-e9b0-4da9-bb4d-040155e7d9db

https://github.com/user-attachments/assets/3b09ea7c-2338-4226-8669-79534a385dcd


## Funkcje dla poszczególnych ról użytkowników

### Grafik 3D
<p align="center">
  <img src="assets/images/3d-graphic-gun-list.png" width="48%" alt="Lista broni dla grafika">
  <img src="assets/images/3d-model-upload.png" width="48%" alt="Dodawanie modelu 3D">
  <br>
  <em>Lista broni z dodatkowymi opcjami zarządzania (po lewej) i dodawanie nowego modelu 3D (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/gun-educational-sections-edit-buttons.png" width="48%" alt="Sekcje informacyjne z przyciskami edycji">
  <img src="assets/images/gun-information-edit-form.png" width="48%" alt="Formularz edycji informacji">
  <br>
  <em>Sekcje informacyjne z przyciskami edycji w prawym górnym rogu (po lewej) i formularz edycji informacji (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/gun-3d-model-edit-options.png" width="48%" alt="Model 3D z opcjami edycji">
  <img src="assets/images/gun-model-texture-replacement.png" width="48%" alt="Podmiana modelu 3D i tekstur">
  <br>
  <em>Model 3D z opcjami edycji (po lewej) i panel podmiany modelu 3D lub tekstur (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/gun-animation-management-1.png" width="48%" alt="Zarządzanie animacjami - ustawienie klatek">
  <img src="assets/images/gun-animation-management-2.png" width="48%" alt="Zarządzanie animacjami - podświetlenia części">
  <br>
  <em>Ustawienie klatek początkowych i końcowych dla rozłożenia/złożenia broni (po lewej) i konfiguracja podświetleń części z opisami w określonych klatkach (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/gun-renders-management.png" width="48%" alt="Zarządzanie renderami">
  <br>
  <em>Panel zarządzania renderami modeli 3D</em>
</p>

Grafik 3D ma pełny dostęp do zarządzania wszystkimi aspektami modeli 3D. W każdej sekcji informacyjnej (historia, dane techniczne, konserwacja) znajdują się przyciski edycji w prawym górnym rogu, umożliwiające szybką modyfikację treści poprzez dedykowany formularz. System oferuje również zaawansowane opcje edycji samego modelu 3D, w tym możliwość podmiany pliku GLB oraz tekstur (Diffuse, Normal, Roughness).

Zarządzanie animacjami składa się z dwóch etapów: pierwszy pozwala na ustawienie klatek początkowych i końcowych dla animacji rozłożenia oraz złożenia broni, a drugi umożliwia precyzyjną konfigurację tego, które części mają się podświetlić w określonych klatkach animacji wraz z przypisanymi do nich opisami wyskakującymi podczas odtwarzania. Panel zarządzania renderami umożliwia dodawanie, edycję i organizację wszystkich obrazów prezentacyjnych związanych z modelami 3D.

### Moderator

<p align="center">
  <img src="assets/images/moderator-menu.png" width="48%" alt="Menu moderatora">
  <img src="assets/images/moderator-edit.png" width="48%" alt="Edycja przez moderatora">
  <br>
  <em>Menu moderatora dla zarządzania treściami (po lewej) i edycja treści z oznaczeniem moderatora (po prawej)</em>
</p>
<p align="center">
  <img src="assets/images/moderator-reports-panel.png" width="48%" alt="Panel zgłoszeń">
  <img src="assets/images/moderator-user-management.png" width="48%" alt="Zarządzanie użytkownikami">
  <br>
  <em>Panel zgłoszeń (po lewej) i panel zarządzania użytkownikami (po prawej)</em>
</p>
<p align="center">
  <img src="assets/images/moderator-report-solution.png" width="48%" alt="Rozwiązywanie zgłoszenia przez moderatora">
  <img src="assets/images/moderator-ban-form.png" width="48%" alt="Formularz banowania użytkownika">
  <br>
  <em>Panel rozwiązywania zgłoszenia z gotowymi szablonami (po lewej) i formularz banowania użytkownika (po prawej)</em>
</p>

Moderator ma możliwość edycji treści komentarzy i postów wszystkich użytkowników oraz dostęp do dedykowanego panelu do zarządzania zgłoszeniami i użytkownikami z opcjami wyszukiwania, filtrowania i banowania. System rozwiązywania zgłoszeń umożliwia bezpośrednią edycję zgłoszonych treści i opisanie podjętych działań przy użyciu gotowych szablonów. Moderator może również usuwać nieodpowiednie zdjęcia profilowe, tła i opisy użytkowników (częściowa modyfikacja profili).

### Administrator

<p align="center">
  <img src="assets/images/admin-dashboard.png" width="48%" alt="Dashboard administratora">
  <img src="assets/images/admin-posts-category.png" width="48%" alt="Zarządzanie kategoriami">
  <br>
  <em>Dashboard z statystykami systemu (po lewej) i panel zarządzania kategoriami postów (po prawej)</em>
</p>

<p align="center">
  <img src="assets/images/admin-user-management.png" width="68%" alt="Zarządzanie użytkownikami">
  <img src="assets/images/add-user.png" width="30%" alt="Dodawanie użytkownika">
  <br>
  <em>Panel zarządzania użytkownikami (po lewej) i formularz dodawania nowego użytkownika (po prawej)</em>
</p>

Administrator ma dostęp do wszystkich funkcjonalności platformy oraz dedykowanego panelu zarządzania. Dashboard prezentuje kompleksowe statystyki systemu. W zakładce "Kategorie" administrator może zarządzać kategoriami postów. W zakładce "Użytkownicy" zarządza kontami użytkowników systemu, ma możliwość edytowania danych, usuwania kont oraz dodawania nowych kont z przypisaniem odpowiedniej roli.

## Responsywność i motywy

### Jasny motyw interfejsu

<p align="center">
  <img src="assets/images/posts-light-theme.png" width="48%" alt="Posty w jasnym motywie">
  <img src="assets/images/gun-3d-model-light-theme.png" width="48%" alt="Podstrona edukacyjna w jasnym motywie">
  <br>
  <em>Widok postów w jasnym motywie (po lewej) i podstrona edukacyjna modelu 3D w jasnym motywie (po prawej)</em>
</p>

### Widok mobilny

<p align="center">
  <img src="assets/images/posts-mobile.png" width="30%" alt="Posty na urządzeniu mobilnym">
  <img src="assets/images/gun-3d-model-mobile.png" width="30%" alt="Podstrona edukacyjna na urządzeniu mobilnym">
  <img src="assets/images/moderator-user-management-mobile.png" width="30%" alt="Panel moderatora na urządzeniu mobilnym">
  <br>
  <em>Widok postów na mobile (po lewej), podstrona edukacyjna na mobile (środek) i panel zarządzania użytkownikami dla moderatora na mobile (po prawej)</em>
</p>

Aplikacja oferuje pełną responsywność oraz obsługę jasnego motywu interfejsu, zapewniając optymalne doświadczenie użytkownika niezależnie od używanego urządzenia czy preferencji wizualnych.

## Materiały wizualne

We wszystkich prezentowanych widokach aplikacji wykorzystano tło ze wzorem kamuflażu z Vecteezy[1], a zdjęcia i filmy występujące w portalu pochodzą z Adobe Stock[2] oraz Pexels[3] na bazie darmowej licencji.

**Źródła:**
- [1] Vecteezy.com – https://www.vecteezy.com/photo/51259018-green-stylish-camouflage-military-pattern
- [2] Adobe Stock – https://stock.adobe.com/
- [3] Pexels – https://www.pexels.com/

## Informacje kontaktowe

Aby uzyskać więcej informacji o tym projekcie, proszę o kontakt:
- Email: [calka.szymek@gmail.com]
  
---

*Uwaga: Ten projekt został stworzony jako praca inżynierska, dlatego kod źródłowy nie jest udostępniany publicznie. Projekt jest prezentowany jako element portfolio i nie jest dostępny do publicznego użytku ani dystrybucji. Wszystkie materiały wizualne i demonstracje są udostępniane wyłącznie w celu zaprezentowania umiejętności i możliwości programisty.*
