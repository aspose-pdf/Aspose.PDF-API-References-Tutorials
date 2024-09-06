---
title: Dodaj adnotację do pliku PDF
linktitle: Dodaj adnotację
second_title: Aspose.PDF dla .NET API Reference
description: Łatwo dodawaj niestandardowe adnotacje do swoich plików PDF za pomocą Aspose.PDF dla .NET dzięki temu przewodnikowi krok po kroku. Dostosuj swoje adnotacje za pomocą konkretnych szczegółów i ikon.
type: docs
weight: 10
url: /pl/net/annotations/addannotation/
---
## Wstęp

Adnotacje to świetny sposób na wzbogacenie dokumentów PDF, czyniąc je interaktywnymi i informacyjnymi. Niezależnie od tego, czy zostawiasz notatki dla współpracownika, czy dodajesz dodatkowe informacje dla czytelników, adnotacje mogą być niezbędne. W tym samouczku zagłębiamy się w proces dodawania adnotacji PDF przy użyciu Aspose.PDF dla .NET. Podzielimy każdy krok, tak aby pod koniec tego przewodnika stać się profesjonalistą w osadzaniu adnotacji w plikach PDF. Zaczynajmy!

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Możesz ją pobrać ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne: Visual Studio lub inne dowolne środowisko programistyczne C#.
- Podstawowa wiedza o języku C#: W tym przewodniku założono, że znasz już programowanie w języku C#.
- Dokument PDF: przykładowy plik PDF, do którego będziesz dodawać adnotacje.

 Jeśli nie posiadasz jeszcze biblioteki Aspose.PDF, możesz ją pobrać z powyższego łącza i rozpocząć[bezpłatny okres próbny](https://releases.aspose.com/) lub kup[licencja](https://purchase.aspose.com/buy). 

## Importuj pakiety

Zanim zaczniesz kodować, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Te przestrzenie nazw zapewniają dostęp do klas i metod potrzebnych do manipulowania plikami PDF i ich adnotacji.

## Krok 1: Załaduj swój dokument PDF

Najpierw musisz załadować dokument PDF, do którego chcesz dodać adnotację.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DATA DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

 Oto, co się dzieje: określasz katalog, w którym przechowywany jest plik PDF, a następnie ładujesz go za pomocą`Document` Klasa dostarczona przez Aspose.PDF. Ten krok jest kluczowy, ponieważ bez załadowania dokumentu nie można wprowadzać w nim żadnych zmian.

## Krok 2: Utwórz adnotację

### Definiowanie właściwości adnotacji
 Teraz utwórzmy samą adnotację. Użyjemy`TextAnnotation`, co jest idealnym rozwiązaniem do dodawania komentarzy i notatek do pliku PDF.

```csharp
// Utwórz adnotację
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

W tym fragmencie:
-  Lokalizacja i rozmiar:`Rectangle` Klasa definiuje, gdzie na stronie pojawi się Twoja adnotacja i jej wymiary.
- Tytuł, Temat i Zawartość: Te właściwości umożliwiają określenie, czego dotyczy adnotacja i co będzie zawierać.
-  Ikona:`TextIcon.Key` ustawia ikonę dla adnotacji, dzięki czemu staje się ona bardziej atrakcyjna wizualnie.

## Krok 3: Dostosuj wygląd adnotacji

Następnie wyróżnijmy tę adnotację, dodając obramowanie i dostosowując jej wygląd.

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

Oto podsumowanie tego, co się dzieje:
-  Granica: Tworzymy`Border` obiekt i ustaw jego szerokość na 5, nadając naszej adnotacji widoczny zarys.
-  Wzór kreskowy:`Dash` Właściwość ta umożliwia utworzenie przerywanej ramki, co dodaje odrobinę stylu do adnotacji.

## Krok 4: Dodaj adnotację do strony PDF

Po utworzeniu i dostosowaniu adnotacji czas dodać ją do strony PDF.

```csharp
// Dodaj adnotację do kolekcji adnotacji strony
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

 Ten kod dodaje adnotację do pierwszej strony pliku PDF.`Annotations` kolekcja zawiera wszystkie adnotacje dla konkretnej strony, a ten krok zapewnia, że Twoja nowa adnotacja będzie częścią tej kolekcji.

## Krok 5: Zapisz zaktualizowany dokument PDF

Na koniec zapiszmy dokument, aby dodać do niego trwałą adnotację.

```csharp
// Zapisz plik wyjściowy
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nAnnotation added successfully.\nFile saved at " + dataDir);
```

Zapisując dokument pod nową nazwą (`AddAnnotation_out.pdf`), zachowujesz oryginalny plik i generujesz nowy z dodaną adnotacją. Komunikat konsoli potwierdza, że wszystko przebiegło pomyślnie i teraz możesz znaleźć swój adnotowany plik PDF w określonym katalogu.

## Wniosek

Dodawanie adnotacji do plików PDF to nie tylko potężna funkcja; jest to również niezwykle proste dzięki Aspose.PDF dla .NET. Niezależnie od tego, czy zaznaczasz dokument do przeglądu, czy dodajesz notatki do wykorzystania w przyszłości, ten przewodnik obejmuje wszystko, co musisz wiedzieć. Wykonując te kroki, możesz tworzyć niestandardowe adnotacje, które wzbogacą Twoje pliki PDF, czyniąc je bardziej użytecznymi i interaktywnymi.

## Najczęściej zadawane pytania

### Jakie typy adnotacji mogę dodać za pomocą Aspose.PDF dla platformy .NET?
Możesz dodawać różne rodzaje adnotacji, w tym adnotacje tekstowe, linkowe, wyróżnienia i stemple itp.

### Czy mogę dostosować wygląd adnotacji?
Oczywiście! Możesz dostosować rozmiar, kolor, obramowanie, a nawet ikonę swoich adnotacji.

### Czy można dodać wiele adnotacji do jednej strony?
Tak, możesz dodać dowolną liczbę adnotacji do dowolnej strony swojego pliku PDF.

### Czy mogę usunąć adnotacje po ich dodaniu?
 Tak, adnotacje można usunąć za pomocą`Annotations.Delete` metoda dostarczona przez Aspose.PDF.

### Czy potrzebuję licencji, aby używać Aspose.PDF na platformie .NET?
 Tak, aby odblokować wszystkie funkcje i uniknąć wszelkich ograniczeń, będziesz potrzebować[licencja](https://purchase.aspose.com/buy) . Możesz również otrzymać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) do oceny.