---
title: Ustaw domyślną czcionkę w pliku PDF
linktitle: Ustaw domyślną czcionkę w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić domyślną czcionkę w pliku PDF przy użyciu Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 280
url: /pl/net/programming-with-document/setdefaultfont/
---
Jeśli pracujesz z dokumentami PDF w platformie .NET, możesz napotkać problemy polegające na tym, że czcionka użyta w pliku PDF nie jest dostępna w systemie, w którym jest przeglądana lub drukowana. Może to spowodować, że tekst będzie wyświetlany nieprawidłowo lub w ogóle. Aspose.PDF dla .NET zapewnia rozwiązanie tego problemu, umożliwiając ustawienie domyślnej czcionki dla dokumentu. W tym przykładzie, jak ustawić domyślną czcionkę przy użyciu Aspose.PDF dla .NET.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Będziemy przechowywać tę ścieżkę w zmiennej o nazwie „dataDir”.

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
    // kod trafia tutaj
}
```

## Krok 3: Ustaw domyślną czcionkę

 Następnie ustawimy domyślną czcionkę dla dokumentu PDF za pomocą`PdfSaveOptions` klasa. W tym przykładzie ustawimy domyślną czcionkę na „Arial”.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Krok 4: Zapisz zaktualizowany dokument

Na koniec zapiszemy zaktualizowany dokument w nowym pliku. W tym przykładzie zapiszemy zaktualizowany dokument w pliku o nazwie „output_out.pdf” w tym samym katalogu, co plik wejściowy.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Przykładowy kod źródłowy dla Ustaw domyślną czcionkę przy użyciu Aspose.PDF dla .NET

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

Ustawienie domyślnej czcionki w dokumentach PDF przy użyciu Aspose.PDF dla .NET to prosty i skuteczny sposób zapewnienia prawidłowego wyświetlania tekstu, nawet jeśli oryginalne czcionki nie są dostępne. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego języka C#, programiści mogą z łatwością ustawić domyślną czcionkę i utworzyć pliki PDF zapewniające spójne i niezawodne wrażenia wizualne w różnych środowiskach. Ta funkcja jest szczególnie przydatna w scenariuszach, w których pliki PDF będą przeglądane lub drukowane w różnych systemach, w których mogą być zainstalowane różne zestawy czcionek.

### Często zadawane pytania dotyczące ustawiania domyślnej czcionki w pliku PDF

#### P: Dlaczego ustawienie domyślnej czcionki jest ważne w dokumentach PDF?

O: Ustawienie domyślnej czcionki w dokumentach PDF jest ważne, ponieważ gwarantuje, że tekst będzie wyświetlany poprawnie, nawet jeśli oryginalne czcionki nie są dostępne w systemie, w którym przeglądany lub drukowany jest plik PDF. Pomaga zapobiegać problemom takim jak brakujący lub zniekształcony tekst, zapewniając spójne i niezawodne wrażenia wizualne.

#### P: Czy mogę wybrać dowolną czcionkę jako czcionkę domyślną przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz wybrać dowolną czcionkę dostępną w systemie jako czcionkę domyślną, używając Aspose.PDF dla .NET. Wystarczy podać nazwę czcionki w pliku`DefaultFontName` własność`PdfSaveOptions` klasa.

#### P: Co się stanie, jeśli określona domyślna czcionka nie będzie dostępna w systemie?

Odp.: Jeśli określona czcionka domyślna nie jest dostępna w systemie, przeglądarka plików PDF użyje czcionki zastępczej do wyświetlenia tekstu. Zaleca się wybranie powszechnie dostępnej czcionki, takiej jak Arial lub Times New Roman, aby zapewnić kompatybilność w różnych systemach.