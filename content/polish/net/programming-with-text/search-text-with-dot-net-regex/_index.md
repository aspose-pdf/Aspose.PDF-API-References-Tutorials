---
title: Wyszukaj tekst za pomocą wyrażenia regularnego Dot Net
linktitle: Wyszukaj tekst za pomocą wyrażenia regularnego Dot Net
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać tekst za pomocą wyrażeń regularnych .NET w dokumencie PDF, korzystając z Aspose.PDF dla platformy .NET.
type: docs
weight: 480
url: /pl/net/programming-with-text/search-text-with-dot-net-regex/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania tekstu za pomocą wyrażeń regularnych .NET w dokumencie PDF. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Aspose.PDF dla biblioteki .NET jest zainstalowany. Możesz go pobrać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentu

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz obiekt .NET Regex

 Utwórz`.NET Regex` obiekt definiujący wzorzec wyszukiwania:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Zastępować`@"[\S]+"` z wybranym przez Ciebie wzorcem wyrażenia regularnego.

## Krok 5: Załaduj dokument PDF

 Załaduj dokument PDF za pomocą`Document` klasa:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Zastępować`"SearchTextRegex.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 6: Uzyskaj konkretną stronę

Pobierz żądaną stronę dokumentu:

```csharp
Page page = document.Pages[1];
```

 Zastępować`1` z żądanym numerem strony (indeks od 1).

## Krok 7: Utwórz TextFragmentAbsorber

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wyrażenia regularnego wejściowego:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Krok 8: Zaakceptuj absorber dla strony

Zaakceptuj absorber dla strony:

```csharp
page.Accept(textFragmentAbsorber);
```

## Krok 9: Pobierz wyodrębnione fragmenty tekstu

 Pobierz wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 10: Przejrzyj fragmenty tekstu

Przejrzyj pobrane fragmenty tekstu i wykonaj żądane czynności:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

W razie potrzeby zmodyfikuj kod w pętli, aby wykonać dalsze działania na każdym fragmencie tekstu.

### Przykładowy kod źródłowy dla wyszukiwania tekstu za pomocą wyrażenia regularnego Dot Net przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt Regex, aby znaleźć wszystkie słowa
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Otwórz dokument
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Uzyskaj konkretną stronę
Page page = document.Pages[1];
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wyrażenia regularnego wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Zaakceptuj absorber dla strony
page.Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać tekst za pomocą wyrażeń regularnych .NET w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od konfiguracji projektu po dostęp do wyodrębnionych fragmentów tekstu. Teraz możesz włączyć ten kod do własnych projektów C#, aby wykonywać zaawansowane wyszukiwania tekstowe w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie tekstu za pomocą wyrażeń regularnych Dot Net”?

A: Samouczek „Search Text With Dot Net Regex” ma na celu poprowadzenie użytkowników przez bibliotekę Aspose.PDF dla .NET do wyszukiwania tekstu w dokumencie PDF przy użyciu wyrażeń regularnych .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C#, aby zademonstrować ten proces.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu tekstu za pomocą wyrażeń regularnych .NET w plikach PDF?

A: Ten samouczek pomaga użytkownikom zrozumieć, jak wykorzystać możliwości Aspose.PDF dla .NET do wyszukiwania tekstu przy użyciu wyrażeń regularnych .NET w dokumencie PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą skutecznie wyszukiwać wzorce tekstowe, które pasują do określonych przez nich wyrażeń regularnych.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi ci to wykorzystanie funkcji biblioteki do wyszukiwania i pracy z dokumentami PDF.

#### P: Czy mogę użyć tego samouczka do wyszukiwania określonego typu tekstu za pomocą wyrażeń regularnych .NET?

 A: Tak, ten samouczek zawiera instrukcje dotyczące wyszukiwania tekstu za pomocą wyrażeń regularnych .NET w dokumencie PDF. Możesz dostosować`.NET Regex` obiekt, aby zdefiniować konkretny wzorzec wyszukiwania, którego chcesz użyć.

#### P: Jak określić wzorzec wyrażenia regularnego .NET, którego będę szukać w tym samouczku?

 A: Aby określić wzorzec wyrażenia regularnego .NET, którego chcesz szukać, utwórz`.NET Regex` obiekt i ustaw jego wzorzec, używając odpowiedniej składni wyrażenia regularnego. Zastąp domyślny`@"[\S]+"` w kodzie samouczka wpisując żądane wyrażenie regularne.

#### P: W jaki sposób mogę pobrać właściwości wyodrębnionych fragmentów tekstu?

 A: Po zaakceptowaniu`TextFragmentAbsorber` dla konkretnej strony pliku PDF możesz pobrać wyodrębnione fragmenty tekstu, korzystając z`TextFragments` właściwość obiektu absorbera. Zapewnia dostęp do kolekcji fragmentów tekstu, które pasują do określonego wyrażenia regularnego .NET.

#### P: Czy mogę dostosować kod tak, aby wykonywał dodatkowe akcje na każdym wyodrębnionym fragmencie tekstu?

A: Oczywiście. Przykładowy kod samouczka zawiera pętlę do iterowania pobranych fragmentów tekstu. Możesz dostosować kod w tej pętli, aby wykonać dodatkowe czynności na każdym wyodrębnionym fragmencie tekstu w oparciu o wymagania projektu.

#### P: Jak zapisać zmodyfikowany dokument PDF po wyodrębnieniu fragmentów tekstu?

A: Ten samouczek koncentruje się głównie na wyszukiwaniu tekstu za pomocą wyrażeń regularnych .NET i pobieraniu fragmentów tekstu. Jeśli zamierzasz dokonać modyfikacji w pliku PDF, możesz zapoznać się z inną dokumentacją Aspose.PDF, aby dowiedzieć się, jak manipulować dokumentem i zapisywać go zgodnie ze swoimi konkretnymi potrzebami.