---
title: Dodaj stempel tekstowy do pliku PDF
linktitle: Dodaj stempel tekstowy do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak łatwo dodać stempel tekstowy do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 50
url: /pl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
W tym samouczku pokażemy Ci krok po kroku, jak dodać stempel tekstowy do pliku PDF za pomocą Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby dodać niestandardowy stempel tekstowy do określonej strony pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Ładowanie dokumentu PDF

Pierwszym krokiem jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

## Krok 3: Tworzenie bufora tekstu

Teraz, gdy przesłałeś dokument PDF, możesz utworzyć stempel tekstowy, który chcesz dodać. Oto jak to zrobić:

```csharp
// Utwórz bufor tekstu
TextStamp textStamp = new TextStamp("Example Stamp");
```

Powyższy kod tworzy nowy bufor tekstowy zawierający określony tekst.

## Krok 4: Konfigurowanie właściwości znacznika tekstowego

Przed dodaniem stempla tekstowego do dokumentu PDF możesz skonfigurować różne właściwości stempla, takie jak tło, położenie, obrót, czcionkę, rozmiar itp. Oto jak to zrobić:

```csharp
// Konfigurowanie właściwości bufora tekstu
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Możesz dostosować te właściwości do swoich potrzeb.

## Krok 5: Dodaj stempel tekstowy do pliku PDF

Teraz, gdy stempel tekstowy jest gotowy, możesz dodać go do konkretnej strony dokumentu PDF. Oto jak to zrobić:

```csharp
//Dodaj bufor tekstu do określonej strony
pdfDocument.Pages[1].AddStamp(textStamp);
```

Powyższy kod dodaje stempel tekstowy do pierwszej strony dokumentu PDF. W razie potrzeby możesz określić inną stronę.

## Krok 6: Zapisz dokument wyjściowy

Po dodaniu stempla tekstowego możesz zapisać edytowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
```

Powyższy kod zapisuje zmodyfikowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla funkcji Dodaj znacznik tekstowy przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp("Sample Stamp");

// Ustaw, czy znaczek jest tłem
textStamp.Background = true;

// Ustaw początek
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Obróć znaczek
textStamp.Rotate = Rotation.on90;

// Ustaw właściwości tekstu
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Dodaj znaczek do konkretnej strony
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać stempel tekstowy za pomocą Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę w swoich projektach, aby dodać niestandardowe stemple tekstowe do dokumentów PDF.

### FAQ dotyczące dodawania stempla tekstowego do pliku PDF

#### P: Jaki jest cel dodawania znacznika tekstowego do pliku PDF za pomocą Aspose.PDF dla platformy .NET?

A: Dodanie stempla tekstowego pozwala umieścić niestandardowy tekst na określonej stronie dokumentu PDF. Ta funkcja jest przydatna do dodawania etykiet, komentarzy, znaków wodnych lub innych informacji tekstowych w celu wzbogacenia zawartości dokumentu i zapewnienia dodatkowego kontekstu.

#### P: Czy mogę dostosować wygląd znacznika tekstowego, np. czcionkę, rozmiar, kolor i obrót?

 A: Tak, możesz w pełni dostosować wygląd znacznika tekstowego. Dostarczony kod źródłowy C# pokazuje, jak ustawić różne właściwości znacznika`TextStamp` obiekt, w tym czcionka, rozmiar czcionki, styl czcionki, kolor tekstu, kolor tła i obrót.

#### P: Czy można dodać wiele stempli tekstowych na różnych stronach tego samego dokumentu PDF?

A: Oczywiście, możesz dodać wiele stempli tekstowych do różnych stron tego samego dokumentu PDF. Kod dostarczony w samouczku pozwala określić stronę docelową, na której ma zostać dodany stempel tekstowy, dzięki czemu jest on uniwersalny dla różnych stron w dokumencie.

#### P: Jak określić położenie stempla tekstowego w dokumencie PDF?

 A: Możesz dostosować położenie stempla tekstowego, modyfikując`XIndent` I`YIndent` właściwości`TextStamp` obiekt. Właściwości te definiują współrzędne lewego górnego rogu znaczka względem początku strony.

#### P: Czy mogę zastosować tę metodę do istniejących dokumentów PDF, aby dodać stemple tekstowe?

A: Tak, możesz zastosować tę metodę do istniejących dokumentów PDF, aby dodać stemple tekstowe. Kod dostarczony w samouczku pokazuje, jak załadować istniejący dokument PDF i dodać stempel tekstowy do określonej strony.

#### P: Czy mogę dodać do stempla tekstowego zarówno kolory tła, jak i pierwszego planu?

 A: Tak, możesz dodać zarówno kolory tła, jak i pierwszego planu do stempla tekstowego. Ustawiając`Background` nieruchomość do`true` , możesz zapewnić kolorowe tło dla stempla tekstowego. Dodatkowo możesz ustawić`TextState.ForegroundColor` Właściwość umożliwiająca określenie koloru samego tekstu.

#### P: Jak mogę mieć pewność, że stempel tekstowy nie będzie zasłaniał podstawowej treści dokumentu PDF?

A: Dodając stempel tekstowy, pamiętaj o jego umiejscowieniu, aby upewnić się, że nie zasłania on ważnych informacji ani nie wpływa negatywnie na czytelność dokumentu. Możesz dostosować`XIndent` I`YIndent` właściwości umożliwiające odpowiednie umiejscowienie stempla tekstowego.

#### P: Czy mogę użyć tej metody, aby dodać inne stemple niż tekst, np. obrazy lub logo?

A: Ten konkretny samouczek skupia się na dodawaniu stempli tekstowych, ale możesz podobnie dodać inne rodzaje stempli, takie jak obrazy lub logo, używając Aspose.PDF dla .NET. Proces obejmuje utworzenie odpowiedniego obiektu stempla i skonfigurowanie jego właściwości.

#### P: W jaki sposób mogę zautomatyzować proces dodawania znaczników tekstowych do wielu dokumentów PDF?

A: Możesz zautomatyzować proces dodawania znaczników tekstowych do wielu dokumentów PDF, tworząc skrypt lub program, który przechodzi przez listę dokumentów i stosuje ten sam proces dodawania znaczników tekstowych do każdego z nich.