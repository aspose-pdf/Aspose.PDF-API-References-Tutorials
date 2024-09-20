---
title: Dodaj stempel tekstowy do pliku PDF
linktitle: Dodaj stempel tekstowy do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać znacznik tekstowy do pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z naszego przewodnika krok po kroku, i udoskonal prezentacje swoich dokumentów.
type: docs
weight: 50
url: /pl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Wstęp

dzisiejszej erze cyfrowej pliki PDF są powszechnym formatem udostępniania i dostarczania dokumentów. Niezależnie od tego, czy jesteś programistą, twórcą treści, czy po prostu osobą, która chce ulepszyć swoje pliki PDF, wiedza o tym, jak programowo manipulować plikami PDF, może być przełomowa. Jedną z przydatnych funkcji, z których możesz chcieć skorzystać, jest możliwość dodawania stempli tekstowych do plików PDF. Dodanie stempla tekstowego może nadać dokumentom profesjonalny charakter lub przekazać ważne informacje, takie jak „Próbka”, „Poufne” lub nawet znak wodny.

## Wymagania wstępne

Zanim przejdziemy do kodu, jest kilka wymagań wstępnych, aby upewnić się, że wszystko jest poprawnie skonfigurowane. Oto, czego będziesz potrzebować:

1.  Aspose.PDF dla .NET: Upewnij się, że biblioteka Aspose.PDF jest zainstalowana w Twoim projekcie. Jeśli jeszcze tego nie zrobiłeś, możesz ją pobrać z[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio lub kompatybilne IDE: Będziesz potrzebować środowiska programistycznego, aby pisać i uruchamiać kod .NET. Visual Studio jest najczęstszym wyborem wśród deweloperów.
3. Podstawowa znajomość języka C#: Znajomość języka C# i zasad programowania obiektowego pomoże Ci lepiej zrozumieć przykłady.
4. Przykładowy plik PDF: Powinieneś mieć gotowy plik PDF do pracy. Możesz utworzyć podstawowy plik PDF lub użyć dowolnego istniejącego pliku PDF, aby przetestować funkcjonalność.

Gdy już spełnisz te wymagania wstępne, możemy przejść do kodowania!

## Importuj pakiety

Teraz zaimportujmy niezbędne pakiety. Ten krok jest kluczowy, ponieważ udostępnia klasy i metody z biblioteki Aspose w Twoim projekcie.

### Importuj Aspose.PDF Assembly

Aby rozpocząć, musisz zaimportować przestrzeń nazw Aspose.PDF. Na górze pliku C# dodaj następującą dyrektywę using:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Dzięki temu uzyskasz dostęp do zajęć niezbędnych do tworzenia i edytowania dokumentów PDF.

Przejdźmy teraz do sedna samouczka. Podzielimy proces na jasne i zwięzłe kroki. Każdy krok poprowadzi Cię przez kod, aby dodać stempel tekstowy do pliku PDF.

## Krok 1: Skonfiguruj katalog dokumentów

Najpierw musisz ustalić katalog, w którym przechowywany jest Twój dokument PDF. Oznacza to, że Twój kod musi wiedzieć, gdzie znaleźć plik PDF, który chcesz edytować.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Wyjaśnienie: Zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się Twój plik PDF (`AddTextStamp.pdf`) jest przechowywany. Ta ścieżka jest później używana do otwierania i zapisywania zmodyfikowanego pliku PDF.

## Krok 2: Otwórz dokument PDF

 Następnie otworzymy dokument PDF za pomocą`Document` klasa z przestrzeni nazw Aspose.PDF.

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Wyjaśnienie: Tutaj tworzymy instancję`Document` klasa i przekazując ścieżkę do naszego pliku PDF. Spowoduje to załadowanie pliku PDF, abyśmy mogli nim manipulować.

## Krok 3: Utwórz stempel tekstowy

Teraz utworzymy stempel tekstowy, który później zastosujemy w naszym dokumencie PDF.

```csharp
// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Wyjaśnienie:`TextStamp` obiekt jest tworzony z tekstem, który chcesz wyświetlić. W tym przypadku używamy „Sample Stamp” jako tekstu dla naszego stempla.

## Krok 4: Ustaw właściwości stempla

Aby dostosować swój znaczek, możemy ustawić różne właściwości, takie jak kolor tła, położenie i obrót. Zróbmy to teraz:

```csharp
// Ustaw, czy znaczek jest tłem
textStamp.Background = true;

// Ustaw początek
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Obróć znaczek
textStamp.Rotate = Rotation.on90;
```

Wyjaśnienie:
- Tło: Ustawienie tego na`true` oznacza, że znaczek pojawi się za treścią pliku PDF.
- XIndent i YIndent: Te właściwości określają położenie stempla na stronie. W tym przykładzie stempel zostanie umieszczony 100 jednostek od lewej i górnej krawędzi strony.
- Obróć: Obróć znaczek o 90 stopni. Możesz wybrać różne opcje obrotu w zależności od wymagań projektu.

## Krok 5: Dostosuj właściwości tekstu

Następnie pozwólmy sobie na odrobinę kreatywności i dostosujmy wygląd tekstu w naszym stemplu:

```csharp
// Ustaw właściwości tekstu
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Wyjaśnienie:
- Czcionka: Używamy czcionki Arial, pogrubionej i pochylonej.
- Rozmiar czcionki: Ustawiony na 14 punktów.
- ForegroundColor: Używając RGB, aby ustawić kolor tekstu na Aqua. Możesz swobodnie zmieniać kolor, aby dopasować go do potrzeb Twojej marki lub projektu!

## Krok 6: Dodaj stempel do strony PDF

Teraz pora dodać stempel do konkretnej strony dokumentu PDF.

```csharp
// Dodaj znaczek do konkretnej strony
pdfDocument.Pages[1].AddStamp(textStamp);
```

Wyjaśnienie: W tym przykładzie znaczek jest dodawany do pierwszej strony pliku PDF (strony są indeksowane 1). Dostosuj numer strony zgodnie z potrzebami dokumentu.

## Krok 7: Zapisz zmodyfikowany plik PDF

Na koniec zapiszemy dokument z nowo dodanym znacznikiem tekstowym.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Wyjaśnienie: Definiujemy nową ścieżkę dla pliku wyjściowego, a następnie zapisujemy zmodyfikowany dokument. Po zapisaniu ścieżka jest drukowana na konsoli, potwierdzając pomyślną operację.

## Wniosek

Gratulacje! Udało Ci się dodać stempel tekstowy do pliku PDF za pomocą Aspose.PDF dla .NET. Ta metoda pozwala na wydajne adnotowanie dokumentów, zwiększając ich profesjonalizm i użyteczność. Niezależnie od tego, czy dodajesz znaki wodne, podpisy czy proste notatki, biblioteka Aspose zapewnia potężne narzędzia do łatwego manipulowania plikami PDF.

## Najczęściej zadawane pytania

### Czym jest stempel tekstowy w pliku PDF?
Pieczątka tekstowa to graficzna nakładka zawierająca tekst, którą można umieścić na dokumencie PDF, często używana do adnotacji lub znaków wodnych.

### Czy mogę spersonalizować znaczek za pomocą obrazów?
Tak, Aspose.PDF obsługuje również dodawanie stempli graficznych, co zapewnia większą elastyczność projektowania.

### Jakich języków programowania mogę używać w Aspose.PDF?
Aspose.PDF jest przeznaczony głównie dla platformy .NET, ale istnieją wersje dla innych języków, np. Java i Python.

### Jak uzyskać tymczasową licencję na Aspose.PDF?
 Możesz złożyć wniosek o tymczasową licencję, odwiedzając stronę[link do zakupu](https://purchase.aspose.com/temporary-license/) na ich stronie internetowej.

### Gdzie mogę znaleźć pomoc dotyczącą Aspose.PDF?
 Wsparcie dla Aspose.PDF jest dostępne na ich stronie[forum wsparcia](https://forum.aspose.com/c/pdf/10).