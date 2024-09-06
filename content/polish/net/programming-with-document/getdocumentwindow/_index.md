---
title: Pobierz okno dokumentu
linktitle: Pobierz okno dokumentu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać funkcji GetDocumentWindow pakietu Aspose.PDF dla platformy .NET w celu pobierania informacji o właściwościach okna dokumentu PDF.
type: docs
weight: 170
url: /pl/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF dla .NET to potężna biblioteka do manipulacji PDF, która umożliwia programistom tworzenie, edytowanie i konwertowanie plików PDF w aplikacjach .NET. Jedną z funkcji oferowanych przez tę bibliotekę jest możliwość pobierania informacji o właściwościach okna dokumentu. Ten samouczek przeprowadzi Cię przez kroki korzystania z`GetDocumentWindow` Funkcja Aspose.PDF dla platformy .NET umożliwiająca pobieranie informacji o właściwościach okna dokumentu PDF.

## Krok 1: Zainstaluj Aspose.PDF dla .NET

 Aby użyć Aspose.PDF dla .NET w aplikacjach .NET, musisz najpierw zainstalować bibliotekę. Najnowszą wersję biblioteki możesz pobrać ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net).

Po pobraniu biblioteki wypakuj zawartość pliku ZIP do folderu na swoim komputerze. Następnie musisz dodać odwołanie do Aspose.PDF dla .NET DLL w swoim projekcie .NET.

## Krok 2: Załaduj dokument PDF

 Po zainstalowaniu Aspose.PDF dla .NET i dodaniu odwołania do biblioteki DLL w projekcie .NET możesz rozpocząć korzystanie z`GetDocumentWindow`funkcja umożliwiająca pobieranie informacji o właściwościach okna dokumentu PDF.

Pierwszym krokiem w korzystaniu z tej funkcji jest załadowanie dokumentu PDF, o którym chcesz uzyskać informacje. Aby to zrobić, możesz użyć następującego kodu:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 W powyższym kodzie zamień`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym znajduje się Twój dokument PDF. Ten kod załaduje dokument PDF do`Document` obiekt, którego można następnie użyć do pobrania informacji o właściwościach okna dokumentu.

## Krok 3: Pobierz właściwości okna dokumentu

Aby pobrać informacje o właściwościach okna dokumentu PDF, możesz użyć następującego kodu:

```csharp
// Pobierz właściwości okna dokumentu
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

W powyższym kodzie każdy wiersz pobiera inną właściwość okna dokumentu PDF i wyprowadza ją do konsoli. Możesz dostosować ten kod, aby pobrać tylko właściwości, które Cię interesują.

### Przykładowy kod źródłowy do pobrania okna dokumentu pliku PDF przy użyciu Aspose.PDF dla .NET 

 Oto pełny kod źródłowy umożliwiający pobranie właściwości okna dokumentu PDF za pomocą`GetDocumentWindow` funkcja Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Pobierz różne właściwości dokumentu
// Pozycja okna dokumentu - Domyślnie: fałsz
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Dominująca kolejność czytania; określa położenie strony
// Gdy wyświetlane obok siebie - Domyślnie: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Czy pasek tytułu okna powinien wyświetlać tytuł dokumentu
// Jeśli fałsz, pasek tytułu wyświetla nazwę pliku PDF - Domyślnie: fałsz
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Czy zmienić rozmiar okna dokumentu, aby dopasować je do rozmiaru
// Pierwsza wyświetlona strona - Domyślnie: fałsz
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Czy ukryć pasek menu aplikacji przeglądarki - Domyślnie: fałsz
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Czy ukryć pasek narzędzi aplikacji przeglądarki - Domyślnie: fałsz
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Czy ukryć elementy interfejsu użytkownika, takie jak paski przewijania
// I pozostawiając wyświetlaną tylko zawartość strony - Domyślnie: fałsz
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Tryb strony dokumentu. Jak wyświetlić dokument po wyjściu z trybu pełnoekranowego.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Układ strony, tzn. pojedyncza strona, jedna kolumna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Jak powinien wyglądać dokument po otwarciu
// Pokaż miniatury, pełny ekran, pokaż panel załączników
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak używać Aspose.PDF dla .NET do pobierania informacji o właściwościach okna dokumentu PDF. Ładując dokument PDF i uzyskując dostęp do jego właściwości okna, możesz zebrać informacje o tym, jak dokument powinien być wyświetlany po otwarciu w aplikacji przeglądarki. Aspose.PDF dla .NET zapewnia potężny zestaw funkcji do pracy z plikami PDF programowo, co czyni go cennym narzędziem do manipulacji PDF w aplikacjach .NET.

### Najczęściej zadawane pytania

#### P: Jaki jest cel pobierania właściwości okna dokumentu PDF?

A: Pobieranie właściwości okna dokumentu PDF umożliwia zebranie informacji o tym, jak dokument PDF powinien być wyświetlany po otwarciu w aplikacji przeglądarki. Właściwości te kontrolują różne aspekty, takie jak położenie okna, tryb wyświetlania i widoczność elementów interfejsu użytkownika.

#### P: Jak mogę zainstalować Aspose.PDF dla .NET w moim projekcie .NET?

 A: Aby zainstalować Aspose.PDF dla .NET, należy pobrać bibliotekę ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net). Po pobraniu wyodrębnij zawartość pliku ZIP i dodaj odwołanie do pliku Aspose.PDF dla biblioteki DLL .NET w swoim projekcie .NET.

#### P: Czy mogę dostosować kod tak, aby pobierał tylko określone właściwości okna?

A: Tak, możesz dostosować kod, aby pobrać określone właściwości okna, komentując wiersze, których nie potrzebujesz. Każdy wiersz w kodzie odpowiada określonej właściwości okna, więc możesz uwzględnić lub wykluczyć właściwości w zależności od swoich wymagań.

#### P: Jakie typy właściwości okna mogę pobrać za pomocą Aspose.PDF dla .NET?

A: Używając Aspose.PDF dla platformy .NET, można pobrać różne właściwości okna dokumentu PDF, w tym centrować okno, ustawiać układ strony, sterować wyświetlaniem pasków narzędzi i pasków menu i wiele innych.