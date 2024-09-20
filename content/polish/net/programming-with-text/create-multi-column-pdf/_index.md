---
title: Utwórz plik PDF z wieloma kolumnami
linktitle: Utwórz plik PDF z wieloma kolumnami
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak tworzyć wielokolumnowe pliki PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z przykładami kodu i szczegółowymi wyjaśnieniami. Idealny dla profesjonalistów.
type: docs
weight: 110
url: /pl/net/programming-with-text/create-multi-column-pdf/
---
## Wstęp

Tworzenie wielokolumnowych plików PDF to świetny sposób na prezentację tekstu w bardziej uporządkowanym, czytelnym formacie. Niezależnie od tego, czy tworzysz raport, artykuł czy układ publikacji, struktury wielokolumnowe mogą sprawić, że Twoja treść będzie bardziej angażująca. W tym samouczku pokażemy, jak utworzyć wielokolumnowy plik PDF przy użyciu Aspose.PDF dla .NET. Nie martw się, podzielimy wszystko na proste kroki, które ułatwią Ci naśladowanie, nawet jeśli jesteś nowy na tej platformie.

## Wymagania wstępne

Zanim przejdziemy do kodu, jest kilka rzeczy, które musisz mieć na miejscu, aby wszystko działało płynnie:

1.  Aspose.PDF dla .NET: Musisz mieć zainstalowaną tę bibliotekę. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: Skonfiguruj preferowane środowisko IDE, np. Visual Studio, do pisania i uruchamiania kodu C#.
3. .NET Framework: Upewnij się, że masz zainstalowaną zgodną wersję środowiska .NET.
4. Podstawowa znajomość języka C#: Znajomość składni języka C# będzie pomocna, jednak każdy krok zostanie szczegółowo wyjaśniony.
5.  Licencja tymczasowa: Aspose.PDF wymaga licencji, aby uniknąć znaków wodnych lub ograniczeń. Możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) jeśli to konieczne.

## Importuj pakiety

Zanim zaczniesz kodować, musisz zaimportować niezbędne przestrzenie nazw, które pozwolą Ci na interakcję z Aspose.PDF. Oto, co musisz zaimportować:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Te przestrzenie nazw zapewniają dostęp do klas potrzebnych do tworzenia plików PDF, rysowania kształtów i obsługi formatowania tekstu.

Podzielmy proces tworzenia wielokolumnowego pliku PDF na proste i łatwe do opanowania kroki.

## Krok 1: Konfigurowanie dokumentu

Na początek musisz utworzyć nowy dokument PDF. Wiąże się to z określeniem marginesów i dodaniem strony, na której będzie się znajdowała Twoja treść.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument PDF
Document doc = new Document();

// Ustaw marginesy dla pliku PDF
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Dodaj stronę do dokumentu
Page page = doc.Pages.Add();
```

 Tutaj stworzyliśmy`Document`obiekt i ustawiliśmy lewy i prawy margines na 40 jednostek. Następnie dodaliśmy nową stronę do tego dokumentu, która będzie zawierać nasz układ wielokolumnowy.

## Krok 2: Dodawanie linii do oddzielnych sekcji

Następnie dodajmy poziomą linię do strony w celu wizualnego oddzielenia. Pomaga to stworzyć czysty i profesjonalny wygląd.

```csharp
// Utwórz obiekt graficzny, aby utrzymać linię
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Dodaj wiersz do zbioru akapitów strony
page.Paragraphs.Add(graph1);

// Zdefiniuj współrzędne linii
float[] posArr = new float[] { 1, 2, 500, 2 };

// Utwórz linię i dodaj ją do wykresu
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 Tutaj tworzymy linię poziomą za pomocą`Graph` I`Line` klas. Ta linia jest dodawana do strony`Paragraphs` kolekcja zawierająca wszystkie elementy wizualne.

## Krok 3: Dodawanie tekstu HTML z formatowaniem

Następnie wstawimy tekst zawierający znaczniki HTML, aby pokazać, jak można dynamicznie formatować tekst w pliku PDF.

```csharp
// Utwórz ciąg z zawartością HTML
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Utwórz nowy fragment HTML ze sformatowanym tekstem
HtmlFragment heading_text = new HtmlFragment(s);

// Dodaj tekst HTML do strony
page.Paragraphs.Add(heading_text);
```

 Korzystanie z`HtmlFragment`class, możemy dodać sformatowany tekst, który zawiera znaczniki HTML, takie jak rozmiar czcionki, styl i pogrubiony tekst. Jest to przydatne do poprawy wyglądu zawartości PDF.

## Krok 4: Tworzenie układu wielokolumnowego

Teraz utworzymy układ wielokolumnowy. To tutaj dzieje się magia — możesz określić, ile kolumn chcesz i jak szerokie powinny być.

```csharp
// Utwórz pływające pole, w którym będą przechowywane kolumny
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Ustaw liczbę kolumn i odstępy między nimi
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Dodaj pole do strony
page.Paragraphs.Add(box);
```

Tutaj tworzymy pływające pole, które będzie zawierało dwie kolumny. Ustawiamy odstępy między kolumnami i określamy, że każda kolumna powinna mieć 105 jednostek szerokości. Pozwala nam to utworzyć pożądany układ kolumn w pliku PDF.

## Krok 5: Dodawanie tekstu do kolumn

 Teraz wypełnijmy kolumny pewną zawartością tekstową. Możesz dodać różne`TextFragment` obiekty do każdej kolumny.

```csharp
// Utwórz i sformatuj pierwszy fragment tekstu
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Dodaj kolejną linię do rozdzielenia
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//Utwórz i dodaj drugi fragment tekstu
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 Dodajemy`TextFragment` do pływającego pola, a następnie kolejnej poziomej linii. Druga`TextFragment` zawiera więcej tekstu do wypełnienia drugiej kolumny. Te fragmenty pozwalają nam dodawać różne elementy tekstowe do pliku PDF z różnymi opcjami formatowania.

## Krok 6: Zapisywanie pliku PDF

Po dodaniu całej treści ostatnim krokiem jest zapisanie dokumentu jako pliku PDF.

```csharp
// Zdefiniuj ścieżkę wyjściową dla pliku PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Zapisz dokument PDF
doc.Save(dataDir);

// Komunikat o powodzeniu wydruku
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

Ten blok zapisuje plik PDF do określonego katalogu i wyświetla komunikat o powodzeniu w konsoli. Plik PDF jest teraz gotowy do przeglądania!

## Wniosek

Postępując zgodnie z tymi prostymi krokami, możesz łatwo utworzyć profesjonalnie wyglądający plik PDF z wieloma kolumnami, używając Aspose.PDF dla .NET. Niezależnie od tego, czy chodzi o raport, artykuł czy newsletter, ta technika pomaga uporządkować zawartość w wizualnie atrakcyjnym formacie. Aspose.PDF oferuje potężne narzędzia do dostosowywania plików PDF, od marginesów i układu po formatowanie tekstu i rysowanie kształtów. Teraz nadeszła Twoja kolej, aby wypróbować go i przenieść swoje umiejętności tworzenia plików PDF na wyższy poziom!

## Najczęściej zadawane pytania

### Czy w pliku PDF mogę utworzyć więcej niż dwie kolumny?
 Tak, możesz utworzyć tyle kolumn, ile potrzebujesz. Po prostu dostosuj`ColumnCount` Właściwość odpowiadająca liczbie kolumn, których potrzebujesz.

### Jak zmienić szerokość każdej kolumny?
 Możesz zmodyfikować`ColumnWidths` właściwość do określania różnych szerokości dla każdej kolumny. Ta właściwość akceptuje ciąg wartości oddzielonych spacjami.

### Czy można dodawać obrazy do kolumn?
 Oczywiście! Możesz dodać obrazy za pomocą`Image` klasę i umieścić je w pływającym polu lub dowolnym innym elemencie układu w pliku PDF.

### Czy mogę stylizować tekst za pomocą znaczników HTML w kolumnach?
 Tak, możesz używać znaczników HTML w`HtmlFragment` obiekty do stylizacji tekstu. Obejmuje to dodawanie czcionek, rozmiarów, kolorów i innych.

### Jak mogę dodać więcej stron z tym samym układem kolumn?
 Możesz dodać dodatkowe strony za pomocą`doc.Pages.Add()` i powtórz proces dodawania kolumn i treści dla każdej strony.