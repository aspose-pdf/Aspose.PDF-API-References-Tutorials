---
title: Zaokrąglony stół narożny w dokumencie PDF
linktitle: Zaokrąglony stół narożny w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak utworzyć zaokrągloną tabelę narożną w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 190
url: /pl/net/programming-with-tables/rounded-corner-table/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak utworzyć zaokrągloną tabelę narożną w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie tabeli
Najpierw utworzymy tabelę, używając następującego kodu:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 2: Konfiguracja stylu zaokrąglonych narożników
Następnie skonfigurujemy styl zaokrąglonych narożników tabeli:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Krok 3: Konfiguracja obramowania stołu
Aby nadać tabeli zaokrąglony narożnik, musimy utworzyć obiekt BorderInfo i skonfigurować go z odpowiednimi parametrami:

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

### Przykładowy kod źródłowy zaokrąglonego stołu narożnego przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Utwórz pusty obiekt BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Ustaw granicę bardziej zaokrągloną, której promień zaokrąglenia wynosi 15
bInfo.RoundedBorderRadius = 15;
// Ustaw styl narożnika stołu na Okrągły.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Ustaw informacje o obramowaniu tabeli
tab1.Border = bInfo;
```

## Wniosek
Gratulacje! Nauczyłeś się teraz, jak utworzyć zaokrągloną tabelę narożną w dokumencie PDF przy użyciu Aspose.PDF dla .NET. W tym przewodniku krok po kroku pokazano, jak skonfigurować styl zaokrąglonych narożników i obramowania tabeli. Teraz możesz zastosować tę wiedzę w swoich własnych projektach.

### Często zadawane pytania dotyczące zaokrąglonego stołu narożnego w dokumencie PDF

#### P: Czy mogę dostosować promień zaokrąglonych narożników stołu?

Odp.: Tak, możesz dostosować promień zaokrąglonych narożników stołu, modyfikując wartość parametru`bInfo.RoundedBorderRadius` właściwość w podanym kodzie źródłowym C#. Wystarczy ustawić żądaną wartość promienia (w punktach), aby uzyskać pożądany wygląd zaokrąglonych narożników.

#### P: Czy mogę zastosować zaokrąglone rogi do poszczególnych komórek w tabeli?

O: Nie, styl zaokrąglonych narożników jest stosowany do całego stołu jako całości. Aspose.PDF dla .NET obecnie nie zapewnia wbudowanej obsługi stosowania zaokrąglonych narożników do poszczególnych komórek w tabeli.

#### P: Czy mogę zmienić kolor zaokrąglonego narożnika?

 Odp.: Tak, możesz zmienić kolor zaokrąglonego narożnika, modyfikując wartość parametru`graph.Color` właściwość w kodzie źródłowym C#. Wystarczy podać żądany kolor, np`Aspose.Pdf.Color.Red` lub jakakolwiek inna prawidłowa reprezentacja kolorów.

#### P: Czy można zastosować różne style narożników (np. kwadratowe i zaokrąglone) do różnych tabel w tym samym dokumencie PDF?

O: Tak, możliwe jest zastosowanie różnych stylów narożników do różnych tabel w tym samym dokumencie PDF. Możesz utworzyć wiele stołów i skonfigurować ich style narożników indywidualnie, w zależności od wymagań.

#### P: Czy mogę dostosować grubość zaokrąglonego narożnika?

 Odp.: Tak, możesz dostosować grubość zaokrąglonego narożnika, modyfikując plik`BorderInfo` właściwości obiektu w kodzie źródłowym C#. Można na przykład ustawić`bInfo.Width` właściwość umożliwiająca dostosowanie grubości obramowania.