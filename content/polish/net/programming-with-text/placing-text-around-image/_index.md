---
title: Umieszczanie tekstu wokół obrazu w pliku PDF
linktitle: Umieszczanie tekstu wokół obrazu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak umieszczać tekst wokół obrazów w plikach PDF za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby tworzyć profesjonalne pliki PDF z obrazami i tekstem obok siebie.
type: docs
weight: 260
url: /pl/net/programming-with-text/placing-text-around-image/
---
## Wstęp

Czy kiedykolwiek próbowałeś umieścić tekst wokół obrazu w pliku PDF, ale wydawało Ci się to trudne? Jeśli tak, jesteś we właściwym miejscu! Aspose.PDF dla .NET ułatwia ten proces, umożliwiając umieszczanie tekstu obok obrazów za pomocą zaledwie kilku linijek kodu. Niezależnie od tego, czy tworzysz raporty, dokumenty czy prezentacje, ta funkcja jest fantastycznym sposobem na ulepszenie układu treści i uczynienie jej bardziej atrakcyjną wizualnie. Dzisiaj pokażemy, jak używać Aspose.PDF dla .NET, aby umieszczać tekst wokół obrazów w dokumencie PDF.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że wszystko jest skonfigurowane. Oto, czego będziesz potrzebować:

-  Aspose.PDF dla .NET: Możesz go pobrać ze strony[Tutaj](https://releases.aspose.com/pdf/net/).
- Visual Studio: Upewnij się, że masz zainstalowaną najnowszą wersję, aby wszystko przebiegało bezproblemowo.
- .NET Framework: W tym przykładzie użyto platformy .NET, dlatego upewnij się, że Twoje środowisko jest przygotowane pod kątem tworzenia oprogramowania w tej platformie.
-  Licencja tymczasowa: Możesz poprosić o licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) jeśli oceniasz produkt.

Jeśli jeszcze nie skonfigurowałeś Aspose.PDF dla .NET, postępuj zgodnie z instrukcjami instalacji w[dokumentacja](https://reference.aspose.com/pdf/net/).

## Importuj przestrzenie nazw

Zanim zaczniemy kodować, musimy zaimportować niezbędne przestrzenie nazw. Oto fragment kodu, który to umożliwia:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Te przestrzenie nazw są niezbędne, ponieważ zapewniają dostęp do klas takich jak`Document`, `Page`, `Image` , I`HtmlFragment`, którego użyjemy do utworzenia i edycji pliku PDF.

Teraz, gdy już przygotowaliśmy scenę, omówmy, jak umieścić tekst wokół obrazu w pliku PDF za pomocą Aspose.PDF dla .NET. Przeprowadzimy Cię przez to krok po kroku.

## Krok 1: Utwórz obiekt dokumentu

 Najpierw musisz utworzyć dokument PDF. W Aspose.PDF odbywa się to poprzez utworzenie instancji`Document` obiekt. Ten obiekt będzie służył jako podstawa dla całej zawartości, którą dodamy.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Tutaj utworzyliśmy pusty dokument PDF. Nie ma jeszcze żadnych stron, ale nie martw się, dodamy jedną w następnym kroku.

## Krok 2: Dodaj stronę do dokumentu

Teraz, gdy mamy już dokument, czas dodać stronę. Wyobraź sobie, że tworzysz pustą kartkę papieru, na której będziesz dodawać swoją treść.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Ten kod dodaje nową stronę do dokumentu. Domyślnie strona jest pusta, ale zamierzamy to zmienić.

## Krok 3: Utwórz tabelę, aby uporządkować zawartość

Aby zachować właściwe wyrównanie obrazu i tekstu, użyjemy tabeli. Tabele w plikach PDF mogą pomóc w ustrukturyzowaniu układu, podobnie jak w dokumentach Word lub HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Ten fragment kodu tworzy tabelę i dodaje ją do strony. Pomyśl o tabeli jako o strukturze do wyrównywania obrazu i tekstu.

## Krok 4: Ustaw szerokości kolumn dla tabeli

Teraz, gdy dodaliśmy tabelę, musimy zdefiniować, jak szerokie powinny być kolumny. Dzięki temu obraz i tekst będą miały odpowiedni rozmiar na stronie.

```csharp
table1.ColumnWidths = "120 270";
```

Ten wiersz ustawia szerokość dwóch kolumn — jednej dla obrazu i jednej dla tekstu. Dostosuj te wartości, jeśli obraz lub tekst potrzebują więcej lub mniej miejsca.

## Krok 5: Zdefiniuj marginesy i wypełnienie

Aby mieć pewność, że wszystko wygląda schludnie, dodajmy do tabeli marginesy i wypełnienie.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Ustawienia te zapewniają jednakowe odstępy w tabeli, co sprawia, że jej zawartość jest atrakcyjna wizualnie.

## Krok 6: Wstaw obraz do tabeli

Teraz przejdźmy do zabawnej części — dodania obrazu. W tym przypadku dodamy logo Aspose, ale możesz użyć dowolnego obrazu, który Ci się podoba.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Oto co się dzieje:
- Ładujemy obraz z podanego katalogu.
- Ustawiamy wysokość i szerokość obrazu.
- Na koniec dodajemy obraz do pierwszej komórki w tabeli.

## Krok 7: Dodaj tekst obok obrazu

Teraz, gdy obraz jest już na miejscu, dodajmy obok niego trochę tekstu. W tym przykładzie użyjemy tekstu w formacie HTML, aby nadać styl treści.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Ten blok dodaje stylizowany tytuł i opis w komórce obok obrazu. Możesz sformatować tekst za pomocą znaczników HTML, aby uzyskać więcej możliwości dostosowania.

## Krok 8: Dostosuj wyrównanie pionowe

Domyślnie zawartość komórek tabeli może nie być wyrównana w sposób, w jaki chcesz. W tym przypadku chcemy się upewnić, że tekst jest wyrównany do górnej części komórki.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Dzięki temu tekst znajduje się u góry komórki, a układ jest przejrzysty i profesjonalny.

## Krok 9: Dodaj więcej tekstu pod obrazem i opisem

Możesz chcieć dodać więcej treści poniżej obrazu i tekstu. Dodajmy w tym celu kolejny wiersz do tabeli.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Tutaj dodaliśmy kolejny wiersz z dodatkowym tekstem, rozciągający się na obie kolumny w celu zachowania równowagi w układzie.

## Krok 10: Zapisz dokument PDF

Na koniec musimy zapisać dokument, aby można było obejrzeć zmiany.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Dzięki temu plik PDF zostanie zapisany z obrazem i tekstem sformatowanymi dokładnie tak, jak chcemy.

## Wniosek

Umieszczanie tekstu wokół obrazów w pliku PDF może wydawać się trudnym zadaniem, ale Aspose.PDF dla .NET upraszcza ten proces. Wykorzystując tabele, obrazy i stylizowany tekst, możesz tworzyć profesjonalnie wyglądające pliki PDF przy minimalnym wysiłku. Za pomocą zaledwie kilku linijek kodu możesz umieścić zawartość dokładnie tam, gdzie chcesz, nadając dokumentom dopracowany i dobrze zorganizowany wygląd.

## Najczęściej zadawane pytania

### Czy mogę użyć tej metody do umieszczenia wielu obrazów z tekstem?
Tak, wystarczy dodać więcej wierszy i komórek do tabeli, aby uwzględnić dodatkowe obrazy i tekst.

### Czy mogę zmienić układ obrazu?
Oczywiście! Możesz zmodyfikować wyrównanie obrazu, dostosowując właściwości wyrównania komórki.

### Jak mogę dodatkowo stylizować tekst?
 Możesz używać znaczników HTML w`HtmlFragment` obiekt umożliwiający zastosowanie różnych stylów, takich jak pogrubienie, kursywa lub różne czcionki.

### Czy mogę kontrolować odstęp między tekstem i obrazem?
 Tak, używając`MarginInfo` obiekt umożliwia kontrolowanie odstępu i marginesów pomiędzy elementami.

### Czy można dodać linki do tekstu?
 Zdecydowanie! Możesz osadzać hiperłącza w tekście sformatowanym w HTML, używając`<a>` etykietka.