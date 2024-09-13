---
title: Określ stronę podczas przeglądania
linktitle: Określ stronę podczas przeglądania
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak określić stronę do wyświetlenia w pliku PDF za pomocą Aspose.PDF dla platformy .NET. Ulepsz nawigację użytkownika dzięki temu prostemu przewodnikowi.
type: docs
weight: 110
url: /pl/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Wstęp

Czy chcesz ulepszyć swoje aplikacje PDF, kierując użytkowników do konkretnych stron po otwarciu dokumentu? Jesteś we właściwym miejscu! W tym przewodniku zagłębimy się w szczegóły korzystania z Aspose.PDF dla .NET w celu określenia strony, która powinna zostać wyświetlona po otwarciu pliku PDF. Ta funkcjonalność może znacznie poprawić komfort użytkowania, zwłaszcza gdy trzeba zwrócić uwagę na krytyczne sekcje dokumentu.

## Wymagania wstępne

Zanim zagłębisz się w kodowanie, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć. Oto, czego będziesz potrzebować:

1. Podstawowa wiedza o .NET: Znajomość .NET Framework jest niezbędna. Jeśli dobrze znasz C# i masz podstawową wiedzę na temat programowania obiektowego, jesteś gotowy!

2.  Aspose.PDF dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.PDF w swoim projekcie. Jeśli jeszcze jej nie zainstalowałeś, możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Ten samouczek zakłada, że używasz Visual Studio jako swojego IDE. Upewnij się, że jest ono zainstalowane na Twoim komputerze.

4. Plik PDF: Będziesz potrzebować istniejącego pliku PDF, z którym będziesz pracować. Jeśli go nie masz, możesz utworzyć przykładowy dokument lub użyć dowolnego wybranego pliku PDF.

Gdy już spełnisz te wymagania wstępne, możemy zakasać rękawy i zacząć kodować!

## Importuj pakiety

Teraz, gdy wszystko jest już skonfigurowane, zaimportujmy niezbędne pakiety do naszego projektu. Wykonaj następujące kroki:

### Uruchom program Visual Studio

Otwórz program Visual Studio i utwórz nowy projekt lub załaduj istniejący, w którym chcesz zaimplementować funkcjonalność przeglądania stron PDF.

### Odniesienie Aspose.PDF

Aby użyć biblioteki Aspose.PDF, należy dodać do niej odwołanie:

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3.  Szukaj`Aspose.PDF` i zainstaluj pakiet.

### Importuj przestrzenie nazw

Dodaj następującą dyrektywę using na górze pliku kodu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Teraz możesz zacząć budować logikę nawigacji po stronach pliku PDF!

Podzielmy nasze zadanie na łatwe do opanowania kroki. Napiszemy kod, który otwiera dokument PDF, określa konkretną stronę, która ma zostać wyświetlona po wyświetleniu i zapisuje zaktualizowany dokument. 

## Krok 1: Ustaw katalog dokumentów

Najpierw musisz ustawić ścieżkę do swoich dokumentów:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zastąp swoim katalogiem
```

 Ta linia to w zasadzie Twoja mapa drogowa. Informujesz swój kod, gdzie znaleźć plik PDF. Upewnij się, że zastąpiłeś`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką na Twoim komputerze.

## Krok 2: Załaduj plik PDF

Następnie należy załadować plik PDF do aplikacji:

```csharp
// Załaduj plik PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Tutaj tworzysz nową instancję`Document`obiekt podczas określania ścieżki do pliku PDF. Możesz to sobie wyobrazić jako otwieranie książki, którą właśnie umieściłeś na stole.

## Krok 3: Uzyskaj dostęp do żądanej strony

Teraz przejdźmy do strony, którą chcemy wyświetlić po otwarciu dokumentu:

```csharp
// Pobierz wystąpienie drugiej strony dokumentu
Page page2 = doc.Pages[2]; // Pamiętaj, indeksowanie zaczyna się od 1
```

Tutaj uzyskujemy dostęp do drugiej strony dokumentu. Warto zauważyć, że numeracja stron zaczyna się w tym kontekście od 1, więc jeśli myślisz o stronie 2, musisz użyć indeksu 2.

## Krok 4: Ustaw współczynnik powiększenia

Możesz dostosować poziom powiększenia wyświetlanej strony:

```csharp
// Utwórz zmienną, aby ustawić współczynnik powiększenia strony docelowej
double zoom = 1; // 1 oznacza 100% powiększenia
```

Ustawienie współczynnika powiększenia pomaga określić, ile strony użytkownik widzi od razu po jej otwarciu. Wartość 1 oznacza, że strona będzie wyświetlana w powiększeniu 100%, co jest ogólnie dobrym ustawieniem domyślnym.

## Krok 5: Utwórz instancję GoToAction

Przyjrzyjmy się bliżej funkcjom nawigacyjnym:

```csharp
// Utwórz instancję GoToAction
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 W tym kroku tworzysz instancję`GoToAction` co w zasadzie oznacza czynność nawigacji do określonego punktu w pliku PDF – w tym przypadku do drugiej strony.

## Krok 6: Określ miejsce docelowe

Teraz musisz określić, dokąd ma prowadzić akcja:

```csharp
// Przejdź do 2 strony
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Ten wiersz jest jak ustawienie celu GPS dla GoToAction. Mówisz mu, aby przeszedł do strony 2 na górze strony (wysokość) i na określonym poziomie powiększenia.

## Krok 7: Ustaw akcję otwierania

Upewnijmy się, że ta akcja zostanie wykonana po otwarciu dokumentu:

```csharp
// Ustaw akcję otwierania dokumentu
doc.OpenAction = action;
```

Dzięki temu zadeklarowałeś, że po otwarciu pliku PDF, akcja nawigacyjna, którą właśnie zdefiniowaliśmy, jest aktywowana. To tak, jakbyś ustawił wycieraczkę powitalną przy drzwiach wejściowych dokumentu.

## Krok 8: Zapisz zaktualizowany dokument

Na koniec zapiszmy dokument ze zmianami:

```csharp
// Zapisz zaktualizowany dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

Ten krok kończy Twoją pracę! Będziesz mieć nowy plik PDF o nazwie`goto2page_out.pdf` który otwiera bezpośrednio wskazaną stronę.

Tym samym część kodowania jest ukończona! Udało Ci się zaprogramować Aspose.PDF tak, aby po otwarciu pliku PDF wyświetlał określoną stronę. 

## Wniosek

W tym przewodniku krok po kroku wyjaśniliśmy, jak określić stronę w pliku PDF za pomocą Aspose.PDF dla .NET. Ta funkcjonalność nie tylko usprawnia nawigację dla użytkowników, ale także usprawnia ich interakcję z kluczową treścią w dokumentach. Dzięki wykorzystaniu takich funkcji tworzysz bardziej przyjazne dla użytkownika środowisko, które może wyróżnić Twoje aplikacje PDF.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF for .NET to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i zarządzanie dokumentami PDF w aplikacjach .NET.

### Czy mogę określić wiele stron do przeglądania?
Nie, możesz ustawić otwieranie dokumentu tylko na jednej określonej stronie. Możesz jednak tworzyć różne dokumenty dla różnych stron początkowych.

### Co zrobić, jeśli chcę obejrzeć stronę w innym poziomie powiększenia?
 Możesz zmienić poziom powiększenia, dostosowując`zoom` zmienną przed zapisaniem dokumentu.

### Gdzie mogę znaleźć więcej przykładów wykorzystania Aspose.PDF?
 Możesz sprawdzić[dokumentacja](https://reference.aspose.com/pdf/net/) aby zobaczyć więcej przykładów i funkcjonalności.

### Czy jest dostępna bezpłatna wersja próbna Aspose.PDF dla platformy .NET?
 Tak! Możesz pobrać bezpłatną wersję próbną Aspose.PDF[Tutaj](https://releases.aspose.com/).