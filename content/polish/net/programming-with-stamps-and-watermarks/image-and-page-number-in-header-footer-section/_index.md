---
title: Obraz i numer strony w sekcji nagłówka i stopki
linktitle: Obraz i numer strony w sekcji nagłówka i stopki
second_title: Aspose.PDF dla .NET API Reference
description: tym samouczku krok po kroku dowiesz się, jak dodać obraz i numery stron do nagłówka i stopki pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 110
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Wstęp

Jeśli chodzi o tworzenie profesjonalnych dokumentów PDF, kontrola nad drobnymi szczegółami, takimi jak nagłówki i stopki, jest niezbędna. Chcesz, aby Twoje dokumenty wyglądały na dopracowane i dobrze zorganizowane, prawda? Cóż, dzięki Aspose.PDF dla .NET możesz bezproblemowo dodawać obrazy i numery stron do sekcji nagłówka i stopki dokumentu. W tym samouczku przeprowadzimy Cię przez każdy krok, ułatwiając Ci śledzenie.

## Wymagania wstępne

Zanim przejdziesz do szczegółów tego samouczka, upewnij się, że masz następujące kwestie:

1. .NET Framework: Musisz mieć zainstalowaną na swoim komputerze dowolną wersję .NET Framework. Jeśli jej nie masz, możesz ją łatwo pobrać ze strony internetowej Microsoft.
2.  Aspose.PDF dla .NET: Ponieważ będziemy używać Aspose.PDF, upewnij się, że masz go zainstalowanego w swoim projekcie. Możesz pobrać wersję próbną[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa znajomość języka C#: Znajomość podstaw programowania w języku C# z pewnością pomoże Ci zrozumieć kod bez większych problemów.
4. Plik obrazu: Będziesz potrzebować obrazu, który chcesz umieścić w nagłówku dokumentu PDF, takiego jak logo. Zapisz go w dostępnym katalogu. 
5. IDE: Użyj wybranego zintegrowanego środowiska programistycznego (IDE), np. Visual Studio, do pracy nad projektem .NET.

Gdy już będziesz mieć wszystko, co potrzebne, będziesz gotowy do stworzenia fantastycznego pliku PDF!

## Importuj pakiety

Aby zacząć używać Aspose.PDF dla .NET, musisz zaimportować niezbędne przestrzenie nazw. Na górze pliku C# należy dodać:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Te przestrzenie nazw zapewnią Ci dostęp do klas potrzebnych do manipulowania plikami PDF.

A teraz przejdźmy do konkretów! Wykonaj poniższe kroki, aby utworzyć dokument PDF, dodając obraz w nagłówku i numery stron w stopce.

## Krok 1: Ustaw katalog dokumentów

Każdy dobry projekt zaczyna się od organizacji. Zdefiniuj katalog dokumentów, w którym będziesz zapisywać pliki i gdzie znajduje się obraz. Oto jak to zrobić:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, pod którą chcesz zapisać plik PDF i gdzie znajduje się Twój obraz.

## Krok 2: Utwórz nowy dokument PDF

Następnie utworzymy nowy dokument PDF, w którym będzie się działy wszystkie cuda:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

W tym momencie utworzyłeś pusty dokument PDF. Ekscytujące, prawda?

## Krok 3: Dodaj stronę do dokumentu

PDF to przede wszystkim strony. Dodajmy nową stronę do naszego dokumentu, używając:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Teraz masz płótno, na którym możesz zacząć projektować!

## Krok 4: Utwórz sekcję nagłówka

Twój nagłówek będzie zawierał obraz (jak logo), który chcesz wyświetlić. Utwórz sekcję nagłówka za pomocą następującego kodu:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Teraz masz nagłówek, który możesz dostosować!

## Krok 5: Dodaj obraz do nagłówka

Teraz przechodzimy do zabawy! Musisz dodać obraz do swojego nagłówka. Najpierw utwórz obiekt obrazu:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Ustaw ścieżkę pliku swojego obrazu:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Na koniec dodaj obrazek do nagłówka:

```csharp
header.Paragraphs.Add(image1);
```

Gratulacje! Właśnie dodałeś obraz do nagłówka PDF.

## Krok 6: Utwórz sekcję stopki

Teraz popracujmy nad stopką. Podobnie jak w przypadku nagłówka, utwórz obiekt stopki:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Tutaj należy umieścić numer strony. 

## Krok 7: Dodaj tekst do stopki

Utwórz fragment tekstu, który będzie zawierał numer strony:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Następnie dodaj ten fragment tekstu do stopki:

```csharp
footer.Paragraphs.Add(txt);
```

Widzisz, jakie to było proste? Ustawiłeś numer swojej strony dynamicznie!

## Krok 8: Zapisz dokument PDF

Ostatnim krokiem w naszej przygodzie jest zapisanie dokumentu. Użyj tego polecenia, aby zapisać nowo utworzony plik PDF:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

I tak oto Twój plik PDF jest gotowy, zawiera obraz nagłówka i numery stron w stopce!

## Wniosek

masz! Właśnie utworzyłeś plik PDF z obrazem w nagłówku i dynamicznymi numerami stron w stopce, używając Aspose.PDF dla .NET. To niesamowite, jak kilka linijek kodu może dać tak dopracowany wynik. Niezależnie od tego, czy chodzi o raport korporacyjny, czy spersonalizowany dokument, dodanie tych elementów zmienia ton i profesjonalizm Twojego pliku PDF.

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.PDF na dowolnej platformie .NET?
Tak, Aspose.PDF dla .NET obsługuje wiele platform .NET, w tym .NET Framework, .NET Core i inne.

### Czy jest dostępna bezpłatna wersja próbna Aspose.PDF?
 Oczywiście! Możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Jakie formaty obrazów są obsługiwane w nagłówkach?
Aspose.PDF obsługuje najpopularniejsze formaty obrazów, takie jak JPG, PNG i BMP w przypadku nagłówków i stopek.

### Czy mogę dostosować format numerowania stron?
Tak, możesz łatwo dostosować tekst i format stopki według swoich potrzeb.

### Czy jest dostępne wsparcie techniczne?
 Tak, Aspose zapewnia dedykowane wsparcie poprzez swoje forum. Możesz zwrócić się o pomoc[Tutaj](https://forum.aspose.com/c/pdf/10).