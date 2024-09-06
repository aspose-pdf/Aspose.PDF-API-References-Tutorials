---
title: Ustaw współczynnik powiększenia w pliku PDF
linktitle: Ustaw współczynnik powiększenia w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić współczynnik powiększenia w pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z naszego przewodnika krok po kroku.
type: docs
weight: 340
url: /pl/net/programming-with-document/setzoomfactor/
---
Aspose.PDF dla .NET to potężne API, które pozwala deweloperom pracować z dokumentami PDF w ich aplikacjach .NET. Jedną z funkcji, które oferuje, jest możliwość ustawienia współczynnika powiększenia dokumentu PDF. W tym przewodniku krok po kroku wyjaśnimy, jak używać Aspose.PDF dla .NET do ustawiania współczynnika powiększenia dokumentu PDF przy użyciu dostarczonego kodu źródłowego C#.

## Krok 1: Ustaw ścieżkę do katalogu dokumentu

 Pierwszym krokiem jest ustawienie ścieżki do katalogu, w którym znajduje się dokument PDF. Można to zrobić, ustawiając`dataDir` zmienną do ścieżki katalogu. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zastąp „KATALOG DOKUMENTÓW” rzeczywistą ścieżką katalogu, w którym znajduje się Twój dokument PDF.

## Krok 2: Utwórz nowy obiekt Document

 Aby pracować z dokumentem PDF przy użyciu Aspose.PDF dla .NET, musimy utworzyć nowy`Document` obiekt i załaduj do niego plik PDF. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Ten kod utworzy nowy`Document` obiekt i załaduj plik PDF o nazwie „SetZoomFactor.pdf” z`dataDir` katalog do niego.

## Krok 3: Ustaw współczynnik powiększenia

 Kiedy`Document`obiekt jest tworzony, możemy ustawić współczynnik powiększenia dokumentu PDF. W poniższym kodzie ustawiamy współczynnik powiększenia na 50%.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Ten kod ustawia współczynnik powiększenia na 50% poprzez utworzenie nowego`GoToAction` obiekt i przekazanie`XYZExplicitDestination` obiekt z współczynnikiem powiększenia 50%.`OpenAction` własność`Document` obiekt jest następnie ustawiany na to`GoToAction` obiekt.

## Krok 4: Zapisz dokument PDF

 Na koniec możemy zapisać zmodyfikowany dokument PDF do nowego pliku. W poniższym kodzie zapisujemy dokument PDF do nowego pliku o nazwie „Zoomed_pdf_out.pdf” w`dataDir` informator.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Ustaw współczynnik powiększenia za pomocą Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy obiekt dokumentu
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Zapisz dokument
doc.Save(dataDir);
```

## Wniosek

Aspose.PDF dla .NET zapewnia prosty i wydajny sposób ustawiania współczynnika powiększenia dokumentu PDF za pomocą kodu C#. Postępując zgodnie z powyższymi krokami, możesz łatwo zmodyfikować współczynnik powiększenia dowolnego dokumentu PDF w swojej aplikacji .NET.

### Często zadawane pytania

#### P: Jaki jest współczynnik powiększenia w dokumencie PDF i jak wpływa on na jego przeglądanie?

A: Współczynnik powiększenia w dokumencie PDF określa poziom powiększenia podczas przeglądania dokumentu. Określa skalę, w jakiej wyświetlany jest dokument, wpływając na to, jak duża lub mała jest zawartość wyświetlana na ekranie. Współczynnik powiększenia 1,0 oznacza 100% powiększenia (rzeczywisty rozmiar), podczas gdy współczynnik większy niż 1,0 powoduje powiększenie, a współczynnik mniejszy niż 1,0 — pomniejszenie.

#### P: Czy mogę ustawić konkretny współczynnik powiększenia dla różnych stron w tym samym dokumencie PDF?

 A: Tak, w Aspose.PDF dla .NET możesz ustawić różne współczynniki powiększenia dla różnych stron w tym samym dokumencie PDF. Przykładowy kod źródłowy pokazuje, jak ustawić współczynnik powiększenia dla pierwszej strony za pomocą`GoToAction` obiekt. Możesz zmodyfikować kod, aby ustawić różne współczynniki powiększenia dla innych stron, jeśli to konieczne.

#### P: W jaki sposób zmiana współczynnika powiększenia wpływa na drukowanie i zapisywanie dokumentu PDF?

A: Zmiana współczynnika powiększenia za pomocą Aspose.PDF dla .NET nie wpływa na rzeczywistą zawartość samego dokumentu PDF. Wpływa tylko na wrażenia wizualne, gdy dokument jest otwierany w przeglądarce PDF. Współczynnik powiększenia ustawiony programowo nie będzie miał wpływu na wydruk ani zapisany plik PDF.