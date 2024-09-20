---
title: Dodaj powtarzającą się kolumnę w dokumencie PDF
linktitle: Dodaj powtarzającą się kolumnę w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać powtarzające się kolumny do dokumentów PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z przykładami i kodem. Idealny dla programistów.
type: docs
weight: 20
url: /pl/net/programming-with-tables/add-repeating-column/
---
## Wstęp

Jeśli pracujesz z dokumentami PDF i musisz dodać powtarzające się kolumny, jesteś we właściwym miejscu! Używając Aspose.PDF dla .NET, możesz łatwo zarządzać tabelami i treścią w pliku PDF. Niezależnie od tego, czy tworzysz dynamiczne raporty, faktury czy jakikolwiek inny ustrukturyzowany dokument, powtarzające się kolumny mogą być przełomem w organizacji danych. Zanurzmy się w przewodniku krok po kroku, jak dodać powtarzające się kolumny do dokumentu PDF.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że wszystko jest skonfigurowane:

- Aspose.PDF dla .NET: Biblioteka Aspose.PDF dla .NET musi być zainstalowana w projekcie.
- [Pobierz Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/)
- [Bezpłatna wersja próbna](https://releases.aspose.com/)
- Środowisko programistyczne: Upewnij się, że masz zainstalowane środowisko programistyczne (IDE) zgodne z platformą .NET, np. Visual Studio.
- Podstawowa znajomość języka C#: Choć szczegółowo omówimy każdy element, podstawowa znajomość języka C# pozwoli Ci bez problemu nadążyć za materiałem.
  
 Jeśli nie masz jeszcze pliku Aspose.PDF dla platformy .NET, możesz go pobrać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby rozpocząć odkrywanie jego funkcji.

## Importuj pakiety

Na początek musisz zaimportować niezbędne przestrzenie nazw z Aspose.PDF dla .NET. Oto jak to zrobić:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Pakiety te zawierają podstawowe klasy i metody wymagane do pracy z dokumentami PDF i manipulowania tabelami.

Teraz podzielmy proces na kilka kroków, aby dodać powtarzające się kolumny do dokumentu PDF. Postępuj zgodnie z instrukcjami!

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

Zanim utworzymy lub zmanipulujemy jakiekolwiek pliki, musimy zdefiniować ścieżkę, w której wygenerowany plik PDF zostanie zapisany. W swoim projekcie C# ustaw ścieżkę do katalogu, w którym będą znajdować się Twoje pliki:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Ta ścieżka wskazuje na katalog, w którym zostanie zapisany wyjściowy plik PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką na Twoim komputerze.

## Krok 2: Utwórz nowy dokument PDF

 Aby rozpocząć, utwórz nową instancję`Document` obiekt. Będzie on służył jako kontener dla wszystkich stron i treści w pliku PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Tutaj utworzyliśmy nowy dokument PDF i dodaliśmy do niego pustą stronę.`doc.Pages.Add()` Metoda wstawia nową stronę do dokumentu.

## Krok 3: Utwórz instancję tabeli zewnętrznej

Następnie tworzymy zewnętrzną tabelę. Ta tabela będzie rozciągać się na całą szerokość strony i będzie służyć jako kontener dla innych tabel, w tym tej, która będzie zawierać powtarzające się kolumny.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Ustawiliśmy`ColumnWidths` właściwość na „100%”, co oznacza, że tabela zostanie rozciągnięta na całą szerokość strony.

## Krok 4: Utwórz tabelę wewnętrzną

 Teraz utwórzmy wewnętrzną tabelę, która będzie miała powtarzające się kolumny. Kluczowe właściwości tutaj to:`Broken` , co pozwala na kontynuację tabeli na tej samej stronie i`ColumnAdjustment`, która automatycznie dostosowuje szerokość kolumn do zawartości.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Ta tabela wewnętrzna będzie zagnieżdżona w tabeli zewnętrznej.

## Krok 5: Dodaj tabele do strony

Teraz, gdy mamy gotowe zarówno tabele zewnętrzne, jak i wewnętrzne, dodajmy je do strony. Ten krok zapewnia, że tabele zostaną uwzględnione w strukturze dokumentu.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Tutaj dodaliśmy`outerTable` do strony, a następnie w zewnętrznej tabeli zagnieździliśmy`mytable` Dodatkowo ustawiliśmy`RepeatingColumnsCount`do 5, określając liczbę kolumn, które mają się powtarzać po dodaniu danych.

## Krok 6: Dodaj wiersz nagłówka

Teraz czas dodać nagłówki do tabeli. Wiersz nagłówka nadaje kontekst danym i pomaga ustrukturyzować kolumny. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Ten fragment kodu dodaje pierwszy wiersz (którego użyjemy jako nagłówków) i wypełnia go komórkami zawierającymi tekst, taki jak „nagłówek 1”, „nagłówek 2” itd.

## Krok 7: Dodaj wiersze danych

Na koniec możemy dodać trochę danych do tabeli. Ta pętla dynamicznie tworzy wiersze i wypełnia komórki treścią:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Pętla powtarza się sześć razy, dodając wiersze i wypełniając każdą komórkę danymi z odpowiedniej kolumny (np. „col 1, 1”, „col 2, 2” itd.).

## Krok 8: Zapisz dokument

Po dodaniu wszystkich wierszy i kolumn ostatnim krokiem jest zapisanie dokumentu w określonej ścieżce dostępu.

```csharp
doc.Save(outFile);
```

Twój dokument został zapisany z powtarzającymi się kolumnami!

## Wniosek

Oto i masz! Dzięki tym prostym krokom możesz utworzyć dokument PDF z powtarzającymi się kolumnami przy użyciu Aspose.PDF dla .NET. Wykorzystując elastyczność zagnieżdżonych tabel, możesz uzyskać złożone układy, które sprawią, że Twoje pliki PDF będą wyglądać profesjonalnie i uporządkowanie. Wypróbuj to w swoim następnym projekcie i odkryj pełny potencjał Aspose.PDF, aby sprostać potrzebom generowania plików PDF.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka umożliwiająca programistom programowe tworzenie, edycję i zarządzanie dokumentami PDF.

### Czy mogę dynamicznie zmieniać liczbę powtarzających się kolumn?
 Tak, możesz zmienić liczbę powtarzających się kolumn, modyfikując`RepeatingColumnsCount` nieruchomość.

### Jak mogę zastosować licencję do Aspose.PDF dla platformy .NET?
 Licencję można zastosować z pliku lub strumienia, postępując zgodnie z poniższą instrukcją:[dokumentacja](https://reference.aspose.com/pdf/net/).

### Czy można dodawać obrazy do komórek tabeli?
Tak, Aspose.PDF dla platformy .NET obsługuje dodawanie różnych typów zawartości, w tym obrazów, do komórek tabeli.

### Czy mogę dodatkowo dostosować układ tabeli?
Oczywiście! Aspose.PDF oferuje rozbudowane funkcje dostosowywania stylów tabeli, w tym obramowania, wypełnienia, wyrównania i wiele innych.