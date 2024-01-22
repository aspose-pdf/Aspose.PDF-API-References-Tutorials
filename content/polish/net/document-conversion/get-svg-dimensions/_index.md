---
title: Pobierz wymiary SVG
linktitle: Pobierz wymiary SVG
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący uzyskiwania wymiarów SVG przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/document-conversion/get-svg-dimensions/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces uzyskiwania wymiarów pliku SVG przy użyciu Aspose.PDF dla .NET. SVG (Scalable Vector Graphics) to format obrazu oparty na języku XML używany do reprezentowania grafiki wektorowej. Wykonując poniższe czynności, będziesz mógł uzyskać wymiary pliku SVG i zapisać je jako plik PDF.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Ładowanie pliku SVG
tym kroku załadujemy plik SVG przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z poniższym kodem:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik SVG.

## Krok 2: Dostosowanie rozmiaru strony
Teraz, gdy załadowaliśmy plik SVG, możemy dostosować rozmiar strony, aby pomieścić zawartość SVG. Użyj następującego kodu:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Powyższy kod ustawia marginesy strony na zero, umożliwiając dostosowanie rozmiaru strony w oparciu o zawartość SVG.

## Krok 3: Zapisywanie wynikowego pliku PDF
Po dostosowaniu rozmiaru strony możemy teraz zapisać powstały dokument PDF. Oto ostatni krok:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z żądanym katalogiem, w którym chcesz zapisać wyjściowy plik PDF.
  
### Przykładowy kod źródłowy narzędzia Get SVG Dimensions przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Wniosek
W tym samouczku omówiliśmy krok po kroku proces uzyskiwania wymiarów pliku SVG przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, powinno być teraz możliwe uzyskanie wymiarów pliku SVG i zapisanie ich w formacie PDF. Ta funkcja może być przydatna, gdy trzeba zmierzyć wymiary grafiki wektorowej.

### Często zadawane pytania

#### P: Co to jest SVG?

Odp.: SVG (Scalable Vector Graphics) to format obrazu oparty na języku XML używany do reprezentowania grafiki wektorowej. W przeciwieństwie do obrazów rastrowych, pliki SVG są niezależne od rozdzielczości i można je skalować bez utraty jakości. SVG jest szeroko stosowany do wyświetlania grafiki w Internecie i można go z łatwością edytować i manipulować.

#### P: Dlaczego warto używać Aspose.PDF dla .NET do konwersji SVG na PDF?

Odp.: Aspose.PDF dla .NET zapewnia niezawodny i wydajny sposób obsługi plików SVG i konwertowania ich do formatu PDF. Oferuje różne opcje i ustawienia umożliwiające dostosowanie procesu konwersji, takie jak dostosowywanie rozmiaru strony, marginesów i innych właściwości, aby zapewnić dokładne odwzorowanie w pliku PDF.

#### P: Czy mogę konwertować pliki SVG ze złożoną grafiką i tekstem?

O: Tak, Aspose.PDF dla .NET może obsługiwać pliki SVG ze złożoną grafiką, tekstem i elementami wektorowymi. Dokładnie zachowuje szczegóły i jakość treści SVG podczas procesu konwersji, czego efektem są wysokiej jakości dokumenty PDF.

#### P: Czy można wyodrębnić tekst z plików SVG za pomocą Aspose.PDF dla .NET?

Odp.: Tak, Aspose.PDF dla .NET umożliwia wyodrębnianie tekstu z plików SVG. Możesz użyć funkcji wyodrębniania tekstu z biblioteki, aby wyodrębnić elementy tekstowe z pliku SVG i zapisać je oddzielnie do dalszego przetwarzania.