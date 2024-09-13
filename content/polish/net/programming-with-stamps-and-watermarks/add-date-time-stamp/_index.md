---
title: Dodaj znacznik daty i godziny w pliku PDF
linktitle: Dodaj znacznik daty i godziny w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać znacznik daty i godziny do plików PDF za pomocą Aspose.PDF dla .NET dzięki temu przewodnikowi krok po kroku. Idealne do zwiększenia autentyczności dokumentów.
type: docs
weight: 10
url: /pl/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Wstęp

Jeśli chodzi o zarządzanie dokumentami, zwłaszcza plikami PDF, dodanie znacznika daty i godziny może być przełomem. Niezależnie od tego, czy pracujesz nad dokumentami prawnymi, raportami z projektów czy fakturami, znacznik czasu nie tylko dodaje autentyczności, ale także zapewnia wyraźny zapis tego, kiedy dokument został utworzony lub zmodyfikowany. W tym przewodniku przeprowadzimy Cię przez proces dodawania znacznika daty i godziny do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. 

Ten artykuł został zaprojektowany tak, aby był prosty i łatwy do zrozumienia, więc nawet jeśli jesteś nowicjuszem w programowaniu lub bibliotece Aspose.PDF, będziesz w stanie wdrożyć tę funkcję z pewnością siebie. Zanurzmy się!

## Wymagania wstępne

Zanim zaczniemy, musisz spełnić kilka warunków wstępnych:

1. Visual Studio: Upewnij się, że masz zainstalowany Visual Studio na swoim komputerze. Tutaj będziesz pisać i wykonywać swój kod.
2. Aspose.PDF dla .NET: Musisz pobrać i zainstalować bibliotekę Aspose.PDF. Najnowszą wersję znajdziesz[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć przykłady, ale nie martw się, jeśli dopiero zaczynasz – wyjaśnimy wszystko krok po kroku.
4.  Plik PDF: Przygotuj przykładowy plik PDF. W naszym przykładzie użyjemy pliku o nazwie`AddTextStamp.pdf`.

Gdy już spełnisz te wymagania wstępne, będziesz gotowy dodać znaczniki daty i godziny do swoich plików PDF!

## Importuj pakiety

Na początek musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Oto jak to zrobić:

### Utwórz nowy projekt

1. Otwórz program Visual Studio: Uruchom aplikację Visual Studio.
2. Utwórz nowy projekt: Wybierz opcję „Utwórz nowy projekt” na ekranie startowym.
3. Wybierz aplikację konsolową: Wybierz „Aplikacja konsolowa (.NET Framework)” z listy szablonów projektu.
4.  Nazwij swój projekt: Nadaj swojemu projektowi nazwę, na przykład:`PDFDateTimeStamp`.

### Dodaj odniesienie Aspose.PDF

1. Kliknij prawym przyciskiem myszy na Odwołania: W Eksploratorze rozwiązań kliknij prawym przyciskiem myszy folder „Odwołania” swojego projektu.
2. Wybierz „Dodaj odniesienie”: Wybierz „Dodaj odniesienie” z menu kontekstowego.
3. Przeglądaj Aspose.PDF: Przejdź do lokalizacji, w której pobrałeś Aspose.PDF i wybierz go. Kliknij „OK”, aby dodać go do swojego projektu.

### Importuj wymagane przestrzenie nazw

 Na szczycie twojego`Program.cs` plik, należy zaimportować następujące przestrzenie nazw:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Teraz, gdy wszystko już skonfigurowaliśmy, możemy podzielić proces dodawania znacznika daty i godziny do pliku PDF na jasne i łatwe do wykonania kroki.

## Krok 1: Ustaw katalog dokumentów

Najpierw musisz określić katalog, w którym znajduje się plik PDF. Jest to kluczowe, ponieważ kod będzie szukał pliku PDF w tym katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zastąp swoją rzeczywistą ścieżką
```

 Pamiętaj o wymianie`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką do pliku PDF.

## Krok 2: Otwórz dokument PDF

Następnie otwórz dokument PDF, do którego chcesz dodać znacznik czasu. 

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Ta linia kodu inicjuje`Document` klasa i ładuje plik PDF do`pdfDocument` obiekt.

## Krok 3: Utwórz znacznik daty i godziny

Teraz czas wygenerować znacznik daty i godziny. Sformatuj go, aby wyświetlał się w określony sposób. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Tutaj,`DateTime.Now` pobiera aktualną datę i godzinę, i`ToString` formatuje go do żądanego formatu.

## Krok 4: Utwórz stempel tekstowy

Mając już gotowy ciąg daty i godziny, możesz utworzyć znacznik tekstowy, który zostanie dodany do pliku PDF.

```csharp
// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp(annotationText);
```

 Ten wiersz tworzy nową instancję`TextStamp` używając sformatowanego ciągu daty i godziny.

## Krok 5: Ustaw właściwości znaczka

Możesz dostosować wygląd i położenie znaczka. Oto jak ustawić jego właściwości:

```csharp
// Ustaw właściwości znaczka
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

W tym kroku ustawiamy marginesy i wyrównujemy stempel do prawego dolnego rogu strony PDF.

## Krok 6: Dodaj znaczek do pliku PDF

Teraz czas dodać stempel tekstowy do dokumentu PDF. 

```csharp
// Dodawanie znaczka do kolekcji znaczków
pdfDocument.Pages[1].AddStamp(textStamp);
```

Ten wiersz dodaje znaczek do pierwszej strony pliku PDF. Możesz zmienić numer strony, jeśli chcesz umieścić go na innej stronie.

## Krok 7: Utwórz adnotację tekstową (opcjonalnie)

Jeśli chcesz dodać adnotację do znaczka, możesz utworzyć`FreeTextAnnotation` następująco:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Ten opcjonalny krok pozwala na utworzenie adnotacji w postaci dowolnego tekstu, która może zawierać dodatkowy kontekst lub informacje na temat znaczka.

## Krok 8: Skonfiguruj obramowanie adnotacji

Jeśli chcesz dostosować obramowanie swojej adnotacji, możesz to również zrobić:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Ten fragment kodu ustawia szerokość obramowania na 0, czyniąc je niewidocznym, i dodaje adnotację do pliku PDF.

## Krok 9: Zapisz dokument PDF

Na koniec należy zapisać zmodyfikowany dokument PDF. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Podaj nazwę pliku wyjściowego
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Ten wiersz zapisuje plik PDF z dodanym znacznikiem czasu do nowego pliku. Możesz sprawdzić swój określony katalog, aby zobaczyć wynik.

## Wniosek

Gratulacje! Udało Ci się dodać znacznik daty i godziny do pliku PDF za pomocą Aspose.PDF dla .NET. Ta prosta, ale skuteczna funkcja może ulepszyć Twoje dokumenty, czyniąc je bardziej profesjonalnymi i zapewniając wyraźny zapis tego, kiedy zostały utworzone lub zmodyfikowane. 

## Najczęściej zadawane pytania

### Czy mogę dostosować format daty w znaczniku czasu?
 Tak, możesz zmodyfikować`ToString`metoda zmiany formatu daty według własnych preferencji.

### Czy korzystanie z Aspose.PDF jest bezpłatne?
 Aspose.PDF oferuje bezpłatną wersję próbną, ale aby korzystać z pełnych funkcji, musisz kupić licencję. Możesz uzyskać tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).

### Czy mogę dodać wiele znaczników czasu do pliku PDF?
 Oczywiście! Możesz utworzyć wiele`TextStamp` wystąpienia i dodać je do różnych stron lub pozycji w pliku PDF.

### A co jeśli nie mam programu Visual Studio?
Możesz wykorzystać dowolne środowisko IDE języka C# lub edytor tekstu, ale do uruchamiania i debugowania projektu zaleca się korzystanie z programu Visual Studio.

### Gdzie mogę znaleźć więcej przykładów wykorzystania Aspose.PDF?
 Więcej przykładów i samouczków znajdziesz w[Dokumentacja Aspose.PDF](https://reference.aspose.com/pdf/net/).