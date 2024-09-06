---
title: Podaj dane uwierzytelniające podczas konwersji HTML na PDF
linktitle: Podaj dane uwierzytelniające podczas konwersji HTML na PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak konwertować HTML do PDF za pomocą Aspose.PDF dla .NET dzięki temu przewodnikowi krok po kroku. Idealne dla programistów, którzy chcą usprawnić generowanie dokumentów.
type: docs
weight: 240
url: /pl/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Wstęp

W świecie rozwoju oprogramowania konwersja HTML do PDF jest powszechnym wymogiem. Niezależnie od tego, czy generujesz raporty, faktury czy jakikolwiek inny dokument, posiadanie niezawodnej biblioteki do obsługi tego zadania może zaoszczędzić Ci dużo czasu i wysiłku. Wprowadź Aspose.PDF dla .NET, potężną bibliotekę, która pozwala programistom na łatwe tworzenie, manipulowanie i konwertowanie dokumentów PDF. W tym samouczku przeprowadzimy Cię przez proces używania Aspose.PDF do konwersji HTML do PDF, zapewniając jednocześnie poświadczenia dla bezpiecznego dostępu. Więc chwyć swój kapelusz kodera i zanurzmy się!

## Wymagania wstępne

Zanim zaczniemy, jest kilka rzeczy, które musisz mieć na miejscu:

1. Visual Studio: Upewnij się, że masz zainstalowane Visual Studio na swoim komputerze. To będzie nasze środowisko programistyczne.
2.  Aspose.PDF dla .NET: Bibliotekę można pobrać ze strony[strona internetowa](https://releases.aspose.com/pdf/net/) . Jeśli chcesz najpierw spróbować, możesz również uzyskać[bezpłatny okres próbny](https://releases.aspose.com/).
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć przykłady.
4. Dostęp do Internetu: Ponieważ będziemy pobierać zawartość HTML z adresu URL, upewnij się, że masz aktywne połączenie z Internetem.

## Importuj pakiety

Aby rozpocząć pracę z Aspose.PDF, musisz zaimportować niezbędne pakiety do swojego projektu. Oto, jak możesz to zrobić:

1. Otwórz projekt programu Visual Studio.
2. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i zainstaluj najnowszą wersję.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Teraz, gdy wszystko już skonfigurowaliśmy, możemy podzielić proces konwersji pliku HTML na PDF z danymi uwierzytelniającymi na mniejsze, łatwiejsze do wykonania kroki.

## Krok 1: Skonfiguruj katalog dokumentów

Zanim będziemy mogli przekonwertować HTML na PDF, musimy określić, gdzie nasz wyjściowy PDF zostanie zapisany. Robimy to, definiując ścieżkę do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać plik PDF. Może to być folder na pulpicie lub dowolna inna lokalizacja w systemie.

## Krok 2: Utwórz żądanie internetowe

 Następnie musimy utworzyć żądanie pobrania zawartości HTML z określonego adresu URL. Tutaj użyjemy`WebRequest` klasa.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Tutaj tworzymy żądanie do adresu URL zawierającego kod HTML, który chcemy przekonwertować. Upewnij się, że zastąpisz adres URL tym, którego zamierzasz użyć.

## Krok 3: Ustaw dane uwierzytelniające (jeśli wymagane)

Jeśli serwer wymaga danych uwierzytelniających, aby uzyskać dostęp do treści, musimy je ustawić. Robi się to za pomocą`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Ten wiersz zapewnia, że żądanie używa domyślnych poświadczeń bieżącego użytkownika. Jeśli musisz podać konkretne poświadczenia, możesz utworzyć nowe`NetworkCredential` obiekt.

## Krok 4: Uzyskaj odpowiedź

Teraz, gdy skonfigurowaliśmy nasze żądanie, pora na uzyskanie odpowiedzi z serwera.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Ta linia wysyła żądanie i czeka na odpowiedź serwera. Jeśli wszystko pójdzie dobrze, otrzymamy potrzebną nam zawartość HTML.

## Krok 5: Odczytaj strumień odpowiedzi

 Gdy już otrzymamy odpowiedź, musimy odczytać treść zwróconą przez serwer. Robi się to za pomocą`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Tutaj odczytujemy całą zawartość strumienia odpowiedzi do zmiennej ciągu o nazwie`responseFromServer`. Nie zapomnij zamknąć czytnika i strumienia, aby zwolnić zasoby.

## Krok 6: Konwersja HTML do PDF

Teraz nadchodzi ekscytująca część! Przekonwertujemy zawartość HTML na dokument PDF za pomocą Aspose.PDF.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://Mój.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

 tym kroku tworzymy`MemoryStream` z zawartości HTML i konfiguracji`HtmlLoadOptions`. Pozwala nam to określić bazowy adres URL dla wszelkich zasobów zewnętrznych (takich jak obrazy lub arkusze stylów), do których może odwoływać się kod HTML.

## Krok 7: Zapisz dokument PDF

Na koniec musimy zapisać wygenerowany dokument PDF w określonym katalogu.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Ten wiersz zapisuje plik PDF pod nazwą`ProvideCredentialsDuringHTMLToPDF_out.pdf` w katalogu, który określiliśmy wcześniej.

## Wniosek

I masz! Udało Ci się przekonwertować HTML na PDF za pomocą Aspose.PDF dla .NET, podając jednocześnie poświadczenia dla bezpiecznego dostępu. Ta potężna biblioteka ułatwia obsługę dokumentów PDF, a za pomocą zaledwie kilku linijek kodu możesz generować profesjonalnie wyglądające pliki PDF z treści HTML. 

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF for .NET to biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Jak zainstalować Aspose.PDF?
 Możesz zainstalować Aspose.PDF za pomocą Menedżera pakietów NuGet w programie Visual Studio lub pobrać go ze strony[strona internetowa](https://releases.aspose.com/pdf/net/).

### Czy mogę używać Aspose.PDF bezpłatnie?
Tak, Aspose oferuje bezpłatną wersję próbną, dzięki której możesz sprawdzić bibliotekę przed zakupem.

### Jakie typy dokumentów mogę tworzyć za pomocą Aspose.PDF?
Za pomocą Aspose.PDF można tworzyć szeroką gamę dokumentów, w tym raporty, faktury i formularze.

### Gdzie mogę znaleźć pomoc dotyczącą Aspose.PDF?
 Wsparcie i zadawanie pytań można znaleźć na stronie[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10).