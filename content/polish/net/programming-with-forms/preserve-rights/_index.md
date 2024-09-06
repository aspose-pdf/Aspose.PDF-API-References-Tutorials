---
title: Zachowaj prawa
linktitle: Zachowaj prawa
second_title: Aspose.PDF dla .NET API Reference
description: Zachowaj uprawnienia formularzy w dokumentach PDF dzięki Aspose.PDF dla platformy .NET.
type: docs
weight: 210
url: /pl/net/programming-with-forms/preserve-rights/
---
W tym samouczku pokażemy, jak zachować prawa formularza w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument

 Otwórz dokument źródłowy PDF za pomocą`FileStream` z uprawnieniami do odczytu i zapisu:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Krok 3: Edytuj pola formularza

Przejdź przez wszystkie pola formularza w dokumencie i wprowadź niezbędne zmiany. W tym przykładzie zmieniamy wartość pola formularza, które ma „A1” w nazwie:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Krok 4: Zapisz zaktualizowany dokument

Zapisz zmodyfikowany dokument PDF:

```csharp
pdfDocument.Save();
```

##  Krok 5: Zamknij`FileStream`

 Nie zapomnij zamknąć`FileStream` obiekt, gdy skończysz:

```csharp
fs. Close();
```

### Przykładowy kod źródłowy dla Preserve Rights przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Przeczytaj źródłowy formularz PDF za pomocą FileAccess z funkcją odczytu i zapisu.
// Potrzebujemy uprawnienia ReadWrite, ponieważ po modyfikacji
// Musimy zapisać zaktualizowaną zawartość w tym samym dokumencie/pliku.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Utwórz wystąpienie dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Pobierz wartości ze wszystkich pól
foreach (Field formField in pdfDocument.Form)
{
	// Jeżeli pełna nazwa pola zawiera A1, wykonaj operację
	if (formField.FullName.Contains("A1"))
	{
		// Rzutuj pole formularza jako pole tekstowe
		TextBoxField textBoxField = formField as TextBoxField;
		// Modyfikuj wartość pola
		textBoxField.Value = "Testing";
	}
}
// Zapisz zaktualizowany dokument w pliku FileStream
pdfDocument.Save();
// Zamknij obiekt strumienia plików
fs.Close();
```

## Wniosek

W tym samouczku dowiedzieliśmy się, jak zachować prawa formularza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z tymi krokami, możesz łatwo uzyskać dostęp do pól formularza i wprowadzić określone zmiany, zachowując jednocześnie uprawnienia dostępu i zapisu.


### Najczęściej zadawane pytania

#### P: Czy mogę zachować prawa do określonych pól formularza bez wpływu na inne pola w dokumencie PDF?

 A: Tak, za pomocą`FullName` właściwości pól formularza, możesz wskazać konkretne pola formularza do zachowania, nie zmieniając innych pól.

#### P: Czy mogę zachować prawa do formularza w dokumencie PDF chronionym hasłem?

O: Tak, Aspose.PDF dla platformy .NET pozwala zachować uprawnienia do formularza nawet w dokumentach PDF chronionych hasłem, pod warunkiem podania prawidłowego hasła w celu dostępu do pliku i jego modyfikacji.

#### P: Co się stanie, jeśli spróbuję zmodyfikować pola formularza nie mając odpowiednich uprawnień dostępu?

O: Jeśli spróbujesz zmodyfikować pola formularza bez odpowiednich uprawnień dostępu, zmiany nie zostaną zapisane w dokumencie PDF i może pojawić się wyjątek lub komunikat o błędzie.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?

O: Tak, Aspose.PDF dla platformy .NET jest zgodny ze wszystkimi wersjami platformy .NET Framework, w tym .NET Core i .NET Standard.

#### P: Czy mogę programowo zachować prawa do formularza w dokumencie PDF w innych językach programowania niż C#?

O: Tak, Aspose.PDF dla platformy .NET obsługuje różne języki programowania, takie jak VB.NET i ASP.NET, a także język C#.