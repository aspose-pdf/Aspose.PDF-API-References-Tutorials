---
title: Oznacz obraz w istniejącym pliku PDF
linktitle: Oznacz obraz w istniejącym pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak oznaczyć obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący dodawania tagów do obrazów.
type: docs
weight: 210
url: /pl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
W tym szczegółowym samouczku przeprowadzimy Cię krok po kroku przez dostarczony kod źródłowy C#, aby oznaczyć obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z poniższymi instrukcjami, aby dowiedzieć się, jak dodać znaczniki do obrazu w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do korzystania z Aspose.PDF dla .NET. Obejmuje to instalację biblioteki Aspose.PDF i skonfigurowanie projektu tak, aby się do niej odwoływał.

## Krok 2: Otwórz istniejący dokument PDF

tym kroku otworzymy istniejący dokument PDF przy użyciu Aspose.PDF.

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

## Krok 3: Uzyskaj oznakowaną treść i element struktury głównej

Teraz otrzymamy oznaczoną treść dokumentu PDF i odpowiadający jej element struktury głównej.

```csharp
// Pobierz otagowaną treść i element struktury głównej
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy oznaczoną treść dokumentu PDF i odpowiadający jej element struktury głównej.

## Krok 4: Ustawianie tytułu oznaczonego dokumentu PDF

Teraz ustawmy tytuł otagowanego dokumentu PDF.

```csharp
// Zdefiniuj tytuł oznaczonego dokumentu PDF
taggedContent.SetTitle("Document with images");
```

Ustawiliśmy tytuł dla oznaczonego dokumentu PDF.

## Krok 5: Przypisz teksty alternatywne i obwiednię do obrazu

Teraz dla każdego elementu obrazu przypiszemy tekst alternatywny i obwiednię.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Przypisz tekst alternatywny do obrazu
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Utwórz i przypisz obwiednię (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Do każdego elementu obrazu w dokumencie PDF przypisaliśmy tekst alternatywny i obwiednię.

## Krok 6: Przeniesienie elementu Span do akapitu

Teraz przenieśmy element Span do akapitu.

```csharp
// Przenieś element Span do akapitu (znajdź nieprawidłowy zakres i akapit w pierwszym TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Przesuń element Rozpiętość w akapicie
spanElement.ChangeParentElement(paragraph);
```

Przenieśliśmy element Span do określonego akapitu.

## Krok 7: Zapisanie zmodyfikowanego dokumentu PDF

Teraz, gdy dokonaliśmy niezbędnych zmian, zapiszemy zmodyfikowany dokument PDF.

```csharp
// Zapisz dokument PDF
document. Save(outFile);
```

Zapisaliśmy zmodyfikowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy dla obrazu znacznika w istniejącym pliku PDF przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otwórz dokument
Document document = new Document(inFile);

// Pobiera oznakowaną treść i element struktury głównej
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Ustaw tytuł oznaczonego dokumentu PDF
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Ustaw tekst alternatywny dla rysunku
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Utwórz i ustaw atrybut BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Przenieś element rozpiętości do akapitu (znajdź niewłaściwy rozpiętość i akapit w pierwszym TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Przenieś element rozpiętości do akapitu
spanElement.ChangeParentElement(paragraph);

// Zapisz dokument
document.Save(outFile);

//Sprawdzanie zgodności wychodzącego dokumentu z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyliśmy się, jak oznaczać obraz w istniejącym pliku PDF za pomocą Aspose.PDF dla .NET. Możesz teraz używać Aspose.PDF do dodawania tagów i edytowania obrazów w dokumentach PDF.

### Często zadawane pytania

#### P: Jaki jest główny cel tego samouczka dotyczącego oznaczania obrazów w istniejącym pliku PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Głównym celem tego samouczka jest poprowadzenie Cię przez proces zaznaczania obrazu w istniejącym dokumencie PDF przy użyciu Aspose.PDF dla .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu źródłowego języka C#, które pomogą Ci zrozumieć, jak przypisywać alternatywny tekst i ramki ograniczające do obrazów, przenosić elementy w dokumencie i dodawać tagi do obrazów.

#### P: Jakie są wymagania wstępne, aby skorzystać z tego samouczka dotyczącego oznaczania obrazów w pliku PDF przy użyciu Aspose.PDF dla .NET?

O: Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do korzystania z Aspose.PDF dla .NET. Obejmuje to zainstalowanie biblioteki Aspose.PDF i skonfigurowanie projektu tak, aby się do niej odwoływał.

#### P: Jak mogę otworzyć istniejący dokument PDF i uzyskać dostęp do jego oznaczonej zawartości przy użyciu Aspose.PDF dla .NET?

Odp.: W samouczku znajdują się przykłady kodu źródłowego C#, które pokazują, jak otworzyć istniejący dokument PDF przy użyciu Aspose.PDF dla .NET i uzyskać dostęp do jego oznaczonej zawartości w celu dalszej manipulacji.

#### P: Jaki jest cel przypisywania alternatywnego tekstu i ramek ograniczających do obrazów w dokumencie PDF?

Odp.: Przypisanie alternatywnego tekstu i ramek ograniczających do obrazów zwiększa dostępność, zapewniając tekst opisowy dla obrazów oraz definiując ich układ i położenie w dokumencie. Informacje te są kluczowe dla czytników ekranu i innych technologii wspomagających.

#### P: Jak mogę ustawić tytuł oznaczonego dokumentu PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Samouczek zawiera przykłady kodu źródłowego C#, które ilustrują, jak ustawić tytuł oznakowanego dokumentu PDF przy użyciu Aspose.PDF dla .NET.

#### P: Na czym polega proces przenoszenia elementów w dokumencie PDF?

Odp.: Przenoszenie elementów w dokumencie PDF wiąże się ze zmianą elementu nadrzędnego określonego elementu. W tym samouczku dowiesz się, jak przenieść element Span do określonego elementu Akapit w tabeli.

#### P: Jak zapisać zmodyfikowany dokument PDF po dodaniu tagów i dokonaniu edycji obrazów?

 O: Po dodaniu tagów, przypisaniu tekstu alternatywnego, ustawieniu ramek ograniczających i wprowadzeniu zmian w dokumencie PDF możesz użyć dostarczonych przykładów kodu źródłowego C#, aby zapisać zmodyfikowany dokument PDF za pomocą`Save()` metoda.

#### P: Jaki jest cel przykładowego kodu źródłowego udostępnionego w samouczku?

O: Przykładowy kod źródłowy służy jako praktyczne odniesienie do wdrażania tagowania i manipulacji obrazami przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu jako punktu wyjścia i zmodyfikować go tak, aby odpowiadał Twoim konkretnym wymaganiom.

#### P: Czy mogę zastosować te techniki do innych typów elementów w dokumencie PDF, a nie tylko do obrazów?

O: Tak, techniki zademonstrowane w tym samouczku można dostosować do pracy z różnymi typami elementów w dokumencie PDF. Możesz zastosować podobne zasady do oznaczania i manipulowania innymi elementami, takimi jak tekst, tabele i inne.

#### P: Jak mogę sprawdzić zgodność zmodyfikowanego dokumentu PDF z formatem PDF/UA?

 O: W samouczku znajdują się przykłady kodu źródłowego języka C#, które pokazują, jak sprawdzić zgodność zmodyfikowanego dokumentu PDF z formatem PDF/UA za pomocą`Validate()` metodę i wygenerowanie raportu XML.

#### P: Jakie inne funkcje oferuje Aspose.PDF dla .NET do pracy z dokumentami PDF?

Odp.: Aspose.PDF dla .NET oferuje szeroką gamę funkcji do pracy z dokumentami PDF, w tym manipulację tekstem, wstawianie obrazów, tworzenie tabel, zarządzanie polami formularzy, podpisy cyfrowe, adnotacje i inne. Aby uzyskać dalsze informacje, zapoznaj się z oficjalną dokumentacją i zasobami.