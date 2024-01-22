---
title: Pobierz numer strony zakładki w pliku PDF
linktitle: Pobierz numer strony zakładki w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością uzyskaj numer strony zakładek w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 60
url: /pl/net/programming-with-bookmarks/get-bookmark-page-number/
---
Pobieranie numerów stron powiązanych z zakładkami w pliku PDF może być przydatne do nawigacji. Dzięki Aspose.PDF dla .NET możesz łatwo uzyskać numer strony zakładek, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf.Facades;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, z którego chcesz wyodrębnić numery stron zakładek. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Utwórz edytor zakładek

 Teraz utworzymy`PdfBookmarkEditor` obiekt do manipulowania zakładkami dokumentu. Użyj następującego kodu:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Krok 4: Otwórz plik PDF

 Na tym etapie otwieramy plik PDF za pomocą`BindPdf` metoda edytora zakładek. Oto odpowiedni kod:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Krok 5: Wyodrębnij zakładki

 Teraz wyodrębnimy zakładki z dokumentu za pomocą`ExtractBookmarks` metoda edytora zakładek. Oto odpowiedni kod:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Krok 6: Przeglądaj zakładki i uzyskaj numery stron

 Na koniec przeglądamy wyodrębnione zakładki i uzyskujemy numery stron powiązane z każdą zakładką za pomocą a`foreach` pętla. Oto odpowiedni kod:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Przykładowy kod źródłowy dla opcji Pobierz numer strony zakładek przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz edytor zakładek PDF
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Otwórz plik PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Wyodrębnij zakładki
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku, jak uzyskać numery stron zakładek za pomocą Aspose.PDF dla .NET. Możesz użyć tego kodu, aby pobrać informacje nawigacyjne powiązane z każdą zakładką w dokumentach PDF.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji manipulacji zakładkami.

### Często zadawane pytania dotyczące pobierania numeru strony zakładki w pliku PDF

#### P: Czym są zakładki w pliku PDF?

Odp.: Zakładki w pliku PDF to pomoce w nawigacji, które umożliwiają użytkownikom szybkie przechodzenie do określonych sekcji lub stron dokumentu. Poprawiają wygodę użytkownika, udostępniając skróty do odpowiednich treści.

#### P: Dlaczego miałbym chcieć pobrać numery stron zakładek z pliku PDF?

O: Pobieranie numerów stron zakładek pomaga użytkownikom efektywniej poruszać się po dokumencie, zapewniając jasne wskazanie, dokąd prowadzi każda zakładka. Jest to szczególnie przydatne w przypadku dłuższych dokumentów zawierających wiele sekcji.

#### P: Jak zaimportować niezbędne biblioteki do mojego projektu C#?

Odp.: Aby zaimportować wymaganą bibliotekę do projektu C#, użyj następującej dyrektywy importu:

```csharp
using Aspose.Pdf.Facades;
```

Ta dyrektywa pozwala na wykorzystanie klas i metod dostarczonych przez Aspose.PDF dla .NET.

#### P: Jak określić ścieżkę do folderu dokumentów?

 Odp.: W dostarczonym kodzie źródłowym zamień`"YOUR DOCUMENT DIRECTORY"` rzeczywistą ścieżką do folderu zawierającego plik PDF, z którego chcesz wyodrębnić numery stron zakładek. Dzięki temu kod będzie mógł zlokalizować docelowy plik PDF.

#### P: Jak utworzyć edytor zakładek?

O: Aby utworzyć edytor zakładek, użyj następującego kodu:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### P: Jak otworzyć plik PDF w celu manipulowania zakładkami?

Odp.: Aby otworzyć plik PDF w celu wyodrębnienia informacji o zakładkach, użyj następującego kodu:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Zastępować`"GetBookmarks.pdf"` z rzeczywistą nazwą pliku.

#### P: Jak wyodrębnić zakładki z pliku PDF?

 Odp.: Aby wyodrębnić zakładki z pliku PDF, użyj metody`ExtractBookmarks` metoda edytora zakładek:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### P: Jak odzyskać i wyświetlić numery stron zakładek?

 Odp.: Przeglądaj wyodrębnione zakładki za pomocą a`foreach` pętli i uzyskaj dostęp do`PageNumber` właściwość każdej zakładki, aby pobrać i wyświetlić powiązany numer strony:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### P: Czy mogę modyfikować właściwości zakładek, korzystając z tego podejścia?

 Odp.: Chociaż ten samouczek koncentruje się na pobieraniu numerów stron zakładek, możesz modyfikować inne właściwości zakładek, korzystając z tego samego`Bookmark`obiekt i związane z nim właściwości.

#### P: Jak zapisać zaktualizowany plik PDF po wyodrębnieniu informacji o zakładkach?

Odp.: Wyodrębnianie zakładek nie modyfikuje oryginalnego pliku PDF. Jeśli chcesz zapisać jakiekolwiek zmiany, możesz to zrobić za pomocą innych metod dostarczonych przez Aspose.PDF dla .NET.