---
title: Dodaj podpowiedź do tekstu w pliku PDF
linktitle: Dodaj podpowiedź do tekstu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać podpowiedzi do tekstu w plikach PDF za pomocą Aspose.PDF dla .NET. Bez wysiłku ulepsz swoje pliki PDF za pomocą informacyjnych tekstów wyświetlanych po najechaniu kursorem.
type: docs
weight: 90
url: /pl/net/programming-with-text/add-tooltip-to-text/
---
## Wstęp

Jeśli chodzi o tworzenie angażujących i interaktywnych plików PDF, podpowiedzi mogą być bezcenne. Znasz te małe wyskakujące okienka, które dostarczają dodatkowych informacji, gdy najedziesz na coś kursorem? Mogą one zapewnić kontekst, opisy, a nawet porady bez zaśmiecania dokumentu. W tym samouczku pokażemy, jak dodawać podpowiedzi do tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero stawiasz pierwsze kroki w świecie plików PDF, jesteś we właściwym miejscu! Więc zanurzmy się!

## Wymagania wstępne

Zanim przejdziemy do części poświęconej kodowaniu, upewnijmy się, że masz wszystko, czego potrzebujesz, aby wszystko poszło gładko.

### Zainstalowano program Visual Studio
Zainstalowanie na komputerze programu Visual Studio jest niezbędne, ponieważ będzie on stanowił podstawowe środowisko programistyczne dla aplikacji .NET.

### Aspose.PDF dla biblioteki .NET
 Będziesz także potrzebować biblioteki Aspose.PDF do swojej dyspozycji. Możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/). Upewnij się, że uwzględniłeś to w odniesieniach do swojego projektu.

### Podstawowa wiedza z języka C#
Znajomość języka C# będzie bardzo pomocna, ponieważ będziemy kodować w tym języku. Ale nie martw się — poprowadzę cię przez każdy krok!

### Dokument PDF do pracy
Możesz zacząć od pustego dokumentu PDF, jak zrobiliśmy w tym przykładzie, lub, jeśli wolisz, wykorzystać istniejący dokument.

Przejdźmy teraz do części kodowania!

## Importuj pakiety 

 Pierwszy krok w naszej przygodzie z kodowaniem obejmuje importowanie niezbędnych pakietów. Otwórz projekt Visual Studio i na górze pliku C# dodaj następujące`using` dyrektywy:

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

Pakiety te zapewniają dostęp do wszystkich klas i funkcjonalności potrzebnych do tworzenia i edytowania dokumentów PDF.

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musimy ustawić ścieżkę, w której będziesz zapisywać swoje dokumenty. Pomyśl o tym jak o znalezieniu przytulnego miejsca w systemie plików, w którym będą przechowywane wszystkie Twoje dzieła.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

 Pamiętaj o wymianie`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką na Twoim komputerze.

## Krok 2: Utwórz przykładowy dokument PDF

Następnie czas na stworzenie prostego pliku PDF z tekstem. To tutaj rozpoczynamy nasz proces twórczy!

```csharp
//Utwórz przykładowy dokument z tekstem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

W tym kroku tworzymy dokument, dodajemy dwa fragmenty tekstu i zapisujemy go we wcześniej określonej ścieżce.

## Krok 3: Otwórz dokument do przetworzenia

Teraz, gdy utworzyliśmy dokument, otwórzmy go, abyśmy mogli pracować nad podpowiedziami!

```csharp
// Otwórz dokument z tekstem
Document document = new Document(outputFile);
```

Tutaj po prostu ładujemy dokument, który właśnie utworzyliśmy.

## Krok 4: Utwórz absorber tekstu, aby znaleźć fragmenty tekstu

Musimy znaleźć fragmenty tekstu, do których chcemy dodać podpowiedzi. To jak używanie lupy do podświetlenia określonej części dużej mapy! 

```csharp
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## Krok 5: Wyodrębnij fragmenty tekstu

Następnie wyodrębniamy fragmenty tekstu, które znaleźliśmy w poprzednim kroku.

```csharp
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragments = absorber.TextFragments;
```

Ten fragment kodu umożliwia nam przechowywanie odniesień do fragmentów tekstu, które nas interesują.

## Krok 6: Przejrzyj fragmenty i dodaj podpowiedzi

Teraz nadchodzi zabawna część! Przejdziemy przez każdy z fragmentów tekstu i dodamy do każdego z nich podpowiedź. Wyobraź sobie, że owijasz małe prezenty (podpowiedzi) wokół konkretnych przedmiotów (fragmentów tekstu).

```csharp
// Przejrzyj fragmenty
foreach (TextFragment fragment in textFragments)
{
	// Utwórz niewidoczny przycisk w pozycji fragmentu tekstu
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Wartość AlternateName będzie wyświetlana jako podpowiedź przez aplikację przeglądarki
	field.AlternateName = "Tooltip for text.";
	// Dodaj pole przycisku do dokumentu
	document.Form.Add(field);
}
```

W każdej iteracji tworzymy pole przycisku odpowiadające pozycji fragmentu tekstu i przypisujemy do niego tekst podpowiedzi.

## Krok 7: Powtórz dla długich podpowiedzi

Tak jak dodaliśmy prostą podpowiedź, możemy zrobić to samo dla dłuższego tekstu. Rozszerzmy naszą kreatywność!

```csharp
// Następnie zostanie pokazany przykład bardzo długiego dymka
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Ustaw bardzo długi tekst
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

Tutaj wykonujemy tę samą pracę, co poprzednio, ale z o wiele bardziej rozbudowaną podpowiedzią.

## Krok 8: Zapisz swój dokument

Ostatnim krokiem jest zapisanie dokumentu ze wszystkimi nowymi, błyszczącymi podpowiedziami. 

```csharp
// Zapisz dokument
document.Save(outputFile);
```

tak po prostu, gotowe! Dodałeś podpowiedzi do swojego pliku PDF, czyniąc go bardziej przyjaznym dla użytkownika i interaktywnym.

## Wniosek

Oto łatwy w użyciu przewodnik, jak dodawać podpowiedzi do tekstu w plikach PDF za pomocą Aspose.PDF dla .NET. Ta technika może znacznie poprawić wrażenia użytkownika, czyniąc Twoje dokumenty bardziej informacyjnymi bez przytłaczania czytelnika zbyt dużą ilością tekstu na raz. 

Po prostu najeżdżając kursorem na słowo lub frazę, czytelnik otrzymuje istotne informacje, które dodają wartości bez zbędnego bałaganu. Więc zakasaj rękawy i spróbuj! Zanim się obejrzysz, możesz tworzyć wszelkiego rodzaju angażujące dokumenty, które się wyróżniają.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF for .NET to biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, Aspose oferuje bezpłatny okres próbny, abyś mógł zapoznać się z jego funkcjami! Możesz go znaleźć[Tutaj](https://releases.aspose.com/).

### Czy są dostępne jakieś opcje licencjonowania dla Aspose.PDF?
Tak, możesz kupić licencję lub uzyskać tymczasową licencję. Sprawdź opcje[Tutaj](https://purchase.aspose.com/).

### Czy za pomocą Aspose.PDF mogę dodać inne elementy interaktywne niż podpowiedzi?
Oczywiście! Aspose.PDF pozwala na dodawanie różnych interaktywnych elementów, takich jak hiperłącza, przyciski i formularze.

### Gdzie mogę znaleźć dalszą dokumentację dotyczącą Aspose.PDF?
 Możesz sprawdzić dokumentację[Tutaj](https://reference.aspose.com/pdf/net/) w celu uzyskania bardziej szczegółowych wskazówek.