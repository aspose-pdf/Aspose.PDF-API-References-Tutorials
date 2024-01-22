---
title: Znaczki z numerem strony w pliku PDF
linktitle: Znaczki z numerem strony w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać znaczniki numerów stron do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 160
url: /pl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak dodać stemple z numerami stron do pliku PDF za pomocą Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby otworzyć istniejący dokument PDF, utworzyć znacznik numeru strony, ustawić jego właściwości i dodać go do określonej strony w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Ładowanie istniejącego dokumentu PDF

Pierwszym krokiem jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz istniejący dokument PDF
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

## Krok 3: Tworzenie i konfiguracja stempla numerującego strony

Po załadowaniu dokumentu PDF możemy utworzyć bufor numeracji stron i skonfigurować go według naszych potrzeb. Oto jak:

```csharp
// Utwórz bufor numeru strony
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

Powyższy kod tworzy stempel numeru strony z właściwościami takimi jak format numeru strony, dolny margines, wyrównanie w poziomie, numer początkowy i właściwości tekstu.

## Krok 4: Dodanie stempla z numerem strony do konkretnej strony

Po skonfigurowaniu znacznika numeru strony możemy dodać go do konkretnej strony dokumentu PDF. Oto jak:

```csharp
// Dodaj bufor numeru strony do określonej strony
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Powyższy kod dodaje stempel z numerem strony do pierwszej strony dokumentu PDF. W razie potrzeby możesz zmienić numer strony.

## Krok 5: Zapisanie zmodyfikowanego dokumentu PDF

Po dodaniu stempla numeru strony do dokumentu PDF możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać edytowany dokument PDF.

### Przykładowy kod źródłowy znaczków z numerami stron przy użyciu Aspose.PDF dla .NET 
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

Gratulacje! Nauczyłeś się, jak dodawać znaczniki numerów stron do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz personalizować swoje dokumenty PDF, dodając jasne i informacyjne numery stron.

### Często zadawane pytania dotyczące znaczników numerów stron w pliku PDF

#### P: Co to jest stempel z numerem strony i jak się go używa do dodawania numerów stron do pliku PDF?

Odp.: Stempel numeru strony to funkcja w Aspose.PDF, która umożliwia dodawanie dynamicznych numerów stron do określonych stron dokumentu PDF. W tym samouczku można to osiągnąć poprzez utworzenie obiektu PageNumberStamp, skonfigurowanie jego właściwości i dodanie go do wyznaczonej strony.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie znaczników numerów stron do pliku PDF?

O: Kod demonstruje, jak załadować istniejący dokument PDF, utworzyć PageNumberStamp, ustawić różne właściwości (takie jak format, czcionka, wyrównanie itp.), a następnie dodać stempel do określonej strony. Stempel automatycznie oblicza całkowitą liczbę stron i wstawia prawidłowe numery stron.

#### P: Czy mogę dostosować wygląd numeru strony, na przykład styl, kolor i rozmiar czcionki?

O: Oczywiście możesz dostosować wygląd stempla numeru strony, dostosowując właściwości takie jak czcionka, rozmiar czcionki, styl czcionki (pogrubienie, kursywa itp.) i kolor tekstu.

#### P: Czy można dodać znaczniki numeru strony do wielu stron w dokumencie PDF?

O: Tak, możesz dodać znaczniki numerów stron do wielu stron, tworząc wiele obiektów PageNumberStamp i dodając każdy z nich do wybranych stron.

#### P: Czy mogę wybrać, czy stempel z numerem strony ma być wyświetlany jako część treści strony, czy jako element tła?

 O: Tak, możesz kontrolować, czy stempel z numerem strony będzie wyświetlany jako część treści strony, czy jako element tła, ustawiając`Background` właściwość PageNumberStamp.

#### P: Jak określić format numeru strony, łącznie z całkowitą liczbą stron?

 Odp.: Kod używa`Format`właściwość PageNumberStamp, aby określić format numeru strony. Makro „# of” służy do reprezentowania całkowitej liczby stron.

#### P: Co się stanie, jeśli dodam ten sam stempel z numerem strony do wielu stron?

Odp.: Dodanie tej samej instancji PageNumberStamp do wielu stron spowoduje wyświetlenie prawidłowych numerów stron dla każdej strony. Stempel automatycznie dostosowuje numer strony i całkowitą liczbę stron.

#### P: Czy mogę dodać znaczniki numeru strony do sekcji nagłówka lub stopki dokumentu PDF?

O: Chociaż znaczniki PageNumberStamps są zwykle dodawane bezpośrednio do zawartości strony, możesz użyć FloatingBox lub innych technik, aby umieścić je w sekcjach nagłówka lub stopki.

#### P: Jak określić położenie stempla z numerem strony na stronie?

 O:`BottomMargin` I`HorizontalAlignment` właściwości PageNumberStamp pozwalają kontrolować położenie stempla na stronie.

#### P: Co się stanie, jeśli chcę rozpocząć numerację stron od innego numeru, a nie od 1?

 O: Możesz ustawić`StartingNumber`właściwość PageNumberStamp, aby określić numer strony początkowej.