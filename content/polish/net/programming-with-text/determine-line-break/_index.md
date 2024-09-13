---
title: Określ podział wiersza w pliku PDF
linktitle: Określ podział wiersza w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak określić podziały wierszy w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 130
url: /pl/net/programming-with-text/determine-line-break/
---
Ten samouczek przeprowadzi Cię przez proces określania podziałów wierszy w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz określić podziały wierszy, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nową instancję dokumentu
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Dodaj fragmenty tekstu z podziałem wiersza
Utwórz pętlę, aby dodać do strony wiele fragmentów tekstu, z których każdy będzie zawierał akapit z podziałem wiersza.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Krok 7: Zapisz dokument PDF i wyodrębnij informacje o podziale wiersza
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Następnie wyodrębnij informacje o podziale wiersza za pomocą`GetNotifications` metoda żądanej strony.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Przykładowy kod źródłowy dla funkcji Określ podział wiersza za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Wniosek
Udało Ci się ustalić podziały wierszy w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Informacje o podziale wierszy zostały wyodrębnione i zapisane w pliku tekstowym.

### Najczęściej zadawane pytania

#### P: Na czym głównie skupia się ten samouczek?

A: Ten samouczek koncentruje się na przeprowadzeniu Cię przez proces określania podziałów wierszy w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby to osiągnąć.

#### P: Jakie przestrzenie nazw powinienem zaimportować na potrzeby tego samouczka?

A: W pliku kodu, w którym chcesz określić podziały wierszy, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć nową instancję dokumentu?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając dostarczonego kodu.

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja.

#### P: Jak dodać fragmenty tekstu z podziałem wiersza?

A: W kroku 6 utworzysz pętlę, aby dodać do strony wiele fragmentów tekstu, z których każdy będzie zawierał akapit z podziałami wiersza.

#### P: Jak zapisać dokument PDF i wyodrębnić informacje o podziale wiersza?

 A: W kroku 7 zapiszesz dokument PDF za pomocą`Save` metoda`Document` obiekt. Następnie wyodrębnisz informacje o podziale wiersza za pomocą`GetNotifications` metodę wybranej strony i zapisać ją do pliku tekstowego.

#### P: Jaki jest cel wyodrębnionych informacji o podziale wiersza?

A: Wyodrębnione informacje o podziale wiersza zawierają szczegóły dotyczące podziałów wiersza i powiadomień obecnych w dokumencie PDF. Może to być przydatne do analizy i zrozumienia, w jaki sposób tekst i akapity są ustrukturyzowane w dokumencie.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak określić podziały wierszy w dokumencie PDF za pomocą Aspose.PDF dla .NET. Możesz użyć tej wiedzy, aby programowo wyodrębnić i przeanalizować informacje o podziałach wierszy z plików PDF.