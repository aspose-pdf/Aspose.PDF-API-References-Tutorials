---
title: Pobierz okno dokumentu
linktitle: Pobierz okno dokumentu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać funkcji GetDocumentWindow pakietu Aspose.PDF dla platformy .NET w celu pobierania informacji o właściwościach okna dokumentu PDF.
type: docs
weight: 170
url: /pl/net/programming-with-document/getdocumentwindow/
---
# Wstęp

Czy pracujesz z plikami PDF i chcesz mieć większą kontrolę nad tym, jak wyglądają po otwarciu? Niezależnie od tego, czy chodzi o ukrycie paska menu, czy zmianę rozmiaru okna, aby dopasować je do pierwszej strony, Aspose.PDF dla .NET zapewnia wszystkie narzędzia potrzebne do dostosowania zachowania pliku PDF po otwarciu w przeglądarce. W tym samouczku pokażemy, jak pobierać i manipulować ustawieniami okna dokumentu w Aspose.PDF dla .NET.


# Wymagania wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:

- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym.
  - [Pobierz Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/)
-  Ważna licencja na Aspose.PDF lub możesz uzyskać[bezpłatny okres próbny](https://releases.aspose.com/) Lub[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).
- Podstawowa znajomość .NET i C#.
- Visual Studio lub inne odpowiednie środowisko IDE.

# Importuj pakiety

Zanim zaczniesz pisać kod, musisz zaimportować niezbędne pakiety. Otwórz swój projekt i na górze pliku C# dodaj następującą przestrzeń nazw:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dzięki temu uzyskasz dostęp do wszystkich klas i metod niezbędnych do manipulowania dokumentami PDF za pomocą Aspose.PDF dla .NET.

 Teraz rozłóżmy proces pobierania różnych ustawień okna dokumentu. W tym przykładzie użyjemy przykładowego pliku PDF o nazwie`GetDocumentWindow.pdf`.

## Krok 1: Ustaw ścieżkę katalogu dokumentu

Po pierwsze, musimy zdefiniować ścieżkę do naszego pliku PDF. Ważne jest, aby mieć poprawną ścieżkę do pliku, aby uniknąć błędów podczas wykonywania.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tutaj zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się Twój plik PDF. To jest Twój katalog roboczy, z którego będziesz ładować dokument PDF.

## Krok 2: Otwórz dokument PDF

Teraz, gdy ścieżka pliku jest ustawiona, następnym krokiem jest otwarcie dokumentu PDF za pomocą Aspose.PDF. Spowoduje to załadowanie dokumentu do pamięci, umożliwiając pobranie jego właściwości.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Dzięki tej prostej linijce kodu udało Ci się pomyślnie załadować plik PDF do`pdfDocument` obiekt, co umożliwi Ci dostęp do wszystkich jego właściwości.

## Krok 3: Pobierz stan centrowania okna

 Następnie sprawdźmy, czy okno dokumentu powinno być wyśrodkowane po otwarciu. Domyślna wartość to`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Jeśli wyjście jest`true`, okno dokumentu otworzy się na środku ekranu. W przeciwnym wypadku otworzy się w domyślnej pozycji.

## Krok 4: Sprawdź kierunek tekstu

Innym istotnym aspektem wyglądu pliku PDF jest kierunek tekstu, który określa, czy tekst jest czytany od lewej do prawej (L2R) czy od prawej do lewej (R2L). Możesz pobrać te informacje, używając następującego kodu:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Wynik będzie następujący`L2R` dla tekstu pisanego od lewej do prawej i`R2L` dla tekstu od prawej do lewej. To ustawienie jest szczególnie przydatne w przypadku dokumentów w językach takich jak arabski lub hebrajski.

## Krok 5: Wyświetl tytuł dokumentu w oknie

Następna właściwość pozwala kontrolować, czy tytuł dokumentu czy nazwa pliku ma być wyświetlana na pasku tytułu okna. Domyślnie jest to ustawione na`false`, co oznacza, że zostanie wyświetlona nazwa pliku.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Jeśli chcesz, aby zamiast nazwy pliku był wyświetlany tytuł dokumentu, to ustawienie musi być włączone.

## Krok 6: Zmień rozmiar okna, aby dopasować je do pierwszej strony

Czasami możesz chcieć, aby okno dokumentu automatycznie zmieniało rozmiar, aby dopasować się do pierwszej strony pliku PDF po jego otwarciu. Oto jak sprawdzić, czy ta funkcja jest włączona:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Domyślnie jest to ustawione na`false`, co oznacza, że rozmiar okna pozostanie taki sam, niezależnie od rozmiaru pierwszej strony.

## Krok 7: Ukryj pasek menu

Aby uzyskać bardziej skoncentrowane wrażenia z czytania, możesz ukryć pasek menu aplikacji przeglądarki. Możesz odzyskać to ustawienie, używając następującego wiersza:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 To wróci`true` jeśli pasek menu jest ukryty i`false` W przeciwnym razie.

## Krok 8: Ukryj pasek narzędzi

Podobnie, możesz również chcieć ukryć pasek narzędzi w przeglądarce PDF, aby uzyskać czystszy interfejs użytkownika. To ustawienie można pobrać w następujący sposób:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Jeśli to ustawienie jest włączone, pasek narzędzi będzie ukryty po otwarciu pliku PDF.

## Krok 9: Ukryj paski przewijania i elementy interfejsu użytkownika

Jeśli chcesz wyświetlić tylko zawartość strony, bez żadnych dodatkowych elementów interfejsu użytkownika, takich jak paski przewijania, to ustawienie kontroluje to zachowanie:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Gdy ustawione na`true`przeglądarka PDF ukryje paski przewijania oraz inne elementy interfejsu użytkownika, pozostawiając tylko treść dokumentu.

## Krok 10: Ustaw tryb strony inny niż pełny ekran

 Możesz kontrolować sposób wyświetlania dokumentu po wyjściu z trybu pełnoekranowego za pomocą`NonFullScreenPageMode` właściwość. To ustawienie jest pomocne w definiowaniu sposobu interakcji użytkownika z dokumentem w trybie innym niż pełny ekran.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Wyjście można ustawić w różnych trybach, takich jak miniatury, kontury lub panel załączników.

## Krok 11: Zdefiniuj układ strony

To ustawienie pozwala kontrolować układ stron dokumentu. Na przykład możesz wybrać widok pojedynczej strony lub widok ciągłej kolumny:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Dzięki temu użytkownicy mają większą swobodę w sposobie czytania i przeglądania treści dokumentu.

## Krok 12: Określ tryb strony

 Na koniec,`PageMode` właściwość definiuje sposób wyświetlania dokumentu po jego otwarciu. Opcje obejmują wyświetlanie miniatur, wchodzenie w tryb pełnoekranowy lub wyświetlanie panelu załączników.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Możesz ustawić dowolny tryb, zależnie od potrzeb, odpowiadający celowi Twojego pliku PDF.

## Wniosek

Jak widać, Aspose.PDF dla .NET zapewnia kompleksowe narzędzia do manipulowania sposobem wyświetlania dokumentów PDF w różnych przeglądarkach PDF. Niezależnie od tego, czy chcesz ukryć pasek narzędzi, wyśrodkować okno, czy kontrolować kierunek tekstu, Aspose.PDF oferuje elastyczność, aby ulepszyć wrażenia użytkownika podczas oglądania.

# Często zadawane pytania

### Czy mogę dostosować początkowy poziom powiększenia pliku PDF?
Tak, Aspose.PDF pozwala na ustawienie poziomu powiększenia podczas otwierania dokumentu.

### Jak mogę zablokować rozmiar okna pliku PDF?
 Możesz ustawić`FitWindow` właściwość zapobiegająca zmianie rozmiaru okna.

### Czy Aspose.PDF obsługuje różne tryby czytania?
Tak, obsługuje różne tryby, takie jak pełny ekran, miniatury i załączniki.

### Czy można ukryć paski przewijania w przeglądarce PDF?
 Oczywiście, możesz ukryć paski przewijania, ustawiając`HideWindowUI` nieruchomość do`true`.

### Czy mogę wyśrodkować okno otwartego dokumentu?
 Tak, możesz to kontrolować, ustawiając`CenterWindow` nieruchomość.