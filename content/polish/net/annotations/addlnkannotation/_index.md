---
title: Dodaj adnotację dotyczącą linku
linktitle: Dodaj adnotację dotyczącą linku
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać funkcję adnotacji odręcznej do dokumentów PDF w języku C# przy użyciu Aspose.PDF dla .NET z przewodnikiem krok po kroku i pełnym kodem źródłowym.
type: docs
weight: 20
url: /pl/net/annotations/addlnkannotation/
---
Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom wykonywanie różnych operacji na plikach PDF. Jedną z takich operacji jest dodanie adnotacji odręcznej do dokumentów PDF. W tym artykule przedstawimy przewodnik krok po kroku wyjaśniający kod źródłowy C# umożliwiający dodawanie adnotacji odręcznych przy użyciu Aspose.PDF dla .NET. Zacznijmy!

## Zrozumienie funkcji adnotacji atramentowych w Aspose.PDF dla .NET

Zanim zagłębimy się w kod źródłowy C#, przyjrzyjmy się najpierw, czym jest adnotacja odręczna i jakie są jej zastosowania.

Adnotacje odręczne to sposób na rysowanie dowolnych adnotacji odręcznych w dokumentach PDF. Umożliwia tworzenie adnotacji za pomocą rysika lub myszy. Ta funkcja jest przydatna w sytuacjach, gdy trzeba narysować diagramy, szkice lub innego rodzaju adnotacje.

## Krok 1: Tworzenie nowego dokumentu

Pierwszym krokiem podczas dodawania adnotacji odręcznej do dokumentu PDF jest utworzenie nowej instancji klasy Document. Osiąga się to za pomocą następującego fragmentu kodu:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Tutaj tworzymy nową instancję klasy Document i dodajemy do niej nową stronę.

## Krok 2: Tworzenie adnotacji odręcznej

Następnym krokiem jest utworzenie instancji klasy InkAnnotation. Odbywa się to za pomocą następującego fragmentu kodu:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Tutaj najpierw tworzymy prostokąt przy użyciu klasy System.Drawing.Rectangle i konwertujemy go do Aspose.Pdf.Rectangle przy użyciu metody FromRect. Następnie tworzymy instancję klasy InkAnnotation, korzystając z prostokąta, listy punktów i strony, na której dodawana jest adnotacja.

Następnie ustawiamy różne właściwości InkAnnotation, takie jak tytuł, kolor, styl zakończenia, obramowanie i krycie. Na koniec dodajemy adnotację na stronę metodą Annotations.Add.

## Krok 3: Zapisywanie dokumentu

Ostatnim krokiem jest zapisanie dokumentu PDF z dodaną adnotacją odręczną. Osiąga się to za pomocą następującego fragmentu kodu:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Tutaj łączymy nazwę pliku wyjściowego z katalogiem danych i zapisujemy dokument metodą Save.

### Przykładowy kod źródłowy dodawania adnotacji odręcznych przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Zapisz plik wyjściowy
doc.Save(dataDir);
```

## Wniosek

tym samouczku omówiliśmy, jak dodać adnotacje odręczne do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i dostarczonym kodem źródłowym C#, programiści mogą łatwo wdrożyć funkcję adnotacji odręcznych w swoich aplikacjach do przetwarzania plików PDF.

### Często zadawane pytania

#### P: Co to jest adnotacja odręczna w dokumencie PDF?

Odp.: Adnotacja odręczna w dokumencie PDF umożliwia użytkownikom rysowanie dowolnych adnotacji odręcznych za pomocą rysika lub myszy. Jest powszechnie używany do dodawania ręcznie rysowanych szkiców, diagramów i innych odręcznych adnotacji do plików PDF.

#### P: Czy mogę dostosować wygląd adnotacji odręcznej?

Odp.: Tak, Aspose.PDF dla .NET zapewnia różne właściwości umożliwiające dostosowanie wyglądu adnotacji odręcznej, takie jak kolor, krycie, styl czapki, szerokość obramowania i inne. Deweloperzy mogą dostosować te właściwości do swoich specyficznych wymagań.

#### P: Czy można dodać wiele adnotacji odręcznych do jednej strony PDF?

Odp.: Tak, możesz dodać wiele adnotacji odręcznych do pojedynczej strony PDF przy użyciu Aspose.PDF dla .NET. Każda adnotacja odręczna może mieć własny zestaw punktów i dostosowany wygląd.

#### P: Czy mogę dodawać adnotacje odręczne do istniejących dokumentów PDF?

Odp.: Tak, Aspose.PDF dla .NET umożliwia dodawanie adnotacji atramentowych zarówno do nowo utworzonych dokumentów PDF, jak i istniejących plików PDF. Możesz otworzyć istniejący plik PDF, dodać adnotacje odręczne i zapisać zaktualizowany dokument.

#### P: Jakie są typowe przypadki użycia adnotacji odręcznych w dokumentach PDF?

Odp.: Adnotacje odręczne są przydatne w szerokim zakresie zastosowań, w tym do dodawania podpisów lub odręcznych notatek do formularzy PDF, dodawania adnotacji do planów architektonicznych lub rysunków technicznych oraz oznaczania dokumentów do wspólnego przeglądu.