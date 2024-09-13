---
title: Dodaj uporządkowaną listę HTML do dokumentów
linktitle: Dodaj listę HTMLOrdered do dokumentów
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać uporządkowaną listę HTML do dokumentu przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-text/add-html-ordered-list-into-documents/
---
W tym samouczku dowiesz się, jak używać biblioteki Aspose.PDF dla .NET, aby dodać uporządkowaną listę HTML do dokumentu. Dostarczony kod demonstruje niezbędne kroki, aby wykonać to zadanie.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać uporządkowaną listę HTML, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentu i ścieżkę pliku wyjściowego
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

 Następnie znajdź linię, która mówi`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` i zastąpić`"AddHTMLOrderedListIntoDocuments_out.pdf"` z żądaną nazwą dla pliku PDF wyjściowego.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Utwórz obiekt HtmlFragment z zawartością HTML
 Utwórz instancję`HtmlFragment` obiekt z zawartością HTML, którą chcesz dodać do dokumentu. W podanym kodzie zawartość HTML jest przypisana do zmiennej`t`. Zawartość HTML można modyfikować według potrzeb.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Krok 6: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 7: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciw wobec strony za pomocą`Add` metoda`Paragraphs` kolekcja.

```csharp
page.Paragraphs.Add(t);
```

## Krok 8: Zapisz dokument PDF
 Zapisz wynikowy plik PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego, którą ustawiłeś w kroku 3.

```csharp
doc.Save(outFile);
```

### Przykładowy kod źródłowy dla dodawania listy HTMLOrdered do dokumentów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ścieżka do dokumentu wyjściowego.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Utwórz obiekt dokumentu
Document doc = new Document();
// Utwórz obiekt HtmlFragment z odpowiadającym mu fragmentem HTML
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Dodaj stronę do kolekcji stron
Page page = doc.Pages.Add();
// Dodaj fragment HTML do strony
page.Paragraphs.Add(t);
//Zapisz wynikowy plik PDF
doc.Save(outFile);
```

## Wniosek
Pomyślnie dodano uporządkowaną listę HTML do dokumentu przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

Pamiętaj o dostosowaniu zawartości HTML i dostosowaniu kodu do swoich konkretnych wymagań.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek ma na celu przeprowadzenie Cię przez proces dodawania uporządkowanej listy HTML do dokumentu przy użyciu biblioteki Aspose.PDF dla .NET. Zawiera instrukcje krok po kroku i fragmenty kodu, które pomogą Ci wykonać to zadanie.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: Musisz zaimportować następujące przestrzenie nazw na górze pliku kodu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentu i ścieżkę do pliku wyjściowego?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów. Znajdź również linię`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` i zastąpić`"AddHTMLOrderedListIntoDocuments_out.pdf"` z wybraną nazwą pliku PDF.

#### P: Czy mogę dostosować zawartość HTML dodawaną do dokumentu?

 A: Oczywiście! W kroku 5 utworzysz`HtmlFragment` obiekt o nazwie`t` który zawiera zawartość HTML. Możesz modyfikować zawartość HTML w znakach odwrotnego apostrofu, aby dostosować ją do swoich wymagań.

#### P: Jak dodać uporządkowaną listę HTML do strony w dokumencie?

 A: W kroku 7 dodasz`HtmlFragment` obiekt (`t` ) do strony za pomocą`Add` metoda`Paragraphs` kolekcja. To płynnie zintegruje uporządkowaną listę HTML z dokumentem.

#### P: Jak zapisać powstały dokument PDF?

 A: Po dodaniu zawartości HTML i umieszczeniu jej na stronie możesz zapisać dokument PDF za pomocą`Save` metoda`Document` obiekt. Upewnij się, że podałeś poprawną ścieżkę pliku wyjściowego, którą ustawiłeś wcześniej.

#### P: Czy możesz udostępnić streszczenie przykładowego kodu źródłowego w celach informacyjnych?

A: Oczywiście! Oto skrócona wersja przykładowego kodu źródłowego podanego w tym samouczku:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Dzięki temu samouczkowi udało Ci się nauczyć, jak wykorzystać bibliotekę Aspose.PDF dla .NET do włączenia uporządkowanej listy HTML do dokumentu. Ta nowo odkryta wiedza może zostać wykorzystana do ulepszenia procesów tworzenia i manipulacji dokumentami.