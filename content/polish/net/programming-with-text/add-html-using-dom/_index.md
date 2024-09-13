---
title: Dodaj HTML za pomocą DOM
linktitle: Dodaj HTML za pomocą DOM
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać zawartość HTML za pomocą DOM w Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-text/add-html-using-dom/
---
Ten samouczek przeprowadzi Cię przez proces dodawania zawartości HTML przy użyciu DOM (Document Object Model) w Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

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
```

## Krok 3: Ustaw katalog dokumentu i ścieżkę pliku wyjściowego
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Utwórz fragment HTML z zawartością HTML
 Utwórz instancję`HtmlFragment` obiekt i podaj żądaną zawartość HTML. W podanym kodzie zawartość HTML jest przypisana do zmiennej`titel`. Zawartość HTML można modyfikować według potrzeb.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Krok 7: Ustaw informacje o marginesie
razie potrzeby dostosuj dolny i górny margines fragmentu HTML. W podanym kodzie dolny margines jest ustawiony na 10, a górny na 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Krok 8: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciw wobec zbioru akapitów na stronie.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Krok 9: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego, którą ustawiłeś w kroku 3.

```csharp
doc.Save(dataDir);
```

## Krok 10: Wyświetl komunikat o powodzeniu
Wyświetl komunikat o powodzeniu operacji i ścieżkę, pod którą zapisano plik PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla Add HTMLUsing DOM using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt dokumentu
Document doc = new Document();
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz HtmlFragment z zawartością HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Ustaw informacje o dolnym marginesie
titel.Margin.Bottom = 10;
// Ustaw informacje o górnym marginesie
titel.Margin.Top = 200;
// Dodaj fragment HTML do zbioru akapitów strony
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie dodano zawartość HTML za pomocą DOM w Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego samouczka?

A: Ten samouczek ma na celu dostarczenie przewodnika krok po kroku, jak dodać zawartość HTML do dokumentu PDF przy użyciu modelu obiektów dokumentu (DOM) w Aspose.PDF dla .NET. Zawiera fragmenty kodu źródłowego C#, które pomogą Ci zrozumieć i wdrożyć ten proces.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: W pliku kodu, do którego planujesz dodać zawartość HTML, zaimportuj następującą przestrzeń nazw na początku pliku:

```csharp
using Aspose.Pdf;
```

#### P: Jak określić katalog dokumentu i ścieżkę do pliku wyjściowego?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 A: W kroku 4 utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page page = doc.Pages.Add();
```

#### P: Jak mogę ustawić zawartość HTML za pomocą DOM?

 A: W kroku 6 utworzysz`HtmlFragment` obiekt i przypisz mu pożądaną zawartość HTML. Zawartość HTML jest przypisana do zmiennej`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### P: Czy mogę dostosować marginesy zawartości HTML?

O: Tak, w kroku 7 możesz dostosować dolny i górny margines fragmentu HTML według potrzeb:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### P: Jak dodać fragment HTML do dokumentu PDF?

 A: W kroku 8 dodasz`HtmlFragment` obiekt (`titel`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### P: Jak zapisać powstały dokument PDF?

 A: Po dodaniu zawartości HTML i dostosowaniu marginesów użyj`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
doc.Save(dataDir);
```

#### P: Czy istnieje sposób, aby sprawdzić czy proces zakończył się powodzeniem?

O: Oczywiście, w kroku 10 wyświetlany jest komunikat o powodzeniu i ścieżka, pod którą zapisano plik PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Dzięki temu samouczkowi udało Ci się nauczyć, jak wykorzystać Document Object Model (DOM) w Aspose.PDF dla .NET, aby dodać zawartość HTML do dokumentu PDF. Ta wiedza pozwoli Ci udoskonalić możliwości generowania plików PDF.