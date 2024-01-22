---
title: Pobierz okno dokumentu
linktitle: Pobierz okno dokumentu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak korzystać z funkcji GetDocumentWindow w Aspose.PDF dla .NET, aby pobrać informacje o właściwościach okna dokumentu PDF.
type: docs
weight: 170
url: /pl/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF dla .NET to potężna biblioteka do manipulacji plikami PDF, która umożliwia programistom tworzenie, edytowanie i konwertowanie plików PDF w aplikacjach .NET. Jedną z funkcji oferowanych przez tę bibliotekę jest możliwość pobrania informacji o właściwościach okna dokumentu. Ten samouczek przeprowadzi Cię przez kolejne etapy korzystania z narzędzia`GetDocumentWindow` funkcja Aspose.PDF dla .NET do pobierania informacji o właściwościach okna dokumentu PDF.

## Krok 1: Zainstaluj Aspose.PDF dla .NET

 Aby używać Aspose.PDF dla .NET w aplikacjach .NET, musisz najpierw zainstalować bibliotekę. Najnowszą wersję biblioteki można pobrać ze strony[Aspose.PDF dla strony pobierania .NET](https://releases.aspose.com/pdf/net).

Po pobraniu biblioteki rozpakuj zawartość pliku ZIP do folderu na swoim komputerze. Następnie będziesz musiał dodać odwołanie do biblioteki DLL Aspose.PDF dla .NET w swoim projekcie .NET.

## Krok 2: Załaduj dokument PDF

Po zainstalowaniu Aspose.PDF dla .NET i dodaniu odniesienia do biblioteki DLL w projekcie .NET możesz rozpocząć korzystanie z`GetDocumentWindow` funkcja pobierania informacji o właściwościach okna dokumentu PDF.

Pierwszym krokiem w korzystaniu z tej funkcji jest załadowanie dokumentu PDF, o którym chcesz pobrać informacje. Aby to zrobić, możesz użyć następującego kodu:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 W powyższym kodzie zamień`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym znajduje się dokument PDF. Ten kod załaduje dokument PDF do pliku`Document` obiekt, którego można następnie użyć do pobrania informacji o właściwościach okna dokumentu.

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

powyższym kodzie każda linia pobiera inną właściwość okna dokumentu PDF i wysyła ją do konsoli. Możesz dostosować ten kod, aby pobrać tylko te właściwości, które Cię interesują.

### Przykładowy kod źródłowy okna pobierania dokumentu z pliku PDF przy użyciu Aspose.PDF dla .NET 

 Oto pełny kod źródłowy umożliwiający pobieranie właściwości okna dokumentu PDF za pomocą pliku`GetDocumentWindow` funkcja Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Uzyskaj różne właściwości dokumentu
// Pozycja okna dokumentu - Domyślnie: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Dominująca kolejność czytania; określa pozycję strony
// Gdy wyświetlane są obok siebie — wartość domyślna: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Określa, czy pasek tytułu okna powinien wyświetlać tytuł dokumentu
// Jeśli fałsz, na pasku tytułu wyświetlana jest nazwa pliku PDF - Domyślnie: fałsz
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Określa, czy zmienić rozmiar okna dokumentu, aby dopasować go do rozmiaru
// Pierwsza wyświetlona strona - Wartość domyślna: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Czy ukryć pasek menu przeglądarki - Domyślnie: fałsz
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Czy ukryć pasek narzędzi przeglądarki - Domyślnie: fałsz
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Określa, czy ukryć elementy interfejsu użytkownika, takie jak paski przewijania
// I pozostawienie tylko wyświetlanej zawartości strony - Domyślnie: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Tryb strony dokumentu. Jak wyświetlić dokument po wyjściu z trybu pełnoekranowego.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Układ strony tj. pojedyncza strona, jedna kolumna
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Jak powinien wyglądać dokument po otwarciu
// Tj. pokaż miniatury, na pełnym ekranie, pokaż panel załączników
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak używać Aspose.PDF dla .NET do pobierania informacji o właściwościach okna dokumentu PDF. Ładując dokument PDF i uzyskując dostęp do właściwości jego okna, można zebrać informacje o tym, jak dokument powinien być wyświetlany po otwarciu w aplikacji przeglądarki. Aspose.PDF dla .NET zapewnia potężny zestaw funkcji do programowej pracy z plikami PDF, co czyni go cennym narzędziem do manipulacji plikami PDF w aplikacjach .NET.

### Często zadawane pytania

#### P: Jaki jest cel pobierania właściwości okna dokumentu PDF?

O: Pobranie właściwości okna dokumentu PDF umożliwia zebranie informacji o tym, jak dokument PDF powinien być wyświetlany po otwarciu w przeglądarce. Te właściwości kontrolują różne aspekty, takie jak położenie okna, tryb wyświetlania i widoczność elementów interfejsu użytkownika.

#### P: Jak mogę zainstalować Aspose.PDF dla .NET w moim projekcie .NET?

 O: Aby zainstalować Aspose.PDF dla .NET, musisz pobrać bibliotekę z[Aspose.PDF dla strony pobierania .NET](https://releases.aspose.com/pdf/net). Po pobraniu wyodrębnij zawartość pliku ZIP i dodaj odniesienie do biblioteki DLL Aspose.PDF dla .NET w swoim projekcie .NET.

#### P: Czy mogę dostosować kod tak, aby pobierał tylko określone właściwości okna?

O: Tak, możesz dostosować kod tak, aby pobierał określone właściwości okna, komentując niepotrzebne linie. Każda linia kodu odpowiada określonej właściwości okna, więc możesz uwzględnić lub wykluczyć właściwości w zależności od wymagań.

#### P: Jakie typy właściwości okien mogę pobrać za pomocą Aspose.PDF dla .NET?

Odp.: Używając Aspose.PDF dla .NET, możesz pobrać różne właściwości okna dokumentu PDF, w tym centrowanie okna, ustawienie układu strony, kontrolowanie wyświetlania pasków narzędzi i pasków menu i wiele więcej.