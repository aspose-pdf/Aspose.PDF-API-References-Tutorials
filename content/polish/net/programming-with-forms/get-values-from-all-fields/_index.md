---
title: Uzyskaj wartości ze wszystkich pól w dokumencie PDF
linktitle: Uzyskaj wartości ze wszystkich pól w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością uzyskaj wartości wszystkich pól formularza w dokumencie PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 150
url: /pl/net/programming-with-forms/get-values-from-all-fields/
---
tym samouczku pokażemy, jak uzyskać wartości wszystkich pól formularza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument

Otwórz dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Krok 3: Uzyskaj wartości dla wszystkich pól

Przejdź przez wszystkie pola formularza w dokumencie i uzyskaj ich nazwy i wartości:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Przykładowy kod źródłowy dla opcji Pobierz wartości ze wszystkich pól przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Pobierz wartości ze wszystkich pól
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak uzyskać wartości wszystkich pól formularza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo wyodrębnić wartości wszystkich pól formularzy z dokumentów PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czy mogę modyfikować wartości pól formularzy podczas ich pobierania przy użyciu Aspose.PDF dla .NET?

 Odp.: Tak, możesz modyfikować wartości pól formularzy podczas ich pobierania za pomocą Aspose.PDF dla .NET. Gdy już to zrobisz`Field` obiekt reprezentujący pole formularza, możesz go zaktualizować`Value`właściwość o żądanej wartości. Po dokonaniu niezbędnych zmian możesz zapisać zaktualizowany dokument PDF, aby odzwierciedlić zmiany.

#### P: Jak mogę filtrować i pobierać określone pola formularzy na podstawie ich typów (np. pola tekstowe, pola wyboru)?

 Odp.: Aby pobrać określone pola formularza na podstawie ich typów, możesz użyć instrukcji warunkowych lub zapytań LINQ w celu filtrowania interesujących pól. Możesz sprawdzić typ każdego pola formularza za pomocą pola`FieldType` właściwość, a następnie odpowiednio pobierz wartości.

#### P: Co się stanie, jeśli dokument PDF nie będzie zawierał pól formularzy?

 Odp.: Jeśli dokument PDF nie zawiera żadnych pól formularza, plik`pdfDocument.Form` właściwość zwróci pustą kolekcję. W takich przypadkach pętla do pobierania wartości nie zostanie wykonana i żadne wartości nie zostaną wyświetlone.

#### P: Czy mogę wyodrębnić wartości pól formularza w określonej kolejności lub posortować je alfabetycznie?

O: Kolejność pobierania pól formularza zależy od podstawowej struktury dokumentu PDF. Aspose.PDF dla .NET zwraca pola formularza w kolejności, w jakiej zostały dodane do dokumentu. Jeśli chcesz wyświetlać lub przetwarzać pola formularza w określonej kolejności, możesz zaimplementować niestandardową logikę sortowania w oparciu o swoje wymagania.

#### P: Jak mogę obsługiwać zaszyfrowane dokumenty PDF z polami formularzy chronionymi hasłem?

 Odp.: Aspose.PDF dla .NET zapewnia funkcje do pracy z zaszyfrowanymi dokumentami PDF i polami formularzy chronionymi hasłem. Przed załadowaniem dokumentu możesz ustawić hasło za pomocą`pdfDocument.Password` aby uzyskać dostęp do zabezpieczonego dokumentu PDF i jego pól formularza.