---
title: Znaczki Numeru Strony W Pliku PDF
linktitle: Znaczki Numeru Strony W Pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać znaczniki numeracji stron do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 160
url: /pl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
W tym samouczku pokażemy Ci krok po kroku, jak dodać stemple z numerami stron w pliku PDF za pomocą Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby otworzyć istniejący dokument PDF, utworzyć stempel z numerem strony, ustawić jego właściwości i dodać go do określonej strony w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Ładowanie istniejącego dokumentu PDF

Pierwszym krokiem jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz istniejący dokument PDF
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

## Krok 3: Tworzenie i konfigurowanie stempla numeracji stron

Teraz, gdy dokument PDF jest załadowany, możemy utworzyć bufor numeracji stron i skonfigurować go zgodnie z naszymi potrzebami. Oto jak to zrobić:

```csharp
// Utwórz bufor numerów stron
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Określ, czy bufor znajduje się w tle, czy nie
pageNumberStamp.Background = false;

// Format bufora numeracji stron
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Dolny margines bufora numeracji stron
pageNumberStamp.BottomMargin = 10;

// Poziome wyrównanie bufora numeracji stron
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Numer początkowy numeracji stron
pageNumberStamp.StartingNumber = 1;

// Ustaw właściwości tekstu bufora numeru strony
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Powyższy kod tworzy stempel numeru strony z właściwościami takimi jak format numeru strony, dolny margines, wyrównanie poziome, numer początkowy i właściwości tekstu.

## Krok 4: Dodawanie stempla z numerem strony do konkretnej strony

Po skonfigurowaniu stempla numeru strony możemy dodać go do konkretnej strony dokumentu PDF. Oto jak to zrobić:

```csharp
// Dodaj bufor numeru strony do określonej strony
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Powyższy kod dodaje stempel numeru strony do pierwszej strony dokumentu PDF. Możesz zmienić numer strony w razie potrzeby.

## Krok 5: Zapisywanie zmodyfikowanego dokumentu PDF

Po dodaniu stempla z numerem strony do dokumentu PDF możemy zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać edytowany dokument PDF.

### Przykładowy kod źródłowy dla pieczątek numeracji stron przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Utwórz stempel z numerem strony
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Czy znaczek jest tłem
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Ustaw właściwości tekstu
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Dodaj znaczek do konkretnej strony
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodawać stemple numeracji stron do dokumentu PDF za pomocą Aspose.PDF dla .NET. Teraz możesz personalizować swoje dokumenty PDF, dodając wyraźne i informacyjne numery stron.

### FAQ dotyczące stempli z numerami stron w plikach PDF

#### P: Czym jest stempel z numerami stron i jak za jego pomocą można dodawać numery stron do pliku PDF?

A: Znacznik numeru strony to funkcja w Aspose.PDF, która umożliwia dodawanie dynamicznych numerów stron do określonych stron dokumentu PDF. W tym samouczku jest to osiągane poprzez utworzenie obiektu PageNumberStamp, skonfigurowanie jego właściwości i dodanie go do wyznaczonej strony.

#### P: W jaki sposób udostępniony kod źródłowy C# umożliwia dodanie znaczników numeracji stron do pliku PDF?

A: Kod pokazuje, jak załadować istniejący dokument PDF, utworzyć PageNumberStamp, ustawić różne właściwości (takie jak format, czcionka, wyrównanie itp.), a następnie dodać stempel do określonej strony. Stempel automatycznie oblicza całkowitą liczbę stron i wstawia prawidłowe numery stron.

#### P: Czy mogę dostosować wygląd numeru strony, np. styl czcionki, kolor i rozmiar?

O: Oczywiście, możesz dostosować wygląd stempla z numerem strony, zmieniając właściwości, takie jak czcionka, jej rozmiar, styl (pogrubienie, kursywa itp.) i kolor tekstu.

#### P: Czy można dodawać numery stron do wielu stron dokumentu PDF?

O: Tak, możesz dodać stemple z numerami stron do wielu stron, tworząc wiele obiektów PageNumberStamp i dodając każdy z nich do wybranych stron.

#### P: Czy mogę wybrać, czy numer strony ma być widoczny jako część zawartości strony czy jako element tła?

 O: Tak, możesz kontrolować, czy numeracja stron ma być wyświetlana jako część zawartości strony, czy jako element tła, ustawiając`Background` Właściwość PageNumberStamp.

#### P: Jak mogę określić format numeru strony, uwzględniając całkowitą liczbę stron?

 A: Kod wykorzystuje`Format`właściwość PageNumberStamp do określania formatu numeru strony. Makro „# of” jest używane do reprezentowania całkowitej liczby stron.

#### P: Co się stanie, jeśli dodam ten sam numer strony do wielu stron?

A: Dodanie tej samej instancji PageNumberStamp do wielu stron spowoduje wyświetlenie prawidłowych numerów stron dla każdej strony. Znacznik automatycznie dostosowuje numer strony i całkowitą liczbę stron.

#### P: Czy mogę dodać numery stron do sekcji nagłówka lub stopki dokumentu PDF?

A: Chociaż elementy PageNumberStamps są zazwyczaj dodawane bezpośrednio do zawartości strony, można użyć FloatingBox lub innych technik, aby umieścić je w sekcjach nagłówka lub stopki.

#### P: Jak określić położenie stempla z numerem strony na stronie?

 A: Ten`BottomMargin` I`HorizontalAlignment` Właściwości PageNumberStamp pozwalają kontrolować położenie stempla na stronie.

#### P: Co zrobić, jeśli chcę rozpocząć numerację stron od innego numeru niż 1?

 A: Możesz ustawić`StartingNumber`Właściwość PageNumberStamp określająca numer strony początkowej.