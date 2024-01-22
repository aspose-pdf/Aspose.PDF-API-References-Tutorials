---
title: Dodaj element struktury do elementu
linktitle: Dodaj element struktury do elementu
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący dodawania elementu konstrukcji do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 20
url: /pl/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
W tym samouczku przedstawimy krok po kroku, jak dodać element konstrukcji do elementu w dokumencie PDF za pomocą Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z zaznaczonych funkcji struktury treści Aspose.PDF, możesz stworzyć hierarchiczną strukturę w swoim dokumencie PDF.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio zainstalowany z platformą .NET.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod dostarczonych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Utworzenie dokumentu PDF i zdefiniowanie elementów strukturalnych

Użyj poniższego kodu, aby utworzyć dokument PDF i zdefiniować elementy strukturalne:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Ten kod tworzy pusty dokument PDF i dodaje elementy strukturalne, takie jak akapity i rozpiętości. Każdy element konstrukcji jest tworzony przy użyciu metod dostarczonych przez Aspose.PDF.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document. Save(outFile);
```

Ten kod zapisuje dokument PDF z elementami strukturalnymi do określonego pliku.

### Przykładowy kod źródłowy dla opcji Dodaj element struktury do elementu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Tworzenie dokumentu i pobieranie oznaczonej zawartości PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Ustawianie tytułu i języka natury dokumentu
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Pobieranie elementu struktury root (element struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Zapisz oznaczony dokument PDF
document.Save(outFile);
// Sprawdzanie zgodności z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyłeś się, jak dodać element konstrukcji do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Korzystając z funkcji zaznaczonej struktury treści w Aspose.PDF, możesz stworzyć hierarchiczną strukturę w swoim dokumencie PDF, co ułatwia zarządzanie i nawigację po zawartości.

### Często zadawane pytania

#### P: Jaki jest cel dodawania elementu struktury do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Dodanie elementu struktury do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET umożliwia utworzenie hierarchicznej struktury w treści dokumentu. Ta hierarchiczna struktura usprawnia organizację i nawigację po treści, ułatwiając zarządzanie i dostęp do określonych elementów.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w dodawaniu elementów struktury do dokumentu PDF?

Odp.: Aspose.PDF dla .NET to potężna biblioteka zapewniająca możliwości programowego tworzenia, manipulowania i konwertowania dokumentów PDF. W tym samouczku funkcje struktury oznaczonej zawartości biblioteki zostaną wykorzystane do tworzenia i dołączania elementów struktury do zawartości dokumentu PDF.

#### P: Jakie są wymagania wstępne dotyczące dodawania elementów struktury do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio ze środowiskiem .NET i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla .NET.

#### P: W jaki sposób dostarczony kod C# tworzy i dołącza elementy struktury do zawartości dokumentu PDF?

O: Kod demonstruje, jak utworzyć dokument PDF, zdefiniować główny element struktury i dołączyć do niego różne elementy strukturalne, takie jak akapity i zakresy. Każdy element strukturalny jest tworzony przy użyciu metod dostarczonych przez Aspose.PDF, co pozwala na zbudowanie struktury hierarchicznej.

#### P: Czy mogę dostosować typy elementów struktury dołączanych do dokumentu PDF?

Odp.: Tak, możesz dostosować typy elementów konstrukcji, eksplorując różne metody udostępniane przez bibliotekę Aspose.PDF. Kod przedstawia akapity i zakresy jako przykłady, ale w razie potrzeby możesz tworzyć i dołączać inne typy elementów strukturalnych.

#### P: Jak zdefiniować hierarchiczną relację pomiędzy dodanymi elementami konstrukcji?

 O: Hierarchiczna relacja między elementami konstrukcji jest definiowana przez kolejność dołączania ich do ich elementów nadrzędnych. W kodzie relacje rodzic-dziecko są ustanawiane za pomocą`AppendChild` metoda.

#### P: Jakie są korzyści z utworzenia struktury hierarchicznej w dokumencie PDF?

Odp.: Utworzenie hierarchicznej struktury w dokumencie PDF poprawia jego dostępność, nawigację i organizację. Umożliwia technologiom wspomagającym lepszą interpretację i przekazanie treści dokumentu, czyniąc go bardziej przyjaznym dla osób niepełnosprawnych.

#### P: Jak mogę sprawdzić zgodność z PDF/UA po dodaniu elementów struktury?

 O: Kod podany w samouczku pokazuje, jak sprawdzić zgodność z PDF/UA za pomocą pliku`Validate` metoda. Walidując dokument pod kątem standardu PDF/UA, możesz mieć pewność, że dodane elementy struktury są zgodne z wytycznymi dostępności.

#### P: Czy mogę zastosować to podejście, aby dodać elementy struktury do istniejącego dokumentu PDF?

Odp.: Tak, możesz zmodyfikować podane podejście, aby dodać elementy struktury do istniejącego dokumentu PDF. Zamiast tworzyć nowy dokument, załadujesz istniejący dokument za pomocą Aspose.PDF, a następnie wykonaj podobne kroki, aby dołączyć elementy struktury.