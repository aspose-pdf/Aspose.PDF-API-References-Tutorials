---
title: Tekst i obraz jako akapit w pliku PDF
linktitle: Tekst i obraz jako akapit w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Twórz pliki PDF z tekstem i obrazami za pomocą Aspose.PDF dla .NET. Dowiedz się, jak krok po kroku dodawać tekst i obrazy w tekście.
type: docs
weight: 530
url: /pl/net/programming-with-text/text-and-image-as-paragraph/
---
## Wstęp

W dzisiejszym cyfrowym świecie pliki PDF są uniwersalnym formatem dokumentów, z którym większość z nas spotyka się codziennie. Niezależnie od tego, czy jest to raport, e-book czy faktura biznesowa, pliki PDF ułatwiają udostępnianie informacji na różnych platformach. Ale co, jeśli chcesz dostosować plik PDF programowo? Tutaj wkracza Aspose.PDF dla .NET. W tym samouczku przeprowadzimy Cię przez proces wstawiania tekstu i obrazów jako akapitów w tekście do pliku PDF przy użyciu Aspose.PDF dla .NET.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz wszystko, czego potrzebujesz, aby płynnie kontynuować pracę:

-  Aspose.PDF dla biblioteki .NET: Musisz zainstalować Aspose.PDF dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/pdf/net/).
- Visual Studio: Każda wersja obsługująca platformę .NET będzie działać dobrze.
- Podstawowa znajomość języka C#: Pewna znajomość języka C# będzie pomocna, ale nie martw się – przeprowadzę Cię przez każdy krok!
- Gotowy dokument PDF: Jeśli chcesz dodać niestandardowy obraz, przygotuj go.

 Możesz również otrzymać bezpłatną wersję próbną biblioteki[Tutaj](https://releases.aspose.com/) lub jeśli pracujesz nad projektem na dużą skalę, rozważ jego zakup[Tutaj](https://purchase.aspose.com/buy) . Potrzebujesz więcej szczegółów? Sprawdź dokumentację[Tutaj](https://reference.aspose.com/pdf/net/).

## Importuj pakiety

Aby rozpocząć pracę z Aspose.PDF dla .NET, musisz zaimportować wymagane przestrzenie nazw. Te przestrzenie nazw pozwalają Twojemu kodowi C# na interakcję z funkcjonalnościami Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Proste, prawda? Teraz przejdźmy do zabawnej części — tworzenia własnego pliku PDF.

## Przewodnik krok po kroku: Tworzenie pliku PDF z tekstem i obrazem w tekście

Podzielmy to na przyswajalne, łatwe do naśladowania kroki. Wyobraź sobie, że składasz układankę; każdy krok jest jak znalezienie i umieszczenie właściwego elementu.

## Krok 1: Zainicjuj dokument PDF

Pierwszym krokiem jest zainicjowanie nowego dokumentu PDF za pomocą Aspose.PDF. Ten dokument będzie stanowił podstawę do dodawania tekstu i obrazów.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz wystąpienie dokumentu
Document doc = new Document();
```

 Co się tu dzieje? Po prostu tworzymy nowy dokument za pomocą`Document`class i zdefiniowanie katalogu, w którym chcesz zapisać plik PDF. To jak otwarcie nowego płótna dla swojego arcydzieła!

## Krok 2: Dodaj stronę do pliku PDF

Dokument nie jest zbyt przydatny bez stron, prawda? Dodajmy pustą stronę do dokumentu.

```csharp
// Dodaj stronę do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
```

Ten fragment kodu dodaje nową stronę do kolekcji stron dokumentu. Wyobraź sobie, że otwierasz pustą stronę w notatniku.

## Krok 3: Dodaj tekst jako akapit

Następnie dodamy akapit tekstu. Tutaj możesz wstawić swoją wiadomość lub nagłówek.

```csharp
// Utwórz fragment tekstu
TextFragment text = new TextFragment("Hello World.. ");
// Dodaj fragment tekstu do kolekcji akapitów obiektu Page
page.Paragraphs.Add(text);
```

 Tutaj tworzymy`TextFragment` obiekt do przechowywania tekstu „Hello World..”, który jest następnie dodawany do strony jako akapit. To tak, jakby napisać pierwsze zdanie w dokumencie PDF.

## Krok 4: Dodaj obraz jako akapit w tekście

Teraz, gdy mamy już tekst, urozmaicimy to, dodając obraz jako akapit w tekście. Akapit w tekście oznacza po prostu, że obraz pojawi się zaraz po tekście, podobnie jak obrazy są wyświetlane w dokumentach Word.

```csharp
// Utwórz instancję obrazu
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Ustaw obraz jako akapit w tekście, aby pojawiał się zaraz po nim
// Poprzedni obiekt akapitu (TextFragment)
image.IsInLineParagraph = true;
// Określ ścieżkę do pliku obrazu
image.File = dataDir + "aspose-logo.jpg";
```

 W tym fragmencie kodu tworzymy`Image` obiekt, powiedz mu, aby wyrównał się z tekstem i określ ścieżkę do pliku obrazu. Jest to odpowiednik wklejenia obrazu zaraz po zdaniu w dokumencie. Możesz zamienić „aspose-logo.jpg” na żądany obraz.

## Krok 5: Ustaw rozmiar obrazu (opcjonalnie)

Chcesz zmienić rozmiar obrazu? Nie ma problemu. Aspose.PDF daje Ci możliwość dostosowania wysokości i szerokości obrazu przed dodaniem go do dokumentu.

```csharp
// Ustaw wysokość obrazu (opcjonalnie)
image.FixHeight = 30;
// Ustaw szerokość obrazu (opcjonalnie)
image.FixWidth = 100;
```

Ta część jest opcjonalna, ale pomaga kontrolować, jak duży lub mały obraz pojawia się w pliku PDF. To jak zmiana rozmiaru zdjęcia przed wydrukowaniem.

## Krok 6: Dodaj obraz do kolekcji akapitów

Przygotowaliśmy obraz. Teraz wstawmy go do dokumentu jako akapit inline.

```csharp
// Dodaj obraz do kolekcji akapitów obiektu strony
page.Paragraphs.Add(image);
```

Ten wiersz dodaje obraz zaraz po tekście w kolekcji akapitów. To jak naciśnięcie przycisku „Wstaw obraz” w edytorze tekstu.

## Krok 7: Dodaj kolejny akapit tekstu w tekście

Co jeśli chcesz dodać więcej tekstu zaraz po obrazku? Zróbmy to, wstawiając kolejny fragment tekstu inline.

```csharp
// Ponowna inicjalizacja obiektu TextFragment z inną zawartością
text = new TextFragment(" Hello Again..");
// Ustaw TextFragment jako akapit w tekście
text.IsInLineParagraph = true;
// Dodaj nowo utworzony fragment tekstu do kolekcji akapitów strony
page.Paragraphs.Add(text);
```

 Ponownie wykorzystujemy`TextFragment`obiekt tutaj z nowym tekstem ("Hello Again..") i wstawienie go w linii, zaraz po obrazku. To nada Twojemu PDF-owi płynny, spójny wygląd.

## Krok 8: Zapisz dokument PDF

Już prawie skończyliśmy! Teraz zapiszmy dokument w podanym katalogu.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Ten ostatni krok zapisuje plik w Twoim katalogu pod nazwą „TextAndImageAsParagraph_out.pdf”. Gratulacje — utworzyłeś plik PDF z tekstem i obrazami w tekście!

## Wniosek

I oto masz — tworzenie pliku PDF z tekstem i obrazami jako akapitami w tekście przy użyciu Aspose.PDF dla .NET jest tak proste, jak wykonanie tych kroków. Za pomocą zaledwie kilku linijek kodu możesz dodać dynamiczną zawartość do plików PDF, czyniąc je bardziej atrakcyjnymi wizualnie i profesjonalnymi. Niezależnie od tego, czy chodzi o raport biznesowy, czy e-book, kontrola nad układem plików PDF może mieć ogromne znaczenie.

## Najczęściej zadawane pytania

### Czy mogę dodać wiele obrazów jako akapity w tekście?  
 Tak, możesz dodać wiele obrazów, tworząc oddzielne`Image` obiektów i dodawanie ich do zbioru akapitów.

### Czy mogę kontrolować położenie tekstu i obrazu w pliku PDF?  
Tak, korzystając z właściwości, takich jak marginesy, możesz kontrolować dokładne rozmieszczenie tekstu i obrazów.

### Czy Aspose.PDF dla .NET jest darmowy?  
 Nie, to produkt licencjonowany, ale możesz go uzyskać[bezpłatny okres próbny](https://releases.aspose.com/) lub kup licencję[Tutaj](https://purchase.aspose.com/buy).

### Czy mogę dodać hiperłącza do tekstu?  
 Tak, Aspose.PDF pozwala na dodawanie hiperłączy w obrębie fragmentów tekstu. Sprawdź[dokumentacja](https://reference.aspose.com/pdf/net/) po więcej szczegółów.

### Czy mogę dostosować czcionkę i styl tekstu?  
Oczywiście! Możesz łatwo dostosować czcionki, kolory i inne właściwości stylistyczne fragmentów tekstu.