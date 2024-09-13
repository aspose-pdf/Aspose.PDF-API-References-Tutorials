---
title: Utwórz elementy struktury
linktitle: Utwórz elementy struktury
second_title: Aspose.PDF dla .NET API Reference
description: W tym samouczku dowiesz się, jak używać Aspose.PDF dla .NET do tworzenia elementów strukturalnych w tagowanym dokumencie PDF.
type: docs
weight: 60
url: /pl/net/programming-with-tagged-pdf/create-structure-elements/
---
Poniższy kod źródłowy C# używa Aspose.PDF dla .NET do tworzenia elementów struktury. Wykonaj poniższe kroki, aby zrozumieć, jak działa kod.

## Krok 1: Zaimportuj niezbędne biblioteki

```csharp
using Aspose.Pdf;
```

## Krok 2: Określ katalog swoich dokumentów

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pamiętaj o podaniu prawidłowej ścieżki do katalogu z dokumentami.

## Krok 3: Utwórz dokument PDF

```csharp
Document document = new Document();
```

Tworzymy nowy obiekt Document, który reprezentuje dokument PDF.

## Krok 4: Przygotuj treść do pracy z TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Pobieramy oznaczoną zawartość dokumentu PDF. Pozwoli nam to manipulować elementami strukturalnymi.

## Krok 5: Ustaw tytuł i język dokumentu

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Ustawiamy tytuł i język oznaczonego dokumentu PDF. Poprawia to dostępność dokumentu.

## Krok 6: Utwórz elementy grupujące

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Tworzymy różne elementy strukturalne służące do grupowania treści w dokumencie PDF.

## Krok 7: Utwórz elementy struktury akapitu

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Tworzymy elementy strukturalne na poziomie bloku dla akapitów i nagłówków. Powyższy przykład pokazuje tworzenie nagłówka poziomu 1.

## Krok 8: Utwórz elementy struktury poziomu inline

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Tworzymy elementy struktury inline dla części tekstu, które pojawiają się wewnątrz akapitu lub nagłówka.

## Krok 9: Utwórz elementy struktury dzieła sztuki

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Tworzymy elementy strukturalne dla ilustracji i wzorów matematycznych zawartych w dokumencie.

## Krok 10: Zapisz oznaczony dokument PDF

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Zapisujemy otagowany dokument PDF z utworzonymi elementami struktury.

### Przykładowy kod źródłowy dla funkcji Create Structure Elements using Aspose.PDF for .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz dokument PDF
Document document = new Document();
// Pobierz zawartość do pracy z TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Ustaw tytuł i język dla dokumentu
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Utwórz elementy grupujące
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Utwórz elementy struktury bloków tekstowych
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Utwórz elementy struktury tekstowej na poziomie wiersza
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Utwórz elementy struktury ilustracji
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Metody są w trakcie opracowywania
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StructureElements.pdf");

```

## Wniosek

W tym samouczku nauczyliśmy się, jak używać Aspose.PDF dla .NET do tworzenia elementów strukturalnych w oznaczonym dokumencie PDF. Elementy strukturalne pomagają poprawić dostępność dokumentu i organizować zawartość w sensowny sposób. Teraz możesz wykorzystać tę wiedzę do tworzenia ustrukturyzowanych, łatwych w nawigacji dokumentów PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tworzenia elementów struktury w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

A: Tworzenie elementów struktury w dokumencie PDF przy użyciu Aspose.PDF dla .NET zwiększa dostępność i organizację treści dokumentu. Elementy struktury zapewniają hierarchiczną strukturę, która poprawia nawigację, semantykę i zgodność z technologiami wspomagającymi.

#### P: W jaki sposób dostarczony kod C# tworzy elementy struktury w dokumencie PDF?

A: Przykład kodu pokazuje, jak tworzyć różne typy elementów struktury, w tym elementy grupujące (takie jak części, sekcje i divy), elementy blokowe (takie jak akapity i nagłówki), elementy liniowe (span, quote, note) i elementy graficzne (takie jak rysunki i wzory). Te elementy struktury pomagają organizować zawartość.

####  P: Dlaczego ważne jest ustawienie tytułu i języka dokumentu za pomocą`SetTitle` and `SetLanguage` methods?

 A: Ustawianie tytułu i języka dokumentu za pomocą`SetTitle` I`SetLanguage`metody poprawiają dostępność i semantykę dokumentu. Tytuł zawiera krótki opis celu dokumentu, podczas gdy atrybut języka poprawia specyficzne dla języka renderowanie i dostępność.

####  P: W jaki sposób grupuje się elementy, takie jak:`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Grupowanie elementów tworzy hierarchiczną strukturę w dokumencie PDF, umożliwiając logiczną organizację i grupowanie powiązanej zawartości. Ulepsza to nawigację i zapewnia użytkownikom przejrzystą strukturę.

#### P: Czym są elementy struktury blokowej i liniowej i czym się one różnią?

A: Elementy struktury na poziomie bloku reprezentują większe bloki treści, takie jak akapity i nagłówki, podczas gdy elementy na poziomie wiersza reprezentują części tekstu w akapicie lub nagłówku, takie jak rozpiętości, cytaty i notatki. Pomagają one zdefiniować hierarchię i relacje treści.

####  P: Jak struktura dzieła sztuki, np.`FigureElement` and `FormulaElement`, contribute to the document?

A: Elementy struktury dzieła sztuki pozwalają dodawać ilustracje, rysunki i wzory matematyczne do dokumentu. Zapewniają ustrukturyzowany sposób uwzględniania treści wizualnych i matematycznych.

#### P: Czy mogę użyć podobnych technik do tworzenia innych typów elementów struktury, takich jak listy, tabele lub adnotacje?

A: Tak, możesz użyć podobnych technik, aby utworzyć inne typy elementów struktury, takie jak listy, tabele, adnotacje, odniesienia i inne. Aspose.PDF zapewnia szeroki zakres metod tworzenia elementów struktury.

####  P: W jaki sposób można zapisać oznaczony dokument PDF za pomocą`Save` method ensure the preservation of structure elements?

 A: Ten`Save` Metoda ta zapisuje dokument PDF wraz z utworzonymi elementami struktury, zapewniając zachowanie hierarchicznej i semantycznej struktury dokumentu, co ułatwia dostęp i nawigację.

#### P: Jakie korzyści wnoszą elementy struktury do dokumentów PDF pod względem dostępności i zgodności z technologiami wspomagającymi?

A: Elementy struktury zwiększają dostępność, zapewniając dokumentowi znaczącą strukturę i semantykę. Pozwala to technologiom wspomagającym, takim jak czytniki ekranu, na skuteczniejsze interpretowanie i przekazywanie treści dokumentu użytkownikom niepełnosprawnym.

#### P: W jaki sposób mogę dodatkowo dostosować i łączyć różne typy elementów strukturalnych w moich dokumentach PDF?

A: Możesz łączyć i dostosowywać elementy struktury, używając odpowiednich metod tworzenia dostarczonych przez Aspose.PDF. Eksperymentuj z różnymi elementami i ich właściwościami, aby utworzyć dobrze ustrukturyzowany i zorganizowany dokument PDF.