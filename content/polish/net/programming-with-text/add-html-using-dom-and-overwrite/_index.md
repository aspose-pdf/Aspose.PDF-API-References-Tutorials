---
title: Dodaj HTML za pomocą DOM i nadpisywania PDF
linktitle: Dodaj HTML za pomocą DOM i nadpisz
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać zawartość HTML za pomocą DOM i nadpisywania PDF w Aspose.PDF dla platformy .NET.
type: docs
weight: 50
url: /pl/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Ten samouczek przeprowadzi Cię przez proces dodawania zawartości HTML przy użyciu DOM (Document Object Model) w Aspose.PDF dla .NET. Ponadto nauczysz się, jak nadpisywać style dla zawartości HTML. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać zawartość HTML, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentu i ścieżkę pliku wyjściowego
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Utwórz fragment HTML z zawartością HTML
 Utwórz instancję`HtmlFragment` obiekt i podaj żądaną zawartość HTML. W podanym kodzie zawartość HTML jest przypisana do zmiennej`title`. Zawartość HTML można modyfikować według potrzeb.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Krok 7: Nadpisz style dla zawartości HTML
 Aby nadpisać style zawartości HTML, możesz zmodyfikować`TextState` właściwości`HtmlFragment` obiekt. W podanym kodzie rodzina czcionek jest zmieniona na „Arial”, a rozmiar czcionki jest ustawiony na 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Krok 8: Ustaw informacje o marginesie
razie potrzeby dostosuj dolny i górny margines fragmentu HTML. W podanym kodzie dolny margines jest ustawiony na 10, a górny na 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Krok 9: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciw wobec zbioru akapitów na stronie.

```csharp
page.Paragraphs.Add(title);
```

## Krok 10: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego, którą ustawiłeś w kroku 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Dodaj HTMLUżywając DOM i Nadpisz używając Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt dokumentu
Document doc = new Document();
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz HtmlFragment z zawartością HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Rodzina czcionek „Verdana” zostanie zresetowana do „Arial”
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Ustaw informacje o dolnym marginesie
title.Margin.Bottom = 10;
// Ustaw informacje o górnym marginesie
title.Margin.Top = 400;
// Dodaj fragment HTML do zbioru akapitów strony
page.Paragraphs.Add(title);
// Zapisz plik PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
```

## Wniosek
Pomyślnie dodano zawartość HTML za pomocą DOM w Aspose.PDF dla .NET i nadpisano style zawartości HTML. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym skupia się ten samouczek?

A: Ten samouczek ma na celu przeprowadzenie Cię przez proces dodawania zawartości HTML do dokumentu PDF przy użyciu Document Object Model (DOM) w Aspose.PDF dla .NET. Ponadto nauczysz się, jak nadpisywać style zawartości HTML, co pozwoli Ci dostosować jej wygląd. Samouczek zawiera fragmenty kodu źródłowego C#, aby zademonstrować wymagane kroki.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: W pliku kodu, do którego chcesz dodać zawartość HTML, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentu i ścieżkę do pliku wyjściowego?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając następującego wiersza kodu:

```csharp
Document doc = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page page = doc.Pages.Add();
```

#### P: Jak mogę ustawić zawartość HTML za pomocą DOM?

 A: W kroku 6 utworzysz`HtmlFragment` obiekt i przypisz mu pożądaną zawartość HTML. Zawartość HTML jest przypisana do zmiennej`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### P: Jak mogę nadpisać style zawartości HTML?

 A: W kroku 7 nadpiszesz style zawartości HTML, modyfikując`TextState` właściwości`HtmlFragment` obiekt. Na przykład możesz zmienić rodzinę czcionek na „Arial” i ustawić rozmiar czcionki na 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### P: Czy mogę dostosować marginesy zawartości HTML?

O: Tak, w kroku 8 możesz dostosować dolny i górny margines fragmentu HTML według potrzeb:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### P: Jak dodać fragment HtmlFragment do dokumentu PDF?

 A: W kroku 9 dodasz`HtmlFragment` obiekt (`title`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(title);
```

#### P: Jak zapisać powstały dokument PDF?

 A: Po dodaniu zawartości HTML i dostosowaniu jej stylów użyj`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak włączać zawartość HTML za pomocą Document Object Model (DOM) w Aspose.PDF dla .NET. Ponadto, zyskałeś możliwość nadpisywania stylów, aby dostosować wygląd zawartości HTML w wynikowym dokumencie PDF.