---
title: Podaj dane uwierzytelniające podczas HTML do formatu PDF
linktitle: Podaj dane uwierzytelniające podczas HTML do formatu PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji HTML do formatu PDF poprzez podanie poświadczeń w Aspose.PDF dla .NET.
type: docs
weight: 240
url: /pl/net/document-conversion/provide-credentials-during-html-to-pdf/
---
tym samouczku przeprowadzimy Cię przez proces konwersji pliku HTML do formatu PDF, jednocześnie podając dane uwierzytelniające podczas uzyskiwania dostępu do bezpiecznego adresu URL za pomocą Aspose.PDF dla .NET. Wykonując poniższe kroki, będziesz mógł przekonwertować treść HTML na format PDF przy użyciu odpowiednich poświadczeń.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Pobierz bezpieczną zawartość HTML
Na tym etapie pobierzemy bezpieczną treść HTML z adresu URL przy użyciu odpowiednich danych uwierzytelniających. Użyj następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz żądanie dotyczące adresu URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Jeśli jest to wymagane dla serwera, ustaw poświadczenia.
request.Credentials = CredentialCache.DefaultCredentials;
// Uzyskaj odpowiedź.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Pobierz strumień zawierający treść zwróconą przez serwer.
Stream dataStream = response. GetResponseStream();
// Otwórz strumień za pomocą StreamReadera, aby uzyskać łatwy dostęp.
StreamReader reader = new StreamReader(dataStream);
// Przeczytaj treść.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym chcesz zapisać wynikowy plik PDF.

## Krok 2: Konwertuj HTML na PDF, podając dane uwierzytelniające
Teraz załadujemy pobraną treść HTML i przekonwertujemy ją do formatu PDF, podając odpowiednie dane uwierzytelniające. Użyj następującego kodu:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Mój.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Załaduj plik HTML
Document pdfDocument = new Document(stream, options);
```

## Krok 3: Zapisanie wynikowego pliku PDF
Na koniec zapiszemy powstały plik PDF. Użyj następującego kodu:

```csharp
// Zapisz wynikowy plik PDF
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Powyższy kod zapisuje wynikowy plik PDF z nazwą pliku`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Przykładowy kod źródłowy dla podawania poświadczeń podczas HTML do formatu PDF przy użyciu Aspose.PDF dla .NET

```csharp
try
{
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Utwórz żądanie dotyczące adresu URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Jeśli serwer tego wymaga, ustaw poświadczenia.
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Mój.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Załaduj plik HTML
	Document pdfDocument = new Document(stream, options);
	// Zapisz wynikowy plik
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek
tym samouczku omówiliśmy krok po kroku proces konwersji pliku HTML do formatu PDF, jednocześnie podając dane uwierzytelniające podczas uzyskiwania dostępu do bezpiecznego adresu URL za pomocą Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, będziesz mógł pomyślnie przekonwertować zawartość HTML na format PDF, podając jednocześnie prawidłowe dane uwierzytelniające.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to solidna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Oferuje szeroką gamę funkcjonalności, w tym konwersję HTML do PDF.

#### P: Jak mogę pobrać bezpieczną treść HTML z adresu URL?

 O: Aby pobrać bezpieczną zawartość HTML z adresu URL, możesz użyć metody`WebRequest` klasa w języku C#. Upewnij się, że ustawiłeś odpowiednie poświadczenia za pomocą`Credentials` nieruchomość.

#### P: Jakie są wymagania wstępne dotyczące tego samouczka?

O: Przed kontynuowaniem samouczka upewnij się, że spełnione są następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

#### P: W jaki sposób Aspose.PDF dla .NET obsługuje zasoby zewnętrzne podczas konwersji HTML na PDF?

 Odp.: Aspose.PDF dla .NET zapewnia`HtmlLoadOptions`klasa do obsługi zasobów zewnętrznych podczas konwersji HTML na PDF. Możesz ustawić poświadczenia zasobów zewnętrznych za pomocą`ExternalResourcesCredentials` nieruchomość.

#### P: Czy mogę dostosować nazwę wynikowego pliku PDF?

 O: Tak, możesz dostosować nazwę wynikowego pliku PDF, modyfikując kod, który zapisuje dokument PDF. Po prostu zmień żądaną nazwę pliku w`pdfDocument.Save()` metoda.