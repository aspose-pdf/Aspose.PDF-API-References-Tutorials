---
title: Uzyskaj informacje o pliku w pliku PDF
linktitle: Uzyskaj informacje o pliku w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak korzystać z funkcji GetFileInfo w pliku PDF w Aspose.PDF dla .NET, aby pobrać informacje o metadanych o dokumencie PDF.
type: docs
weight: 180
url: /pl/net/programming-with-document/getfileinfo/
---
 Aspose.PDF dla .NET to popularna biblioteka do manipulacji plikami PDF, która umożliwia programistom tworzenie, edytowanie i konwertowanie plików PDF w aplikacjach .NET. Jedną z funkcji oferowanych przez tę bibliotekę jest możliwość pobierania informacji o metadanych dokumentu PDF. Ten samouczek przeprowadzi Cię przez kolejne etapy korzystania z narzędzia`GetFileInfo` funkcja Aspose.PDF dla .NET do pobierania informacji o metadanych dokumentu PDF.

## Krok 1: Zainstaluj Aspose.PDF dla .NET

 Aby używać Aspose.PDF dla .NET w aplikacjach .NET, musisz najpierw zainstalować bibliotekę. Najnowszą wersję biblioteki można pobrać ze strony[Aspose.PDF dla strony pobierania .NET](https://releases.aspose.com/pdf/net).

Po pobraniu biblioteki rozpakuj zawartość pliku ZIP do folderu na swoim komputerze. Następnie będziesz musiał dodać odwołanie do biblioteki DLL Aspose.PDF dla .NET w swoim projekcie .NET.

## Krok 2: Załaduj dokument PDF

Po zainstalowaniu Aspose.PDF dla .NET i dodaniu odniesienia do biblioteki DLL w projekcie .NET możesz rozpocząć korzystanie z`GetFileInfo` funkcja pobierania informacji o metadanych dokumentu PDF.

Pierwszym krokiem w korzystaniu z tej funkcji jest załadowanie dokumentu PDF, o którym chcesz pobrać informacje. Aby to zrobić, możesz użyć następującego kodu:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 W powyższym kodzie zamień`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym znajduje się dokument PDF. Ten kod załaduje dokument PDF do pliku`Document` obiekt, którego można następnie użyć do pobrania informacji o metadanych dokumentu.

## Krok 3: Pobierz metadane dokumentu

Aby pobrać informacje o metadanych dokumentu PDF, możesz użyć następującego kodu:

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

W powyższym kodzie każda linia pobiera inną właściwość metadanych dokumentu PDF i wysyła ją do konsoli. Możesz dostosować ten kod, aby pobrać tylko te właściwości, które Cię interesują.

### Przykładowy kod źródłowy pobiera informacje o pliku PDF przy użyciu Aspose.PDF dla .NET

 Oto pełny kod źródłowy umożliwiający pobieranie metadanych dokumentu PDF za pomocą narzędzia`GetFileInfo` funkcja Aspose.PDF dla .NET:

```csharp
// Ścieżka do dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otwórz dokument PDF
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

tym samouczku omówiliśmy, jak używać Aspose.PDF dla .NET do pobierania informacji o metadanych dokumentu PDF. Ładując dokument PDF i uzyskując dostęp do jego właściwości metadanych, można zebrać informacje o charakterystyce i właściwościach dokumentu. Aspose.PDF dla .NET zapewnia prosty i łatwy w użyciu interfejs API do pracy z dokumentami PDF, w tym do pobierania informacji o metadanych, co czyni go cennym narzędziem do manipulacji plikami PDF w aplikacjach .NET.

### Często zadawane pytania

#### P: Czym są metadane w dokumencie PDF?

Odp.: Metadane w dokumencie PDF odnoszą się do informacji opisujących właściwości i cechy dokumentu. Informacje te zazwyczaj obejmują tytuł dokumentu, autora, temat, słowa kluczowe, datę utworzenia, datę modyfikacji i inne.

#### P: Jak mogę zainstalować Aspose.PDF dla .NET w moim projekcie .NET?

 O: Aby zainstalować Aspose.PDF dla .NET, musisz pobrać bibliotekę z[Aspose.PDF dla strony pobierania .NET](https://releases.aspose.com/pdf/net). Po pobraniu wyodrębnij zawartość pliku ZIP i dodaj odniesienie do biblioteki DLL Aspose.PDF dla .NET w swoim projekcie .NET.

#### P: Czy mogę dostosować kod tak, aby pobierał tylko określone właściwości metadanych?

O: Tak, możesz dostosować kod tak, aby pobierał określone właściwości metadanych, komentując niepotrzebne wiersze. Każda linia kodu odpowiada określonej właściwości metadanych, więc możesz uwzględnić lub wykluczyć właściwości w zależności od wymagań.

#### P: Jakie typy właściwości metadanych mogę pobrać za pomocą Aspose.PDF dla .NET?

Odp.: Używając Aspose.PDF dla .NET, możesz pobrać różne właściwości metadanych dokumentu PDF, w tym autora, tytuł, temat, słowa kluczowe, datę utworzenia i datę modyfikacji.