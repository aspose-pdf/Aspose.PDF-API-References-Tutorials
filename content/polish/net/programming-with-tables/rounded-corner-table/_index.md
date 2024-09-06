---
title: Zaokrąglony stół narożny w dokumencie PDF
linktitle: Zaokrąglony stół narożny w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć tabelę o zaokrąglonych rogach w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 190
url: /pl/net/programming-with-tables/rounded-corner-table/
---
W tym samouczku poprowadzimy Cię krok po kroku, aby utworzyć tabelę z zaokrąglonymi rogami w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie tabeli
Najpierw utworzymy tabelę, korzystając z następującego kodu:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 2: Konfiguracja stylu zaokrąglonych rogów
Następnie skonfigurujemy styl zaokrąglonych narożników tabeli:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Krok 3: Konfiguracja obramowania tabeli
Aby nadać tabeli zaokrąglone narożniki, musimy utworzyć obiekt BorderInfo i skonfigurować go za pomocą odpowiednich parametrów:

```csharp
// Utwórz obiekt GraphInfo, aby ustawić kolor obramowania
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Utwórz pusty obiekt BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Ustaw promień zaokrąglonej krawędzi na 15
bInfo.RoundedBorderRadius = 15;

// Zastosuj informacje o obramowaniu do tabeli
tab1.Border = bInfo;
```

### Przykładowy kod źródłowy dla tabeli z zaokrąglonymi rogami przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Utwórz pusty obiekt BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Ustaw obramowanie jako bardziej okrągłe, gdzie promień okręgu wynosi 15
bInfo.RoundedBorderRadius = 15;
// Ustaw styl narożnika tabeli na okrągły.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Ustaw informacje o obramowaniu tabeli
tab1.Border = bInfo;
```

## Wniosek
Gratulacje! Teraz nauczyłeś się, jak utworzyć tabelę z zaokrąglonymi rogami w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał Ci, jak skonfigurować styl zaokrąglonych rogów i obramowanie tabeli. Teraz możesz zastosować tę wiedzę w swoich projektach.

### FAQ dotyczące stołu z zaokrąglonymi narożnikami w dokumencie PDF

#### P: Czy mogę dostosować promień zaokrąglonych narożników stołu?

O: Tak, możesz dostosować promień zaokrąglonych rogów stołu, modyfikując wartość`bInfo.RoundedBorderRadius` właściwość w dostarczonym kodzie źródłowym C#. Po prostu ustaw żądaną wartość promienia (w punktach), aby uzyskać pożądany wygląd zaokrąglonych narożników.

#### P: Czy mogę zastosować zaokrąglone rogi do poszczególnych komórek w tabeli?

A: Nie, styl zaokrąglonych rogów jest stosowany do całej tabeli jako całości. Aspose.PDF dla .NET obecnie nie zapewnia wbudowanej obsługi stosowania zaokrąglonych rogów do poszczególnych komórek w tabeli.

#### P: Czy mogę zmienić kolor zaokrąglonej ramki?

 A: Tak, możesz zmienić kolor zaokrąglonej krawędzi narożnika, modyfikując wartość`graph.Color` właściwość w kodzie źródłowym C#. Po prostu podaj żądany kolor, taki jak`Aspose.Pdf.Color.Red` lub jakikolwiek inny prawidłowy sposób przedstawienia koloru.

#### P: Czy można zastosować różne style narożników (np. kwadratowe i zaokrąglone) do różnych tabel w tym samym dokumencie PDF?

A: Tak, możliwe jest zastosowanie różnych stylów narożników do różnych tabel w tym samym dokumencie PDF. Możesz utworzyć wiele tabel i skonfigurować ich style narożników indywidualnie w oparciu o swoje wymagania.

#### P: Czy mogę dostosować grubość zaokrąglonej krawędzi?

 A: Tak, możesz dostosować grubość zaokrąglonej krawędzi narożnika, modyfikując`BorderInfo` właściwości obiektu w kodzie źródłowym C#. Na przykład możesz ustawić`bInfo.Width` właściwość umożliwiająca dostosowanie grubości obramowania.