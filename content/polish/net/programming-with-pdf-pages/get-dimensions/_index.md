---
title: Pobierz wymiary strony PDF
linktitle: Pobierz wymiary strony PDF
second_title: Aspose.PDF dla .NET API Reference
description: W tym samouczku wyjaśniamy, jak uzyskać wymiary strony PDF i wykonać manipulacje za pomocą Aspose.PDF dla .NET. Szczegółowe kroki są podane, aby poprowadzić Cię przez proces.
type: docs
weight: 60
url: /pl/net/programming-with-pdf-pages/get-dimensions/
---
## Wstęp

Czy kiedykolwiek musiałeś manipulować wymiarami strony dokumentu PDF? Może chciałeś zmienić rozmiar strony lub obrócić ją, aby dopasować ją do swoich potrzeb? Jeśli tak, jesteś we właściwym miejscu! W tym samouczku przeprowadzimy Cię przez pobieranie i modyfikowanie wymiarów strony PDF za pomocą Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś początkującym, czy doświadczonym programistą, ten przewodnik okaże się prosty i łatwy do naśladowania.

Aspose.PDF dla .NET to potężna biblioteka, która umożliwia łatwe tworzenie, manipulowanie i przekształcanie plików PDF. To jak posiadanie scyzoryka szwajcarskiego dla plików PDF – możesz dostosować każdy najmniejszy szczegół, aby dopasować go do swoich dokładnych wymagań. Więc zanurzmy się i dowiedzmy się, jak pobierać i aktualizować wymiary stron PDF za pomocą tego niesamowitego narzędzia!

## Wymagania wstępne

Zanim zaczniesz, musisz zadbać o kilka rzeczy, aby móc płynnie korzystać z tego samouczka:

1.  Aspose.PDF dla .NET: Możesz[pobierz najnowszą wersję tutaj](https://releases.aspose.com/pdf/net/) . Jeśli nie masz licencji, nie martw się! Możesz poprosić o[bezpłatny okres próbny](https://releases.aspose.com/) lub wybierz[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: środowisko programistyczne, w którym będziesz pisać i wykonywać kod.
3. Podstawowa znajomość języka C#: Choć postaramy się przedstawić sprawę prosto, pewna znajomość języka C# ułatwi cały proces.
4. Plik PDF do pracy: Pobierz dowolny przykładowy plik PDF lub utwórz nowy, aby przetestować.

## Importuj pakiety

Aby pracować z Aspose.PDF dla .NET, musisz zaimportować kilka niezbędnych przestrzeni nazw. To przygotowuje grunt pod interakcję z dokumentami PDF. Oto, jak to zrobić:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dzięki temu importowi masz dostęp do podstawowych klas potrzebnych do manipulowania plikami PDF, a w szczególności do zarządzania stronami i pobierania ich wymiarów.

Teraz, gdy wszystko już mamy na swoim miejscu, podzielmy proces na łatwe do wykonania kroki.

## Krok 1: Określ ścieżkę pliku i załaduj dokument

Pierwszym krokiem jest określenie ścieżki do dokumentu PDF i załadowanie go za pomocą Aspose.PDF. Umożliwi to interakcję ze stronami w pliku PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

W tym kroku zasadniczo otwierasz plik PDF, nad którym chcesz pracować. Jeśli kiedykolwiek otwierałeś książkę na konkretnej stronie, jest to dość podobne – ale zamiast tego otwierasz dokument PDF, aby uzyskać dostęp do jego stron.

## Krok 2: Dodaj pustą stronę, jeśli nie ma żadnych stron

Co jeśli Twój dokument nie ma stron? Nie martw się! Możemy dodać pustą stronę do dokumentu i z nią pracować. Oto jak sprawdzić, czy strona istnieje i dodać nową, jeśli to konieczne:

```csharp
// Dodaje pustą stronę do dokumentu PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Ta linia kodu sprawdza, czy w dokumencie jest już strona. Jeśli tak, wybiera pierwszą stronę (`Pages[1]`). W przeciwnym wypadku tworzy pustą stronę i dodaje ją do pliku PDF.

Można to porównać do otwarcia pustego notatnika i napisania czegoś na pierwszej stronie – proste, prawda?

## Krok 3: Uzyskaj informacje o wysokości i szerokości strony

 Teraz, gdy mamy stronę do pracy, pobierzmy wymiary strony. Użyjemy`GetPageRect()` metoda uzyskania wysokości i szerokości.

```csharp
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Tutaj,`GetPageRect(true)` zwraca prostokąt, który zawiera wysokość i szerokość strony. To jak mierzenie kawałka papieru linijką. Dane wyjściowe zostaną wyświetlone w konsoli, podając bieżące wymiary strony.

## Krok 4: Obróć stronę o 90 stopni

Chcesz obrócić stronę? Nie ma problemu! Za pomocą prostej właściwości możesz obrócić stronę o 90 stopni.

```csharp
// Obróć stronę o 90 stopni
page.Rotate = Rotation.on90;
```

Ten krok obraca stronę zgodnie z ruchem wskazówek zegara o 90 stopni. Wyobraź sobie, że obracasz wydrukowaną kartkę na biurku – teraz jest w trybie poziomym!

## Krok 5: Ponowne sprawdzenie wymiarów strony po obrocie

Po obróceniu strony, dobrym pomysłem jest ponowne sprawdzenie wymiarów. Dlaczego? Ponieważ obrót może wpłynąć na interpretację wysokości i szerokości.

```csharp
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Teraz wymiary strony zostaną zaktualizowane na podstawie nowej orientacji. To jak obracanie zdjęcia w telefonie – nagle szerokość staje się wysokością i odwrotnie.


## Wniosek

Gratulacje! Udało Ci się nauczyć, jak pobierać i modyfikować wymiary strony PDF za pomocą Aspose.PDF dla .NET. Teraz powinieneś być w stanie załadować plik PDF, sprawdzić wymiary strony, a nawet obrócić stronę, jeśli to konieczne.

Manipulowanie plikami PDF nie musi być skomplikowane. Dzięki Aspose.PDF jest to tak proste, jak wykonanie kilku kroków i użycie intuicyjnych metod. Więc następnym razem, gdy będziesz musiał obsługiwać wymiary stron PDF, będziesz dokładnie wiedział, co robić!

## Najczęściej zadawane pytania

### Czy mogę obrócić stronę pod innym kątem niż 90 stopni?
 Tak, Aspose.PDF pozwala na obracanie stron o 0, 90, 180 lub 270 stopni za pomocą`Rotation` nieruchomość.

### Co się stanie, jeśli mój plik PDF nie będzie miał żadnych stron?
 Jeżeli Twój plik PDF nie ma żadnych stron, możesz dodać pustą stronę za pomocą`Pages.Add()` metodą, jak pokazano w tym samouczku.

### Czy mogę manipulować wieloma stronami jednocześnie?
Tak, możesz przeglądać wiele stron i stosować transformacje, takie jak zmiana rozmiaru lub obrót, na każdej z nich.

### Czy wymiary strony mają wpływ na zawartość pliku PDF?
Wymiary strony zmieniają tylko rozmiar płótna, nie zawartość. Jednak zmiana rozmiaru może zmienić sposób wyświetlania zawartości na stronie.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.PDF dla .NET?
 Możesz odwiedzić[dokumentacja tutaj](https://reference.aspose.com/pdf/net/) aby uzyskać bardziej szczegółowe informacje i zaawansowane przypadki użycia.