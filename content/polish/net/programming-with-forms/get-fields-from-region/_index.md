---
title: Pobierz pola z regionu w pliku PDF
linktitle: Pobierz pola z regionu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością uzyskaj pola z określonego regionu w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 130
url: /pl/net/programming-with-forms/get-fields-from-region/
---
W tym samouczku pokażemy, jak uzyskać pola określonego regionu w pliku PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz plik PDF

Otwórz plik PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Krok 3: Utwórz obiekt prostokątny, aby ograniczyć region

Utwórz obiekt prostokątny, aby ograniczyć region, w którym chcesz uzyskać pola:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Krok 4: Uzyskaj formularz PDF

Pobierz dokument w formacie PDF:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Krok 5: Zdobądź pola w prostokątnym regionie

Pobierz pola znajdujące się w określonym prostokątnym regionie:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Krok 6: Wyświetl nazwy i wartości pól

Iteruj po powstałych polach i wyświetl ich nazwy i wartości:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Przykładowy kod źródłowy dla opcji Pobierz pola z regionu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz plik pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Utwórz obiekt prostokątny, aby uzyskać pola w tym obszarze
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Pobierz formularz PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Uzyskaj pola w obszarze prostokątnym
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Wyświetl nazwy pól i wartości
foreach (Field field in fields)
{
	// Wyświetl właściwości rozmieszczenia obrazu dla wszystkich miejsc docelowych
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak uzyskać pola określonego regionu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo wyodrębnić pola znajdujące się w danym prostokątnym obszarze dokumentu PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czy mogę użyć tej metody, aby uzyskać pola z obszaru innego niż prostokątny w dokumencie PDF?

 Odp.: Nie, podana metoda`GetFieldsInRect` jest specjalnie zaprojektowany do pobierania pól znajdujących się w prostokątnym obszarze w dokumencie PDF. Jeśli chcesz wyodrębnić pola z regionu innego niż prostokątny, musisz zaimplementować niestandardową logikę, aby zidentyfikować i wyodrębnić pola na podstawie innych kryteriów, takich jak współrzędne lub nazwy pól.

#### P: Jak mogę zmodyfikować rozmiar lub położenie prostokąta, aby uzyskać pola z innego regionu?

 Odp.: Aby uzyskać pola z innego regionu, możesz zmodyfikować plik`Aspose.Pdf.Rectangle` parametry obiektu użyte do zdefiniowania prostokąta ograniczającego. The`Rectangle` konstruktor przyjmuje cztery parametry:`x`, `y`, `width` , I`height`które reprezentują współrzędne lewego górnego rogu i wymiary prostokąta. Dostosowanie tych parametrów spowoduje zmianę regionu, z którego wyodrębniane są pola.

#### P: Co się stanie, jeśli w określonym prostokątnym obszarze nie ma żadnych pól?

 Odp.: Jeśli w określonym prostokątnym obszarze nie ma żadnych pól, plik`GetFieldsInRect` metoda zwróci pustą tablicę. Możesz sprawdzić długość tablicy, aby określić, czy w regionie znajdują się jakieś pola.

#### P: Czy mogę uzyskać pola z nakładających się regionów w dokumencie PDF?

 O: Tak, możesz uzyskać pola z nakładających się regionów w dokumencie PDF, tworząc ich wiele`Aspose.Pdf.Rectangle` obiektów i wywoływanie`GetFieldsInRect` metoda dla każdego z nich. Nakładające się regiony będą obsługiwane niezależnie i dla każdego regionu otrzymasz oddzielne tablice pól.

#### P: Czy można uzyskać pola z określonej strony lub wielu stron w dokumencie PDF?

Odp.: Tak, możesz uzyskać pola z określonej strony lub wielu stron w dokumencie PDF. Aby to osiągnąć, możesz załadować dokument PDF i uzyskać dostęp do żądanych stron za pomocą`doc.Pages` kolekcję, a następnie zastosuj`GetFieldsInRect` metodę do określonego regionu każdej strony.