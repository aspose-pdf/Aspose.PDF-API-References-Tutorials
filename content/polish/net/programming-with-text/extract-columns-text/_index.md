---
title: Wyodrębnij tekst kolumn w pliku PDF
linktitle: Wyodrębnij tekst kolumn w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić kolumny tekstu z plików PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik rozbija każdy krok na przykłady kodu i wyjaśnienia.
type: docs
weight: 150
url: /pl/net/programming-with-text/extract-columns-text/
---
## Wstęp

Czy pracujesz z plikami PDF i potrzebujesz wyodrębnić tekst w określonym formacie kolumn? Niezależnie od tego, czy przetwarzasz faktury, raporty czy jakiekolwiek dokumenty strukturalne, dokładne wyodrębnienie tekstu z pliku PDF może być trudnym zadaniem. W tym miejscu Aspose.PDF for .NET wkracza, aby uprościć proces. W tym samouczku przeprowadzimy Cię przez proces łatwego wyodrębniania kolumn tekstu z pliku PDF. 

## Wymagania wstępne

Zanim zagłębimy się w kod, omówmy podstawowe rzeczy, których będziesz potrzebować:

-  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną najnowszą wersję Aspose.PDF dla .NET. Jeśli nie, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne: Do pracy z kodem potrzebne będzie środowisko Visual Studio lub inne środowisko programistyczne .NET.
- Dokument PDF: Przygotuj przykładowy dokument PDF, najlepiej taki, który zawiera kolumny tekstu, ponieważ będziemy wyodrębniać z niego tekst.

 Jeśli jeszcze nie zainstalowałeś Aspose.PDF dla .NET, możesz pobrać[bezpłatny okres próbny](https://releases.aspose.com/) Lub[kup licencję](https://purchase.aspose.com/buy) aby uzyskać pełne funkcje. Możesz również ubiegać się o[licencja tymczasowa](https://purchase.aspose.com/temporary-license) jeśli to konieczne.

## Importuj przestrzenie nazw

Aby użyć Aspose.PDF dla .NET w swoim projekcie, musisz zaimportować następujące przestrzenie nazw:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Przewodnik krok po kroku: Wyodrębnij kolumny tekstu z pliku PDF

Teraz rozbijmy każdą część kodu, aby lepiej zrozumieć, jak on działa. Podążaj za nami krok po kroku, wyjaśniając każdy segment procesu.

## Krok 1: Załaduj dokument PDF

 Pierwszą rzeczą, którą musisz zrobić, jest załadowanie pliku PDF do`Document`obiekt. W ten sposób Aspose.PDF wchodzi w interakcję z Twoim dokumentem.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 W tym kroku po prostu definiujemy katalog, w którym przechowywany jest dokument PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do lokalnego pliku PDF.`Document` Obiekt ładuje plik PDF do pamięci, umożliwiając jego dalsze przetwarzanie.

## Krok 2: Skonfiguruj absorber fragmentów tekstu

 Następnie użyjemy`TextFragmentAbsorber` aby wchłonąć lub przechwycić cały tekst z pliku PDF. Ta klasa absorbera została zaprojektowana w celu wyodrębnienia fragmentów tekstu z określonych obszarów w pliku PDF, co czyni ją idealną do wyodrębniania kolumn tekstu.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Tutaj tworzymy instancję`TextFragmentAbsorber` i zastosuj go do wszystkich stron pliku PDF za pomocą`Accept()` . Ten`TextFragmentCollection` przechowuje wyodrębniony tekst, z którego możemy modyfikować lub wyodrębniać tekst według potrzeb.

## Krok 3: Dostosuj rozmiar czcionki wyodrębnionego tekstu

Po przechwyceniu fragmentów tekstu możesz chcieć zmniejszyć ich rozmiar czcionki, zwłaszcza gdy oryginalny tekst jest zbyt duży. W tym przykładzie zmniejszamy rozmiar czcionki o 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Zmniejsz rozmiar czcionki o 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Ten kod przechodzi przez każdy`TextFragment` w kolekcji i zmniejsza rozmiar czcionki o 70%. Dostosowanie rozmiaru czcionki może sprawić, że wyodrębniony tekst będzie łatwiejszy w zarządzaniu, zwłaszcza jeśli formatujesz go do różnych celów.

## Krok 4: Zapisz dokument w strumieniu pamięci

 Po zmodyfikowaniu tekstu zapisujemy plik PDF do pliku`MemoryStream`. Pozwala nam to zachować dokument w pamięci do dalszego przetwarzania bez konieczności zapisywania go z powrotem na dysku.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Tutaj zapisujemy plik PDF do strumienia pamięci, a następnie ponownie ładujemy dokument. Ta metoda jest przydatna, gdy pracujesz z dużymi plikami i chcesz uniknąć niepotrzebnych operacji dyskowych.

## Krok 5: Wyodrębnij cały tekst za pomocą Text Absorber

 Teraz, gdy przygotowaliśmy plik PDF, czas wyodrębnić tekst. Użyjemy`TextAbsorber` aby pobrać cały tekst z dokumentu.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Na tym etapie`TextAbsorber` pochłania cały tekst z pliku PDF, a wyodrębniony tekst jest przechowywany w`extractedText` string. To tutaj dzieje się magia — Twoje kolumny tekstu są teraz w formacie zwykłego tekstu!

## Krok 6: Zapisz wyodrębniony tekst do pliku

 Na koniec zapisujemy wyodrębniony tekst w pliku`.txt` plik w celu łatwego dostępu i dalszego wykorzystania.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Ten kod zapisuje wyodrębniony tekst do nowego`.txt` plik i zapisuje go w podanym katalogu. Na konsoli wyświetla się komunikat potwierdzający, że proces zakończył się powodzeniem.

## Wniosek

I masz! Wyodrębnianie kolumn tekstu z pliku PDF za pomocą Aspose.PDF dla .NET jest łatwiejsze niż myślisz. Za pomocą zaledwie kilku linijek kodu możesz załadować plik PDF, wyodrębnić określony tekst, dostosować formatowanie i zapisać wyniki w pliku tekstowym.

Ta technika jest niezwykle przydatna do przetwarzania ustrukturyzowanych dokumentów, takich jak tabele, raporty lub dowolna treść zorganizowana w kolumnach. Niezależnie od tego, czy potrzebujesz zautomatyzować ekstrakcję danych, czy przetworzyć dokumenty zbiorcze, Aspose.PDF zapewnia narzędzia, aby to się udało wydajnie.

## Najczęściej zadawane pytania

### Czy mogę wyodrębnić tekst z wybranych stron pliku PDF?  
 Tak! Możesz modyfikować`TextFragmentAbsorber` aby kierować określone strony za pomocą`pdfDocument.Pages[pageIndex].Accept(tfa);` metoda.

### Czy można wyodrębnić tekst tylko z jednej kolumny w pliku PDF zawierającym wiele kolumn?  
 Tak, ale będziesz musiał pracować ze współrzędnymi fragmentów tekstu, używając`TextFragment.Rectangle` aby wskazać konkretne obszary dokumentu.

### Jak mogę poprawić dokładność wyodrębniania tekstu?  
 Aby uzyskać większą dokładność, upewnij się, że struktura pliku PDF jest dobrze zdefiniowana i unikaj dokumentów o skomplikowanych układach. Możesz także dostroić`TextFragmentAbsorber` aby wyodrębnić tekst w oparciu o styl, rozmiar lub region czcionki.

### Czy Aspose.PDF obsługuje wyodrębnianie tekstu z zeskanowanych dokumentów?  
Tak, ale będziesz musiał użyć technologii OCR (Optical Character Recognition). Aspose udostępnia również narzędzia do tego celu.

### Jak radzić sobie z dużymi plikami PDF zawierającymi tysiące stron?  
W przypadku dużych plików PDF przetwarzaj dokument fragmentami, wyodrębniając tekst z kilku stron naraz, aby uniknąć dużego wykorzystania pamięci.