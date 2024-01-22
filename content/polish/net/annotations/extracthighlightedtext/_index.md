---
title: Wyodrębnij zaznaczony tekst w pliku PDF
linktitle: Wyodrębnij zaznaczony tekst w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić zaznaczony tekst z pliku PDF przy użyciu Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 60
url: /pl/net/annotations/extracthighlightedtext/
---
Aby wyodrębnić zaznaczony tekst w pliku PDF, możesz użyć Aspose.PDF dla .NET API. Ten interfejs API zapewnia prosty sposób pobrania całego tekstu, który został wyróżniony w dokumencie.

## Krok 1: Załaduj dokument PDF

 Pierwszym krokiem w wyodrębnieniu wyróżnionego tekstu z pliku PDF jest załadowanie dokumentu przy użyciu interfejsu API Aspose.PDF dla .NET. Można to zrobić, tworząc nową instancję pliku`Document` class i przekazanie ścieżki do dokumentu PDF jako parametru. 

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Krok 2: Przejrzyj wszystkie adnotacje w pętli

 Następnym krokiem jest przejrzenie wszystkich adnotacji w dokumencie PDF. Można to zrobić za pomocą a`foreach` pętla, tak:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Kod trafia tutaj
}
```

## Krok 3: Filtruj adnotacje znaczników tekstowych

 W środku`foreach` pętli, będziesz musiał odfiltrować wszystkie adnotacje, które nie są adnotacjami ze znacznikami tekstowymi. Można to zrobić, sprawdzając, czy adnotacja jest instancją klasy`TextMarkupAnnotation` klasa.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Kod trafia tutaj
}
```

## Krok 4: Pobierz zaznaczone fragmenty tekstu

 Po odfiltrowaniu wszystkich adnotacji znaczników tekstowych możesz pobrać wyróżnione fragmenty tekstu dla każdej adnotacji. Można to zrobić dzwoniąc pod nr`GetMarkedTextFragments()` metoda na`TextMarkupAnnotation` obiekt.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Krok 5: Wyświetl podświetlony tekst

 Na koniec możesz wyświetlić użytkownikowi zaznaczony tekst. Można to zrobić, przechodząc przez każdy z nich`TextFragment` obiekt w`TextFragmentCollection` i dzwonienie do`Text` nieruchomość.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Przykładowy kod źródłowy dla wyodrębnienia wyróżnionego tekstu przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Wniosek

W tym samouczku omówiliśmy, jak wyodrębnić zaznaczony tekst z dokumentu PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo wyodrębniać wyróżniony tekst z dokumentów PDF i zarządzać nim.

### Często zadawane pytania dotyczące wyodrębniania zaznaczonego tekstu w pliku PDF

#### P: Czym są adnotacje ze znacznikami tekstowymi w dokumencie PDF?

Odp.: Adnotacje ze znacznikami tekstowymi to adnotacje, które podkreślają lub zaznaczają określony tekst w dokumencie PDF. Przykłady adnotacji ze znacznikami tekstowymi obejmują wyróżnienia, podkreślenia i przekreślenia.

#### P: Czy mogę wyodrębnić tekst z innych typów adnotacji przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, Aspose.PDF dla .NET zapewnia różne metody wyodrębniania tekstu z różnych typów adnotacji, w tym adnotacje ze znacznikami tekstowymi, adnotacje z dowolnym tekstem i inne.

#### P: Czy Aspose.PDF dla .NET obsługuje wyodrębnianie tekstu z plików PDF chronionych hasłem?

 O: Tak, Aspose.PDF dla .NET obsługuje wyodrębnianie tekstu z plików PDF chronionych hasłem. Musisz podać prawidłowe hasło podczas ładowania dokumentu PDF za pomocą`Document` klasa.

#### P: Czy mogę filtrować zaznaczony tekst na podstawie innych kryteriów, takich jak kolor lub autor?

O: Tak, możesz filtrować zaznaczony tekst na podstawie innych kryteriów, takich jak kolor, autor lub data utworzenia. Aspose.PDF dla .NET zapewnia metody dostępu i filtrowania adnotacji na podstawie ich właściwości.

#### P: Czy można zapisać wyodrębniony podświetlony tekst w osobnym pliku?

O: Tak, możesz zapisać wyodrębniony zaznaczony tekst w oddzielnym pliku lub zapisać go w strukturze danych w celu dalszego przetwarzania lub analizy.
