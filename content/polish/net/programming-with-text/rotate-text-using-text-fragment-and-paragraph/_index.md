---
title: Obróć tekst za pomocą fragmentu tekstu i akapitu
linktitle: Obróć tekst za pomocą fragmentu tekstu i akapitu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak obracać tekst przy użyciu fragmentu tekstu i akapitu w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 400
url: /pl/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do obracania tekstu za pomocą fragmentu tekstu i akapitu. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

## Warunki wstępne

Przed kontynuowaniem samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Utwórz dokument PDF

 Zainicjuj`Document` obiekt, aby utworzyć nowy dokument PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Dodaj stronę

 Pobierz określoną stronę z dokumentu za pomocą metody`Pages.Add()` metoda:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 5: Utwórz fragmenty tekstu

 Utwórz wiele`TextFragment` obiekty, ustaw ich tekst i właściwości oraz określ kąt obrotu:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Dostosuj tekst, kąt obrotu i inne właściwości według potrzeb.

## Krok 6: Dodaj fragmenty tekstu do strony

 Dodaj utworzone fragmenty tekstu do strony, dołączając je do pliku`Paragraphs` kolekcja:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Krok 7: Zapisz dokument PDF

 Zapisz zmodyfikowany dokument PDF do pliku za pomocą`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Pamiętaj o wymianie`"TextFragmentTests_Rotated3_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy funkcji Obróć tekst przy użyciu fragmentu tekstu i akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Uzyskaj konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Utwórz fragment tekstu
TextFragment textFragment1 = new TextFragment("main text");
// Ustaw właściwości tekstu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Utwórz fragment tekstu
TextFragment textFragment2 = new TextFragment("rotated text");
// Ustaw właściwości tekstu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ustaw obrót
textFragment2.TextState.Rotation = 315;
// Utwórz fragment tekstu
TextFragment textFragment3 = new TextFragment("rotated text");
// Ustaw właściwości tekstu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ustaw obrót
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Zapisz dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się obracać tekst przy użyciu fragmentów tekstu i akapitów w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od utworzenia dokumentu do zapisania zmodyfikowanej wersji. Możesz teraz włączyć ten kod do własnych projektów C#, aby manipulować rotacją tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Obróć tekst za pomocą fragmentu tekstu i akapitu”?

Odp.: Samouczek „Obróć tekst za pomocą fragmentu tekstu i akapitu” ma na celu poprowadzenie Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu przy użyciu zarówno fragmentów tekstu, jak i akapitów w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod umożliwiający osiągnięcie tej funkcjonalności.

#### P: Czym ten samouczek różni się od poprzednich samouczków dotyczących rotacji tekstu?

Odp.: W tym samouczku zastosowano fragmenty tekstu i akapity w celu uzyskania rotacji tekstu w dokumencie PDF. Pokazuje, jak obracać fragmenty tekstu indywidualnie, a następnie dodawać je do strony`Paragraphs` kolekcję, aby uzyskać bardziej kompleksowy efekt rotacji tekstu.

#### P: Jakie są zalety używania fragmentów tekstu i akapitów do obracania tekstu?

Odp.: Łączne używanie fragmentów tekstu i akapitów pozwala na większą elastyczność w rotacji tekstu. Fragmenty tekstu umożliwiają indywidualne ustawienia rotacji i formatowania, natomiast akapity zapewniają strukturę do rozmieszczania i pozycjonowania fragmentów tekstu na stronie.

#### P: Czy mogę zastosować różne kąty obrotu do różnych fragmentów tekstu w tym samym akapicie?

 Odp.: Tak, możesz zastosować różne kąty obrotu do różnych`TextFragment` obiektów w tym samym akapicie. Każdy fragment tekstu może mieć swój własny kąt obrotu określony za pomocą opcji`TextState.Rotation` nieruchomość.

#### P: Czy przy użyciu tej metody można uzyskać złożone efekty rotacji tekstu?

O: Tak, łącząc fragmenty tekstu o różnych kątach obrotu i układając je w akapitach, można uzyskać złożone i dostosowane efekty rotacji tekstu, zwiększając atrakcyjność wizualną dokumentów PDF.

#### P: Jakie kroki obejmują obracanie tekstu przy użyciu fragmentów tekstu i akapitów?

Odp.: Te kroki obejmują:

1. Konfiguracja projektu poprzez utworzenie nowego projektu C# i dodanie odniesienia do biblioteki Aspose.PDF for .NET.
2. Tworzenie dokumentu PDF i dodawanie strony.
3. Tworzenie fragmentów tekstu, ustawianie ich właściwości i określanie kątów obrotu.
4.  Dodawanie fragmentów tekstu do strony za pomocą metody`Paragraphs` kolekcja.
5. Zapisywanie zmodyfikowanego dokumentu PDF.

#### P: Czy mogę zastosować obrót do całych akapitów?

 Odp.: Tak, możesz zastosować obrót całych akapitów, ustawiając opcję`TextState.Rotation` właściwość samego akapitu. Spowoduje to obrócenie wszystkich fragmentów tekstu w tym akapicie.