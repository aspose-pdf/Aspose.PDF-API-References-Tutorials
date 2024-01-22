---
title: Dodaj podpowiedź do tekstu w pliku PDF
linktitle: Dodaj podpowiedź do tekstu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać podpowiedzi do tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 90
url: /pl/net/programming-with-text/add-tooltip-to-text/
---
Ten samouczek poprowadzi Cię przez proces dodawania podpowiedzi do tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz dodać podpowiedzi do tekstu, dodaj następujące dyrektywy using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz przykładowy dokument z tekstem
 Stwórz nowy`Document` obiekt i dodaj strony z fragmentami tekstu. W dostarczonym kodzie do dokumentu dodano dwa fragmenty tekstu z odpowiednim tekstem podpowiedzi.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Krok 5: Otwórz dokument i znajdź fragmenty tekstu
 Załaduj utworzony dokument za pomocą`Document` konstruktor i znajdź fragmenty tekstu, które wymagają użycia podpowiedzi`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Krok 6: Dodaj podpowiedzi do fragmentów tekstu
 Przejrzyj wyodrębnione fragmenty tekstu w pętli i utwórz niewidoczne przyciski w ich miejscach. Przypisz żądany tekst podpowiedzi do`AlternateName` własność`ButtonField`. Dodaj pola przycisków do formularza dokumentu.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Krok 7: Powtórz tę czynność dla dodatkowych fragmentów tekstu z długimi etykietami narzędzi
Powtórz kroki 5 i 6 dla fragmentów tekstu z długimi etykietami narzędzi. Zmodyfikuj odpowiednio kryteria wyszukiwania i tekst podpowiedzi.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Krok 8: Zapisz zmodyfikowany dokument
 Zapisz zmodyfikowany dokument PDF za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
document. Save(outputFile);
```

### Przykładowy kod źródłowy dla opcji Dodaj etykietkę narzędzia do tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Utwórz przykładowy dokument z tekstem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Otwórz dokument z tekstem
Document document = new Document(outputFile);
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Zaakceptuj pochłaniacz stron dokumentu
document.Pages.Accept(absorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragments = absorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment fragment in textFragments)
{
	// Utwórz niewidoczny przycisk na pozycji fragmentu tekstu
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Wartość AlternateName zostanie wyświetlona jako podpowiedź w aplikacji przeglądarki
	field.AlternateName = "Tooltip for text.";
	// Dodaj pole przycisku do dokumentu
	document.Form.Add(field);
}
// Następna będzie próbka z bardzo długą podpowiedzią
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Ustaw bardzo długi tekst
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Zapisz dokument
document.Save(outputFile);
```

## Wniosek
Pomyślnie dodałeś podpowiedzi do tekstu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

## Często zadawane pytania

#### P: Na czym skupia się ten samouczek?

Odp.: Ten samouczek koncentruje się na dodawaniu podpowiedzi do tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje kroki wymagane do osiągnięcia tego celu.

#### P: Które przestrzenie nazw należy zaimportować na potrzeby tego samouczka?

O: W pliku kodu, w którym chcesz dodać podpowiedzi do tekstu, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak mogę utworzyć przykładowy dokument z tekstem?

 Odp.: W kroku 4 utworzysz nowy plik`Document` obiekt i dodaj strony z fragmentami tekstu. Dostarczony kod dodaje dwa fragmenty tekstu z odpowiednim tekstem podpowiedzi.

#### P: Jak otworzyć dokument i znaleźć fragmenty tekstu?

 Odp.: W kroku 5 załadujesz utworzony dokument za pomocą`Document` konstruktor i znajdź fragmenty tekstu wymagające podpowiedzi za pomocą`TextFragmentAbsorber`.

#### P: Jak dodać podpowiedzi do fragmentów tekstu?

 O: W kroku 6 będziesz przeglądać wyodrębnione fragmenty tekstu i tworzyć niewidoczne przyciski w ich miejscach. Tekst podpowiedzi jest przypisany do`AlternateName` własność`ButtonField`który jest dodawany do formularza dokumentu.

#### P: Jak powtórzyć proces dla dodatkowych fragmentów tekstu z długimi etykietami narzędzi?

O: W przypadku fragmentów tekstu z długimi etykietami narzędzi powtórz kroki 5 i 6. Odpowiednio zmodyfikuj kryteria wyszukiwania i tekst podpowiedzi.

#### P: Jak zapisać zmodyfikowany dokument?

 O: W kroku 8 zapiszesz zmodyfikowany dokument PDF za pomocą pliku`Save` metoda`Document` obiekt.

#### P: Jaki jest główny wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się, jak ulepszyć swój dokument PDF, dodając podpowiedzi do tekstu za pomocą Aspose.PDF dla .NET. Może to zapewnić czytelnikom cenne dodatkowe informacje podczas interakcji z zawartością pliku PDF.