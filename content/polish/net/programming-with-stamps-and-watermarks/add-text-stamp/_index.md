---
title: Dodaj stempel tekstowy w pliku PDF
linktitle: Dodaj stempel tekstowy w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak łatwo dodać stempel tekstowy do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 50
url: /pl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
W tym samouczku przeprowadzimy Cię krok po kroku, jak dodać stempel tekstowy do pliku PDF za pomocą Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby dodać niestandardowy znacznik tekstowy do określonej strony pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Ładowanie dokumentu PDF

Pierwszym krokiem jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

## Krok 3: Tworzenie bufora tekstowego

Po przesłaniu dokumentu PDF możesz utworzyć stempel tekstowy do dodania. Oto jak to zrobić:

```csharp
// Utwórz bufor tekstowy
TextStamp textStamp = new TextStamp("Example Stamp");
```

Powyższy kod tworzy nowy bufor tekstowy zawierający określony tekst.

## Krok 4: Konfigurowanie właściwości stempla tekstowego

Przed dodaniem stempla tekstowego do dokumentu PDF możesz skonfigurować różne właściwości stempla, takie jak tło, położenie, obrót, czcionka, rozmiar itp. Oto jak:

```csharp
// Skonfiguruj właściwości bufora tekstu
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

Teraz, gdy stempel tekstowy jest już gotowy, możesz dodać go do określonej strony dokumentu PDF. Oto jak:

```csharp
//Dodaj bufor tekstowy do określonej strony
pdfDocument.Pages[1].AddStamp(textStamp);
```

Powyższy kod dodaje stempel tekstowy do pierwszej strony dokumentu PDF. W razie potrzeby możesz określić inną stronę.

## Krok 6: Zapisz dokument wyjściowy

Po dodaniu stempla tekstowego możesz zapisać edytowany dokument PDF. Oto jak:

```csharp
// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
```

Powyższy kod zapisuje zmodyfikowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla opcji Dodaj stempel tekstowy przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp("Sample Stamp");

// Ustaw, czy stempel ma być tłem
textStamp.Background = true;

// Ustaw pochodzenie
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Obróć stempel
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

Gratulacje! Nauczyłeś się, jak dodać stempel tekstowy za pomocą Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę we własnych projektach, aby dodać niestandardowe znaczniki tekstowe do dokumentów PDF.

### Często zadawane pytania dotyczące dodawania stempla tekstowego w pliku PDF

#### P: Jaki jest cel dodawania stempla tekstowego do pliku PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Dodanie stempla tekstowego umożliwia umieszczenie niestandardowego tekstu na określonej stronie dokumentu PDF. Ta funkcja jest przydatna do dodawania etykiet, komentarzy, znaków wodnych lub innych informacji tekstowych w celu ulepszenia zawartości dokumentu i zapewnienia dodatkowego kontekstu.

#### P: Czy mogę dostosować wygląd stempla tekstowego, np. czcionkę, rozmiar, kolor i obrót?

 Odp.: Tak, możesz w pełni dostosować wygląd stempla tekstowego. Dostarczony kod źródłowy języka C# demonstruje, jak ustawić różne właściwości pliku`TextStamp` obiektu, w tym czcionkę, rozmiar czcionki, styl czcionki, kolor tekstu, kolor tła i obrót.

#### P: Czy można dodać wiele znaczników tekstowych do różnych stron tego samego dokumentu PDF?

Odp.: Oczywiście możesz dodać wiele znaczników tekstowych do różnych stron tego samego dokumentu PDF. Kod dostarczony w samouczku pozwala określić stronę docelową do dodania znacznika tekstowego, dzięki czemu jest uniwersalny w przypadku różnych stron w dokumencie.

#### P: Jak określić położenie stempla tekstowego w dokumencie PDF?

 Odp.: Możesz dostosować położenie stempla tekstowego, modyfikując plik`XIndent` I`YIndent` właściwości`TextStamp` obiekt. Właściwości te definiują współrzędne lewego górnego rogu stempla względem początku strony.

#### P: Czy mogę zastosować tę metodę do istniejących dokumentów PDF, aby dodać znaczniki tekstowe?

Odp.: Tak, możesz zastosować tę metodę do istniejących dokumentów PDF, aby dodać znaczniki tekstowe. Kod dostarczony w samouczku pokazuje, jak załadować istniejący dokument PDF i dodać znacznik tekstowy do określonej strony.

#### P: Czy do stempla tekstowego mogę dodać kolory tła i pierwszego planu?

 Odp.: Tak, do stempla tekstowego można dodać zarówno kolory tła, jak i pierwszego planu. Ustawiając`Background` własność do`true` , możesz zapewnić kolorowe tło dla stempla tekstowego. Dodatkowo możesz ustawić`TextState.ForegroundColor` właściwość określająca kolor samego tekstu.

#### P: Jak mogę mieć pewność, że stempel tekstowy nie zasłania podstawowej zawartości dokumentu PDF?

 Odpowiedź: Podczas dodawania stempla tekstowego należy zwrócić uwagę na jego umiejscowienie, aby nie zasłaniać najważniejszych informacji ani nie wpływać negatywnie na czytelność dokumentu. Możesz dostosować`XIndent` I`YIndent` właściwości, aby odpowiednio umieścić znacznik tekstowy.

#### P: Czy mogę użyć tej metody do dodania znaczków innych niż tekst, takich jak obrazy lub logo?

Odp.: Ten konkretny samouczek koncentruje się na dodawaniu znaczków tekstowych, ale możesz w podobny sposób dodawać inne typy stempli, takie jak obrazy lub logo, używając Aspose.PDF dla .NET. Proces polega na utworzeniu odpowiedniego obiektu stempla i skonfigurowaniu jego właściwości.

#### P: Jak mogę zautomatyzować proces dodawania znaczników tekstowych do wielu dokumentów PDF?

O: Możesz zautomatyzować proces dodawania znaczników tekstowych do wielu dokumentów PDF, tworząc skrypt lub program, który przegląda listę dokumentów i stosuje ten sam proces znakowania tekstem do każdego z nich.