---
title: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
linktitle: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak obracać tekst w plikach PDF za pomocą Aspose.PDF dla .NET, korzystając z przewodnika krok po kroku. Odkryj techniki manipulacji tekstem, od pozycjonowania po obracanie.
type: docs
weight: 390
url: /pl/net/programming-with-text/rotate-text-using-text-fragment/
---
## Wstęp

Tworzenie plików PDF to jedno, ale manipulowanie nimi w celu spełnienia określonych wymagań? To właśnie tam dzieje się prawdziwa magia! Czy kiedykolwiek zastanawiałeś się, jak obrócić tekst w pliku PDF? Niezależnie od tego, czy generujesz raporty, czy tworzysz dokument o niestandardowym projekcie, obracanie fragmentów tekstu może sprawić, że Twoje pliki PDF będą bardziej atrakcyjne wizualnie. W tym samouczku przyjrzymy się, jak obracać tekst za pomocą Aspose.PDF dla .NET, potężnej biblioteki, która umożliwia bezproblemową manipulację dokumentami PDF.

## Wymagania wstępne

Zanim przejdziemy do kodu, szybko omówmy narzędzia i konfiguracje, których będziesz potrzebować. Chcesz, aby wszystko było gotowe, abyś mógł bez wysiłku nadążać.

### Aspose.PDF dla biblioteki .NET
Po pierwsze, musisz mieć zainstalowany Aspose.PDF for .NET w swoim projekcie. Ta biblioteka jest wypełniona funkcjami, które pomogą Ci programowo tworzyć, modyfikować i zarządzać plikami PDF. Jeśli jeszcze jej nie pobrałeś, oto, skąd ją pobrać:
- [Pobierz Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/)

Na potrzeby tego samouczka upewnij się, że korzystasz z najnowszej wersji biblioteki.

### Środowisko programistyczne
Będziesz także potrzebować środowiska programistycznego .NET, takiego jak Visual Studio. To IDE do tworzenia C#, które sprawi, że Twoje doświadczenie kodowania będzie płynne i wydajne.

### Licencja tymczasowa lub pełna
Chociaż możesz zacząć od bezpłatnej wersji próbnej Aspose.PDF, jeśli chcesz uniknąć jakichkolwiek ograniczeń, lepiej jest użyć tymczasowej lub pełnej licencji. Oto jak możesz ją uzyskać:
- [Bezpłatna wersja próbna](https://releases.aspose.com/)
- [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/)
- [Kup pełną licencję](https://purchase.aspose.com/buy)

Gdy już przygotujesz wszystkie niezbędne rzeczy, możemy iść dalej!

## Importuj pakiety

Zanim zaczniemy kodować, musisz zaimportować niezbędne przestrzenie nazw, które są dołączone do Aspose.PDF. Jest to kluczowe dla pracy z dokumentami, stronami, fragmentami tekstu i nie tylko. Dodaj następujący kod na początku pliku C#:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

Teraz przeanalizujemy przykładowy kod krok po kroku, dzięki czemu będziesz mógł obracać tekst jak profesjonalista!

## Krok 1: Zainicjuj obiekt dokumentu

Każda manipulacja PDF zaczyna się od utworzenia lub załadowania dokumentu PDF. Tutaj zainicjujemy nowy dokument PDF od podstaw za pomocą Aspose.PDF.

 Tworzymy nowy`Document` obiekt, który reprezentuje plik PDF. Początkowo ten dokument jest pusty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
```

Wyjaśnienie:  
- `dataDir`:To jest katalog, w którym zostanie zapisany ostateczny plik PDF.
- `Document pdfDocument = new Document();`: Inicjuje nowy, pusty dokument PDF. 

## Krok 2: Dodaj stronę do dokumentu

Następnie musimy dodać stronę do dokumentu. PDF to zasadniczo zbiór stron i potrzebujesz co najmniej jednej strony, aby dodać swoją treść.

```csharp
// Pobierz konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Jeśli nie dodasz strony, nie będziesz mieć płótna, na którym mógłbyś rysować lub umieszczać tekst!

## Krok 3: Utwórz pierwszy fragment tekstu

Teraz nadchodzi ekscytująca część! Dodajmy fragment tekstu do pliku PDF. Fragment tekstu to fragment tekstu o określonych właściwościach, takich jak czcionka, rozmiar i pozycja.

```csharp
// Utwórz fragment tekstu
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment("tekst główny"): Tworzy nowy fragment tekstu o zawartości "tekst główny".
- Position(100, 600): Definiuje pozycję tekstu na stronie. Pierwsza liczba to współrzędna x, a druga to współrzędna y.
- TextState.FontSize: Ustawia rozmiar czcionki tekstu.
- FontRepository.FindFont: Znajduje określoną czcionkę do zastosowania w tekście.

## Krok 4: Utwórz obrócone fragmenty tekstu

Dodajmy więcej fragmentów tekstu, ale tym razem obróćmy je pod innymi kątami!

### Obrót fragmentu tekstu o 45 stopni

```csharp
// Utwórz obrócony fragment tekstu
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

Tutaj kluczowa zmiana jest następująca:
- TextState.Rotation: Ta właściwość ustawia kąt obrotu fragmentu tekstu, w tym przypadku jest to 45 stopni.

### Obrót fragmentu tekstu o 90 stopni

```csharp
// Utwórz obrócony fragment tekstu
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

tym przypadku obrót wynosi 90 stopni.

## Krok 5: Dołącz fragmenty tekstu do strony PDF

Teraz, gdy wszystkie fragmenty tekstu są już gotowe, czas dołączyć je do strony PDF korzystając z klasy TextBuilder.

```csharp
// utwórz obiekt TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Dołącz fragment tekstu do strony PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

Klasa TextBuilder pomaga w dodawaniu wielu fragmentów tekstu do jednej strony, dając możliwość elastycznego manipulowania nimi indywidualnie.

## Krok 6: Zapisz dokument PDF

Na koniec zapisz dokument w określonym katalogu. Bez tego kroku cała Twoja ciężka praca rozpłynie się w powietrzu!

```csharp
// Zapisz dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Udało Ci się obrócić tekst w pliku PDF za pomocą Aspose.PDF dla .NET. Teraz możesz otworzyć plik PDF, aby wyświetlić obrócone fragmenty tekstu!

## Wniosek

Obrót tekstu w pliku PDF może dodać Twoim dokumentom profesjonalnego charakteru, czyniąc je wizualnie atrakcyjnymi i wyjątkowymi. Dzięki Aspose.PDF dla .NET niezwykle łatwo jest manipulować fragmentami tekstu, co daje Ci pełną kontrolę nad wyglądem treści. Teraz, gdy nauczyłeś się, jak obracać tekst, możesz eksperymentować z różnymi kątami i układami, aby dopasować je do potrzeb swojego projektu.

## Najczęściej zadawane pytania

### Czy mogę obracać fragmenty tekstu pod dowolnym kątem?
 Tak! Możesz ustawić`TextState.Rotation` właściwość umożliwiająca obrót tekstu pod dowolnym kątem (nawet pod kątem ujemnym) w razie potrzeby.

### Czy mogę użyć różnych czcionek dla każdego fragmentu tekstu?
 Oczywiście. Możesz dostosować czcionkę każdego fragmentu tekstu za pomocą`FontRepository.FindFont` i podaj czcionkę, którą chcesz zastosować.

### Czy Aspose.PDF obsługuje wielostronicowe pliki PDF?
Tak, do dokumentu PDF możesz dodać wiele stron i niezależnie nimi manipulować.

### Czy istnieje ograniczenie co do liczby fragmentów tekstu, które mogę dodać?
Nie, możesz dodać tyle fragmentów tekstu, ile potrzebujesz. Upewnij się tylko, że są one prawidłowo rozmieszczone na stronie.

### Czy mogę modyfikować fragmenty tekstu po ich dołączeniu?
Tak, po dodaniu fragmentu tekstu nadal możesz aktualizować jego właściwości lub usunąć go ze strony.