---
title: Obraz w stopce
linktitle: Obraz w stopce
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać obraz w sekcji stopki dokumentu PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 130
url: /pl/net/programming-with-stamps-and-watermarks/image-in-footer/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak dodać obraz w sekcji stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby otworzyć istniejący dokument PDF, utworzyć bufor obrazu, ustawić jego właściwości i dodać go do wszystkich stron dokumentu PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Ładowanie istniejącego dokumentu PDF

Pierwszym krokiem jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz istniejący dokument PDF
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

## Krok 3: Tworzenie i dodanie obrazu w sekcji stopki

Teraz, gdy dokument PDF jest załadowany, możemy utworzyć stempel graficzny i dodać go do wszystkich stron dokumentu. Oto jak:

```csharp
// Utwórz bufor ramki
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Ustaw właściwości bufora obrazu
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Dodaj bufor obrazu do wszystkich stron
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Powyższy kod tworzy bufor obrazu z pliku „aspose-logo.jpg” i ustawia jego właściwości, takie jak dolny margines, wyrównanie w poziomie i pionie. Następnie do wszystkich stron dokumentu PDF dodawany jest bufor obrazu.

## Krok 4: Zapisanie zmodyfikowanego dokumentu PDF

Po dodaniu obrazu do sekcji stopki możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy obrazu w stopce przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Utwórz stopkę
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Ustaw właściwości stempla
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Dodaj stopkę na wszystkich stronach
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Zapisz zaktualizowany plik PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać obraz w sekcji stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz dostosować stopki swoich dokumentów PDF, dodając obrazy.

### Często zadawane pytania dotyczące obrazu w stopce

#### P: Jaki jest cel dodawania obrazu do sekcji stopki dokumentu PDF?

Odp.: Dodanie obrazu do sekcji stopki dokumentu PDF umożliwia umieszczenie elementów wizualnych, takich jak logo lub znak wodny, u dołu każdej strony. Może to poprawić markę i estetykę treści PDF.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie obrazu do sekcji stopki dokumentu PDF?

 O: Dostarczony kod demonstruje, jak załadować istniejący dokument PDF, utworzyć plik`ImageStamp` obiektu z pliku obrazu, ustaw właściwości, takie jak dolny margines i wyrównanie, a następnie dodaj stempel obrazu do stopki wszystkich stron.

#### P: Czy mogę dostosować położenie i wyrównanie obrazu w sekcji stopki?

 O: Tak, możesz dostosować położenie i wyrównanie obrazu w sekcji stopki, modyfikując właściwości pliku`ImageStamp` obiekt. Fragment kodu ustawia właściwości takie jak`BottomMargin`, `HorizontalAlignment` , I`VerticalAlignment`.

#### P: Czy można dodać różne obrazy do sekcji stopki na różnych stronach dokumentu PDF?

 Odp.: Tak, możesz dodać różne obrazy do sekcji stopki na różnych stronach, tworząc osobne`ImageStamp` obiekty o różnych plikach obrazów i właściwościach, a następnie dodawanie ich do określonych stron.

#### P: W jaki sposób kod zapewnia dodanie obrazu do wszystkich stron dokumentu PDF?

Odp.: Dostarczony kod wykorzystuje a`foreach` pętla, aby iterować po wszystkich stronach dokumentu PDF i dodaje to samo`ImageStamp` do sekcji stopki każdej strony.

#### P: Czy mogę dodać inne elementy, takie jak tekst lub kształty, do sekcji stopki, stosując podobne podejście?

 O: Tak, możesz dodać inne elementy, takie jak tekst lub kształty, do sekcji stopki, stosując podobne podejście, tworząc odpowiednie obiekty stempla (np.`TextStamp`) i odpowiednio ustawiając ich właściwości.

#### P: Jak określić ścieżkę do pliku obrazu, który chcę dodać do stopki?

 Odp.: Ścieżka do pliku obrazu jest określana podczas tworzenia pliku`ImageStamp` obiekt, jak pokazano w kodzie. Upewnij się, że podałeś poprawną ścieżkę do pliku obrazu.

#### P: Czy mogę dostosować rozmiar obrazu w sekcji stopki?

 O: Tak, możesz dostosować rozmiar obrazu w sekcji stopki, dostosowując wymiary pliku`ImageStamp` używając właściwości takich jak`Width` I`Height`.

#### P: Czy można usunąć lub zastąpić obraz w stopce po jego dodaniu?

 O: Tak, możesz usunąć lub zastąpić obraz w sekcji stopki, modyfikując zawartość pliku`ImageStamp` obiektu lub usunięcia stempla z określonych stron.

#### P: Jak kod radzi sobie ze scenariuszami, w których wymiary obrazu przekraczają dostępne miejsce w stopce?

 O: Kod ustawia właściwości takie jak`BottomMargin`, `HorizontalAlignment` , I`VerticalAlignment` do kontrolowania położenia i wyrównania obrazu. Upewnij się, że te właściwości są dostosowane, aby zapobiec nakładaniu się lub problemom z układem.