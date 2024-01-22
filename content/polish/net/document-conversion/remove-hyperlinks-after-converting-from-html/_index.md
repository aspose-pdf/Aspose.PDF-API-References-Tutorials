---
title: Usuń hiperłącza po konwersji z HTML
linktitle: Usuń hiperłącza po konwersji z HTML
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący usuwania hiperłączy po konwersji HTML na PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 250
url: /pl/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
W tym samouczku przeprowadzimy Cię przez proces usuwania hiperłączy z pliku PDF wygenerowanego z pliku HTML przy użyciu Aspose.PDF dla .NET. Hiperłącza to klikalne łącza, które mogą przekierowywać do innych stron lub witryn internetowych. Wykonując poniższe czynności, będziesz mógł usunąć hiperłącza z wynikowego pliku PDF.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Ładowanie pliku HTML i usuwanie hiperłączy
Na tym etapie załadujemy plik HTML i usuniemy hiperłącza z wynikowego dokumentu PDF. Użyj następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj plik HTML, korzystając z opcji ładowania HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Przeglądaj adnotacje na pierwszej stronie dokumentu
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Sprawdź, czy adnotacja jest linkiem
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Sprawdź, czy akcja jest typu GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Użyj pochłaniacza fragmentów tekstu, aby znaleźć pasujące fragmenty tekstu
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Przeglądaj pasujące fragmenty tekstu i usuwaj atrybuty z hiperłączy
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Usuń adnotację ze strony
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik HTML.

## Krok 2: Zapisanie wynikowego pliku PDF
Na koniec zapiszemy wynikowy plik PDF bez hiperłączy. Użyj następującego kodu:

```csharp
// Zapisz wynikowy plik PDF
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Powyższy kod zapisuje wynikowy plik PDF z nazwą pliku`"RemoveHyperlinksFromText_out.pdf"`.

### Przykładowy kod źródłowy narzędzia Usuń hiperłącza po konwersji z HTML przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Wniosek
W tym samouczku omówiliśmy krok po kroku proces usuwania hiperłączy z pliku PDF wygenerowanego z pliku HTML przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, będziesz mógł skutecznie usunąć hiperłącza z wynikowego pliku PDF.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Oferuje szeroką gamę funkcjonalności, w tym możliwość konwersji plików HTML do formatu PDF i manipulowania zawartością PDF.

#### P: Dlaczego miałbym chcieć usunąć hiperłącza z pliku PDF?

Odp.: Istnieje wiele powodów usuwania hiperłączy z pliku PDF. Na przykład możesz chcieć wyeliminować linki zewnętrzne do celów drukowania lub archiwizacji lub upewnić się, że po zawartości pliku PDF nie będzie można nawigować za pomocą hiperłączy.

#### P: Jak mogę załadować plik HTML i usunąć hiperłącza przy użyciu Aspose.PDF dla .NET?

 O: Aby załadować plik HTML i usunąć hiperłącza, możesz użyć Aspose.PDF dla .NET`HtmlLoadOptions` klasa. Przeglądaj adnotacje na stronach PDF, aby znaleźć adnotacje do linków i zmodyfikować ich atrybuty.

#### P: Czy mogę dostosować nazwę pliku wyjściowego wynikowego pliku PDF?

O: Tak, możesz dostosować nazwę pliku wyjściowego wynikowego pliku PDF, modyfikując kod, który zapisuje dokument PDF. Po prostu zmień żądaną nazwę pliku w`doc.Save()` metoda.

#### P: Czy możliwe jest selektywne usuwanie hiperłączy w oparciu o określone kryteria?

O: Tak, możesz selektywnie usuwać hiperłącza na podstawie określonych kryteriów. Możesz na przykład usunąć tylko linki zewnętrzne lub linki prowadzące do określonych adresów URL.