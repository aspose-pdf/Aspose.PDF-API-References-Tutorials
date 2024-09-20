---
title: Zamień tekst na wyrażenie regularne w pliku PDF
linktitle: Zamień wyrażenie regularne Texton w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zastąpić tekst na podstawie wyrażeń regularnych w pliku PDF za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby skutecznie automatyzować zmiany tekstu.
type: docs
weight: 360
url: /pl/net/programming-with-text/replace-text-on-regular-expression/
---
## Wstęp

Aspose.PDF dla .NET to niesamowite narzędzie, które pozwala programistom z łatwością manipulować plikami PDF. Jedną z jego potężnych funkcji jest możliwość wyszukiwania tekstu na podstawie wyrażeń regularnych i zastępowania go. Jeśli kiedykolwiek musiałeś obsługiwać plik PDF, w którym trzeba było zmienić określone wzorce tekstu, takie jak daty, numery telefonów lub kody — to jest dokładnie to, czego szukasz. W tym samouczku przeprowadzę Cię przez proces zastępowania tekstu za pomocą wyrażeń regularnych w pliku PDF. Podzielimy go na łatwe do wykonania kroki, abyś mógł płynnie zintegrować tę funkcjonalność ze swoimi projektami.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnijmy się, że wszystko jest skonfigurowane:

1.  Aspose.PDF dla .NET: Będziesz potrzebować najnowszej wersji Aspose.PDF dla .NET. Możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio lub inne zintegrowane środowisko programistyczne (IDE) zgodne ze standardem .NET.
3. .NET Framework: Upewnij się, że masz zainstalowany .NET Framework 4.0 lub nowszy.
4. Dokument PDF: przykładowy plik PDF, w którym chcesz wyszukiwać i zamieniać tekst.

Gdy już wszystko jest na swoim miejscu, możesz zacząć!

## Importuj pakiety

Pierwszą rzeczą, którą musimy zrobić, jest zaimportowanie wymaganych pakietów. Dzięki temu mamy dostęp do wszystkich niezbędnych klas i metod z Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Dzięki temu możemy pracować z dokumentami PDF i zarządzać fragmentami tekstu w dokumencie.

Przejdźmy teraz przez proces krok po kroku. Podążaj za nami, gdy będziemy zastępować tekst na podstawie wyrażeń regularnych.

## Krok 1: Załaduj dokument PDF

 Najpierw musisz załadować dokument PDF, w którym będziesz wykonywać zamianę tekstu. Robi się to za pomocą`Document` klasa z Aspose.PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

 W tym kroku zastąp`"YOUR DOCUMENT DIRECTORY"` rzeczywistą ścieżką, w której przechowywany jest plik PDF. Ten kod otwiera plik PDF i ładuje go do`pdfDocument` obiekt, którym będziemy manipulować w kolejnych krokach.

## Krok 2: Zdefiniuj wyrażenie regularne

 Teraz, gdy masz już załadowany dokument, następnym krokiem jest zdefiniowanie wyrażenia regularnego, które będzie wyszukiwać interesujące Cię wzorce tekstowe. Na przykład, jeśli chcesz zastąpić zakres lat, taki jak „1999-2000”, możesz użyć wyrażenia regularnego`\d{4}-\d{4}`.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); 
```

 Ta linia tworzy`TextFragmentAbsorber` który wyszuka dowolną czterocyfrową liczbę, po której następuje myślnik, a następnie kolejna czterocyfrowa liczba. Możesz zmodyfikować wyrażenie regularne w razie potrzeby, aby dopasować je do konkretnego przypadku użycia.

## Krok 3: Włącz opcję wyszukiwania wyrażeń regularnych

 Aspose.PDF pozwala na dokładne dostrojenie sposobu wyszukiwania tekstu. W tym przypadku włączymy dopasowywanie wyrażeń regularnych za pomocą`TextSearchOptions` klasa.

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 Ustawiając tę opcję na`true`, umożliwiasz używanie wyrażeń regularnych do wyszukiwania w pliku PDF.

## Krok 4: Zastosuj Absorber do określonej strony

 Następnie zastosujemy`TextFragmentAbsorber` do konkretnej strony dokumentu. Ten przykład stosuje się do pierwszej strony.

```csharp
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

Ta metoda wyodrębnia wszystkie fragmenty tekstu, które pasują do wyrażenia regularnego z pierwszej strony dokumentu. Jeśli chcesz przeszukać cały dokument, możesz przejść przez wszystkie strony.

## Krok 5: Przejrzyj i zamień tekst

Teraz nadchodzi zabawna część! Przejdziemy przez wyodrębnione fragmenty tekstu, zastąpimy tekst i dostosujemy właściwości, takie jak rozmiar czcionki, typ czcionki i kolor.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase"; // Zastąp nowym tekstem
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 Tutaj przechodzisz przez każdy fragment tekstu, który pasował do wyrażenia regularnego. Dla każdego dopasowania tekst jest zastępowany przez`"New Phrase"`Możesz także dostosować czcionkę do „Verdana”, ustawić rozmiar czcionki na 22 i zmienić kolor tekstu i tła.

## Krok 6: Zapisz zaktualizowany dokument PDF

Po wprowadzeniu wszystkich zmian nadszedł czas na zapisanie zmodyfikowanego dokumentu PDF.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
```

Spowoduje to zapisanie zaktualizowanego pliku PDF ze wszystkimi zamianami tekstu w nowym pliku o nazwie`ReplaceTextonRegularExpression_out.pdf`.

## Krok 7: Zweryfikuj zmiany

Na koniec, aby potwierdzić, że wszystko zadziałało, wyświetl komunikat na konsoli:

```csharp
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

Ten komunikat potwierdzi, że proces zamiany tekstu zakończył się powodzeniem i wskaże lokalizację, w której zapisano nowy plik PDF.

## Wniosek

Udało Ci się zastąpić tekst w pliku PDF na podstawie wyrażeń regularnych za pomocą Aspose.PDF dla .NET! Niezależnie od tego, czy automatyzujesz przetwarzanie dokumentów, czy po prostu usuwasz nieaktualne informacje, ta funkcja jest niezwykle potężna. Za pomocą zaledwie kilku linii kodu możesz wprowadzać złożone zmiany tekstowe w dużych dokumentach w ciągu kilku sekund.

## Najczęściej zadawane pytania

### Czy mogę używać wielu wyrażeń regularnych w jednym dokumencie?
 Tak, możesz utworzyć wiele`TextFragmentAbsorber` obiektów, każdy z różnymi wyrażeniami regularnymi, i zastosować je w dokumencie.

### Czy Aspose.PDF dla .NET jest zgodny z .NET Core?
Tak, Aspose.PDF dla .NET obsługuje zarówno .NET Framework, jak i .NET Core.

### Czy mogę zastąpić tekst na wielu stronach jednocześnie?
Oczywiście! Zamiast stosować absorber do pojedynczej strony, możesz przejść przez wszystkie strony lub nawet zastosować go do całego dokumentu na raz.

### Co zrobić, jeśli chcę wyszukać tekst bez uwzględniania wielkości liter?
Możesz zmodyfikować wyrażenie regularne, tak aby nie uwzględniało wielkości liter, używając odpowiednich flag wyrażenia regularnego lub dostosowując opcje wyszukiwania.

### Czy mogę zastąpić obrazy w pliku PDF?
Tak, Aspose.PDF dla platformy .NET obsługuje również zastępowanie i manipulację obrazami w dokumentach PDF.