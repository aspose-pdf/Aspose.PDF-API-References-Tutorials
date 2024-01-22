---
title: Dodaj HTML za pomocą DOM i nadpisz PDF
linktitle: Dodaj HTML za pomocą DOM i nadpisz
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać zawartość HTML przy użyciu DOM i nadpisywania plików PDF w Aspose.PDF dla .NET.
type: docs
weight: 50
url: /pl/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Ten samouczek poprowadzi Cię przez proces dodawania treści HTML przy użyciu DOM (Document Object Model) w Aspose.PDF dla .NET. Dodatkowo dowiesz się jak nadpisywać style dla treści HTML. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać zawartość HTML, dodaj następujące dyrektywy używające na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów i ścieżkę pliku wyjściowego
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz instancję nowego`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Utwórz fragment HtmlFragment z zawartością HTML
 Utwórz instancję`HtmlFragment` obiekt i zapewnić żądaną treść HTML. W dostarczonym kodzie treść HTML jest przypisana do zmiennej`title`. W razie potrzeby możesz modyfikować zawartość HTML.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Krok 7: Zastąp style zawartości HTML
 Aby zastąpić style treści HTML, możesz zmodyfikować plik`TextState` właściwości`HtmlFragment` obiekt. W dostarczonym kodzie rodzina czcionek została zmieniona na „Arial”, a rozmiar czcionki jest ustawiony na 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Krok 8: Ustaw informacje o marginesie
razie potrzeby dostosuj dolny i górny margines fragmentu HTML. W podanym kodzie dolny margines jest ustawiony na 10, a górny margines na 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Krok 9: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciwić się zbiorowi akapitów na stronie.

```csharp
page.Paragraphs.Add(title);
```

## Krok 10: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego ustawioną w kroku 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla opcji Dodaj HTMLUsing DOMAnd Overwrite przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję HtmlFragment za pomocą treści HTML
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Rodzina czcionek z „Verdana” zostanie zresetowana do „Arial”
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Ustaw informacje o dolnym marginesie
title.Margin.Bottom = 10;
// Ustaw informacje o górnym marginesie
title.Margin.Top = 400;
// Dodaj fragment HTML do kolekcji akapitów strony
page.Paragraphs.Add(title);
// Zapisz plik PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
```

## Wniosek
Pomyślnie dodałeś treść HTML przy użyciu DOM w Aspose.PDF dla .NET i nadpisałeś style zawartości HTML. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Na czym skupia się ten samouczek?

Odp.: Ten samouczek ma na celu przeprowadzić Cię przez proces dodawania zawartości HTML do dokumentu PDF przy użyciu Document Object Model (DOM) w Aspose.PDF dla .NET. Dodatkowo dowiesz się jak nadpisywać style treści HTML, co pozwoli Ci dostosować jej wygląd. Samouczek zawiera fragmenty kodu źródłowego języka C# ilustrujące wymagane kroki.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

O: W pliku kodu, do którego chcesz dodać treść HTML, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów i ścieżkę pliku wyjściowego?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 O: W kroku 4 utworzysz nową instancję`Document` obiekt za pomocą następującego wiersza kodu:

```csharp
Document doc = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 Odp.: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page page = doc.Pages.Add();
```

#### P: Jak mogę ustawić zawartość HTML za pomocą modelu DOM?

 O: W kroku 6 utworzysz plik`HtmlFragment` obiekt i przypisz do niego żądaną treść HTML. Do zmiennej przypisana jest treść HTML`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### P: Jak mogę zastąpić style treści HTML?

 O: W kroku 7 nadpiszesz style treści HTML, modyfikując plik`TextState` właściwości`HtmlFragment` obiekt. Na przykład możesz zmienić rodzinę czcionek na „Arial” i ustawić rozmiar czcionki na 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### P: Czy mogę dostosować margines treści HTML?

O: Tak, w kroku 8 możesz dostosować dolny i górny margines fragmentu HTML według potrzeb:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### P: Jak dodać fragment HtmlFragment do dokumentu PDF?

 Odp.: W kroku 9 dodasz plik`HtmlFragment` obiekt (`title`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(title);
```

#### P: Jak zapisać wynikowy dokument PDF?

 O: Po dodaniu treści HTML i dostosowaniu jej stylów użyj pliku`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się włączać treść HTML przy użyciu Document Object Model (DOM) w Aspose.PDF dla .NET. Dodatkowo zyskałeś możliwość nadpisywania stylów, aby dostosować wygląd zawartości HTML w wynikowym dokumencie PDF.