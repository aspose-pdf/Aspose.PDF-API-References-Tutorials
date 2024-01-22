---
title: lnk Szerokość linii adnotacji
linktitle: lnk Szerokość linii adnotacji
second_title: Aspose.PDF z dokumentacją API .NET
description: W tym artykule przedstawiono przewodnik krok po kroku dotyczący ustawiania szerokości linii adnotacji lnk przy użyciu pliku Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF to potężne i powszechnie używane narzędzie do pracy z plikami PDF w aplikacjach .NET. Zapewnia różnorodne funkcje tworzenia, edytowania i manipulowania plikami PDF, w tym możliwość dodawania adnotacji do stron. W tym samouczku wyjaśnimy, jak ustawić szerokość linii adnotacji łącza za pomocą Aspose.PDF dla .NET.

Po spełnieniu tych wymagań wstępnych utwórz nowy projekt aplikacji konsolowej w programie Visual Studio. Następnie Dodaj odwołanie do biblioteki Aspose.PDF dla .NET, klikając prawym przyciskiem myszy projekt w Eksploratorze rozwiązań, wybierając „Zarządzaj pakietami NuGet” i wyszukując „Aspose.PDF” w Menedżerze pakietów NuGet.

Aby dodać adnotację do łącza do dokumentu PDF, wykonaj następujące kroki:

##  Krok 1: Utwórz nowy`Document` object.
```csharp
Document doc = new Document();
```
## Krok 2: Dodaj nową stronę do dokumentu.
```csharp
doc.Pages.Add();
```
##  Krok 3: Utwórz listę`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Krok 4: Utwórz nowy`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Krok 5: Utwórz nowy`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Krok 6: Dodaj gest do listy gestów pisma odręcznego.
```csharp
inkList.Add(gesture);
```
##  Krok 7: Utwórz nowy`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Krok 8: Ustaw temat i tytuł adnotacji.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Krok 9: Ustaw kolor adnotacji.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Krok 10: Utwórz nowy`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Krok 11: Dodaj adnotację do strony.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Krok 12: Zapisz dokument do pliku.
```csharp
// Zapisz plik wyjściowy
doc.Save(dataDir);


```
### Przykład pokazuje szerokość linii adnotacji lnk w pliku Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Zapisz plik wyjściowy
doc.Save(dataDir);
```

## Wniosek

tym samouczku nauczyliśmy się, jak ustawić szerokość linii adnotacji łącza w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF dla .NET zapewnia szeroką gamę narzędzi i funkcji do pracy z dokumentami PDF, w tym możliwość tworzenia i dostosowywania adnotacji do linków. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo dodawać interaktywne łącza do swoich dokumentów PDF, poprawiając wygodę użytkownika i interaktywność swoich aplikacji. Aspose.PDF dla .NET to wszechstronna biblioteka, która umożliwia programistom .NET wydajną i efektywną pracę z plikami PDF.

### Często zadawane pytania

#### P: Co to jest adnotacja łącza w dokumencie PDF?

O: Adnotacja łącza w dokumencie PDF to interaktywny element, który umożliwia tworzenie hiperłączy lub akcji kierujących użytkownika do innej lokalizacji w tym samym dokumencie, zewnętrznej witrynie internetowej lub innym dokumencie PDF.

#### P: Jak mogę ustawić szerokość linii adnotacji łącza przy użyciu Aspose.PDF dla .NET?

O: Aby ustawić szerokość linii adnotacji łącza za pomocą Aspose.PDF dla .NET, możesz utworzyć`InkAnnotation` obiekt i określ właściwość szerokości linii.

#### P: Jakie właściwości można dostosować dla adnotacji łącza w Aspose.PDF dla .NET?

Odp.: Możesz dostosować różne właściwości adnotacji łącza w Aspose.PDF dla .NET, takie jak jego lokalizacja, rozmiar, kolor, właściwości obramowania (szerokość, styl, wzór kreski i efekt), temat, tytuł i widoczność.

#### P: Czy mogę utworzyć adnotację łącza zawierającą wiele gestów pisma odręcznego?

 Odp.: Tak, możesz utworzyć adnotację łącza zawierającą wiele gestów pisma odręcznego, dodając wiele`Point` tablice do`InkAnnotation` obiekt.

#### P: Jak mogę dodać adnotację łącza do określonej strony dokumentu PDF?

 O: Aby dodać adnotację łącza do konkretnej strony dokumentu PDF, podczas tworzenia dokumentu PDF należy określić numer strony.`InkAnnotation` obiekt. Na przykład,`new InkAnnotation(doc.Pages[1], ...)` dodaje adnotację o linku do pierwszej strony.