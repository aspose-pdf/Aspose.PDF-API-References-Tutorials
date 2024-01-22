---
title: Pole tekstowe
linktitle: Pole tekstowe
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak utworzyć pole tekstowe w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 290
url: /pl/net/programming-with-forms/text-box/
---
W tym przewodniku wyjaśnimy krok po kroku, jak używać biblioteki Aspose.PDF dla .NET do tworzenia pola tekstowego w dokumencie PDF. Pokażemy Ci, jak otworzyć dokument, utworzyć pole tekstowe, dostosować jego właściwości i zapisać edytowany plik PDF.

## Krok 1: Konfiguracja katalogu dokumentów

 Pierwszym krokiem jest skonfigurowanie katalogu dokumentów, w którym znajduje się plik PDF, nad którym chcesz pracować. Możesz skorzystać z`dataDir` zmienna określająca ścieżkę katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Otwieranie dokumentu PDF

 tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Upewnij się, że plik PDF znajduje się w określonym katalogu dokumentów.

## Krok 3: Tworzenie pola tekstowego

 Stworzymy pole tekstowe za pomocą`TextBoxField` klasa. Możesz określić współrzędne pozycji i rozmiar pola za pomocą`Rectangle` klasa.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

W razie potrzeby dostosuj współrzędne, rozmiar, częściową nazwę i wartość pola tekstowego.

## Krok 4: Dostosuj właściwości pola tekstowego

Na tym etapie dostosujemy właściwości pola tekstowego, takie jak obramowanie, kolor itp.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Dostosuj właściwości pola tekstowego zgodnie ze swoimi preferencjami.

## Krok 5: Dodanie pola do dokumentu

Teraz, gdy utworzyliśmy i skonfigurowaliśmy pole tekstowe, możemy dodać je do dokumentu PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Krok 6: Zapisywanie zmodyfikowanego pliku PDF

 Na koniec możemy zapisać zmodyfikowany plik PDF za pomocą pliku`Save` metoda`Document` klasa.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Pamiętaj, aby podać pełną ścieżkę i nazwę pliku edytowanego pliku PDF.

### Przykładowy kod źródłowy pola tekstowego przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Utwórz pole
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = nowe obramowanie(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Dodaj pole do dokumentu
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Zapisz zmodyfikowany plik PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Wniosek

W tym przewodniku dowiedzieliśmy się, jak używać biblioteki Aspose.PDF dla platformy .NET do tworzenia pola tekstowego w dokumencie PDF. Wykonując opisane kroki, możesz dostosować właściwości pola tekstowego i dodać je do dokumentu według potrzeb. Zachęcamy do dalszego odkrywania funkcji Aspose.PDF dla .NET, aby rozszerzyć możliwości manipulowania plikami PDF.

### Często zadawane pytania

#### P: Czy mogę używać Aspose.PDF dla .NET do tworzenia wielu pól tekstowych w jednym dokumencie PDF?

Odp.: Tak, możesz utworzyć wiele pól tekstowych w jednym dokumencie PDF przy użyciu Aspose.PDF dla .NET. Po prostu powtórz proces tworzenia i dostosowywania pól tekstowych dla każdej żądanej lokalizacji w dokumencie.

#### P: Jak mogę dostosować wygląd pola tekstowego, np. rozmiar i kolor czcionki?

O: Możesz dostosować wygląd pola tekstowego, dostosowując jego właściwości, takie jak rozmiar czcionki, styl czcionki, kolor, styl obramowania, kolor tła i inne. W dostarczonym przykładowym kodzie źródłowym szerokość obramowania, wzór kreski obramowania i kolor tekstu są dostosowywane.

#### P: Czy można wyodrębnić tekst wprowadzony przez użytkownika z utworzonego pola tekstowego?

O: Tak, możesz wyodrębnić tekst wprowadzony przez użytkownika z utworzonego pola tekstowego. Gdy użytkownicy wypełnią pole tekstowe w dokumencie PDF, możesz programowo pobrać wartość pola za pomocą Aspose.PDF dla .NET.

#### P: Czy mogę dodać pola tekstowe do istniejącego dokumentu PDF bez tworzenia nowego?

Odp.: Tak, możesz dodać pola tekstowe do istniejącego dokumentu PDF bez tworzenia nowego. Aspose.PDF dla .NET zapewnia możliwość modyfikowania istniejących dokumentów PDF, w tym dodawania pól tekstowych, pól wyboru i innych elementów formularzy.

#### P: Czy Aspose.PDF dla .NET obsługuje inne typy pól formularzy, takie jak pola wyboru i przyciski opcji?

Odp.: Tak, Aspose.PDF dla .NET obsługuje różne typy pól formularzy, w tym pola wyboru, przyciski opcji, listy rozwijane i inne. Biblioteki można używać do pracy z różnymi typami elementów formularzy w dokumentach PDF.