---
title: Dodaj i wyszukaj ukryty tekst w pliku PDF
linktitle: Dodaj i wyszukaj ukryty tekst w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Naucz się dodawać i wyszukiwać ukryty tekst w dokumentach PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z dołączonymi przykładami kodu.
type: docs
weight: 20
url: /pl/net/programming-with-text/add-and-search-hidden-text/
---
## Wstęp

W tym samouczku przeprowadzimy Cię przez przewodnik krok po kroku, jak dodawać i wyszukiwać ukryty tekst w pliku PDF za pomocą Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, który chce poprawić swoje umiejętności programistyczne, ten artykuł dostarczy Ci informacji, których potrzebujesz, aby włączyć funkcjonalność ukrytego tekstu do swoich aplikacji.

## Wymagania wstępne

Zanim przejdziesz do części poświęconej kodowaniu, musisz spełnić kilka warunków wstępnych:

### Lista kontrolna wymagań
- Visual Studio: Upewnij się, że masz zainstalowany Visual Studio. Ten samouczek zakłada, że używasz .NET Framework.
-  Aspose.PDF dla .NET: Musisz mieć bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/).
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

## Importuj pakiety

Zanim zaczniesz pracę nad kodem, musisz upewnić się, że zaimportowałeś niezbędne przestrzenie nazw Aspose.PDF. Oto, jak to zrobić:

### Skonfiguruj swój projekt
1. Otwórz program Visual Studio i utwórz nowy projekt C# lub użyj istniejącego.
2.  Zainstaluj Aspose.PDF, dodając pakiet NuGet. Możesz to zrobić, przechodząc do Menedżera pakietów NuGet i wyszukując`Aspose.PDF`. 
3.  Alternatywnie możesz pobrać bibliotekę bezpośrednio z[Tutaj](https://releases.aspose.com/pdf/net/) i dodaj go jako odniesienie w swoim projekcie.

### Importuj wymagane przestrzenie nazw
Na górze pliku C# zaimportuj następujące przestrzenie nazw:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ten krok jest kluczowy, ponieważ te przestrzenie nazw zawierają klasy i metody niezbędne do manipulowania dokumentami PDF.

## Tworzenie dokumentu PDF z ukrytym tekstem

Teraz, gdy wszystko jest już skonfigurowane, przejdźmy przez kroki tworzenia dokumentu PDF zawierającego zarówno widoczny, jak i niewidoczny tekst.

### Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę, w której plik PDF zostanie zapisany. To tutaj zaczyna się magia!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zmień to na swój katalog
```

 Ta linia definiuje, gdzie będzie przechowywany wygenerowany plik PDF. Nie zapomnij zastąpić`YOUR DOCUMENT DIRECTORY` z twoją rzeczywistą ścieżką.

### Krok 2: Utwórz dokument PDF
Następnie utwórzmy nowy dokument PDF i dodajmy do niego strony.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Tutaj inicjujemy nowy dokument i dodajemy stronę, na której umieścimy fragmenty tekstu.

### Krok 3: Dodaj widoczny i ukryty tekst
Teraz dodamy do naszego pliku PDF zarówno widoczny, jak i niewidoczny tekst.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 W tym fragmencie,`frag1` będzie widoczny, podczas gdy`frag2` zostanie ustawiony jako niewidoczny.

### Krok 4: Ustaw tekst jako niewidoczny
 Aby utworzyć tekst`frag2` niewidoczne, po prostu je modyfikujesz`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Ustawiając tę właściwość, każdy tekst powiązany z`frag2` nie zostanie wyświetlona podczas przeglądania pliku PDF.

### Krok 5: Dodaj fragmenty tekstu do strony
Na koniec dodajemy te fragmenty tekstu do strony i zapisujemy plik PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Ta część kodu dodaje nasze fragmenty tekstu do strony. Następnie zapisujemy i usuwamy dokument prawidłowo.

## Wyszukiwanie ukrytego tekstu w pliku PDF

Teraz, gdy utworzyliśmy nasz plik PDF z widocznym i ukrytym tekstem, jak wyszukać ten ukryty tekst? Rozłóżmy to na czynniki pierwsze.

### Krok 1: Załaduj dokument PDF
Aby przeszukać tekst w pliku PDF, musimy najpierw załadować właśnie utworzony dokument.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Krok 2: Utwórz absorber fragmentów tekstu
 Użyjemy`TextFragmentAbsorber` aby przechwycić wszystkie fragmenty tekstu w pliku PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Tutaj określamy, że chcemy wchłonąć wszystkie fragmenty tekstu z pierwszej strony.

### Krok 3: Przejrzyj fragmenty
Teraz możemy przejrzeć zebrane fragmenty tekstu, aby dowiedzieć się, które z nich są widoczne, a które ukryte.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Ta pętla sprawdza każdy fragment tekstu i drukuje jego zawartość wraz z jego pozycją i statusem widoczności. Jeśli`fragment.TextState.Invisible` jest ustawione na true, oznacza to, że tekst jest ukryty!

### Krok 4: Usuń dokument
Na koniec pamiętaj, żeby usunąć dokument, gdy już skończysz.

```csharp
doc.Dispose();
```

## Wniosek

W tym samouczku przeszliśmy przez ekscytujący proces dodawania i wyszukiwania ukrytego tekstu w plikach PDF przy użyciu Aspose.PDF dla .NET. Dowiedzieliśmy się, jak utworzyć dokument PDF z widocznym i ukrytym tekstem, a także jak programowo wyszukiwać ten ukryty tekst. Ta możliwość może być niezwykle przydatna w różnych aplikacjach, niezależnie od tego, czy musisz przechowywać poufne informacje, czy zapewnić unikalne wrażenia użytkownika w swoich dokumentach.

W miarę jak będziesz coraz bardziej zaznajomiony z ASPose.PDF, możliwości staną się nieograniczone. Eksperymentuj i przesuwaj granice tego, co możesz osiągnąć dzięki swoim dokumentom PDF!

## Najczęściej zadawane pytania

### Czy Aspose.PDF obsługuje zaszyfrowane pliki PDF?  
Tak, Aspose.PDF obsługuje szyfrowanie i deszyfrowanie dokumentów PDF. Możesz łatwo zabezpieczyć swoje pliki PDF hasłami.

### Czy jest dostępna wersja próbna Aspose.PDF?  
 Oczywiście! Możesz pobrać darmową wersję próbną z[Tutaj](https://releases.aspose.com/).

### Jakie języki programowania obsługuje Aspose.PDF?  
Aspose.PDF obsługuje wiele języków, w tym C#, Java i Python.

### Gdzie mogę znaleźć dokumentację dla Aspose.PDF?  
 Możesz uzyskać dostęp do dokumentacji[Tutaj](https://reference.aspose.com/pdf/net/).

### Jak mogę uzyskać pomoc, jeśli napotkam problemy?  
 Aby uzyskać pomoc, możesz odwiedzić fora Aspose[Tutaj](https://forum.aspose.com/c/pdf/10).