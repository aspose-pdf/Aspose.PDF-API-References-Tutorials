---
title: Ustaw domyślną nazwę czcionki
linktitle: Ustaw domyślną nazwę czcionki
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku, jak ustawić domyślną nazwę czcionki w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 270
url: /pl/net/document-conversion/set-default-font-name/
---
tym samouczku pokażemy, jak ustawić domyślną nazwę czcionki w pliku PDF przy użyciu Aspose.PDF dla .NET. Czasami podczas wyodrębniania obrazów z pliku PDF mogą wystąpić problemy z brakującymi czcionkami. Określając domyślną nazwę czcionki, możesz mieć pewność, że wyodrębniony tekst będzie wyświetlany poprawnie. Wykonaj poniższe czynności, aby ustawić domyślną nazwę czcionki w pliku PDF.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Ładowanie dokumentu PDF
 Pierwszym krokiem jest załadowanie dokumentu PDF do pliku`Document` obiekt. Użyj następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Kod do dodania
}
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 2: Ustaw domyślną nazwę czcionki
 Następnie ustawimy domyślną nazwę czcionki za pomocą`DefaultFontName` opcja`RenderingOptions` obiekt. Użyj następującego kodu:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Kod do dodania
     }
}
```

 Pamiętaj o wymianie`"Arial"` z żądaną nazwą czcionki.

## Krok 3: Ekstrakcja obrazu
Następnie wyodrębnimy obraz z określonej strony dokumentu PDF. Użyj następującego kodu:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Pamiętaj o podaniu prawidłowego numeru strony w`pdfDocument.Pages[1]`.

### Przykładowy kod źródłowy dla Ustaw domyślną nazwę czcionki przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Wniosek
tym samouczku nauczyliśmy się, jak ustawić domyślną nazwę czcionki w pliku PDF przy użyciu Aspose.PDF dla .NET. Określając domyślną nazwę czcionki, możesz mieć pewność, że wyodrębniony tekst będzie wyświetlany poprawnie. Użyj tej metody, aby rozwiązać problemy z brakującymi czcionkami podczas wyodrębniania obrazów z plików PDF.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Oferuje różne funkcjonalności, w tym ustawienie domyślnej nazwy czcionki w pliku PDF.

#### P: Dlaczego miałbym ustawić domyślną nazwę czcionki w pliku PDF?

Odp.: Ustawienie domyślnej nazwy czcionki jest przydatne podczas wyodrębniania tekstu z dokumentu PDF. Jeśli plik PDF zawiera tekst z czcionkami, które nie są dostępne w urządzeniu wyodrębniającym, określenie domyślnej nazwy czcionki zapewnia prawidłowe wyświetlanie tekstu.

#### P: Jak mogę załadować dokument PDF i ustawić domyślną nazwę czcionki przy użyciu Aspose.PDF dla .NET?

 O: Aby załadować dokument PDF i ustawić domyślną nazwę czcionki, możesz użyć metody`Document`class, aby załadować plik PDF i plik`RenderingOptions.DefaultFontName` właściwość, aby określić żądaną domyślną nazwę czcionki.

#### P: Czy mogę wybrać dowolną czcionkę jako domyślną nazwę czcionki?

O:Tak, jako domyślną nazwę czcionki możesz wybrać dowolną czcionkę dostępną w urządzeniu wyodrębniającym. Aby zapewnić dokładne renderowanie tekstu, użyj czcionki ściśle odpowiadającej brakującym czcionkom w oryginalnym pliku PDF.

#### P: Czy ustawienie domyślnej nazwy czcionki oznacza trwałą zmianę w pliku PDF?

O: Nie, ustawienie domyślnej nazwy czcionki przy użyciu Aspose.PDF dla .NET jest tymczasową zmianą dokonaną podczas wyodrębniania tekstu. Nie modyfikuje oryginalnego pliku PDF.