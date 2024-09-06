---
title: Dodaj i wyszukaj ukryty tekst w pliku PDF
linktitle: Dodaj i wyszukaj ukryty tekst w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku, jak dodawać i wyszukiwać ukryty tekst w plikach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 20
url: /pl/net/programming-with-text/add-and-search-hidden-text/
---
W tym samouczku pokażemy Ci, jak dodawać i wyszukiwać ukryty tekst w pliku PDF za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## 1. Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowany i skonfigurowany program Visual Studio lub inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana. Możesz ją pobrać z oficjalnej strony Aspose.

## 2. Tworzenie dokumentu PDF z ukrytym tekstem

Aby rozpocząć, użyj poniższego kodu, aby utworzyć nowy dokument PDF zawierający ukryty tekst:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Utwórz dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Ustaw właściwość tekstu - niewidoczny
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Pamiętaj o podaniu żądanej ścieżki i nazwy pliku dla dokumentu PDF.

## 3. Wyszukaj tekst w dokumencie

Następnie przeszukamy ukryty tekst w dokumencie PDF. Użyj następującego kodu:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Zrób coś z fragmentami
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Spowoduje to przeszukanie ukrytego tekstu na drugiej stronie dokumentu PDF i wyświetlenie odpowiednich informacji.

### Przykładowy kod źródłowy dla funkcji Dodaj i wyszukaj ukryty tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Utwórz dokument z ukrytym tekstem
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Ustaw właściwość tekstu - niewidoczny
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Wyszukaj tekst w dokumencie
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Zrób coś z fragmentami
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Wniosek

Gratulacje! Udało Ci się dodać i znaleźć ukryty tekst w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Teraz możesz zastosować tę metodę w swoich projektach, aby manipulować i wyszukiwać ukryty tekst w plikach PDF.

### Najczęściej zadawane pytania

#### P: Czym jest Aspose.PDF dla platformy .NET?

A: Aspose.PDF dla platformy .NET to rozbudowana biblioteka umożliwiająca programistom tworzenie, modyfikowanie i przekształcanie dokumentów PDF w aplikacjach .NET.

#### P: Czy ukryty tekst może być wykorzystany do utworzenia znaku wodnego?

A: Oczywiście! Ukryty tekst może służyć jako skuteczny sposób znakowania wodnego dokumentów PDF, dodając dodatkową warstwę bezpieczeństwa.

#### P: Czy można ujawnić ukryty tekst w dokumencie PDF?

O: Tak, proces wyszukiwania i ujawniania ukrytego tekstu w dokumencie PDF można przeprowadzić stosując techniki opisane w tym samouczku.

#### P: Jakie inne funkcjonalności oferuje Aspose.PDF dla .NET?

A: Oprócz możliwości manipulowania ukrytym tekstem Aspose.PDF dla platformy .NET oferuje szeroką gamę funkcji, w tym generowanie plików PDF, konwersję, szyfrowanie i wiele innych.