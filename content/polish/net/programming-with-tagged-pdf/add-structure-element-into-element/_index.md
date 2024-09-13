---
title: Dodaj element struktury do elementu
linktitle: Dodaj element struktury do elementu
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku, jak dodać element struktury do elementu w dokumencie PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 20
url: /pl/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
tym samouczku przedstawimy Ci przewodnik krok po kroku, jak dodać element struktury do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z oznaczonych funkcji struktury treści Aspose.PDF, możesz utworzyć hierarchiczną strukturę w swoim dokumencie PDF.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano program Visual Studio z platformą .NET Framework.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony internetowej Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod udostępnianych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Tworzenie dokumentu PDF i definiowanie elementów strukturalnych

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

Ten kod tworzy pusty dokument PDF i dodaje elementy strukturalne, takie jak akapity i spans. Każdy element struktury jest tworzony przy użyciu metod dostarczonych przez Aspose.PDF.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document. Save(outFile);
```

Ten kod zapisuje dokument PDF ze strukturą elementów do określonego pliku.

### Przykładowy kod źródłowy dla funkcji Dodaj element struktury do elementu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//Dokument tworzenia i uzyskiwania oznaczonych treści PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Ustawianie tytułu i języka natury dla dokumentu
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Pobieranie elementu struktury głównej (element struktury dokumentu)
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
// Sprawdzanie zgodności PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku dowiedziałeś się, jak dodać element struktury do elementu w dokumencie PDF za pomocą Aspose.PDF dla .NET. Używając oznaczonych funkcji struktury zawartości Aspose.PDF, możesz utworzyć hierarchiczną strukturę w dokumencie PDF, co ułatwia zarządzanie i nawigację po zawartości.

### Najczęściej zadawane pytania

#### P: Jaki jest cel dodawania elementu struktury do elementu w dokumencie PDF za pomocą Aspose.PDF dla .NET?

A: Dodanie elementu struktury do elementu w dokumencie PDF przy użyciu Aspose.PDF dla .NET umożliwia utworzenie hierarchicznej struktury w obrębie zawartości dokumentu. Ta hierarchiczna struktura usprawnia organizację i nawigację w zawartości, ułatwiając zarządzanie i dostęp do określonych elementów.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w dodawaniu elementów struktury do dokumentu PDF?

A: Aspose.PDF dla .NET to potężna biblioteka, która zapewnia możliwości tworzenia, manipulowania i konwertowania dokumentów PDF programowo. W tym samouczku funkcje struktury zawartości biblioteki są wykorzystywane do tworzenia i dołączania elementów struktury do zawartości dokumentu PDF.

#### P: Jakie są wymagania wstępne, aby móc dodać elementy struktury do dokumentu PDF za pomocą Aspose.PDF dla platformy .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio z platformą .NET Framework i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla platformy .NET.

#### P: W jaki sposób dostarczony kod C# tworzy i dołącza elementy struktury do zawartości dokumentu PDF?

A: Kod pokazuje, jak utworzyć dokument PDF, zdefiniować element struktury głównej i dołączyć do niego różne elementy strukturalne, takie jak akapity i span. Każdy element strukturalny jest tworzony przy użyciu metod dostarczonych przez Aspose.PDF, co pozwala na zbudowanie struktury hierarchicznej.

#### P: Czy mogę dostosować typy elementów struktury, które dołączam do dokumentu PDF?

A: Tak, możesz dostosować typy elementów struktury, eksplorując różne metody udostępniane przez bibliotekę Aspose.PDF. Kod prezentuje akapity i spany jako przykłady, ale możesz tworzyć i dołączać inne typy elementów strukturalnych w razie potrzeby.

#### P: Jak zdefiniować relacje hierarchiczne pomiędzy dodanymi elementami struktury?

 A: Hierarchiczna relacja między elementami struktury jest definiowana przez kolejność, w jakiej dołączasz je do ich elementów nadrzędnych. W kodzie relacje nadrzędny-podrzędny są ustanawiane za pomocą`AppendChild` metoda.

#### P: Jakie są korzyści ze stworzenia hierarchicznej struktury w dokumencie PDF?

A: Tworzenie hierarchicznej struktury w dokumencie PDF zwiększa jego dostępność, nawigację i organizację. Pozwala technologiom wspomagającym lepiej interpretować i przekazywać zawartość dokumentu, czyniąc go bardziej przyjaznym dla użytkowników niepełnosprawnych.

#### P: W jaki sposób mogę sprawdzić zgodność z PDF/UA po dodaniu elementów struktury?

A: Kod podany w samouczku pokazuje, jak sprawdzić zgodność PDF/UA za pomocą`Validate` metoda. Walidując dokument względem standardu PDF/UA, możesz upewnić się, że dodane elementy struktury są zgodne z wytycznymi dostępności.

#### P: Czy mogę użyć tego podejścia, aby dodać elementy struktury do istniejącego dokumentu PDF?

A: Tak, możesz zmodyfikować podane podejście, aby dodać elementy struktury do istniejącego dokumentu PDF. Zamiast tworzyć nowy dokument, należy załadować istniejący dokument za pomocą Aspose.PDF, a następnie wykonać podobne kroki, aby dodać elementy struktury.