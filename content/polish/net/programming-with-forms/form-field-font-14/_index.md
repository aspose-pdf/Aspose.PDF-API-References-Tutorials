---
title: Czcionka pola formularza 14
linktitle: Czcionka pola formularza 14
second_title: Aspose.PDF dla .NET API Reference
description: Łatwa konfiguracja czcionki pól formularzy w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-forms/form-field-font-14/
---
W tym samouczku pokażemy, jak skonfigurować czcionkę pola formularza za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

Otwórz istniejący dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Krok 3: Pobierz konkretne pole formularza

Pobierz żądane pole formularza (w tym przykładzie używamy pola „textbox1”):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Krok 4: Utwórz obiekt czcionki

Utwórz obiekt czcionki dla nowej czcionki, której chcesz użyć (na przykład „ComicSansMS”):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Krok 5: Skonfiguruj informacje o czcionce dla pola formularza

Skonfiguruj informacje o czcionce dla pola formularza, używając czcionki utworzonej wcześniej:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Krok 6: Zapisz zaktualizowany dokument

Zapisz zaktualizowany dokument PDF:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Przykładowy kod źródłowy dla czcionki pola formularza 14 przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Pobierz określone pole formularza z dokumentu
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Utwórz obiekt czcionki
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Ustaw informacje o czcionce dla pola formularza
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(czcionka, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak skonfigurować czcionkę pola formularza za pomocą Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo określić czcionkę i rozmiar czcionki dla pól formularza w dokumentach PDF za pomocą Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę używać dowolnej czcionki dla pól formularzy w pliku Aspose.PDF dla platformy .NET?

A: Tak, możesz użyć dowolnej czcionki TrueType lub OpenType dla pól formularza w Aspose.PDF dla .NET. O ile czcionka jest dostępna i zainstalowana w systemie lub dostępna za pośrednictwem FontRepository, możesz jej użyć do dostosowania wyglądu tekstu pola formularza.

#### P: Gdzie znajdę dostępne czcionki dla platformy .NET w pliku Aspose.PDF?

 A: Aby znaleźć dostępne czcionki w pliku Aspose.PDF dla platformy .NET, możesz użyć`FontRepository.GetAvailableFonts()`Metoda. Ta metoda zwraca tablicę dostępnych czcionek, których możesz użyć w polach formularza lub innych operacjach tekstowych w dokumencie PDF.

#### P: Czy mogę zmienić rozmiar czcionki w polach formularza na dowolną wartość?

A: Tak, możesz zmienić rozmiar czcionki dla pól formularza na dowolną dodatnią wartość liczbową za pomocą Aspose.PDF dla .NET. Należy jednak upewnić się, że rozmiar czcionki jest odpowiedni dla konkretnego pola formularza i nie powoduje obcięcia tekstu ani nakładania się na inne elementy w dokumencie.

#### P: Czy mogę zmienić kolor czcionki pól formularza?

A: Tak, możesz zmienić kolor czcionki dla pól formularza za pomocą Aspose.PDF dla .NET. W podanym kodzie źródłowym C# kolor czcionki jest ustawiony na czarny (`System.Drawing.Color.Black`), ale możesz dostosować go do dowolnej innej prawidłowej wartości koloru.

#### P: Jak mogę wyrównać tekst w polu formularza?

 A: Aby wyrównać tekst w polu formularza, możesz użyć`Multiline`właściwość pola formularza i ustaw ją na true. Ta właściwość umożliwia tekst wielowierszowy w polu formularza, umożliwiając sterowanie wyrównaniem tekstu za pomocą podziałów wierszy i powrotów karetki.