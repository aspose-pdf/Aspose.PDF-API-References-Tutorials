---
title: Zmiana orientacji
linktitle: Zmiana orientacji
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku, jak zmienić orientację strony pliku PDF za pomocą Aspose.PDF dla .NET. Łatwy do naśladowania i wdrożenia w Twoich projektach.
type: docs
weight: 10
url: /pl/net/programming-with-pdf-pages/change-orientation/
---
## Wstęp

Czy kiedykolwiek miałeś problem z plikiem PDF, w którym orientacja strony jest po prostu... nieprawidłowa? Być może masz do czynienia z dokumentem, który został zeskanowany lub utworzony niepoprawnie, a strony wymagają obrócenia, aby miały sens. Na szczęście dla nas, Aspose.PDF dla .NET zapewnia łatwy, wydajny sposób manipulowania plikami PDF w niemal dowolny sposób — w tym zmianę orientacji stron. Niezależnie od tego, czy chcesz zmienić orientację z pionowej na poziomą, czy odwrotnie, ten przewodnik przeprowadzi Cię przez ten proces krok po kroku.

Jeśli więc jesteś gotowy, aby z łatwością obracać strony pliku PDF, zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do szczegółów zmiany orientacji strony w pliku PDF, omówmy pokrótce, co będzie Ci potrzebne:

-  Aspose.PDF dla .NET: Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF dla .NET. Jeśli nie, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne .NET: Do pracy z platformą .NET możesz używać programu Visual Studio, JetBrains Rider lub dowolnego preferowanego środowiska programistycznego.
- Podstawowa wiedza o języku C#: Chociaż przewodnik ten jest przejrzysty, podstawowa znajomość języka C# sprawi, że będzie on jeszcze łatwiejszy w zrozumieniu.
- Plik PDF: Poniższy przykład zakłada, że masz plik PDF z wieloma stronami. Jeśli nie masz takiego pliku pod ręką, utwórz lub pobierz przykładowy plik PDF, aby z nim pracować.

 Jeśli dopiero zaczynasz, możesz wypróbować Aspose.PDF z[bezpłatna licencja tymczasowa](https://purchase.aspose.com/temporary-license/) zanim się zdecydujesz[kup pełną wersję](https://purchase.aspose.com/buy).

## Importuj przestrzenie nazw

Zanim będziesz mógł manipulować orientacją stron w swoim pliku PDF, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Upewnij się, że masz następujące elementy:

```csharp
using System.IO;
using Aspose.Pdf;
```

Po zaimportowaniu tych danych możemy przejść do właściwej części samouczka.

## Krok 1: Załaduj dokument PDF

 Pierwszą rzeczą, którą musimy zrobić, jest załadowanie pliku PDF, który chcesz zmodyfikować. Możesz użyć`Document` klasę z przestrzeni nazw Aspose.PDF, aby otworzyć plik PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Ta linia ładuje plik PDF z określonego katalogu. Upewnij się, że zastąpiłeś`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku.`"input.pdf"` to plik PDF, którego orientację chcesz zmienić.

## Krok 2: Przejdź przez każdą stronę

 Teraz, gdy mamy załadowany dokument, przejrzyjmy każdą stronę w pliku PDF. Użyjemy`foreach` pętla umożliwiająca przejście przez każdą stronę, co pozwala na zastosowanie zmiany orientacji do każdej z nich.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipuluj każdą stroną
}
```

Pętla ta będzie przechodzić przez wszystkie strony dokumentu.

## Krok 3: Pobierz MediaBox strony

 Każda strona w pliku PDF ma`MediaBox` który definiuje granice strony. Musimy uzyskać do niego dostęp, aby określić bieżącą orientację i ją zmodyfikować.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 Ten`MediaBox` podaje nam wymiary strony, takie jak szerokość, wysokość i położenie.

## Krok 4: Zamień szerokość i wysokość

Aby zmienić orientację strony z pionowej na poziomą lub poziomą na pionową, wystarczy zamienić wartości szerokości i wysokości. Ten krok dostosuje wymiary strony.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Ten kod zamienia wysokość i szerokość oraz zmienia położenie lewego dolnego rogu (`LLY`) tak, aby zawartość po obróceniu była dopasowana.

## Krok 5: Zaktualizuj MediaBox i CropBox

Teraz, gdy mamy nową wysokość i szerokość, zastosujmy zmiany na stronie.`MediaBox` I`CropBox` . Ten`CropBox` jest niezbędne, jeśli oryginalny dokument miał taki zestaw, zapewniając prawidłowe wyświetlanie całej strony.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Ten krok zmienia rozmiar strony na podstawie nowych wymiarów, które właśnie obliczyliśmy.

## Krok 6: Obróć stronę

Na koniec ustawiamy kąt obrotu strony. Aspose.PDF sprawia, że jest to super proste. Możemy obrócić stronę o 90 stopni, aby zmienić orientację z pionowej na poziomą lub odwrotnie.

```csharp
page.Rotate = Rotation.on90;
```

Ten kod obraca stronę o 90 stopni, dostosowując ją do pożądanej orientacji.

## Krok 7: Zapisz plik wyjściowy PDF

Po zastosowaniu zmian orientacji na wszystkich stronach zapisujemy zmodyfikowany dokument do nowego pliku. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Upewnij się, że podajesz nową nazwę pliku (w tym przypadku`ChangeOrientation_out.pdf`) aby zapisać dane wyjściowe. W ten sposób nie nadpiszesz oryginalnego pliku.

### Wniosek

masz to! Zmiana orientacji strony pliku PDF za pomocą Aspose.PDF dla .NET jest tak prosta, jak załadowanie dokumentu, przechodzenie przez strony, dostosowywanie MediaBox i zapisywanie zaktualizowanego pliku. Niezależnie od tego, czy masz do czynienia ze źle zeskanowanym dokumentem, czy też musisz obrócić strony, aby dopasować je do swoich potrzeb formatowania, ten przewodnik krok po kroku powinien Ci pomóc.

## Najczęściej zadawane pytania

### Czy w pliku PDF mogę obracać określone strony zamiast wszystkich stron?  
Tak, możesz zmodyfikować pętlę, aby kierować ją do konkretnych stron za pomocą ich indeksu, zamiast przechodzić przez wszystkie strony.

###  Co to jest`MediaBox`?  
 Ten`MediaBox` definiuje rozmiar i kształt strony w pliku PDF. To miejsce, w którym umieszczana jest zawartość strony.

### Czy Aspose.PDF dla .NET współpracuje z innymi formatami plików?  
Tak, Aspose.PDF obsługuje wiele formatów plików, takich jak HTML, XML, XPS i inne.

### Czy istnieje bezpłatna wersja Aspose.PDF dla platformy .NET?  
 Tak, możesz zacząć od[bezpłatny okres próbny](https://releases.aspose.com/) lub poproś o[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

### Czy mogę cofnąć zapisane zmiany?  
Po zapisaniu dokumentu zmiany są trwałe. Upewnij się, że pracujesz na kopii lub zachowaj kopię zapasową oryginalnego pliku.