---
title: Dodaj HTML za pomocą DOM
linktitle: Dodaj HTML za pomocą DOM
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać zawartość HTML przy użyciu DOM w Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-text/add-html-using-dom/
---
Ten samouczek poprowadzi Cię przez proces dodawania treści HTML przy użyciu DOM (Document Object Model) w Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

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
```

## Krok 3: Ustaw katalog dokumentów i ścieżkę pliku wyjściowego
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

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
 Utwórz instancję`HtmlFragment` obiekt i zapewnić żądaną treść HTML. W dostarczonym kodzie treść HTML jest przypisana do zmiennej`titel`. W razie potrzeby możesz modyfikować zawartość HTML.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Krok 7: Ustaw informacje o marginesie
W razie potrzeby dostosuj dolny i górny margines fragmentu HTML. W podanym kodzie dolny margines jest ustawiony na 10, a górny margines na 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Krok 8: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciwić się zbiorowi akapitów na stronie.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Krok 9: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego ustawioną w kroku 3.

```csharp
doc.Save(dataDir);
```

## Krok 10: Wyświetl komunikat o powodzeniu
Wyświetl komunikat o powodzeniu wraz ze ścieżką, w której zapisano plik PDF.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla Dodaj HTMLUsing DOM przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję HtmlFragment za pomocą treści HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Ustaw informacje o dolnym marginesie
titel.Margin.Bottom = 10;
// Ustaw informacje o górnym marginesie
titel.Margin.Top = 200;
// Dodaj fragment HTML do kolekcji akapitów strony
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie dodałeś treść HTML przy użyciu DOM w Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu zapewnienie szczegółowego przewodnika dotyczącego dodawania zawartości HTML do dokumentu PDF przy użyciu obiektowego modelu dokumentu (DOM) w Aspose.PDF dla .NET. Zawiera fragmenty kodu źródłowego C#, które pomogą Ci zrozumieć i wdrożyć proces.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

O: W pliku kodu, do którego planujesz dodać zawartość HTML, zaimportuj na początku pliku następującą przestrzeń nazw:

```csharp
using Aspose.Pdf;
```

#### P: Jak określić katalog dokumentów i ścieżkę pliku wyjściowego?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 O: W kroku 4 utwórz nową instancję`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 Odp.: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page page = doc.Pages.Add();
```

#### P: Jak mogę ustawić zawartość HTML za pomocą modelu DOM?

 O: W kroku 6 utworzysz plik`HtmlFragment` obiekt i przypisz do niego żądaną treść HTML. Do zmiennej przypisana jest treść HTML`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### P: Czy mogę dostosować margines treści HTML?

O: Tak, w kroku 7 możesz dostosować dolny i górny margines fragmentu HTML według potrzeb:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### P: Jak dodać fragment HTML do dokumentu PDF?

 Odp.: W kroku 8 dodasz plik`HtmlFragment` obiekt (`titel`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### P: Jak zapisać wynikowy dokument PDF?

 O: Po dodaniu treści HTML i dostosowaniu marginesów użyj metody`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
doc.Save(dataDir);
```

#### P: Czy istnieje sposób sprawdzenia, czy proces się powiódł?

O: Oczywiście w kroku 10 zostanie wyświetlony komunikat o powodzeniu wraz ze ścieżką, w której zapisano plik PDF:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się wykorzystywać obiektowy model dokumentu (DOM) w Aspose.PDF dla .NET w celu dodawania zawartości HTML do dokumentu PDF. Dzięki tej wiedzy możesz zwiększyć możliwości generowania plików PDF.