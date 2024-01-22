---
title: Dodaj uporządkowaną listę HTML do dokumentów
linktitle: Dodaj listę zamówioną HTML do dokumentów
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać uporządkowaną listę HTML do dokumentu za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-text/add-html-ordered-list-into-documents/
---
W tym samouczku dowiesz się, jak używać biblioteki Aspose.PDF dla .NET do dodawania uporządkowanej listy HTML do dokumentu. Dostarczony kod demonstruje kroki niezbędne do wykonania tego zadania.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać uporządkowaną listę HTML, dodaj następujące dyrektywy używające na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów i ścieżkę pliku wyjściowego
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

 Następnie znajdź linię, która mówi`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` i wymienić`"AddHTMLOrderedListIntoDocuments_out.pdf"` z żądaną nazwą wyjściowego pliku PDF.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz instancję nowego`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Utwórz obiekt HtmlFragment z zawartością HTML
 Utwórz instancję`HtmlFragment` obiekt z treścią HTML, którą chcesz dodać do dokumentu. W dostarczonym kodzie treść HTML jest przypisana do zmiennej`t`. W razie potrzeby możesz modyfikować zawartość HTML.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Krok 6: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 7: Dodaj fragment HtmlFragment do strony
 Dodaj`HtmlFragment` sprzeciwić się stronie za pomocą metody`Add` metoda`Paragraphs` kolekcja.

```csharp
page.Paragraphs.Add(t);
```

## Krok 8: Zapisz dokument PDF
 Zapisz wynikowy plik PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego ustawioną w kroku 3.

```csharp
doc.Save(outFile);
```

### Przykładowy kod źródłowy dla opcji Dodaj listę zamówioną HTML do dokumentów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ścieżka do dokumentu wyjściowego.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// Utwórz instancję obiektu HtmlFragment z odpowiednim fragmentem HTML
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Dodaj stronę do kolekcji stron
Page page = doc.Pages.Add();
// Dodaj fragment HTML na stronie
page.Paragraphs.Add(t);
// Zapisz wynikowy plik PDF
doc.Save(outFile);
```

## Wniosek
Pomyślnie dodałeś uporządkowaną listę HTML do dokumentu przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

Pamiętaj, aby dostosować zawartość HTML i dostosować kod do swoich konkretnych wymagań.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces dodawania uporządkowanej listy HTML do dokumentu przy użyciu biblioteki Aspose.PDF dla .NET. Zawiera instrukcje krok po kroku i fragmenty kodu, które pomogą Ci osiągnąć to zadanie.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

Odp.: Musisz zaimportować następujące przestrzenie nazw na górze pliku kodu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów i ścieżkę pliku wyjściowego?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów. Znajdź także linię`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` i wymienić`"AddHTMLOrderedListIntoDocuments_out.pdf"` z żądaną nazwą wyjściowego pliku PDF.

#### P: Czy mogę dostosować zawartość HTML dodawaną do dokumentu?

 Odp.: Absolutnie! W kroku 5 utworzysz plik`HtmlFragment` obiekt nazwany`t` przechowujący treść HTML. Możesz modyfikować zawartość HTML w backtickach, aby dostosować ją do swoich wymagań.

#### P: Jak dodać uporządkowaną listę HTML do strony w dokumencie?

 Odp.: W kroku 7 dodasz plik`HtmlFragment` obiekt (`t` ) na stronę za pomocą`Add` metoda`Paragraphs`kolekcja. Spowoduje to bezproblemową integrację uporządkowanej listy HTML z dokumentem.

#### P: Jak zapisać wynikowy dokument PDF?

 Odp.: Po dodaniu treści HTML i uporządkowaniu jej na stronie możesz zapisać dokument PDF za pomocą`Save` metoda`Document` obiekt. Upewnij się, że podałeś poprawną ścieżkę pliku wyjściowego, którą ustawiłeś wcześniej.

#### P: Czy możesz podać podsumowanie przykładowego kodu źródłowego w celach informacyjnych?

Odp.: Oczywiście! Oto skrócona wersja przykładowego kodu źródłowego zawartego w tym samouczku:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się wykorzystywać bibliotekę Aspose.PDF dla .NET do włączenia uporządkowanej listy HTML do dokumentu. Tę nowo odkrytą wiedzę można zastosować w celu usprawnienia procesów tworzenia i manipulacji dokumentami.