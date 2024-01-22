---
title: Ustaw współczynnik powiększenia w pliku PDF
linktitle: Ustaw współczynnik powiększenia w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić współczynnik powiększenia w pliku PDF przy użyciu Aspose.PDF dla .NET, korzystając z naszego przewodnika krok po kroku.
type: docs
weight: 340
url: /pl/net/programming-with-document/setzoomfactor/
---
Aspose.PDF dla .NET to potężny interfejs API, który umożliwia programistom pracę z dokumentami PDF w aplikacjach .NET. Jedną z funkcji, które zapewnia, jest możliwość ustawienia współczynnika powiększenia dokumentu PDF. W tym przewodniku krok po kroku wyjaśnimy, jak używać Aspose.PDF dla .NET do ustawiania współczynnika powiększenia dokumentu PDF przy użyciu dostarczonego kodu źródłowego C#.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

 Pierwszym krokiem jest ustawienie ścieżki do katalogu, w którym znajduje się dokument PDF. Można to zrobić ustawiając`dataDir` zmienną do ścieżki katalogu. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zastąp „KATALOG TWOJEGO DOKUMENTU” rzeczywistą ścieżką katalogu, w którym znajduje się dokument PDF.

## Krok 2: Utwórz instancję nowego obiektu dokumentu

 Aby pracować z dokumentem PDF przy użyciu Aspose.PDF dla .NET, musimy utworzyć nowy`Document` obiekt i załaduj do niego plik PDF. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Ten kod utworzy nowy`Document` obiekt i załaduj plik PDF o nazwie „SetZoomFactor.pdf” z pliku`dataDir` do niego katalog.

## Krok 3: Ustaw współczynnik powiększenia

 Kiedyś`Document`obiekt zostanie utworzony, możemy ustawić współczynnik powiększenia dokumentu PDF. W poniższym kodzie ustawiamy współczynnik powiększenia na 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Ten kod ustawia współczynnik powiększenia na 50%, tworząc nowy`GoToAction` obiekt i mijanie a`XYZExplicitDestination` obiekt ze współczynnikiem powiększenia wynoszącym 50%. The`OpenAction` własność`Document` obiekt jest następnie ustawiany na to`GoToAction` obiekt.

## Krok 4: Zapisz dokument PDF

 Wreszcie możemy zapisać zmodyfikowany dokument PDF w nowym pliku. W poniższym kodzie zapisujemy dokument PDF w nowym pliku o nazwie „Zoomed_pdf_out.pdf” w`dataDir` informator.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Ustaw współczynnik powiększenia przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję nowego obiektu dokumentu
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Zapisz dokument
doc.Save(dataDir);
```

## Wniosek

Aspose.PDF dla .NET zapewnia prosty i skuteczny sposób ustawienia współczynnika powiększenia dokumentu PDF przy użyciu kodu C#. Wykonując powyższe kroki, możesz łatwo zmodyfikować współczynnik powiększenia dowolnego dokumentu PDF w aplikacji .NET.

### Często zadawane pytania

#### P: Jaki jest współczynnik powiększenia w dokumencie PDF i jak wpływa na przeglądanie?

Odp.: Współczynnik powiększenia w dokumencie PDF określa poziom powiększenia podczas przeglądania dokumentu. Określa skalę, w jakiej wyświetlany jest dokument, wpływając na to, jak duża lub mała treść pojawia się na ekranie. Współczynnik powiększenia 1,0 reprezentuje 100% powiększenia (rzeczywisty rozmiar), podczas gdy współczynnik większy niż 1,0 powoduje powiększenie, a współczynnik mniejszy niż 1,0 pomniejsza.

#### P: Czy mogę ustawić określony współczynnik powiększenia dla różnych stron w tym samym dokumencie PDF?

 O: Tak, dzięki Aspose.PDF dla .NET możesz ustawić różne współczynniki powiększenia dla różnych stron w tym samym dokumencie PDF. Dostarczony przykładowy kod źródłowy pokazuje, jak ustawić współczynnik powiększenia dla pierwszej strony za pomocą`GoToAction` obiekt. W razie potrzeby możesz zmodyfikować kod, aby ustawić różne współczynniki powiększenia dla innych stron.

#### P: Jak zmiana współczynnika powiększenia wpływa na drukowanie i zapisywanie dokumentu PDF?

Odp.: Zmiana współczynnika powiększenia przy użyciu Aspose.PDF dla .NET nie wpływa na rzeczywistą zawartość samego dokumentu PDF. Wpływa to tylko na komfort przeglądania, gdy dokument jest otwarty w przeglądarce plików PDF. Współczynnik powiększenia ustawiony programowo nie będzie miał wpływu na wydruk ani na zapisany plik PDF.