---
title: Oznacz obraz w istniejącym pliku PDF
linktitle: Oznacz obraz w istniejącym pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak oznaczać obrazy w istniejących plikach PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak zwiększyć dostępność dzięki zgodności z PDF/UA.
type: docs
weight: 210
url: /pl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Wstęp

tym samouczku przeprowadzimy Cię przez proces tagowania obrazu w istniejącym pliku PDF przy użyciu Aspose.PDF dla .NET. Do końca tego przewodnika będziesz w stanie ustawić tekst alternatywny dla obrazów, dostosować atrybuty układu i upewnić się, że Twój plik PDF jest zgodny ze standardami dostępności.

## Wymagania wstępne

Zanim przejdziemy do konkretów, omówmy, czego będziesz potrzebować, żeby zacząć:

-  Aspose.PDF dla platformy .NET: Upewnij się, że pobrałeś i zainstalowałeś najnowszą wersję pliku Aspose.PDF dla platformy .NET.[Pobierz tutaj](https://releases.aspose.com/pdf/net/).
- .NET Framework: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET, np. Visual Studio.
- Podstawowa znajomość struktury dokumentu PDF: Znajomość elementów struktury dokumentu PDF, takich jak akapity, rozpiętości, tabele i obrazy.
-  Ważna licencja: Możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy) lub użyj tymczasowego[Tutaj](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Aby rozpocząć kodowanie, musisz zaimportować niezbędne przestrzenie nazw z Aspose.PDF dla .NET. Dadzą ci one dostęp do niezbędnych klas i metod do manipulowania dokumentem PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Teraz, gdy już omówiliśmy szczegóły, podzielmy proces tagowania obrazu na kilka kroków.

## Krok 1: Załaduj istniejący dokument PDF

Pierwszym krokiem jest załadowanie pliku PDF, z którym chcesz pracować. Może to być dowolny plik PDF z obrazem, który chcesz oznaczyć.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otwórz dokument
Document document = new Document(inFile);
```

-  Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku.
-  Ten`Document` Klasa pozwala załadować istniejący plik PDF. Będziesz modyfikować ten plik PDF, aby oznaczyć obraz.

## Krok 2: Dostęp do oznaczonej zawartości i elementu struktury głównej

Po otwarciu pliku PDF następnym krokiem jest dostęp do oznaczonej zawartości i zidentyfikowanie elementu struktury głównej. Jest to kluczowe, ponieważ umożliwia nawigację po elementach w pliku PDF i wprowadzanie modyfikacji.

```csharp
// Pobierz oznaczoną zawartość i element struktury głównej
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` zapewnia dostęp do ustrukturyzowanych elementów w pliku PDF.
-  Ten`RootElement` jest najwyższym elementem struktury, z którego można przejść do innych elementów, takich jak akapity, tabele i obrazy.

## Krok 3: Ustaw tytuł dla oznaczonego dokumentu PDF

Dodanie tytułu do oznaczonego dokumentu PDF gwarantuje, że dokument będzie prawidłowo oznaczony, co jest przydatne w kontekście dostępności i zgodności ze standardem PDF/UA.

```csharp
// Ustaw tytuł dla oznaczonego dokumentu PDF
taggedContent.SetTitle("Document with images");
```

- Ustawienie tytułu dla oznaczonego pliku PDF zwiększa dostępność i poprawia przejrzystość dokumentu dla czytników ekranu i technologii wspomagających.

## Krok 4: Znajdź i oznacz obraz

 Teraz znajdźmy element obrazu (nazywany`FigureElement` w pliku Aspose.PDF), ustaw dla niego tekst alternatywny i skonfiguruj jego atrybuty układu.

```csharp
// Przejdź przez wszystkie elementy Figure (obrazy) i ustaw alternatywny tekst oraz atrybuty układu
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Ustaw alternatywny tekst dla rysunku
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Utwórz i ustaw atrybut BBox (pole ograniczające)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Ustaw atrybuty układu dla rysunku
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Ten kod przechodzi przez wszystkie`FigureElement` obiekty w strukturze głównej, które reprezentują obrazy.
- Ustawia tekst alternatywny na potrzeby ułatwień dostępu (czytniki ekranu będą go używać do opisu obrazu).
- Pole ograniczające (`BBox`określa współrzędne układu obrazu, zapewniając jego prawidłowe wyświetlanie w dokumencie.

## Krok 5: Modyfikowanie elementów rozpiętości w tabeli

 W niektórych przypadkach może być konieczna modyfikacja elementów span w tabeli. Tutaj pokażemy, jak znaleźć`SpanElement` i przenieś do akapitu.

```csharp
// Znajdź elementy tabeli, rozpiętości i akapitu
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Przenieś element span do akapitu
spanElement.ChangeParentElement(paragraph);
```

-  Tutaj znajdujemy`TableElement`, `SpanElement` , I`ParagraphElement` w pliku PDF.
-  Korzystanie z`ChangeParentElement` metodą przenosimy rozpiętość do akapitu, aby zapewnić właściwe tagowanie i strukturę.

## Krok 6: Zapisz dokument i sprawdź zgodność z PDF/UA

Po wprowadzeniu wszystkich zmian ostatnim krokiem jest zapisanie zaktualizowanego pliku PDF i sprawdzenie, czy jest on zgodny ze standardami PDF/UA.

```csharp
// Zapisz zaktualizowany dokument PDF
document.Save(outFile);

// Sprawdź zgodność z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  Ten`Validate` Metoda sprawdza zgodność dokumentu PDF ze standardami PDF/UA i rejestruje wyniki.
- Zapewnienie zgodności pomaga poprawić dostępność i spełnić wymogi regulacyjne dotyczące publikowania dokumentów.

## Wniosek

tym samouczku pokazaliśmy, jak oznaczać obrazy w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Ustawiając tekst alternatywny, dostosowując atrybuty układu i weryfikując zgodność dokumentu z PDF/UA, możesz zapewnić dostępność plików PDF i ich zgodność z nowoczesnymi standardami. Aspose.PDF ułatwia pracę ze strukturalnymi elementami, dając Ci kontrolę nad układem i dostępnością dokumentu.

## Najczęściej zadawane pytania

### Do czego służy Aspose.PDF for .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka służąca do tworzenia, edytowania i manipulowania dokumentami PDF programowo w środowisku .NET.

### Jak zapewnić zgodność ze standardem PDF/UA?
 Możesz użyć Aspose.PDF`Validate` metoda sprawdzania zgodności dokumentu ze standardem PDF/UA po wprowadzeniu modyfikacji.

### Czym jest tekst alternatywny w plikach PDF?
Tekst alternatywny to opis dodawany do obrazów w plikach PDF w celu ułatwienia dostępu, zwłaszcza dla użytkowników korzystających z czytników ekranu.

### Czy mogę manipulować tabelami i rozpiętościami w pliku PDF za pomocą Aspose.PDF?
Tak, Aspose.PDF pozwala na manipulowanie tabelami, rozpiętościami i innymi elementami strukturalnymi w dokumencie PDF.

### Gdzie mogę pobrać Aspose.PDF dla .NET?
 Możesz pobrać najnowszą wersję Aspose.PDF dla .NET[Tutaj](https://releases.aspose.com/pdf/net/).