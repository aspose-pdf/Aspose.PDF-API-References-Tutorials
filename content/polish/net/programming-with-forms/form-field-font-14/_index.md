---
title: Czcionka pola formularza 14
linktitle: Czcionka pola formularza 14
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością skonfiguruj czcionkę pól formularzy w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-forms/form-field-font-14/
---
W tym samouczku pokażemy, jak skonfigurować czcionkę pola formularza za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

Otwórz istniejący dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## Krok 3: Uzyskaj określone pole formularza

Uzyskaj żądane pole formularza (w tym przykładzie używamy pola „textbox1”):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## Krok 4: Utwórz obiekt czcionki

Utwórz obiekt czcionki dla nowej czcionki, której chcesz użyć (na przykład „ComicSansMS”):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## Krok 5: Skonfiguruj informacje o czcionce w polu formularza

Skonfiguruj informacje o czcionce w polu formularza, korzystając z utworzonej wcześniej czcionki:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## Krok 6: Zapisz zaktualizowany dokument

Zapisz zaktualizowany dokument PDF:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Przykładowy kod źródłowy czcionki pola formularza 14 przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Pobierz określone pole formularza z dokumentu
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Utwórz obiekt czcionki
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Ustaw informacje o czcionce w polu formularza
// Field.DefaultAppearance = nowy Aspose.Pdf.Forms.in.DefaultAppearance(czcionka, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyliśmy się konfigurować czcionkę pola formularza za pomocą Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo określić czcionkę i rozmiar czcionki dla pól formularzy w dokumentach PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czy mogę używać dowolnej czcionki w polach formularzy w Aspose.PDF dla .NET?

O: Tak, możesz używać dowolnej czcionki TrueType lub OpenType w polach formularzy w Aspose.PDF dla .NET. O ile czcionka jest dostępna i zainstalowana w systemie lub dostępna poprzez FontRepository, można jej używać do dostosowywania wyglądu tekstu w polach formularza.

#### P: Jak znaleźć dostępne czcionki w Aspose.PDF dla .NET?

 Odp.: Aby znaleźć dostępne czcionki w Aspose.PDF dla .NET, możesz użyć`FontRepository.GetAvailableFonts()`metoda. Ta metoda zwraca tablicę dostępnych czcionek, których można używać w polach formularzy lub innych operacjach związanych z tekstem w dokumencie PDF.

#### P: Czy mogę zmienić rozmiar czcionki w polach formularza na dowolną wartość?

O: Tak, możesz zmienić rozmiar czcionki w polach formularza na dowolną dodatnią wartość liczbową, używając Aspose.PDF dla .NET. Należy jednak zadbać o to, aby rozmiar czcionki był odpowiedni dla konkretnego pola formularza i nie powodował obcięcia tekstu lub nałożenia się na inne elementy dokumentu.

#### P: Czy mogę zmienić kolor czcionki w polach formularza?

Odp.: Tak, możesz zmienić kolor czcionki w polach formularzy za pomocą Aspose.PDF dla .NET. W dostarczonym kodzie źródłowym C# kolor czcionki jest ustawiony na czarny (`System.Drawing.Color.Black`), ale możesz dostosować go do dowolnej innej prawidłowej wartości koloru.

#### P: Jak mogę wyrównać tekst w polu formularza?

 O: Aby wyrównać tekst w polu formularza, możesz użyć metody`Multiline`właściwość pola formularza i ustaw ją na true. Ta właściwość umożliwia włączenie tekstu wielowierszowego w polu formularza, co pozwala kontrolować wyrównanie tekstu za pomocą podziałów wierszy i znaków powrotu karetki.