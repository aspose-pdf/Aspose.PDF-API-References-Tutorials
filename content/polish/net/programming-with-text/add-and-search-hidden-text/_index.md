---
title: Dodaj i wyszukuj ukryty tekst w pliku PDF
linktitle: Dodaj i wyszukuj ukryty tekst w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący dodawania i wyszukiwania ukrytego tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 20
url: /pl/net/programming-with-text/add-and-search-hidden-text/
---
W tym samouczku przeprowadzimy Cię przez proces dodawania i wyszukiwania ukrytego tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## 1. Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowany i skonfigurowany program Visual Studio lub dowolne inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Można go pobrać z oficjalnej strony Aspose.

## 2. Tworzenie dokumentu PDF z ukrytym tekstem

Na początek użyj poniższego kodu i utwórz nowy dokument PDF zawierający ukryty tekst:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Utwórz dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Ustaw właściwość tekstu - niewidoczna
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Pamiętaj o podaniu żądanej ścieżki i nazwy pliku dokumentu PDF.

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

### Przykładowy kod źródłowy dodawania i wyszukiwania ukrytego tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Utwórz dokument z ukrytym tekstem
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Ustaw właściwość tekstu - niewidoczna
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

Gratulacje! Pomyślnie dodałeś i znalazłeś ukryty tekst w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz zastosować tę metodę do własnych projektów, aby manipulować i wyszukiwać ukryty tekst w plikach PDF.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to solidna biblioteka, która umożliwia programistom tworzenie, manipulowanie i przekształcanie dokumentów PDF w aplikacjach .NET.

#### P: Czy ukryty tekst może być używany do celów znaku wodnego?

Odp.: Absolutnie! Ukryty tekst może służyć jako skuteczny sposób znakowania wodnego dokumentów PDF, dodając dodatkową warstwę bezpieczeństwa.

#### P: Czy można odkryć ukryty tekst w dokumencie PDF?

Odp.: Tak, proces wyszukiwania i ujawniania ukrytego tekstu w dokumencie PDF można przeprowadzić za pomocą technik opisanych w tym samouczku.

#### P: Jakie inne funkcje oferuje Aspose.PDF dla .NET?

Odp.: Oprócz manipulacji ukrytym tekstem, Aspose.PDF dla .NET zapewnia szeroką gamę funkcji, w tym generowanie plików PDF, konwersję, szyfrowanie i wiele innych.