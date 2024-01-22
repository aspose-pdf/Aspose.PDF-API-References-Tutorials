---
title: Zastosuj styl liczbowy w pliku PDF
linktitle: Zastosuj styl liczbowy w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zastosować styl numerowania do nagłówków w pliku PDF przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-headings/apply-number-style/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby zastosować styl numerowania w pliku PDF przy użyciu Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

### Krok 1: Konfiguracja katalogu dokumentów

W dostarczonym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wygenerowany plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Tworzenie dokumentu PDF

Tworzymy nowy dokument PDF o określonych wymiarach i marginesach.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Krok 3: Tworzenie strony i pływającego kontenera

Dodajemy stronę do dokumentu i tworzymy pływający kontener do porządkowania treści.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Krok 4: Dodaj nagłówki z numeracją

Tworzymy nagłówki z określoną numeracją i dodajemy je do pływającego kontenera.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Krok 5: Zapisywanie dokumentu PDF

Zapisujemy wygenerowany dokument PDF we wskazanym katalogu.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Przykładowy kod źródłowy dla Zastosuj styl liczbowy przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Wniosek

W tym samouczku wyjaśniliśmy, jak zastosować styl numerowania do nagłówków w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do tworzenia dokumentów PDF z niestandardową numeracją nagłówków.

### Często zadawane pytania dotyczące stosowania stylu liczb w pliku PDF

#### P: Jaki jest styl numeracji w dokumencie PDF?

Odp.: Styl numeracji odnosi się do formatu, w jakim numerowane są nagłówki lub sekcje w dokumencie PDF. Może zawierać cyfry, litery lub inne znaki, aby zapewnić strukturę hierarchiczną.

#### P: Dlaczego miałbym zastosować styl numerowania do nagłówków w dokumencie PDF?

Odp.: Zastosowanie stylu numeracji do nagłówków poprawia czytelność i organizację dokumentu PDF. Pomaga czytelnikom w łatwej nawigacji i zrozumieniu hierarchicznej struktury treści.

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to biblioteka, która umożliwia programistom programową pracę z plikami PDF w aplikacjach .NET. Zapewnia szeroką gamę funkcji do tworzenia, edytowania, konwertowania i manipulowania dokumentami PDF.

#### P: Jak zaimportować wymagane biblioteki do mojego projektu C#?

O: Aby zaimportować niezbędne biblioteki do projektu C#, dołącz następujące dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dyrektywy te umożliwiają dostęp do klas i metod potrzebnych do pracy z dokumentami PDF i stosowania stylów numeracji.

#### P: Jak określić katalog, w którym ma zostać zapisany wygenerowany plik PDF?

O: W dostarczonym kodzie źródłowym zmodyfikuj zmienną „dataDir”, aby określić katalog, w którym chcesz zapisać wygenerowany plik PDF.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu.

#### P: Jak utworzyć dokument PDF o określonych wymiarach i marginesach?

O: Aby utworzyć dokument PDF o określonych wymiarach i marginesach, użyj następującego kodu:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### P: Jak dodać nagłówki ze stylem numeracji do dokumentu PDF?

Odp.: Aby dodać nagłówki ze stylem numeracji do dokumentu PDF, użyj dostarczonych przykładów kodu, aby utworzyć nagłówki i dostosować ich style numeracji. W razie potrzeby dostosuj właściwości, takie jak tekst, styl numeracji, numer początkowy i sekwencja automatyczna.

#### P: Jak zapisać wygenerowany dokument PDF?

 Odp.: Aby zapisać wygenerowany dokument PDF, użyj pliku`Save` metoda`pdfDoc` obiekt:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### P: Jak mogę sprawdzić, czy zastosowano styl numeracji?

O: Otwórz wygenerowany plik PDF, aby sprawdzić, czy do nagłówków zastosowano określony styl numeracji.

#### P: Czy mogę bardziej dostosować styl numeracji?

 O: Tak, możesz dodatkowo dostosować styl numerowania, dostosowując właściwości pliku`Heading` obiektów, takich jak typ stylu numeracji, numer początkowy i sekwencja automatyczna.

#### P: Czy mogę zastosować różne style numeracji do różnych sekcji dokumentu?

O: Tak, możesz zastosować różne style numeracji do różnych sekcji dokumentu, tworząc ich wiele`Heading` obiekty o różnych stylach i sekwencjach.