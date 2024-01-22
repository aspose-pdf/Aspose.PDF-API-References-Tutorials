---
title: Dodaj warstwy do pliku PDF
linktitle: Dodaj warstwy do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać warstwy do plików PDF przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku z samouczkami dotyczącymi kodu umożliwiającymi tworzenie i zapisywanie warstwowych plików PDF.
type: docs
weight: 20
url: /pl/net/programming-with-document/addlayers/
---
Aby dodać warstwy do pliku PDF, użyjemy Aspose.PDF dla .NET. Ta biblioteka pozwala nam efektywnie pracować z plikami PDF w aplikacjach .NET. Postępuj zgodnie z instrukcjami krok po kroku poniżej, aby dodać warstwy przy użyciu Aspose.PDF dla .NET.

## Krok 1: Utwórz nowy dokument PDF

 Rozpocznij od utworzenia nowej instancji pliku`Document` klasa dostarczona przez Aspose.PDF dla .NET. Będzie to służyć jako dokument PDF, w którym dodamy warstwy.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Krok 2: Dodaj stronę do dokumentu

 Następnie dodaj stronę do dokumentu za pomocą`Add` metoda`Pages` zbiór w`Document` klasa.

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Utwórz i dodaj warstwy do strony

 Utwórz instancje`Layer` class dla każdej warstwy, którą chcesz dodać do pliku PDF. Określ unikalny identyfikator i nazwę każdej warstwy.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

W tym samouczku dodaliśmy do strony trzy warstwy o różnych kolorach i nazwach.

## Krok 4: Zapisz plik PDF

 Zapisz zmodyfikowany plik PDF za pomocą`Save` metoda`Document` klasa.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Ten kod zapisze zmodyfikowany plik PDF w określonym katalogu.

### Przykładowy kod źródłowy dodawania warstw do stron PDF przy użyciu Aspose.PDF dla .NET

```csharp            
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Wniosek

W tym artykule przedstawiliśmy przewodnik krok po kroku dotyczący dodawania warstw do plików PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami i korzystając z dostarczonych samouczków dotyczących kodu, możesz łatwo włączać warstwy do swoich dokumentów PDF. Warstwy umożliwiają organizowanie i kontrolowanie widoczności treści, zapewniając użytkownikom bardziej interaktywne i konfigurowalne doświadczenia.


### Często zadawane pytania dotyczące dodawania warstw do pliku PDF

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom efektywną pracę z plikami PDF w aplikacjach .NET. Zapewnia szeroką gamę funkcji do tworzenia, modyfikowania i manipulowania dokumentami PDF.

#### P: Czym są warstwy PDF?

O: Warstwy PDF, zwane także opcjonalnymi grupami treści (OCG), umożliwiają kontrolowanie widoczności i wyglądu określonej treści w pliku PDF. Są przydatne do porządkowania treści i tworzenia interaktywnych dokumentów.

#### P: Czy mogę dodać wiele warstw do pliku PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, możesz dodać wiele warstw do pliku PDF za pomocą Aspose.PDF dla .NET. Każda warstwa może mieć swój własny, unikalny identyfikator i nazwę, jak pokazano w samouczku.

#### P: Jak mogę dostosować wygląd warstw?

O: Można dostosować wygląd warstw, określając różne właściwości, takie jak kolor, krycie i widoczność. Aspose.PDF dla .NET zapewnia różne opcje umożliwiające osiągnięcie tego celu.

#### P: Czy Aspose.PDF dla .NET nadaje się do profesjonalnych projektów?

O: Tak, Aspose.PDF dla .NET to niezawodna i szeroko stosowana biblioteka do manipulacji plikami PDF w profesjonalnych projektach. Oferuje rozbudowaną funkcjonalność i doskonałą wydajność do pracy z plikami PDF w aplikacjach .NET.