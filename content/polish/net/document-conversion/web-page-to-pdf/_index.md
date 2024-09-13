---
title: Strona internetowa do PDF
linktitle: Strona internetowa do PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak konwertować strony internetowe do formatu PDF za pomocą Aspose.PDF dla platformy .NET, korzystając ze szczegółowego samouczka krok po kroku.
type: docs
weight: 320
url: /pl/net/document-conversion/web-page-to-pdf/
---
## Wstęp

W dzisiejszej erze cyfrowej możliwość konwersji stron internetowych na dokumenty PDF jest niezwykle cenna. Niezależnie od tego, czy chcesz zapisać artykuł do czytania offline, utworzyć raport czy zarchiwizować treści z sieci, posiadanie odpowiednich narzędzi może mieć ogromne znaczenie. Jednym z takich narzędzi jest Aspose.PDF dla .NET, potężna biblioteka, która umożliwia programistom bezproblemowe tworzenie i manipulowanie dokumentami PDF. W tym przewodniku przeprowadzimy Cię przez proces konwersji strony internetowej na PDF przy użyciu Aspose.PDF dla .NET, dzieląc go na łatwe do opanowania kroki.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć:

1. Visual Studio: Upewnij się, że masz zainstalowany Visual Studio na swoim komputerze. Tutaj będziesz pisać i wykonywać swój kod .NET.
2.  Aspose.PDF dla .NET: Będziesz potrzebować biblioteki Aspose.PDF. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć przykłady.
4. Dostęp do Internetu: Ponieważ będziemy pobierać zawartość ze strony internetowej, upewnij się, że Twoje środowisko programistyczne ma dostęp do Internetu.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety do swojego projektu C#. Oto jak to zrobić:

### Utwórz nowy projekt

Najpierw otwórz program Visual Studio i utwórz nowy projekt aplikacji konsolowej w języku C#. 

### Dodaj odniesienie Aspose.PDF

Następnie dodaj odwołanie do biblioteki Aspose.PDF. Możesz to zrobić za pomocą NuGet Package Manager:

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i kliknij „Zainstaluj”.

### Importuj wymagane przestrzenie nazw

 Po dodaniu biblioteki otwórz ją`Program.cs` plik i zaimportuj niezbędne przestrzenie nazw na górze pliku:

```csharp
using System.IO;
using System;
using System.Net;
using Aspose.Pdf;
```

Teraz, gdy wszystko już skonfigurowaliśmy, możemy omówić krok po kroku proces konwersji strony internetowej do dokumentu PDF.

## Krok 1: Zdefiniuj katalog dokumentów

Najpierw musisz określić, gdzie zostanie zapisany wyjściowy plik PDF. Można to zrobić, podając ścieżkę do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zastąp swoją ścieżką
```

## Krok 2: Utwórz żądanie internetowe

Następnie musisz utworzyć żądanie pobrania zawartości ze strony internetowej, którą chcesz przekonwertować. Oto, jak to zrobić:

```csharp
WebRequest request = WebRequest.Create("https://pl.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```

W tym kodzie tworzymy żądanie do strony głównej Wikipedii. Możesz zastąpić adres URL dowolną wybraną przez siebie stroną internetową.

## Krok 3: Uzyskaj odpowiedź

Po skonfigurowaniu żądania nadszedł czas na otrzymanie odpowiedzi z serwera. Wiąże się to z wysłaniem żądania i odczytaniem strumienia odpowiedzi:

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

Tutaj odczytujemy całą zawartość zwróconą przez serwer do zmiennej typu string. To jest zawartość, którą przekonwertujemy do formatu PDF.

## Krok 4: Załaduj zawartość HTML do pamięci

Teraz, gdy mamy już zawartość HTML, musimy ją załadować do`MemoryStream` abyśmy mogli przetworzyć go za pomocą Aspose.PDF:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://pl.wikipedia.org/wiki/");
```

 W tym kroku konwertujemy odpowiedź w postaci ciągu na tablicę bajtów i ładujemy ją do`MemoryStream` . Ten`HtmlLoadOptions` pozwala nam określić bazowy adres URL dla wszelkich linków względnych w HTML.

## Krok 5: Utwórz dokument PDF

Po załadowaniu zawartości HTML możemy utworzyć z niej dokument PDF:

```csharp
Document pdfDocument = new Document(stream, options);
```

 Ta linia kodu inicjuje nowy`Document` obiekt, który reprezentuje plik PDF, który zamierzamy utworzyć.

## Krok 6: Ustaw orientację strony

Jeśli chcesz dostosować układ pliku PDF, np. ustawić go w trybie poziomym, możesz to zrobić za pomocą następującego kodu:

```csharp
options.PageInfo.IsLandscape = true;
```

Jest to opcjonalne, ale może być przydatne w zależności od konwertowanej zawartości.

## Krok 7: Zapisz plik PDF

Na koniec pora zapisać dokument PDF w wybranym katalogu:

```csharp
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```

 Ten wiersz zapisuje plik PDF pod nazwą`WebPageToPDF_out.pdf` w określonym przez Ciebie katalogu dokumentów.

## Krok 8: Obsługa wyjątków

Zawsze dobrą praktyką jest obsługa wyjątków, które mogą wystąpić w trakcie procesu. Możesz opakować swój kod w blok try-catch:

```csharp
try
{
    // Cały poprzedni kod tutaj
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

Dzięki temu, jeśli coś pójdzie nie tak, otrzymasz komunikat informujący o tym, co się stało.

## Wniosek

I masz! Udało Ci się przekonwertować stronę internetową do pliku PDF za pomocą Aspose.PDF dla .NET. Za pomocą zaledwie kilku linijek kodu możesz zautomatyzować proces zapisywania treści internetowych do późniejszego wykorzystania. Może to być niezwykle przydatne dla programistów, którzy chcą tworzyć raporty, archiwa lub po prostu zapisywać artykuły do czytania offline. 

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów PDF.

### Czy mogę przekonwertować dowolną stronę internetową do formatu PDF?
Tak, o ile strona internetowa jest publicznie dostępna, możesz ją przekonwertować do formatu PDF za pomocą Aspose.PDF.

### Czy jest dostępna bezpłatna wersja próbna?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.PDF dla .NET ze strony[Tutaj](https://releases.aspose.com/).

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.PDF?
 Możesz uzyskać wsparcie od społeczności Aspose na ich stronie[forum wsparcia](https://forum.aspose.com/c/pdf/10).

### Jak mogę uzyskać tymczasową licencję?
 Możesz złożyć wniosek o tymczasową licencję na[Strona internetowa Aspose](https://purchase.aspose.com/temporary-license/).