---
title: Ustaw dowolne formatowanie adnotacji tekstowych
linktitle: Ustaw dowolne formatowanie adnotacji tekstowych
second_title: Aspose.PDF z dokumentacją API .NET
description: W tym artykule znajduje się przewodnik krok po kroku dotyczący tworzenia adnotacji tekstowej i określania jej zawartości przy użyciu Aspose.PDF dla .NET
type: docs
weight: 140
url: /pl/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF dla .NET to potężny i łatwy w użyciu interfejs API do manipulacji dokumentami PDF, który umożliwia programową pracę z plikami PDF w aplikacjach .NET. Jedną z funkcji udostępnianych przez Aspose.PDF dla .NET jest możliwość ustawienia dowolnego formatowania adnotacji tekstowych w dokumentach PDF. W tym artykule przeprowadzimy Cię krok po kroku przez proces ustawiania formatowania adnotacji dowolnego tekstu przy użyciu Aspose.PDF dla .NET.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

- Microsoft Visual Studio 2010 lub nowszy
- Aspose.PDF dla .NET
- Podstawowa znajomość C#



## Krok 1: Utwórz nową aplikację konsolową C#

Najpierw utwórz nową aplikację konsolową C# w Microsoft Visual Studio. Aby utworzyć nową aplikację konsolową, wybierz z menu głównego opcję „Plik” > „Nowy” > „Projekt” > „Visual C#” > „Aplikacja konsolowa”.

## Krok 2: Dodaj odniesienie do Aspose.PDF dla .NET

Następnie dodaj w swoim projekcie odwołanie do Aspose.PDF dla .NET. Aby to zrobić, kliknij prawym przyciskiem myszy swój projekt w panelu „Solution Explorer”, wybierz „Dodaj” > „Odniesienie”, a następnie przejdź do lokalizacji, w której zapisałeś plik Aspose.PDF dla .NET DLL. Wybierz plik DLL i kliknij „OK”, aby dodać odniesienie do swojego projektu.

## Krok 3: Skonfiguruj środowisko

Po dodaniu odniesienia do Aspose.PDF dla .NET należy skonfigurować środowisko. Aby to zrobić, utwórz nową zmienną łańcuchową o nazwie „dataDir” i ustaw ją na ścieżkę do katalogu, w którym znajduje się dokument PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” w poniższym kodzie rzeczywistą ścieżką do katalogu dokumentów:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 4: Otwórz dokument PDF

Po skonfigurowaniu środowiska możesz otworzyć dokument PDF za pomocą następującego kodu:

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Zastąp „SetFreeTextAnnotationFormatting.pdf” rzeczywistą nazwą dokumentu PDF.

## Krok 5: Skonfiguruj domyślny wygląd

Aby ustawić domyślny wygląd adnotacji tekstowej, należy utworzyć instancję obiektu DefaultAppearance z żądaną czcionką, jej rozmiarem i kolorem. W tym samouczku ustawiamy czcionkę na „Arial”, rozmiar czcionki na 28 i kolor na czerwony.

```csharp
// Utwórz instancję obiektu DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Krok 6: Utwórz dowolną adnotację tekstową

Po skonfigurowaniu wyglądu domyślnego możesz utworzyć adnotację tekstową, korzystając z następującego kodu:

```csharp
// Utwórz adnotację
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Powyższy kod tworzy nową adnotację tekstową na drugiej stronie dokumentu PDF. Adnotacja zostanie umieszczona w (200, 400) i będzie miała szerokość 400 i wysokość 600.

## Krok 7: Określ treść adnotacji

Po utworzeniu adnotacji tekstowej możesz określić jej treść, korzystając z następującego kodu:

```csharp
// Określ treść adnotacji
freetext.Contents = "Free Text
```

### Przykładowy kod źródłowy dla ustawiania formatowania adnotacji dowolnego tekstu przy użyciu Aspose.PDF dla .NET
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Utwórz instancję obiektu DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Utwórz adnotację
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Określ treść adnotacji
freetext.Contents = "Free Text";
// Dodaj adnotację do kolekcji adnotacji strony
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);            
```

## Wniosek

tym samouczku nauczyliśmy się, jak ustawić formatowanie adnotacji dowolnego tekstu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Biblioteka zapewnia prosty i wydajny sposób programowej pracy z dokumentami PDF, umożliwiając programistom tworzenie i dostosowywanie różnych typów adnotacji, w tym adnotacji w postaci dowolnego tekstu. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo skonfigurować środowisko, otworzyć dokument PDF i utworzyć dowolną adnotację tekstową z niestandardowym formatowaniem. Aspose.PDF dla .NET to solidny i niezawodny interfejs API, który upraszcza zadania manipulacji dokumentami PDF, co czyni go cennym narzędziem dla programistów .NET pracujących z plikami PDF.

### Często zadawane pytania

#### P: Co to jest adnotacja dowolnego tekstu w dokumencie PDF?

O: Dowolna adnotacja tekstowa w dokumencie PDF to rodzaj adnotacji, który umożliwia dodanie tekstu do dokumentu bez konieczności wiązania się z konkretną lokalizacją lub strukturą. Jest powszechnie używany do umieszczania komentarzy, notatek lub innych dodatkowych informacji w dokumencie.

#### P: Czy mogę dostosować wygląd adnotacji tekstowej za pomocą Aspose.PDF dla .NET?

O: Tak, możesz dostosować różne właściwości adnotacji tekstowej, takie jak czcionka, rozmiar czcionki, kolor, położenie i inne.

#### P: Jak określić zawartość adnotacji tekstowej?

 O: Aby określić zawartość adnotacji tekstowej, możesz ustawić`Contents` własność`FreeTextAnnotation` sprzeciw wobec żądanego tekstu.

#### P: Czy mogę dodać wiele adnotacji tekstowych do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz utworzyć wiele dowolnych adnotacji tekstowych w dokumencie PDF, tworząc wiele wystąpień pliku`FreeTextAnnotation`obiektu i dodając je do różnych stron lub lokalizacji w dokumencie.