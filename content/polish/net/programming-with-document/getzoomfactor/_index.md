---
title: Uzyskaj współczynnik powiększenia w pliku PDF
linktitle: Uzyskaj współczynnik powiększenia w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET, aby uzyskać współczynnik powiększenia w pliku PDF, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 210
url: /pl/net/programming-with-document/getzoomfactor/
---
Aspose.PDF dla .NET to biblioteka do manipulacji plikami PDF, która zapewnia wiele funkcji umożliwiających wykonywanie różnych operacji na dokumentach PDF. Jedną z tych funkcji jest możliwość uzyskania współczynnika powiększenia w pliku PDF. W tym samouczku wyjaśnimy, jak używać Aspose.PDF dla .NET, aby uzyskać współczynnik powiększenia w pliku PDF przy użyciu kodu źródłowego C#.


## Krok 1: Utwórz instancję nowego obiektu dokumentu

 Pierwszym krokiem do uzyskania współczynnika powiększenia pliku PDF przy użyciu Aspose.PDF dla .NET jest utworzenie nowej instancji`Document` obiekt. The`Document` obiekt reprezentuje dokument PDF, który można załadować z pliku lub strumienia.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję nowego obiektu dokumentu
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 W powyższym kodzie utworzyliśmy plik`Document` obiektu, przekazując ścieżkę pliku PDF do konstruktora obiektu`Document` klasa. Musisz zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój plik PDF.

## Krok 2: Utwórz obiekt GoToAction

 Następnym krokiem jest utworzenie`GoToAction` obiekt. A`GoToAction`obiekt reprezentuje akcję, która prowadzi do określonego miejsca docelowego w dokumencie PDF. W naszym przypadku chcemy uzyskać współczynnik powiększenia pliku PDF, więc użyjemy`OpenAction` własność`Document` obiekt, aby uzyskać`GoToAction` obiekt.

```csharp
// Utwórz obiekt GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 W powyższym kodzie utworzyliśmy plik`GoToAction` obiekt, rzucając`OpenAction` własność`Document` oponować`GoToAction`.

## Krok 3: Uzyskaj współczynnik powiększenia pliku PDF

 Trzecim krokiem jest uzyskanie współczynnika powiększenia pliku PDF. Możemy uzyskać współczynnik powiększenia pliku PDF, uzyskując dostęp do`Destination` własność`GoToAction` obiekt, a następnie rzutowanie na niego`XYZExplicitDestination` . The`XYZExplicitDestination` class reprezentuje miejsce docelowe w dokumencie PDF, które określa współrzędne i współczynnik powiększenia, do którego należy się udać.

```csharp
// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```

 W powyższym kodzie uzyskaliśmy dostęp do pliku`Destination` własność`GoToAction` obiekt, a następnie rzuć go na`XYZExplicitDestination` . Następnie uzyskaliśmy dostęp do`Zoom` własność`XYZExplicitDestination` obiekt, aby uzyskać współczynnik powiększenia pliku PDF.

## Krok 4: Wyprowadź współczynnik powiększenia

 Ostatnim krokiem jest wyświetlenie współczynnika powiększenia pliku PDF. Możemy skorzystać z`System.Console.WriteLine`

```csharp
// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```        

### Przykładowy kod źródłowy funkcji Get Zoom Factor przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy narzędzia Get Zoom Factor przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję nowego obiektu dokumentu
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Utwórz obiekt GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```

## Wniosek

W tym samouczku omówiliśmy, jak używać Aspose.PDF dla .NET, aby uzyskać współczynnik powiększenia pliku PDF. Współczynnik powiększenia jest kluczowym aspektem dokumentu PDF, ponieważ określa początkowy rozmiar wyświetlanego po otwarciu w przeglądarce. Uzyskując dostęp do współczynnika powiększenia i wykorzystując go, programiści mogą dostosować sposób oglądania dla użytkowników końcowych. Aspose.PDF dla .NET zapewnia prosty i skuteczny interfejs API do pobierania współczynnika powiększenia i innych informacji związanych z nawigacją z dokumentu PDF, umożliwiając programistom tworzenie bogatych w funkcje i interaktywnych aplikacji PDF.

### Często zadawane pytania dotyczące uzyskiwania współczynnika powiększenia w pliku PDF

#### P: Jaki jest współczynnik powiększenia w pliku PDF?

Odp.: Współczynnik powiększenia w pliku PDF odnosi się do poziomu powiększenia zastosowanego do dokumentu podczas jego przeglądania. Określa początkowy rozmiar wyświetlanego pliku PDF na ekranie. Współczynnik powiększenia 1,0 reprezentuje rzeczywisty rozmiar (powiększenie 100%), współczynnik powiększenia większy niż 1,0 oznacza powiększenie, a współczynnik powiększenia mniejszy niż 1,0 oznacza zmniejszenie.

#### P: Jak mogę wykorzystać informacje o współczynniku powiększenia w mojej aplikacji?

O: Możesz użyć informacji o współczynniku powiększenia, aby dostosować początkowy rozmiar wyświetlanego dokumentu PDF po jego otwarciu w przeglądarce. Można na przykład ustawić określony współczynnik powiększenia, aby mieć pewność, że plik PDF będzie wyświetlany w określonym rozmiarze lub dopasuje całą stronę do okna przeglądarki.

#### P: Czy mogę programowo modyfikować współczynnik powiększenia dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz programowo modyfikować współczynnik powiększenia dokumentu PDF za pomocą Aspose.PDF dla .NET. Można ustawić współczynnik powiększenia dla określonych działań, np`GoToAction` Lub`GoToRemoteAction`aby kontrolować sposób wyświetlania dokumentu, gdy użytkownik wchodzi w interakcję z łączami lub zakładkami.

#### P: Czy istnieją inne sposoby nawigacji do określonych lokalizacji w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

 Odp.: Tak, Aspose.PDF dla .NET zapewnia różne funkcje umożliwiające nawigację do określonych lokalizacji w dokumencie PDF. Oprócz używania`GoToAction` , możesz użyć innych akcji, takich jak`GoToURIAction` aby otworzyć adres URL,`GoToEmbeddedAction` aby przejść do osadzonych plików i`GoToNamedAction` aby przejść do nazwanych miejsc docelowych w dokumencie PDF.