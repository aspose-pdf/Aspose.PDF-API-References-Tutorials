---
title: Pobierz pola z regionu w pliku PDF
linktitle: Pobierz pola z regionu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe pobieranie pól z określonego obszaru w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 130
url: /pl/net/programming-with-forms/get-fields-from-region/
---
W tym samouczku pokażemy Ci, jak uzyskać pola określonego regionu w pliku PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz plik PDF

Otwórz plik PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Krok 3: Utwórz obiekt prostokątny, aby ograniczyć obszar

Utwórz obiekt prostokątny, aby ograniczyć obszar, w którym chcesz uzyskać pola:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Krok 4: Pobierz formularz PDF

Pobierz dokument w formacie PDF:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Krok 5: Pobierz pola z obszaru prostokątnego

Pobierz pola znajdujące się w określonym prostokątnym regionie:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Krok 6: Wyświetl nazwy i wartości pól

Przejdź przez pola wynikowe i wyświetl ich nazwy i wartości:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Przykładowy kod źródłowy dla funkcji Pobierz pola z regionu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz plik pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Utwórz obiekt prostokątny, aby uzyskać pola w tym obszarze
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Pobierz formularz PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Pobierz pola w obszarze prostokątnym
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Wyświetl nazwy i wartości pól
foreach (Field field in fields)
{
	// Wyświetl właściwości rozmieszczenia obrazu dla wszystkich rozmieszczeń
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak uzyskać pola określonego regionu w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo wyodrębnić pola znajdujące się w danym prostokątnym obszarze dokumentu PDF za pomocą Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę użyć tej metody, aby pobrać pola z obszaru nieprostokątnego w dokumencie PDF?

 A: Nie, podana metoda`GetFieldsInRect` jest specjalnie zaprojektowany do pobierania pól znajdujących się w prostokątnym regionie w dokumencie PDF. Jeśli musisz wyodrębnić pola z regionu nieprostokątnego, musisz zaimplementować niestandardową logikę, aby zidentyfikować i wyodrębnić pola na podstawie innych kryteriów, takich jak współrzędne lub nazwy pól.

#### P: W jaki sposób mogę zmienić rozmiar lub położenie prostokąta, aby uzyskać pola z innego regionu?

 A: Aby uzyskać pola z innego regionu, możesz zmodyfikować`Aspose.Pdf.Rectangle` parametry obiektu używane do zdefiniowania prostokąta ograniczającego.`Rectangle` konstruktor przyjmuje cztery parametry:`x`, `y`, `width` , I`height`które reprezentują współrzędne lewego górnego rogu i wymiary prostokąta. Dostosowanie tych parametrów zmieni region, z którego wyodrębniane są pola.

#### P: Co się stanie, jeśli w określonym obszarze prostokątnym nie będzie żadnych pól?

 A: Jeżeli w określonym obszarze prostokątnym nie ma żadnych pól,`GetFieldsInRect` Metoda zwróci pustą tablicę. Możesz sprawdzić długość tablicy, aby ustalić, czy w regionie znajdują się jakieś pola.

#### P: Czy mogę uzyskać pola z nakładających się obszarów w dokumencie PDF?

 O: Tak, możesz uzyskać pola z nakładających się obszarów w dokumencie PDF, tworząc wiele`Aspose.Pdf.Rectangle` obiekty i wywoływanie`GetFieldsInRect` metodę dla każdego z nich. Nakładające się regiony będą obsługiwane niezależnie, a Ty otrzymasz oddzielne tablice pól dla każdego regionu.

#### P: Czy w dokumencie PDF można pobrać pola z konkretnej strony lub wielu stron?

A: Tak, możesz uzyskać pola z określonej strony lub wielu stron w dokumencie PDF. Aby to osiągnąć, możesz załadować dokument PDF, uzyskać dostęp do żądanych stron za pomocą`doc.Pages` kolekcję, a następnie zastosuj`GetFieldsInRect` metodę do konkretnego regionu każdej strony.