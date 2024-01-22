---
title: Wykreśl słowa
linktitle: Wykreśl słowa
second_title: Aspose.PDF z dokumentacją API .NET
description: Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z pliku Aspose.PDF dla funkcji Strike Out Words w platformie .NET, w tym przewodnik krok po kroku i wyjaśnienia
type: docs
weight: 150
url: /pl/net/annotations/strikeoutwords/
---
Aspose.PDF dla .NET to biblioteka do manipulacji i przetwarzania dokumentów PDF, która zapewnia różne funkcje do tworzenia, modyfikowania i konwertowania plików PDF. Jedną z przydatnych funkcji udostępnianych przez Aspose.PDF jest możliwość przekreślania słów lub fraz w dokumencie PDF przy użyciu kodu źródłowego C#. W tym artykule przedstawimy przewodnik krok po kroku, jak przekreślać słowa za pomocą Aspose.PDF dla .NET.

## Krok 1: Ładowanie dokumentu PDF
Pierwszym krokiem jest załadowanie dokumentu PDF, który chcesz zmodyfikować. W tym samouczku załadujemy dokument PDF o nazwie „input.pdf” z folderu „TWÓJ KATALOG DOKUMENTÓW”. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Krok 2: Wyszukiwanie fragmentów tekstu
Aby przekreślić określone słowa lub frazy w dokumencie PDF, należy je najpierw wyszukać. Aspose.PDF udostępnia klasę TextFragmentAbsorber, której można użyć do wyszukiwania określonego fragmentu tekstu w dokumencie PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

powyższym kodzie szukamy fragmentu tekstu „Estoque” w dokumencie PDF. Możesz to zmodyfikować, aby wyszukać inne słowo lub frazę, którą chcesz skreślić.

## Krok 3: Wykreślanie fragmentów tekstu
Po odnalezieniu fragmentów tekstu kolejnym krokiem jest ich wykreślenie. Aspose.PDF udostępnia klasę StrikeOutAnnotation, której można użyć do utworzenia przekreślonej adnotacji dla fragmentu tekstu. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

W powyższym kodzie tworzymy przekreśloną adnotację dla każdego znalezionego fragmentu tekstu. Ustawiamy także krycie, obramowanie i kolor przekreślonej adnotacji.

## Krok 4: Zapisanie zmodyfikowanego dokumentu PDF
Po przekreśleniu fragmentów tekstu zapisz zmodyfikowany dokument.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Przykładowy kod źródłowy dla skreślonych słów przy użyciu Aspose.PDF dla .NET


```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document document = new Document(dataDir + "input.pdf");

// Utwórz instancję TextFragment Absorber, aby przeszukać określony fragment tekstu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iteruj po stronach dokumentu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Pobierz pierwszą stronę dokumentu PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Utwórz kolekcję wchłoniętego tekstu
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Wykonaj iterację powyższą kolekcją
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Uzyskaj prostokątne wymiary obiektu TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Utwórz instancję adnotacji StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Ustaw przezroczystość adnotacji
	strikeOut.Opacity = .80f;
	// Ustaw granicę dla instancji adnotacji
	strikeOut.Border = new Border(strikeOut);
	// Ustaw kolor adnotacji
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Dodaj adnotację do kolekcji adnotacji TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak używać Aspose.PDF dla .NET do przekreślania określonych słów w dokumencie PDF. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo załadować dokument PDF, wyszukać określone fragmenty tekstu i utworzyć przekreślone adnotacje, aby wizualnie zaznaczyć i skreślić te słowa. Aspose.PDF dla .NET zapewnia prosty i skuteczny sposób programowego manipulowania dokumentami PDF, co czyni go cennym narzędziem dla programistów pracujących z plikami PDF w aplikacjach .NET.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to potężna biblioteka, która pozwala programistom programowo tworzyć, edytować i manipulować dokumentami PDF w aplikacjach .NET. Zapewnia szeroką gamę funkcji do pracy z plikami PDF, w tym wyodrębnianie tekstu, obsługę adnotacji, wypełnianie formularzy i wiele więcej.

#### P: Czy mogę użyć Aspose.PDF dla .NET do przekreślenia określonych słów w dokumencie PDF?

Odp.: Tak, Aspose.PDF dla .NET zapewnia funkcję wyszukiwania określonych fragmentów tekstu w dokumencie PDF, a następnie tworzenia przekreślonych adnotacji w celu wizualnego zaznaczania i przekreślania tych słów.

#### P: Jak określić tekst, który chcę przekreślić w dokumencie PDF?

 Odp.: Aby określić tekst, który chcesz przekreślić, możesz użyć opcji`TextFragmentAbsorber` klasa dostarczona przez Aspose.PDF dla .NET. Umożliwia wyszukiwanie określonego fragmentu tekstu w dokumencie PDF na podstawie wybranych kryteriów.

#### P: Czy mogę dostosować wygląd przekreślonej adnotacji?

O: Tak, możesz dostosować różne właściwości przekreślonej adnotacji, takie jak krycie, styl obramowania i kolor. Dzięki temu możesz dostosować wygląd przekreślonej adnotacji do swoich konkretnych wymagań.