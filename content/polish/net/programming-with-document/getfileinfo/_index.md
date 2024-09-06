---
title: Pobierz informacje o pliku w pliku PDF
linktitle: Pobierz informacje o pliku w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać funkcji GetFileInfo w pliku PDF programu Aspose.PDF dla platformy .NET, aby pobierać metadane dotyczące dokumentu PDF.
type: docs
weight: 180
url: /pl/net/programming-with-document/getfileinfo/
---
 Aspose.PDF dla .NET to popularna biblioteka do manipulacji PDF, która umożliwia programistom tworzenie, edytowanie i konwertowanie plików PDF w ich aplikacjach .NET. Jedną z funkcji oferowanych przez tę bibliotekę jest możliwość pobierania informacji o metadanych dokumentu PDF. Ten samouczek przeprowadzi Cię przez kroki korzystania z`GetFileInfo` Funkcja Aspose.PDF dla platformy .NET umożliwiająca pobieranie informacji o metadanych dokumentu PDF.

## Krok 1: Zainstaluj Aspose.PDF dla .NET

 Aby użyć Aspose.PDF dla .NET w aplikacjach .NET, musisz najpierw zainstalować bibliotekę. Najnowszą wersję biblioteki możesz pobrać ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net).

Po pobraniu biblioteki wypakuj zawartość pliku ZIP do folderu na swoim komputerze. Następnie musisz dodać odwołanie do Aspose.PDF dla .NET DLL w swoim projekcie .NET.

## Krok 2: Załaduj dokument PDF

 Po zainstalowaniu Aspose.PDF dla .NET i dodaniu odwołania do biblioteki DLL w projekcie .NET możesz rozpocząć korzystanie z`GetFileInfo` funkcja umożliwiająca pobieranie informacji o metadanych dokumentu PDF.

Pierwszym krokiem w korzystaniu z tej funkcji jest załadowanie dokumentu PDF, o którym chcesz uzyskać informacje. Aby to zrobić, możesz użyć następującego kodu:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 W powyższym kodzie zamień`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym znajduje się Twój dokument PDF. Ten kod załaduje dokument PDF do`Document` obiekt, którego można następnie użyć do pobrania informacji o metadanych dokumentu.

## Krok 3: Pobierz metadane dokumentu

Aby pobrać informacje o metadanych dokumentu PDF, możesz skorzystać z następującego kodu:

```csharp
// Uzyskaj informacje o dokumencie
DocumentInfo docInfo = pdfDocument.Info;

// Pokaż informacje o dokumencie
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

W powyższym kodzie każdy wiersz pobiera inną właściwość metadanych dokumentu PDF i wyprowadza ją do konsoli. Możesz dostosować ten kod, aby pobrać tylko właściwości, które Cię interesują.

### Przykładowy kod źródłowy pobiera informacje o pliku PDF za pomocą Aspose.PDF dla .NET

 Oto pełny kod źródłowy umożliwiający pobranie metadanych dokumentu PDF za pomocą`GetFileInfo` funkcja Aspose.PDF dla .NET:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Uzyskaj informacje o dokumencie
DocumentInfo docInfo = pdfDocument.Info;

// Pokaż informacje o dokumencie
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Wniosek

tym samouczku omówiliśmy, jak używać Aspose.PDF dla .NET do pobierania informacji o metadanych dokumentu PDF. Ładując dokument PDF i uzyskując dostęp do jego właściwości metadanych, możesz zebrać informacje o cechach i właściwościach dokumentu. Aspose.PDF dla .NET zapewnia proste i łatwe w użyciu API do pracy z dokumentami PDF, w tym pobierania informacji o metadanych, co czyni go cennym narzędziem do manipulacji PDF w aplikacjach .NET.

### Najczęściej zadawane pytania

#### P: Czym są metadane w dokumencie PDF?

A: Metadane w dokumencie PDF odnoszą się do informacji opisujących właściwości i cechy dokumentu. Informacje te zazwyczaj obejmują tytuł dokumentu, autora, temat, słowa kluczowe, datę utworzenia, datę modyfikacji i inne.

#### P: Jak mogę zainstalować Aspose.PDF dla .NET w moim projekcie .NET?

 A: Aby zainstalować Aspose.PDF dla .NET, należy pobrać bibliotekę ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net). Po pobraniu wyodrębnij zawartość pliku ZIP i dodaj odwołanie do pliku Aspose.PDF dla biblioteki DLL .NET w swoim projekcie .NET.

#### P: Czy mogę dostosować kod tak, aby pobierał tylko określone właściwości metadanych?

A: Tak, możesz dostosować kod, aby pobrać określone właściwości metadanych, komentując wiersze, których nie potrzebujesz. Każdy wiersz w kodzie odpowiada określonej właściwości metadanych, więc możesz uwzględnić lub wykluczyć właściwości w zależności od swoich wymagań.

#### P: Jakie typy właściwości metadanych mogę pobrać za pomocą Aspose.PDF dla .NET?

A: Używając Aspose.PDF dla platformy .NET, można pobrać różne właściwości metadanych dokumentu PDF, w tym autora, tytuł, temat, słowa kluczowe, datę utworzenia oraz datę modyfikacji.