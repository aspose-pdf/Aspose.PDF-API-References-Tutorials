---
title: Dodaj tabelę w pliku PDF
linktitle: Dodaj tabelę w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością dodawaj tabele do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-tables/add-table/
---
Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom programowe tworzenie, manipulowanie i przekształcanie dokumentów PDF. W tym samouczku przeprowadzimy Cię przez proces dodawania tabeli do pliku PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy każdy krok dostarczonego fragmentu kodu i zapewnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć funkcjonalność we własnych projektach.

## Wstęp

Dokumenty PDF są szeroko stosowane do udostępniania i przechowywania informacji w formacie przenośnym. Dodawanie tabel do dokumentów PDF może poprawić ich wygląd i sprawić, że prezentacja danych będzie bardziej zorganizowana i ustrukturyzowana. Aspose.PDF dla .NET zapewnia wygodny sposób dodawania tabel do istniejących dokumentów PDF lub tworzenia nowych od podstaw.

## Co to jest Aspose.PDF dla .NET?

Aspose.PDF dla .NET to potężna i bogata w funkcje biblioteka, która umożliwia programistom .NET programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Zapewnia szeroką gamę funkcji, w tym tworzenie plików PDF od podstaw, modyfikowanie istniejących dokumentów PDF, łączenie lub dzielenie plików PDF, dodawanie tekstu, obrazów i tabel, wyodrębnianie danych z plików PDF i wiele więcej. Dzięki Aspose.PDF dla .NET programiści mogą automatyzować złożone zadania związane z plikami PDF i dostarczać wysokiej jakości rozwiązania PDF.

## Dodawanie tabeli do dokumentu PDF

Aby dodać tabelę do dokumentu PDF przy użyciu Aspose.PDF dla .NET, postępuj zgodnie z poniższym przewodnikiem krok po kroku:

## Krok 1: Ładowanie źródłowego dokumentu PDF

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Powyższy fragment kodu ładuje źródłowy dokument PDF, do którego chcesz dodać tabelę. Upewnij się, że podałeś poprawną ścieżkę do pliku PDF.

## Krok 2: Inicjowanie nowej instancji tabeli

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

W tym kroku tworzymy nową instancję klasy Table, która reprezentuje tabelę w dokumencie PDF.

## Krok 3: Ustawianie koloru obramowania tabeli

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Tutaj ustawiamy kolor obramowania tabeli za pomocą klasy BorderInfo. Możesz dostosować styl, szerokość i kolor obramowania zgodnie ze swoimi wymaganiami.

## Krok 4: Ustawianie obramowania komórek tabeli

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Obramowanie komórek tabeli ustawiamy również za pomocą właściwości DefaultCellBorder obiektu tabeli. Dzięki temu każda komórka w tabeli ma określony styl, szerokość i kolor obramowania.

## Krok 5: Dodawanie wierszy i komórek do tabeli

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

W tym kroku tworzymy pętlę, aby dodać 10 wierszy do tabeli. W każdym wierszu dodajemy trzy komórki z przykładowymi danymi. Możesz zmodyfikować kod, aby dodać wiersze i komórki zgodnie ze swoimi konkretnymi wymaganiami.

## Krok 6: Dodanie obiektu tabeli do dokumentu

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Na koniec dodajemy obiekt tabeli do pierwszej strony dokumentu PDF, korzystając z kolekcji Akapity odpowiedniej strony.

### Przykładowy kod źródłowy dodawania tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Załaduj źródłowy dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Inicjuje nowe wystąpienie Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw kolor obramowania tabeli na Jasnoszary
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ustaw obramowanie komórek tabeli
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Utwórz pętlę, aby dodać 10 wierszy
for (int row_count = 1; row_count < 10; row_count++)
{
	// Dodaj wiersz do tabeli
	Aspose.Pdf.Row row = table.Rows.Add();
	// Dodaj komórki tabeli
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Dodaj obiekt tabeli do pierwszej strony dokumentu wejściowego
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Wniosek

W tym samouczku wyjaśniliśmy krok po kroku proces dodawania tabeli do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Omówiliśmy ładowanie źródłowego dokumentu PDF, inicjowanie nowej instancji klasy Table, ustawianie koloru obramowania tabeli i obramowań komórek, dodawanie wierszy i komórek do tabeli oraz dodawanie obiektu tabeli do dokumentu. Postępując zgodnie z tym przewodnikiem, możesz łatwo programowo włączać tabele do dokumentów PDF i dostosowywać je do swoich konkretnych potrzeb.

### Często zadawane pytania dotyczące dodawania tabeli w pliku PDF

#### P: Czy mogę dodać więcej kolumn do tabeli?

Odp.: Tak, możesz dodać więcej kolumn do tabeli, zwiększając liczbę komórek dodanych do każdego wiersza. W podanym przykładzie każdy wiersz zawiera trzy komórki reprezentujące trzy kolumny. Możesz dodać więcej komórek do każdego wiersza, aby dodać dodatkowe kolumny.

#### P: Jak mogę zmienić wygląd tabeli, np. rozmiar i styl czcionki?

 Odp.: Możesz dostosować wygląd tabeli, w tym rozmiar i styl czcionki, ustawiając właściwości w pliku`Aspose.Pdf.Table` I`Aspose.Pdf.TextFragment` obiekty. Można na przykład ustawić`DefaultCellTextState` właściwość służąca do zmiany właściwości czcionki tekstu w komórkach tabeli.

#### P: Czy można łączyć komórki w tabeli?

 Odp.: Tak, możesz scalić komórki w tabeli za pomocą`MergeCells` metoda`Aspose.Pdf.Row` klasa. Umożliwia to tworzenie komórek obejmujących wiele wierszy i kolumn.

#### P: Czy mogę dodać obrazy lub inną zawartość do komórek tabeli?

Odp.: Tak, do komórek tabeli możesz dodawać różne typy treści, w tym obrazy, tekst, hiperłącza i inne. Możesz użyć odpowiednich klas z Aspose.PDF dla .NET, aby dodać różne typy treści do komórek.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z .NET 5.0 lub nowszymi wersjami?

O: Tak, Aspose.PDF dla .NET jest kompatybilny z .NET 5.0 i nowszymi wersjami. Obsługuje różne platformy .NET, w tym .NET Framework, .NET Core i .NET 5.0+.