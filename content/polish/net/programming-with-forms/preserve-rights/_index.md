---
title: Zachowaj prawa
linktitle: Zachowaj prawa
second_title: Aspose.PDF z dokumentacją API .NET
description: Zachowaj prawa formularzy w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 210
url: /pl/net/programming-with-forms/preserve-rights/
---
W tym samouczku pokażemy, jak zachować prawa do formularza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument

 Otwórz źródłowy dokument PDF za pomocą pliku`FileStream` z uprawnieniami do odczytu i zapisu:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Krok 3: Edytuj pola formularza

Przejdź przez wszystkie pola formularza w dokumencie i dokonaj niezbędnych zmian. W tym przykładzie zmieniamy wartość pola formularza, które ma w nazwie „A1”:

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

### Przykładowy kod źródłowy programu Zachowaj prawa przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Przeczytaj źródłowy formularz PDF za pomocą funkcji FileAccess Read and Write.
// Potrzebujemy uprawnienia ReadWrite, ponieważ po modyfikacji
// Musimy zapisać zaktualizowaną zawartość w tym samym dokumencie/pliku.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Utwórz instancję dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Pobierz wartości ze wszystkich pól
foreach (Field formField in pdfDocument.Form)
{
	// Jeśli pełna nazwa pola zawiera A1, wykonaj operację
	if (formField.FullName.Contains("A1"))
	{
		// Rzuć pole formularza jako TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Zmodyfikuj wartość pola
		textBoxField.Value = "Testing";
	}
}
// Zapisz zaktualizowany dokument w zapisie FileStream
pdfDocument.Save();
// Zamknij obiekt Strumień plików
fs.Close();
```

## Wniosek

W tym samouczku dowiedzieliśmy się, jak zachować prawa formularza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo uzyskać dostęp do pól formularzy i wprowadzić określone zmiany, zachowując jednocześnie uprawnienia dostępu i zapisu.


### Często zadawane pytania

#### P: Czy mogę zachować prawa do określonych pól formularza bez wpływu na inne pola w dokumencie PDF?

 Odp.: Tak, używając`FullName` właściwości pól formularza, możesz wybrać określone pola formularza w celu ich zachowania, pozostawiając inne bez wpływu.

#### P: Czy mogę zachować prawa formularza w dokumencie PDF chronionym hasłem?

Odp.: Tak, Aspose.PDF dla .NET pozwala zachować prawa do formularza nawet w dokumentach PDF chronionych hasłem, o ile podasz prawidłowe hasło, aby uzyskać dostęp do pliku i modyfikować go.

#### P: Co się stanie, jeśli spróbuję zmodyfikować pola formularza bez odpowiednich praw dostępu?

Odp.: Jeśli spróbujesz zmodyfikować pola formularza bez odpowiednich praw dostępu, zmiany nie zostaną zapisane w dokumencie PDF i może pojawić się wyjątek lub komunikat o błędzie.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?

Odp.: Tak, Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework, w tym .NET Core i .NET Standard.

#### P: Czy mogę programowo zachować prawa do formularza w dokumencie PDF w innych językach programowania oprócz C#?

O: Tak, Aspose.PDF dla .NET obsługuje różne języki programowania, takie jak VB.NET i ASP.NET, oprócz C#.