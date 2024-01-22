---
title: Spłaszcz formularze w dokumencie PDF
linktitle: Spłaszcz formularze w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością spłaszczaj formularze w dokumencie PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 100
url: /pl/net/programming-with-forms/flatten-forms/
---
W tym samouczku pokażemy, jak spłaszczyć formularze za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj źródłowy formularz PDF

Załaduj źródłowy formularz PDF:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 3: Spłaszcz formy

Najpierw sprawdź, czy w dokumencie znajdują się pola formularzy. Jeśli tak, wykonaj iterację po każdym polu i zastosuj spłaszczenie:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Krok 4: Zapisz zaktualizowany dokument

Zapisz zaktualizowany dokument PDF:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Flatten Forms przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj źródłowy formularz PDF
Document doc = new Document(dataDir + "input.pdf");
// Spłaszcz formy
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Zapisz zaktualizowany dokument
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak spłaszczać formularze za pomocą Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo spłaszczyć formularze w dokumentach PDF, uniemożliwiając edytowanie pól i łącząc adnotacje z treścią dokumentu.

### Często zadawane pytania

#### P: Co oznacza „spłaszczanie formularzy” w Aspose.PDF dla .NET?

Odp.: Spłaszczanie formularzy w Aspose.PDF dla .NET odnosi się do procesu uniemożliwiającego edytowanie pól formularzy w dokumencie PDF i łączenia adnotacji (takich jak pola formularzy, adnotacje i podpisy cyfrowe) z zawartością dokumentu. Po spłaszczeniu formularzy użytkownicy nie mogą modyfikować pól formularzy, a wygląd pól formularzy staje się częścią statycznej zawartości dokumentu PDF.

#### P: Czy mogę odwrócić proces spłaszczania i ponownie udostępnić pola formularza do edycji?

Odp.: Nie, po spłaszczeniu pól formularza proces jest nieodwracalny przy użyciu Aspose.PDF dla .NET. Spłaszczanie trwale łączy wygląd pól formularza z zawartością pliku PDF, a poszczególne elementy pól formularza nie są już dostępne ani edytowalne.

#### P: Kiedy należy spłaszczyć formularze w dokumencie PDF?

Odp.: Spłaszczanie formularzy jest przydatne, gdy chcesz zachować wygląd pól formularzy i adnotacji w dokumencie PDF, jednocześnie uniemożliwiając użytkownikom modyfikowanie danych. Dzieje się tak często, gdy chcesz udostępnić dokument PDF ze wstępnie wypełnionymi danymi formularza lub adnotacjami, które nie powinny być zmieniane przez odbiorców.

#### P: Czy spłaszczenie formularzy wpłynie na inne adnotacje, takie jak podpisy cyfrowe?

O: Tak, spłaszczenie formularzy spowoduje połączenie wszystkich adnotacji, w tym podpisów cyfrowych, z zawartością pliku PDF. Po spłaszczeniu formularzy wszelkie istniejące podpisy cyfrowe staną się trwałą częścią dokumentu i użytkownicy nie będą mogli ich modyfikować ani usuwać.

#### P: Czy mogę selektywnie spłaszczyć określone pola formularza i pozostawić inne do edycji?

O: Tak, możesz selektywnie spłaszczyć określone pola formularza w dokumencie PDF, pozostawiając inne pola do edycji. Zamiast używać kodu do spłaszczania wszystkich pól formularza, możesz spłaszczyć tylko żądane pola formularza na podstawie ich nazw lub innych kryteriów.