---
title: Dodaj znacznik daty i godziny w pliku PDF
linktitle: Dodaj znacznik daty i godziny w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak łatwo dodać znacznik daty i godziny do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 10
url: /pl/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
tym artykule pokażemy Ci krok po kroku, jak dodać znacznik daty i godziny do pliku PDF za pomocą Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby dodać znacznik daty i godziny do istniejącego pliku PDF.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 1: Konfigurowanie środowiska

Zanim dodasz znacznik daty i godziny do dokumentu PDF, musisz skonfigurować środowisko programistyczne. Oto kroki, które należy wykonać:

1. Otwórz swoje ulubione IDE (zintegrowane środowisko programistyczne).
2. Utwórz nowy projekt C#.
3. Upewnij się, że dodałeś odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Dodawanie biblioteki Aspose.PDF

Biblioteka Aspose.PDF dla platformy .NET jest wymagana do pracy z dokumentami PDF w Twoim projekcie.

## Krok 3: Ładowanie dokumentu PDF

Pierwszym krokiem do dodania znacznika daty i godziny jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

## Krok 4: Tworzenie znacznika daty i godziny

Teraz, gdy przesłałeś dokument

  PDF, możesz utworzyć znacznik daty i godziny do dodania. Oto jak to zrobić:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Utwórz bufor tekstu
TextStamp textStamp = new TextStamp(annotationText);
```

Powyższy kod tworzy nowy bufor tekstowy zawierający bieżącą datę i godzinę.

## Krok 5: Konfigurowanie właściwości stempla

Przed dodaniem stempla do dokumentu PDF możesz skonfigurować różne właściwości stempla, takie jak margines, wyrównanie poziome i pionowe itp. Oto jak to zrobić:

```csharp
// Ustaw właściwości bufora
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Możesz dostosować te właściwości do swoich potrzeb.

## Krok 6: Dodaj znaczek do pliku PDF

Teraz, gdy znacznik daty i godziny jest gotowy, możesz dodać go do konkretnej strony dokumentu PDF. Oto jak to zrobić:

```csharp
// Dodaj znaczek do kolekcji znaczków na stronie
pdfDocument.Pages[1].AddStamp(textStamp);
```

Powyższy kod dodaje znaczek do pierwszej strony dokumentu PDF. W razie potrzeby możesz określić inną stronę.

## Krok 7: Zapisz dokument wyjściowy

Po dodaniu znacznika daty i godziny możesz zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
```

Powyższy kod zapisuje edytowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla funkcji Dodaj znacznik daty i godziny przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp(annotationText);

// Ustaw właściwości znaczka
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Dodawanie znaczka do kolekcji znaczków
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać znacznik daty i godziny za pomocą Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę w swoich projektach, aby dodać znaczniki daty i godziny do dokumentów PDF.

### Często zadawane pytania dotyczące dodawania znacznika daty i godziny do pliku PDF

#### P: Jaki jest cel dodawania znacznika daty i godziny do dokumentu PDF za pomocą Aspose.PDF dla platformy .NET?

A: Dodanie znacznika daty i godziny do dokumentu PDF zwiększa jego wartość informacyjną, wskazując, kiedy dokument został zmodyfikowany lub utworzony. Ta funkcja jest przydatna do śledzenia zmian w dokumencie i zapewniania punktu odniesienia dla historii dokumentu.

#### P: Czy mogę dostosować format znacznika daty i godziny do swoich konkretnych wymagań?

 A: Tak, możesz dostosować format znacznika daty i godziny zgodnie ze swoimi preferencjami. Dostarczony kod źródłowy C# używa`DateTime.Now.ToString()` metoda generowania znacznika czasu w określonym formacie. Możesz zmodyfikować ten kod, aby sformatować znacznik czasu według potrzeb.

#### P: Czy można dodać znacznik daty i godziny w określonym miejscu na stronie pliku PDF?

 O: Oczywiście, możesz dostosować położenie znacznika daty i godziny na stronie PDF, modyfikując właściwości`TextStamp` obiekt. Kod podany w samouczku pokazuje, jak ustawić właściwości, takie jak margines, wyrównanie i pozycjonowanie pionowe.

#### P: Czy mogę dodać wiele znaczników daty i godziny do różnych stron tego samego dokumentu PDF?

 A: Tak, możesz dodać wiele znaczników daty i godziny do różnych stron tego samego dokumentu PDF. Po prostu powtórz proces tworzenia`TextStamp` obiektu i konfigurowanie jego właściwości dla każdej żądanej strony.

#### P: Jak mogę zmienić czcionkę, rozmiar lub kolor tekstu znacznika daty i godziny?

 A: Aby zmienić czcionkę, rozmiar lub kolor tekstu znacznika daty i godziny, możesz dostosować właściwości`DefaultAppearance` obiekt użyty do utworzenia`TextStamp`. Dostosuj nazwę czcionki, jej rozmiar i wartości koloru, aby uzyskać pożądany wygląd.

#### P: Czy można dodawać inne typy adnotacji lub stempli do dokumentu PDF za pomocą Aspose.PDF dla platformy .NET?

A: Tak, Aspose.PDF dla .NET oferuje szeroki zakres typów adnotacji, które można dodawać do dokumentów PDF, w tym adnotacje tekstowe, stemple, linie, kształty i wiele innych. Więcej szczegółów na temat pracy z adnotacjami można znaleźć w dokumentacji Aspose.PDF.

#### P: Czy istnieją jakieś ograniczenia lub kwestie, które należy wziąć pod uwagę przy dodawaniu znacznika daty i godziny do dokumentu PDF?

A: Chociaż dodanie znacznika daty i godziny jest proste, weź pod uwagę takie czynniki, jak układ dokumentu i istniejąca zawartość. Upewnij się, że umiejscowienie znacznika nie przesłania ważnych informacji ani nie wpływa na czytelność dokumentu.

#### P: W jaki sposób mogę zintegrować tę metodę z własnymi projektami, aby dodawać znaczniki daty i godziny do dokumentów PDF?

A: Aby zintegrować tę metodę, wykonaj podane kroki i dostosuj kod do struktury swojego projektu. Możesz dodać znaczniki daty i godziny do istniejących dokumentów PDF, aby zwiększyć ich użyteczność i zapewnić jasną oś czasu zmian.

#### P: Czy mogę zautomatyzować proces dodawania znaczników daty i godziny do wielu dokumentów PDF?

O: Tak, możesz zautomatyzować proces dodawania znaczników daty i godziny do wielu dokumentów PDF, tworząc skrypt lub program, który przechodzi przez listę dokumentów i stosuje ten sam proces dodawania znaczników do każdego z nich.