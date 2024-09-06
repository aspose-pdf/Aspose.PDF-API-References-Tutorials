---
title: Ustaw domyślną czcionkę w pliku PDF
linktitle: Ustaw domyślną czcionkę w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić domyślną czcionkę w pliku PDF za pomocą Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 280
url: /pl/net/programming-with-document/setdefaultfont/
---
Jeśli pracujesz z dokumentami PDF w .NET, możesz napotkać problemy, gdy czcionka używana w pliku PDF nie jest dostępna w systemie, w którym jest on przeglądany lub drukowany. Może to spowodować, że tekst będzie wyświetlany niepoprawnie lub wcale. Aspose.PDF dla .NET zapewnia rozwiązanie tego problemu, umożliwiając ustawienie domyślnej czcionki dla dokumentu. W tym przykładzie pokazano, jak ustawić domyślną czcionkę za pomocą Aspose.PDF dla .NET.

## Krok 1: Ustaw ścieżkę do katalogu dokumentu

musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Zapiszemy tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Zaczniemy od załadowania istniejącego dokumentu PDF, w którym brakuje czcionek. W tym przykładzie założymy, że dokument PDF znajduje się w katalogu określonym przez`dataDir` zmienny.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kod wpisz tutaj
}
```

## Krok 3: Ustaw domyślną czcionkę

 Następnie ustawimy domyślną czcionkę dla dokumentu PDF za pomocą`PdfSaveOptions`klasa. W tym przykładzie ustawimy domyślną czcionkę na „Arial”.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Krok 4: Zapisz zaktualizowany dokument

Na koniec zapiszemy zaktualizowany dokument do nowego pliku. W tym przykładzie zapiszemy zaktualizowany dokument do pliku o nazwie „output_out.pdf” w tym samym katalogu, co plik wejściowy.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Przykładowy kod źródłowy dla ustawienia domyślnej czcionki przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj istniejący dokument PDF z brakującą czcionką
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Określ domyślną nazwę czcionki
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Wniosek

Ustawienie domyślnej czcionki w dokumentach PDF za pomocą Aspose.PDF dla .NET to prosty i skuteczny sposób na zapewnienie, że tekst jest wyświetlany poprawnie, nawet jeśli oryginalne czcionki nie są dostępne. Postępując zgodnie z przewodnikiem krok po kroku i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo ustawić domyślną czcionkę i tworzyć pliki PDF, które oferują spójne i niezawodne wrażenia wizualne w różnych środowiskach. Ta funkcja jest szczególnie przydatna w scenariuszach, w których pliki PDF będą wyświetlane lub drukowane w różnych systemach, które mogą mieć zainstalowane różne zestawy czcionek.

### FAQ dotyczące ustawiania domyślnej czcionki w pliku PDF

#### P: Dlaczego ustawienie domyślnej czcionki w dokumentach PDF jest ważne?

A: Ustawienie domyślnej czcionki w dokumentach PDF jest ważne, ponieważ zapewnia, że tekst będzie wyświetlany poprawnie, nawet jeśli oryginalne czcionki nie są dostępne w systemie, w którym plik PDF jest przeglądany lub drukowany. Pomaga zapobiegać problemom, takim jak brakujący lub zniekształcony tekst, zapewniając spójne i niezawodne wrażenia wizualne.

#### P: Czy mogę wybrać dowolną czcionkę jako czcionkę domyślną, używając Aspose.PDF dla .NET?

 A: Tak, możesz wybrać dowolną czcionkę dostępną w systemie jako domyślną, używając Aspose.PDF dla .NET. Wystarczy podać nazwę czcionki w`DefaultFontName` własność`PdfSaveOptions` klasa.

#### P: Co się stanie, jeśli określona domyślna czcionka nie będzie dostępna w systemie?

A: Jeśli określona domyślna czcionka nie jest dostępna w systemie, przeglądarka PDF użyje czcionki zapasowej do wyświetlenia tekstu. Zaleca się wybranie powszechnie dostępnej czcionki, takiej jak Arial lub Times New Roman, aby zapewnić zgodność w różnych systemach.