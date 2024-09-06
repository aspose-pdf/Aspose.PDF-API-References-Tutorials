---
title: Pobierz współczynnik powiększenia w pliku PDF
linktitle: Pobierz współczynnik powiększenia w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla platformy .NET, aby uzyskać współczynnik powiększenia w pliku PDF, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 210
url: /pl/net/programming-with-document/getzoomfactor/
---
Aspose.PDF dla .NET to biblioteka do manipulacji PDF, która oferuje wiele funkcji do wykonywania różnych operacji na dokumentach PDF. Jedną z tych funkcji jest możliwość uzyskania współczynnika powiększenia w pliku PDF. W tym samouczku wyjaśnimy, jak używać Aspose.PDF dla .NET, aby uzyskać współczynnik powiększenia w pliku PDF przy użyciu kodu źródłowego C#.


## Krok 1: Utwórz nowy obiekt dokumentu

 Pierwszym krokiem do uzyskania współczynnika powiększenia pliku PDF przy użyciu Aspose.PDF dla .NET jest utworzenie nowego wystąpienia`Document` obiekt.`Document` obiekt reprezentuje dokument PDF, który można załadować z pliku lub strumienia.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy obiekt dokumentu
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 W powyższym kodzie utworzyliśmy`Document` obiekt, przekazując ścieżkę do pliku PDF do konstruktora`Document` class. Musisz zastąpić „YOUR DOCUMENT DIRECTORY” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój plik PDF.

## Krok 2: Utwórz obiekt GoToAction

 Następnym krokiem jest utworzenie`GoToAction` obiekt. A`GoToAction`obiekt reprezentuje akcję, która przechodzi do określonego miejsca docelowego w dokumencie PDF. W naszym przypadku chcemy uzyskać współczynnik powiększenia pliku PDF, więc użyjemy`OpenAction` własność`Document` obiekt, aby uzyskać`GoToAction` obiekt.

```csharp
// Utwórz obiekt GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 W powyższym kodzie utworzyliśmy`GoToAction` obiekt poprzez rzutowanie`OpenAction` własność`Document` oponować`GoToAction`.

## Krok 3: Uzyskaj współczynnik powiększenia pliku PDF

 Trzecim krokiem jest uzyskanie współczynnika powiększenia pliku PDF. Możemy uzyskać współczynnik powiększenia pliku PDF, uzyskując dostęp do`Destination` własność`GoToAction` obiekt, a następnie rzutowanie go na`XYZExplicitDestination` . Ten`XYZExplicitDestination` Klasa reprezentuje cel w dokumencie PDF, który określa współrzędne i współczynnik powiększenia miejsca docelowego.

```csharp
// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```

 W powyższym kodzie uzyskaliśmy dostęp do`Destination` własność`GoToAction` obiekt, a następnie rzutować go na`XYZExplicitDestination` . Następnie uzyskaliśmy dostęp do`Zoom` własność`XYZExplicitDestination` obiekt, aby uzyskać współczynnik powiększenia pliku PDF.

## Krok 4: Wyjście współczynnika powiększenia

 Ostatnim krokiem jest wyprowadzenie współczynnika powiększenia pliku PDF. Możemy użyć`System.Console.WriteLine`

```csharp
// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```        

### Przykładowy kod źródłowy do pobrania współczynnika powiększenia przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy dla funkcji Get Zoom Factor przy użyciu Aspose.PDF dla platformy .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy obiekt dokumentu
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Utwórz obiekt GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Uzyskaj współczynnik powiększenia pliku PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Wartość powiększenia dokumentu;
```

## Wniosek

W tym samouczku sprawdziliśmy, jak używać Aspose.PDF dla .NET, aby uzyskać współczynnik powiększenia pliku PDF. Współczynnik powiększenia jest kluczowym aspektem dokumentu PDF, ponieważ określa początkowy rozmiar wyświetlania po otwarciu w przeglądarce. Uzyskując dostęp do współczynnika powiększenia i wykorzystując go, programiści mogą dostosować sposób wyświetlania dla użytkowników końcowych. Aspose.PDF dla .NET zapewnia proste i skuteczne API do pobierania współczynnika powiększenia i innych informacji związanych z nawigacją z dokumentu PDF, umożliwiając programistom tworzenie bogatych w funkcje i interaktywnych aplikacji PDF.

### FAQ dotyczące współczynnika powiększenia w pliku PDF

#### P: Jaki jest współczynnik powiększenia w pliku PDF?

A: Współczynnik powiększenia w pliku PDF odnosi się do poziomu powiększenia stosowanego do dokumentu podczas jego wyświetlania. Określa początkowy rozmiar wyświetlania pliku PDF na ekranie. Współczynnik powiększenia 1,0 oznacza rzeczywisty rozmiar (100% powiększenia), podczas gdy współczynnik powiększenia większy niż 1,0 oznacza powiększenie, a współczynnik powiększenia mniejszy niż 1,0 oznacza zmniejszenie.

#### P: W jaki sposób mogę wykorzystać informacje o współczynniku powiększenia w swojej aplikacji?

A: Możesz użyć informacji o współczynniku powiększenia, aby dostosować początkowy rozmiar wyświetlania dokumentu PDF po jego otwarciu w przeglądarce. Na przykład możesz ustawić określony współczynnik powiększenia, aby zapewnić wyświetlanie pliku PDF w określonym rozmiarze lub dopasować całą stronę do okna przeglądarki.

#### P: Czy mogę programowo modyfikować współczynnik powiększenia dokumentu PDF, korzystając z Aspose.PDF dla platformy .NET?

 A: Tak, możesz programowo modyfikować współczynnik powiększenia dokumentu PDF, używając Aspose.PDF dla .NET. Możesz ustawić współczynnik powiększenia dla określonych działań, takich jak:`GoToAction` Lub`GoToRemoteAction`aby kontrolować sposób wyświetlania dokumentu, gdy użytkownik korzysta z linków lub zakładek.

#### P: Czy istnieją inne sposoby nawigowania do określonych lokalizacji w dokumencie PDF przy użyciu Aspose.PDF dla platformy .NET?

 A: Tak, Aspose.PDF dla .NET oferuje różne funkcje umożliwiające nawigację do określonych lokalizacji w dokumencie PDF. Oprócz korzystania z`GoToAction` możesz użyć innych akcji, takich jak`GoToURIAction` aby otworzyć adres URL,`GoToEmbeddedAction` aby przejść do osadzonych plików i`GoToNamedAction` aby przejść do wskazanych miejsc docelowych w dokumencie PDF.