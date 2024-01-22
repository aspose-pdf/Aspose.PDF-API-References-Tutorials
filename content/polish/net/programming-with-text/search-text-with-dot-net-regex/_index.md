---
title: Wyszukaj tekst za pomocą wyrażenia regularnego Dot Net
linktitle: Wyszukaj tekst za pomocą wyrażenia regularnego Dot Net
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać tekst przy użyciu wyrażeń regularnych .NET w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 480
url: /pl/net/programming-with-text/search-text-with-dot-net-regex/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania tekstu przy użyciu wyrażeń regularnych .NET w dokumencie PDF. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

## Warunki wstępne

Przed kontynuowaniem samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentów

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz obiekt Regex .NET

 Stwórz`.NET Regex` obiekt do zdefiniowania wzorca wyszukiwania:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Zastępować`@"[\S]+"` z żądanym wzorcem wyrażenia regularnego.

## Krok 5: Załaduj dokument PDF

 Załaduj dokument PDF za pomocą`Document` klasa:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Zastępować`"SearchTextRegex.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 6: Uzyskaj konkretną stronę

Uzyskaj żądaną stronę dokumentu:

```csharp
Page page = document.Pages[1];
```

 Zastępować`1` z żądanym numerem strony (indeks od 1).

## Krok 7: Utwórz TextFragmentAbsorber

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wejściowego wyrażenia regularnego:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Krok 8: Zaakceptuj pochłaniacz dla strony

Zaakceptuj absorber dla strony:

```csharp
page.Accept(textFragmentAbsorber);
```

## Krok 9: Pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą metody`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 10: Przejrzyj fragmenty tekstu w pętli

Przejrzyj pobrane fragmenty tekstu w pętli i wykonaj żądane czynności:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Zmodyfikuj kod w pętli, aby w razie potrzeby wykonać dalsze działania na każdym fragmencie tekstu.

### Przykładowy kod źródłowy dla tekstu wyszukiwania za pomocą wyrażenia regularnego Dot Net przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt Regex, aby znaleźć wszystkie słowa
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Otwórz dokument
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Uzyskaj konkretną stronę
Page page = document.Pages[1];
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wejściowego wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Zaakceptuj pochłaniacz dla strony
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

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać tekst przy użyciu wyrażeń regularnych .NET w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od skonfigurowania projektu po uzyskanie dostępu do wyodrębnionych fragmentów tekstu. Możesz teraz włączyć ten kod do własnych projektów C#, aby przeprowadzać zaawansowane wyszukiwanie tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie tekstu za pomocą wyrażenia regularnego Dot Net”?

O: Samouczek „Wyszukaj tekst za pomocą Dot Net Regex” ma na celu poinstruowanie użytkowników, jak używać biblioteki Aspose.PDF dla platformy .NET do wyszukiwania tekstu w dokumencie PDF przy użyciu wyrażeń regularnych platformy .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C# demonstrujące proces.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu tekstu przy użyciu wyrażeń regularnych .NET w pliku PDF?

Odp.: Ten samouczek pomaga użytkownikom zrozumieć, jak wykorzystać możliwości Aspose.PDF dla .NET do wyszukiwania tekstu przy użyciu wyrażeń regularnych .NET w dokumencie PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą skutecznie wyszukiwać wzorce tekstowe pasujące do określonych wyrażeń regularnych.

#### P: Jakie wymagania wstępne są wymagane, aby móc skorzystać z tego samouczka?

Odp.: Przed rozpoczęciem samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi to wykorzystanie funkcji biblioteki do wyszukiwania i pracy z dokumentami PDF.

#### P: Czy mogę skorzystać z tego samouczka, aby wyszukać dowolny konkretny typ tekstu za pomocą wyrażeń regularnych .NET?

 O: Tak, ten samouczek zawiera instrukcje dotyczące wyszukiwania tekstu przy użyciu wyrażeń regularnych .NET w dokumencie PDF. Możesz dostosować`.NET Regex` obiekt, aby zdefiniować konkretny wzorzec wyszukiwania, którego chcesz użyć.

#### P: Jak określić wzorzec wyrażeń regularnych .NET, który będzie wyszukiwany w tym samouczku?

 O: Aby określić wzorzec wyrażenia regularnego .NET, który chcesz wyszukać, utwórz plik`.NET Regex` obiekt i ustaw jego wzorzec, używając odpowiedniej składni wyrażeń regularnych. Zastąp domyślny`@"[\S]+"` w kodzie samouczka żądanym wyrażeniem regularnym.

#### P: Jak odzyskać właściwości wyodrębnionych fragmentów tekstu?

 Odp.: Po zaakceptowaniu`TextFragmentAbsorber` w przypadku określonej strony pliku PDF możesz pobrać wyodrębnione fragmenty tekstu za pomocą`TextFragments` właściwość obiektu absorbera. Zapewnia to dostęp do kolekcji fragmentów tekstu pasujących do określonego wyrażenia regularnego .NET.

#### P: Czy mogę dostosować kod, aby wykonywać dodatkowe działania na każdym wyodrębnionym fragmencie tekstu?

O: Oczywiście. Przykładowy kod samouczka zawiera pętlę umożliwiającą iterację pobranych fragmentów tekstu. Możesz dostosować kod w tej pętli, aby wykonać dodatkowe działania na każdym wyodrębnionym fragmencie tekstu w oparciu o wymagania projektu.

#### P: Jak zapisać zmodyfikowany dokument PDF po wyodrębnieniu fragmentów tekstu?

Odp.: Ten samouczek koncentruje się głównie na wyszukiwaniu tekstu przy użyciu wyrażeń regularnych .NET i pobieraniu fragmentów tekstu. Jeśli zamierzasz dokonać modyfikacji w pliku PDF, możesz zapoznać się z inną dokumentacją Aspose.PDF, aby dowiedzieć się, jak manipulować i zapisywać dokument w zależności od konkretnych potrzeb.