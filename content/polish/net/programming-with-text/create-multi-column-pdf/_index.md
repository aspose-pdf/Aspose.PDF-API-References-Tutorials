---
title: Utwórz plik PDF z wieloma kolumnami
linktitle: Utwórz plik PDF z wieloma kolumnami
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć plik PDF z wieloma kolumnami za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 110
url: /pl/net/programming-with-text/create-multi-column-pdf/
---
Ten samouczek przeprowadzi Cię przez proces tworzenia pliku PDF z wieloma kolumnami przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz utworzyć plik PDF z wieloma kolumnami, dodaj na górze pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nową instancję dokumentu
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Ustaw marginesy strony
 Określ informacje o lewym i prawym marginesie pliku PDF za pomocą`PageInfo.Margin` własność`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Krok 6: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 7: Utwórz obiekt Graph i dodaj linię
 Utwórz nowy`Graph` obiekt o określonych wymiarach i dodaj do niego linię. Następnie dodaj`Graph` sprzeciwić się`Paragraphs` kolekcja stron.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Krok 8: Dodaj tekst nagłówka z formatowaniem HTML
 Utwórz`HtmlFragment` obiekt i ustaw jego zawartość na pożądany tekst HTML. Następnie dodaj fragment do`Paragraphs` kolekcja stron.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Krok 9: Utwórz FloatingBox z wieloma kolumnami
 Utwórz`FloatingBox` obiekt i ustaw liczbę kolumn i odstępy między kolumnami. Następnie dodaj fragmenty tekstu i linię do`Paragraphs` kolekcja`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Krok 10: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Create Multi Column Pdf using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Określ informacje o lewym marginesie dla pliku PDF
doc.PageInfo.Margin.Left = 40;
// Określ informacje o prawym marginesie dla pliku PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Dodaj linię do kolekcji parafraz obiektu sekcji
page.Paragraphs.Add(graph1);
// Określ współrzędne linii
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Utwórz zmienne łańcuchowe z tekstem zawierającym znaczniki html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Utwórz akapity tekstowe zawierające tekst HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Dodaj cztery kolumny w sekcji
box.ColumnInfo.ColumnCount = 2;
// Ustaw odstęp między kolumnami
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Utwórz obiekt wykresu, aby narysować linię
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Określ współrzędne linii
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Dodaj wiersz do kolekcji akapitów obiektu sekcji
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Wniosek
Udało Ci się utworzyć wielokolumnowy plik PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym skupia się ten samouczek?

Ten samouczek koncentruje się na przeprowadzeniu Cię przez proces tworzenia wielokolumnowego pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby to osiągnąć.

#### P: Jakie przestrzenie nazw powinienem zaimportować na potrzeby tego samouczka?

A: W pliku kodu, w którym chcesz utworzyć plik PDF z wieloma kolumnami, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć nową instancję dokumentu?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając dostarczonego kodu.

#### P: Jak ustawić marginesy strony?

 A: W kroku 5 użyjesz`PageInfo.Margin` własność`Document` aby określić informacje o lewym i prawym marginesie pliku PDF.

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 6 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja.

#### P: Jak utworzyć obiekt Graph i dodać linię?

 A: W kroku 7 utworzysz nowy`Graph` obiekt, dodaj do niego linię, a następnie dodaj`Graph` sprzeciwić się`Paragraphs` kolekcja stron.

#### P: Jak dodać tekst nagłówka z formatowaniem HTML?

 A: W kroku 8 utworzysz`HtmlFragment` obiekt i ustaw jego zawartość na żądany tekst HTML, a następnie dodaj fragment do`Paragraphs` kolekcja stron.

#### P: Jak utworzyć obiekt FloatingBox z wieloma kolumnami?

 A: W kroku 9 utworzysz`FloatingBox` obiekt z wieloma kolumnami i odstępami między kolumnami, a następnie dodaj fragmenty tekstu i linię do`Paragraphs` kolekcja`FloatingBox`.

#### P: Jak zapisać dokument PDF?

 A: W kroku 10 zapiszesz dokument PDF za pomocą`Save` metoda`Document` obiekt.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak utworzyć wielokolumnowy dokument PDF przy użyciu Aspose.PDF dla .NET. Może to być przydatne do wyświetlania treści w uporządkowanym i zorganizowanym układzie.