---
title: Dodaj pieczątkę obrazkową do pliku PDF
linktitle: Dodaj pieczątkę obrazkową do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać znacznik graficzny do plików PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z instrukcji krok po kroku i przykładowego kodu.
type: docs
weight: 20
url: /pl/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## Wstęp

Jeśli chodzi o manipulowanie plikami PDF, niewiele narzędzi jest tak solidnych i przyjaznych dla użytkownika jak Aspose.PDF dla .NET. Niezależnie od tego, czy chcesz dodawać adnotacje, tworzyć formularze czy stemplować obrazy, ta biblioteka zapewnia rozbudowaną funkcjonalność, aby sprostać różnym potrzebom manipulacji plikami PDF. W tym samouczku skupimy się na konkretnym zadaniu: dodaniu stempla obrazu do pliku PDF. Nie chodzi tu tylko o umieszczenie obrazu na stronie; chodzi o ulepszenie dokumentów za pomocą brandingu i atrakcyjności wizualnej!

## Wymagania wstępne

Zanim zagłębimy się w szczegóły kodu, upewnijmy się, że masz wszystko, czego potrzebujesz. Oto, czego będziesz potrzebować:

1. Visual Studio lub dowolne środowisko IDE .NET: Aby zaimplementować fragmenty kodu, potrzebne jest środowisko programistyczne .NET.
2.  Aspose.PDF dla biblioteki .NET: To jest główne narzędzie, którego będziemy używać. Najnowszą wersję biblioteki można pobrać ze strony[Strona wydania Aspose](https://releases.aspose.com/pdf/net/).
3. Podstawowa znajomość języka C#: Podstawowa znajomość programowania w języku C# pomoże Ci płynnie poruszać się po kodzie.
4. Plik obrazu: Potrzebujesz pliku obrazu, którego chcesz użyć jako pieczątki. Upewnij się, że jest w obsługiwanym formacie (np. JPEG, PNG itp.).
5. Istniejący plik PDF: Przygotuj przykładowy plik PDF, do którego chcesz dodać stempel graficzny.

Teraz, gdy wszystko jest już gotowe, możemy przejść do kodu!

## Importuj pakiety

Po pierwsze — zanim cokolwiek zrobisz, musisz zaimportować niezbędne przestrzenie nazw. W kodzie C# możesz to zrobić, dodając następującą dyrektywę using na górze pliku:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

Umożliwi to dostęp do różnych klas i metod udostępnianych przez bibliotekę Aspose.PDF.

## Krok 1: Skonfiguruj katalog dokumentów

 Pierwszym krokiem jest określenie ścieżki do dokumentów. Będziesz chciał przechowywać dokument i obrazy w dobrze zdefiniowanym katalogu. Dla uproszczenia zadeklaruj zmienną`dataDir` tak:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką w Twoim systemie.

## Krok 2: Otwórz dokument PDF

Następnie musimy otworzyć dokument PDF, który chcemy zmodyfikować. To jest miejsce, w którym Aspose.PDF błyszczy! Potrzebujesz tylko kilku linijek kodu:

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

 Ta linia tworzy nowy`Document`obiekt, ładując określony plik PDF. Upewnij się, że plik istnieje w określonym katalogu; w przeciwnym razie pojawi się błąd file-not-found!

## Krok 3: Utwórz pieczątkę obrazkową

Teraz nadchodzi zabawna część — dodanie stempla obrazu! Najpierw musimy utworzyć obiekt stempla obrazu, używając pliku obrazu:

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 Ta linia inicjuje`ImageStamp` obiekt, który reprezentuje obraz, który chcesz dodać. Ważne jest, aby sprawdzić, czy ścieżka do pliku obrazu jest poprawna.

## Krok 4: Skonfiguruj właściwości stempla graficznego

Tutaj możesz wykazać się kreatywnością i dostosować swój znaczek. Możesz ustawić właściwości, takie jak pozycja, rozmiar, obrót i krycie. Oto przykład, jak to zrobić:

```csharp
imageStamp.Background = true; // Ustaw na true, jeśli chcesz, aby znaczek znajdował się w tle
imageStamp.XIndent = 100; // Pozycja od lewej
imageStamp.YIndent = 100; // Pozycja od góry
imageStamp.Height = 300; // Ustaw wysokość znaczka
imageStamp.Width = 300; // Ustaw szerokość znaczka
imageStamp.Rotate = Rotation.on270; // Obróć, jeśli to konieczne
imageStamp.Opacity = 0.5; // Ustaw krycie
```

Możesz swobodnie modyfikować te wartości zgodnie ze swoimi wymaganiami! Ta personalizacja pozwala Ci umieścić swój znaczek dokładnie tam, gdzie chcesz.

## Krok 5: Dodaj znaczek do konkretnej strony

Teraz, gdy mamy już skonfigurowany nasz znaczek, następnym krokiem jest określenie, gdzie chcemy go umieścić w dokumencie PDF. W tym przykładzie dodamy go do pierwszej strony:

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Ten fragment kodu informuje program Aspose o konieczności dodania stempla na pierwszej stronie dokumentu.

## Krok 6: Zapisz dokument

Po zastosowaniu stempla, czas zapisać zmiany. Musisz określić ścieżkę do pliku wyjściowego PDF:

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

Twój dokument został zapisany z nowym stemplem graficznym!

## Krok 7: Potwierdź modyfikację

Na koniec, zawsze dobrze jest potwierdzić, że operacja się powiodła. Możesz to zrobić za pomocą prostej wiadomości w konsoli:

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

Ta wiadomość powiadomi Cię, że dodany został znacznik obrazu i wskaże, gdzie można znaleźć zmodyfikowany plik PDF.

## Wniosek

Gratulacje! Właśnie dodałeś stempel graficzny do pliku PDF za pomocą Aspose.PDF dla .NET. Na początku może się to wydawać skomplikowane, ale przy odrobinie praktyki możesz dostosować swoje dokumenty PDF na niezliczone sposoby. Kluczem jest eksperymentowanie z różnymi właściwościami oferowanymi przez Aspose — ogranicza Cię tylko wyobraźnia.

## Najczęściej zadawane pytania

### Czy korzystanie z Aspose.PDF dla platformy .NET jest bezpłatne?  
 Aspose.PDF oferuje bezpłatną wersję próbną, ale do dalszego korzystania po okresie próbnym wymagana jest licencja. Możesz sprawdzić[opcje cenowe tutaj](https://purchase.aspose.com/buy).

### Czy mogę dodać wiele znaczków do jednego pliku PDF?  
 Oczywiście! Możesz utworzyć wiele`ImageStamp` obiekty i dodawać je do dowolnej strony w pliku PDF.

### Jakie formaty obrazów są obsługiwane w przypadku znaczków?  
Aspose.PDF obsługuje różne formaty obrazów, w tym JPEG, PNG i BMP.

### Jak mogę obrócić stempel graficzny?  
 Możesz ustawić`Rotate` własność`ImageStamp` obiekt, aby obrócić obraz pod żądanym kątem. Opcje obejmują`Rotation.on90`, `Rotation.on180`itp.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.PDF?  
 Możesz zapoznać się z pełną dokumentacją i referencjami API[Tutaj](https://reference.aspose.com/pdf/net/).