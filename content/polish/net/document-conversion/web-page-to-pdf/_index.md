---
title: Strona internetowa do pliku PDF
linktitle: Strona internetowa do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji strony internetowej do formatu PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 320
url: /pl/net/document-conversion/web-page-to-pdf/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak przekonwertować stronę internetową do formatu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach. Pod koniec tego samouczka będziesz mógł bez wysiłku konwertować strony internetowe do dokumentów PDF.

## Wstęp
Konwersja stron internetowych do formatu PDF jest powszechnym wymogiem w wielu aplikacjach. Konwertując zawartość internetową do formatu PDF, można łatwo zachować układ, formatowanie i obrazy oryginalnej strony internetowej. Aspose.PDF dla .NET to potężna biblioteka, która pozwala wydajnie i dokładnie przeprowadzić tę konwersję.

## Wymagania
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
- Program Visual Studio zainstalowany na Twoim komputerze
- Biblioteka Aspose.PDF dla .NET (można ją pobrać z oficjalnej strony Aspose)
- Podstawowa znajomość programowania w języku C#


## Krok 1: Zdefiniuj katalog dokumentów
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Zastępować`"YOUR DOCUMENT DIRECTORY"` ze ścieżką, w której chcesz zapisać wygenerowany plik PDF.

## Krok 2: Utwórz żądanie internetowe
```csharp
WebRequest request = WebRequest.Create("https://pl.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Utwórz obiekt żądania internetowego i określ adres URL strony internetowej, którą chcesz przekonwertować. Możesz zastąpić adres URL dowolną żądaną stroną internetową.

## Krok 3: Uzyskaj odpowiedź internetową
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Wyślij żądanie internetowe i pobierz odpowiedź z serwera.

## Krok 4: Przeczytaj zawartość internetową
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Przeczytaj zawartość strony internetowej za pomocą a`StreamReader` przechowuj go w`responseFromServer` zmienny.

## Krok 5: Konwertuj HTML na PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://pl.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Stwórz`MemoryStream` obiekt, aby załadować zawartość strony internetowej. Następnie utwórz instancję`HtmlLoadOptions` i przekazać podstawowy adres URL strony internetowej. Następnie utwórz plik`Document` obiekt przy użyciu załadowanego strumienia i opcji ładowania HTML. Ustaw`IsLandscape` własność do`true` jeśli chcesz, aby plik PDF był w orientacji poziomej. Na koniec zapisz dokument PDF w określonym katalogu

.

## Krok 6: Obsługa wyjątków
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Wyłap wszelkie wyjątki, które mogą wystąpić podczas procesu konwersji i wyświetl komunikat o błędzie.

### Przykładowy kod źródłowy strony internetowej do formatu PDF przy użyciu Aspose.PDF dla .NET

```csharp
try
{
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz żądanie dotyczące adresu URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Jeśli serwer tego wymaga, ustaw poświadczenia.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Limit czasu w milisekundach przed upływem limitu czasu żądania
	// Żądanie. Limit czasu = 100;

	// Uzyskaj odpowiedź.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Pobierz strumień zawierający treść zwróconą przez serwer.
	Stream dataStream = response.GetResponseStream();
	// Otwórz strumień za pomocą StreamReadera, aby uzyskać łatwy dostęp.
	StreamReader reader = new StreamReader(dataStream);
	// Przeczytaj treść.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Załaduj plik HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Zapisz dane wyjściowe w formacie PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek
tym samouczku nauczyliśmy się, jak konwertować stronę internetową do formatu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Przeszliśmy przez przewodnik krok po kroku wyjaśniający dostarczony kod źródłowy C#. Postępując zgodnie z tymi instrukcjami, można łatwo zintegrować funkcję konwersji strony internetowej do formatu PDF z własnymi aplikacjami .NET.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Zapewnia różne funkcjonalności, w tym konwersję stron internetowych do formatu PDF.

#### P: Dlaczego miałbym chcieć przekonwertować stronę internetową do formatu PDF?

O: Konwersja stron internetowych do formatu PDF jest przydatna do zachowania układu, formatowania i obrazów oryginalnej zawartości internetowej. Umożliwia utworzenie migawki strony internetowej do przeglądania w trybie offline lub udostępniania innym.

#### P: Jakie są wymagania wstępne dotyczące tego samouczka?

Odp.: Aby skorzystać z tego samouczka, musisz mieć zainstalowany program Visual Studio na swoim komputerze, bibliotekę Aspose.PDF dla .NET i podstawową wiedzę na temat programowania w języku C#.

#### P: Czy mogę przekonwertować dowolną stronę internetową na format PDF?

Odp.: Tak, możesz przekonwertować dowolną stronę internetową do formatu PDF, podając adres URL strony internetowej w kodzie. Aspose.PDF dla .NET pobierze zawartość internetową i przekonwertuje ją do formatu PDF.

#### P: Jak mogę dostosować wydruk PDF, np. orientację strony?

 Odp.: Możesz dostosować wyjściowy plik PDF, korzystając z opcji takich jak`IsLandscape` aby ustawić orientację strony. W podanym kodzie`options.PageInfo.IsLandscape = true` służy do tworzenia pliku PDF w orientacji poziomej.