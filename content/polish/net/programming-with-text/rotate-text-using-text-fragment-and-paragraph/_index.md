---
title: Obróć tekst za pomocą fragmentu tekstu i akapitu
linktitle: Obróć tekst za pomocą fragmentu tekstu i akapitu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak obracać tekst za pomocą fragmentu tekstu i akapitu w dokumencie PDF, korzystając z Aspose.PDF dla platformy .NET.
type: docs
weight: 400
url: /pl/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do obracania tekstu za pomocą fragmentu tekstu i akapitu. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Aspose.PDF dla biblioteki .NET jest zainstalowany. Możesz go pobrać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw

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

 Pobierz konkretną stronę z dokumentu za pomocą`Pages.Add()` metoda:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 5: Utwórz fragmenty tekstu

 Utwórz wiele`TextFragment` obiekty, ustaw ich tekst i właściwości, a także określ kąt obrotu:

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

 Dodaj utworzone fragmenty tekstu do strony, dołączając je do`Paragraphs` kolekcja:

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

### Przykładowy kod źródłowy dla funkcji Obróć tekst za pomocą fragmentu tekstu i akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Pobierz konkretną stronę
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

Gratulacje! Udało Ci się nauczyć, jak obracać tekst za pomocą fragmentów tekstu i akapitów w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od tworzenia dokumentu do zapisywania zmodyfikowanej wersji. Teraz możesz włączyć ten kod do własnych projektów C#, aby manipulować obrotem tekstu w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Obróć tekst za pomocą fragmentu tekstu i akapitu”?

A: Samouczek „Obróć tekst za pomocą fragmentu tekstu i akapitu” ma na celu przeprowadzenie Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu za pomocą zarówno fragmentów tekstu, jak i akapitów w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod, aby osiągnąć tę funkcjonalność.

#### P: Czym ten samouczek różni się od poprzednich samouczków dotyczących obracania tekstu?

A: Ten samouczek łączy użycie fragmentów tekstu i akapitów, aby uzyskać obrót tekstu w dokumencie PDF. Pokazuje, jak obracać fragmenty tekstu indywidualnie, a następnie dodawać je do strony.`Paragraphs` kolekcja umożliwiająca uzyskanie bardziej kompleksowego efektu obrotu tekstu.

#### P: Jakie są zalety stosowania fragmentów tekstu i akapitów do obracania tekstu?

A: Używanie fragmentów tekstu i akapitów razem pozwala na większą elastyczność w rotacji tekstu. Fragmenty tekstu umożliwiają indywidualne ustawienia rotacji i formatowania, podczas gdy akapity zapewniają strukturę do układania i pozycjonowania fragmentów tekstu na stronie.

#### P: Czy mogę stosować różne kąty obrotu do różnych fragmentów tekstu w obrębie tego samego akapitu?

 A: Tak, można stosować różne kąty obrotu do różnych`TextFragment` obiektów w tym samym akapicie. Każdy fragment tekstu może mieć swój własny kąt obrotu określony za pomocą`TextState.Rotation` nieruchomość.

#### P: Czy stosując tę metodę można uzyskać złożone efekty obrotu tekstu?

O: Tak. Łącząc fragmenty tekstu z różnymi kątami obrotu i układając je w akapitach, można uzyskać złożone i niestandardowe efekty obrotu tekstu, zwiększając atrakcyjność wizualną dokumentów PDF.

#### P: Jakie kroki obejmuje obracanie tekstu za pomocą fragmentów tekstu i akapitów?

A: Kroki obejmują:

1. Konfigurowanie projektu poprzez utworzenie nowego projektu C# i dodanie odwołania do biblioteki Aspose.PDF dla .NET.
2. Tworzenie dokumentu PDF i dodawanie strony.
3. Tworzenie fragmentów tekstu, ustawianie ich właściwości i określanie kątów obrotu.
4.  Dodawanie fragmentów tekstu do strony za pomocą`Paragraphs` kolekcja.
5. Zapisywanie zmodyfikowanego dokumentu PDF.

#### P: Czy mogę zastosować obrót do całych akapitów?

 A: Tak, możesz zastosować obrót do całych akapitów, ustawiając`TextState.Rotation` właściwość samego akapitu. Spowoduje to obrócenie wszystkich fragmentów tekstu w obrębie tego akapitu.