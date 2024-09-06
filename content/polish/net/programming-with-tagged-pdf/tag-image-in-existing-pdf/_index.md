---
title: Oznacz obraz w istniejącym pliku PDF
linktitle: Oznacz obraz w istniejącym pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak oznaczyć obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla platformy .NET. Przewodnik krok po kroku dotyczący dodawania tagów do obrazów.
type: docs
weight: 210
url: /pl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
W tym szczegółowym samouczku przeprowadzimy Cię krok po kroku przez dostarczony kod źródłowy C#, aby oznaczyć obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z poniższymi instrukcjami, aby dowiedzieć się, jak dodawać tagi do obrazu w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do używania Aspose.PDF dla .NET. Obejmuje to zainstalowanie biblioteki Aspose.PDF i skonfigurowanie projektu, aby się do niej odwoływał.

## Krok 2: Otwórz istniejący dokument PDF

tym kroku otworzymy istniejący dokument PDF za pomocą Aspose.PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ścieżki plików wejściowych i wyjściowych
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otwórz dokument
Document document = new Document(inFile);
```

Otworzyliśmy istniejący dokument PDF za pomocą Aspose.PDF.

## Krok 3: Uzyskaj oznaczoną zawartość i element struktury głównej

Teraz otrzymamy oznaczoną zawartość dokumentu PDF i odpowiadający jej element struktury głównej.

```csharp
// Pobierz oznaczoną zawartość i element struktury głównej
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy oznaczoną zawartość dokumentu PDF i odpowiadający jej element struktury głównej.

## Krok 4: Ustawianie tytułu dla oznaczonego dokumentu PDF

Teraz ustawmy tytuł dla oznaczonego dokumentu PDF.

```csharp
// Zdefiniuj tytuł dla oznaczonego dokumentu PDF
taggedContent.SetTitle("Document with images");
```

Ustawiliśmy tytuł dla oznaczonego dokumentu PDF.

## Krok 5: Przypisz tekst alternatywny i pole ograniczające do obrazu

Teraz każdemu elementowi obrazu przypiszemy tekst alternatywny i ramkę ograniczającą.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Przypisz tekst alternatywny do obrazu
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Utwórz i przypisz pole ograniczające (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Każdemu elementowi obrazu w dokumencie PDF przypisaliśmy tekst alternatywny i ramkę ograniczającą.

## Krok 6: Przenoszenie elementu Span do akapitu

Teraz przenieśmy element Span do akapitu.

```csharp
// Przenieś element Span do akapitu (znajdź nieprawidłowy element Span i akapit w pierwszym TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Przesuń element Span w akapicie
spanElement.ChangeParentElement(paragraph);
```

Przenieśliśmy element Span do określonego akapitu.

## Krok 7: Zapisywanie zmodyfikowanego dokumentu PDF

Teraz, gdy wprowadziliśmy niezbędne zmiany, zapiszemy zmodyfikowany dokument PDF.

```csharp
// Zapisz dokument PDF
document. Save(outFile);
```

Zapisaliśmy zmodyfikowany dokument PDF w podanym katalogu.

### Przykładowy kod źródłowy dla tagowania obrazu w istniejącym pliku PDF przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otwórz dokument
Document document = new Document(inFile);

// Pobiera oznaczoną zawartość i element struktury głównej
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Ustaw tytuł dla oznaczonego dokumentu PDF
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Ustaw alternatywny tekst dla rysunku
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Utwórz i ustaw atrybut BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Przenieś element Span do akapitu (znajdź niewłaściwy element Span i akapit w pierwszym TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Przenieś element Span do akapitu
spanElement.ChangeParentElement(paragraph);

// Zapisz dokument
document.Save(outFile);

//Sprawdzanie zgodności PDF/UA dla naszego dokumentu
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyliśmy się, jak oznaczyć obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Teraz możesz użyć Aspose.PDF, aby dodać tagi i edytować obrazy w dokumentach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest główny cel tego samouczka dotyczącego tagowania obrazów w istniejącym pliku PDF przy użyciu Aspose.PDF dla platformy .NET?

A: Głównym celem tego samouczka jest przeprowadzenie Cię przez proces oznaczania obrazu w istniejącym dokumencie PDF przy użyciu Aspose.PDF dla .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu źródłowego C#, które pomogą Ci zrozumieć, jak przypisywać tekst alternatywny i pola ograniczające do obrazów, przenosić elementy w dokumencie i dodawać tagi do obrazów.

#### P: Jakie wymagania należy spełnić, aby móc skorzystać z tego samouczka dotyczącego tagowania obrazów w pliku PDF za pomocą Aspose.PDF dla platformy .NET?

A: Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do używania Aspose.PDF dla .NET. Wiąże się to z zainstalowaniem biblioteki Aspose.PDF i skonfigurowaniem projektu tak, aby się do niej odwoływał.

#### P: W jaki sposób mogę otworzyć istniejący dokument PDF i uzyskać dostęp do jego oznaczonej zawartości przy użyciu Aspose.PDF dla platformy .NET?

A: W tym samouczku zamieszczono przykłady kodu źródłowego w języku C#, które pokazują, jak otworzyć istniejący dokument PDF za pomocą Aspose.PDF dla platformy .NET i uzyskać dostęp do jego oznaczonej zawartości w celu dalszej obróbki.

#### P: Jaki jest cel przypisywania tekstu alternatywnego i ramek ograniczających do obrazów w dokumencie PDF?

A: Przypisywanie alternatywnego tekstu i ramek ograniczających do obrazów zwiększa dostępność, zapewniając opisowy tekst dla obrazów i definiując ich układ i pozycję w dokumencie. Informacje te są kluczowe dla czytników ekranu i innych technologii wspomagających.

#### P: Jak mogę ustawić tytuł dla oznaczonego dokumentu PDF za pomocą Aspose.PDF dla platformy .NET?

A: W tym samouczku znajdują się przykłady kodu źródłowego w języku C#, które ilustrują, jak ustawić tytuł dla oznaczonego dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.

#### P: Na czym polega proces przenoszenia elementów w dokumencie PDF?

A: Przenoszenie elementów w dokumencie PDF wiąże się ze zmianą elementu nadrzędnego konkretnego elementu. W tym samouczku dowiesz się, jak przenieść element Span do określonego elementu Paragraph w tabeli.

#### P: Jak zapisać zmodyfikowany dokument PDF po dodaniu tagów i wprowadzeniu zmian w obrazach?

 A: Po dodaniu tagów, przypisaniu tekstu alternatywnego, ustawieniu pól ograniczających i wprowadzeniu zmian w dokumencie PDF możesz użyć podanych przykładów kodu źródłowego w języku C#, aby zapisać zmodyfikowany dokument PDF za pomocą`Save()` metoda.

#### P: Jaki jest cel przykładowego kodu źródłowego udostępnionego w samouczku?

A: Przykładowy kod źródłowy służy jako praktyczne odniesienie do implementacji tagowania i manipulacji obrazami przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu jako punktu wyjścia i zmodyfikować go, aby odpowiadał Twoim konkretnym wymaganiom.

#### P: Czy mogę zastosować te techniki nie tylko do obrazów, ale także do innych typów elementów w dokumencie PDF?

A: Tak, techniki zaprezentowane w tym samouczku można dostosować do pracy z różnymi typami elementów w dokumencie PDF. Możesz zastosować podobne zasady do tagowania i manipulowania innymi elementami, takimi jak tekst, tabele i inne.

#### P: W jaki sposób mogę sprawdzić zgodność zmodyfikowanego dokumentu PDF ze standardem PDF/UA?

 A: W tym samouczku przedstawiono przykłady kodu źródłowego w języku C#, które pokazują, jak sprawdzić zgodność zmodyfikowanego dokumentu PDF ze standardem PDF/UA, korzystając z`Validate()` metody i generowania raportu XML.

#### P: Jakie inne funkcje oferuje Aspose.PDF dla .NET do pracy z dokumentami PDF?

A: Aspose.PDF dla .NET oferuje szeroki zakres funkcji do pracy z dokumentami PDF, w tym manipulację tekstem, wstawianie obrazów, tworzenie tabel, zarządzanie polami formularzy, podpisy cyfrowe, adnotacje i wiele innych. Zapoznaj się z oficjalną dokumentacją i zasobami, aby uzyskać dalsze informacje.