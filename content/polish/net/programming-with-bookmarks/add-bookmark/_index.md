---
title: Dodaj zakładkę w pliku PDF
linktitle: Dodaj zakładkę w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością dodawaj zakładki w pliku PDF, aby usprawnić nawigację dzięki Aspose.PDF dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/add-bookmark/
---
Dodawanie zakładek w pliku PDF umożliwia łatwą i szybką nawigację. Dzięki Aspose.PDF dla .NET możesz łatwo dodać zakładkę do pliku PDF, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, do którego chcesz dodać zakładkę. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otwórz dokument PDF

Teraz otworzymy dokument PDF, do którego chcemy dodać zakładkę, korzystając z następującego kodu:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Krok 4: Utwórz obiekt zakładki

 W tym kroku utworzymy obiekt zakładki za pomocą`OutlineItemCollection` class i ustaw jej właściwości, takie jak tytuł, atrybut kursywy, atrybut pogrubienia i akcja wykonywana po kliknięciu. Oto odpowiedni kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Krok 5: Dodaj zakładkę do dokumentu

 Na koniec dodajemy utworzoną zakładkę do kolekcji zakładek dokumentu za pomocą metody`Add` metoda`Outlines` nieruchomość. Oto odpowiedni kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Przykładowy kod źródłowy dla Dodaj zakładkę przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Utwórz obiekt zakładki
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Ustaw numer strony docelowej
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Dodaj zakładkę do kolekcji konspektów dokumentu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Zapisz dane wyjściowe
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku, jak dodać zakładkę przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu, aby usprawnić nawigację w dokumentach PDF, dodając niestandardowe zakładki.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji manipulacji zakładkami.


### Często zadawane pytania dotyczące dodawania zakładek w pliku PDF

#### P: Czym są zakładki w pliku PDF?

O: Zakładki, zwane także konturami, to interaktywne elementy umożliwiające nawigację i strukturę dokumentu PDF. Umożliwiają użytkownikom szybkie przechodzenie do określonych sekcji lub stron.

#### P: Dlaczego miałbym dodawać zakładki do pliku PDF?

Odp.: Dodawanie zakładek do pliku PDF poprawia komfort użytkownika i ułatwia czytelnikom poruszanie się po zawartości dokumentu. Zakładki mogą służyć jako spis treści lub zapewniać szybki dostęp do ważnych sekcji.

#### P: Jak zaimportować wymagane biblioteki do mojego projektu C#?

O: Aby zaimportować niezbędne biblioteki do projektu C#, dołącz następujące dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dyrektywy te umożliwiają dostęp do klas i metod potrzebnych do pracy z dokumentami PDF i zakładkami.

#### P: Jak określić ścieżkę do folderu dokumentów?

 O: Wymień`"YOUR DOCUMENT DIRECTORY"` w dostarczonym kodzie źródłowym rzeczywistą ścieżkę do folderu zawierającego plik PDF, do którego chcesz dodać zakładkę.

#### P: Jak otworzyć dokument PDF w celu dodania zakładek?

Odp.: Aby otworzyć dokument PDF w celu dodania zakładek, użyj następującego kodu:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Zastępować`"AddBookmark.pdf"` z rzeczywistą nazwą pliku.

#### P: Jak utworzyć obiekt zakładki?

 Odp.: Aby utworzyć obiekt zakładki, użyj metody`OutlineItemCollection` klasa. Dostosuj jego właściwości, takie jak tytuł, styl kursywy, pogrubiony styl i akcja wykonywana po kliknięciu.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  P: Jaki jest cel`Action` property in a bookmark?

 O:`Action` Właściwość określa akcję, która ma zostać wykonana po kliknięciu zakładki. W tym przykładzie używamy`GoToAction`class, aby przejść do określonej strony (w tym przypadku strona 2).

#### P: Jak dodać zakładkę do dokumentu?

 O: Skorzystaj z`Add` metoda`Outlines` aby dodać utworzoną zakładkę do kolekcji zakładek dokumentu.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### P: Czy mogę dodać wiele zakładek za pomocą tej metody?

Odp.: Tak, możesz powtórzyć kroki od 4 do 8, aby dodać wiele zakładek do dokumentu. W razie potrzeby dostosuj właściwości i działania każdej zakładki.

#### P: Jak zapisać zaktualizowany plik PDF?

 Odp.: Zapisz zaktualizowany plik PDF za pomocą rozszerzenia`Save` metoda`pdfDocument` obiekt:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### P: Jak mogę potwierdzić, że zakładki zostały dodane?

Odp.: Otwórz wygenerowany plik PDF, aby sprawdzić, czy określone zakładki zostały dodane do dokumentu.

#### P: Czy istnieje ograniczenie liczby zakładek, które mogę dodać?

O: Generalnie nie ma ścisłego ograniczenia liczby zakładek, które można dodać, ale w celu uzyskania optymalnej wydajności należy wziąć pod uwagę rozmiar i złożoność dokumentu.

#### P: Czy mogę dostosować wygląd zakładek?

Odp.: Tak, możesz dodatkowo dostosować wygląd, kolor, styl i inne atrybuty zakładek, korzystając z funkcji Aspose.PDF.