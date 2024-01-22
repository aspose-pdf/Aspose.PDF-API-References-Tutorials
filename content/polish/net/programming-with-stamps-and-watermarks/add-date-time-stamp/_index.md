---
title: Dodaj znacznik daty i godziny w pliku PDF
linktitle: Dodaj znacznik daty i godziny w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak łatwo dodać znacznik daty i godziny do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
tym artykule przeprowadzimy Cię krok po kroku, jak dodać znacznik daty i godziny do pliku PDF przy użyciu Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby dodać znacznik daty i godziny do istniejącego pliku PDF.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 1: Konfigurowanie środowiska

Zanim będzie można dodać sygnaturę daty i godziny do dokumentu PDF, należy skonfigurować środowisko programistyczne. Oto kroki, które należy wykonać:

1. Otwórz swoje ulubione IDE (zintegrowane środowisko programistyczne).
2. Utwórz nowy projekt C#.
3. Upewnij się, że dodałeś odniesienie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Dodanie biblioteki Aspose.PDF

Do pracy z dokumentami PDF w Twoim projekcie wymagana jest biblioteka Aspose.PDF dla .NET.

## Krok 3: Ładowanie dokumentu PDF

Pierwszym krokiem do dodania znacznika daty i godziny jest załadowanie istniejącego dokumentu PDF do projektu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

## Krok 4: Tworzenie znacznika daty i godziny

Teraz, gdy przesłałeś dokument

  PDF, możesz utworzyć znacznik daty i godziny, aby go dodać. Oto jak to zrobić:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Utwórz bufor tekstowy
TextStamp textStamp = new TextStamp(annotationText);
```

Powyższy kod tworzy nowy bufor tekstowy zawierający bieżącą datę i godzinę.

## Krok 5: Konfiguracja właściwości stempla

Przed dodaniem stempla do dokumentu PDF możesz skonfigurować różne właściwości stempla, takie jak margines, wyrównanie w poziomie i pionie itp. Oto jak to zrobić:

```csharp
// Ustaw właściwości bufora
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Możesz dostosować te właściwości do swoich potrzeb.

## Krok 6: Dodaj stempel do pliku PDF

Teraz, gdy znacznik daty i godziny jest już gotowy, możesz dodać go do określonej strony dokumentu PDF. Oto jak:

```csharp
// Dodaj znaczek do kolekcji znaczków strony
pdfDocument.Pages[1].AddStamp(textStamp);
```

Powyższy kod dodaje stempel do pierwszej strony dokumentu PDF. W razie potrzeby możesz określić inną stronę.

## Krok 7: Zapisz dokument wyjściowy

Po dodaniu znacznika daty i godziny możesz zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy dla Dodaj znacznik czasu i daty przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Utwórz stempel tekstowy
TextStamp textStamp = new TextStamp(annotationText);

// Ustaw właściwości stempla
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Dodanie znaczka do kolekcji znaczków
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

Gratulacje! Nauczyłeś się, jak dodać znacznik daty i godziny przy użyciu Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę we własnych projektach, aby dodać znaczniki daty i godziny do dokumentów PDF.

### Często zadawane pytania dotyczące dodawania znacznika daty i godziny w pliku PDF

#### P: Jaki jest cel dodawania znacznika daty i godziny do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Dodanie sygnatury daty i godziny do dokumentu PDF zwiększa jego wartość informacyjną, wskazując, kiedy dokument został zmodyfikowany lub utworzony. Ta funkcja jest przydatna do śledzenia zmian w dokumencie i zapewniania punktu odniesienia dla historii dokumentu.

#### P: Czy mogę dostosować format znacznika daty i godziny, aby odpowiadał konkretnym wymaganiom?

 Odp.: Tak, możesz dostosować format znacznika daty i godziny zgodnie ze swoimi preferencjami. Dostarczony kod źródłowy C# używa`DateTime.Now.ToString()` metoda generowania znacznika czasu w określonym formacie. Możesz zmodyfikować ten kod, aby sformatować znacznik czasu zgodnie z potrzebami.

#### P: Czy można dodać znacznik daty i godziny w określonym miejscu na stronie PDF?

 O: Oczywiście możesz dostosować położenie znacznika daty i godziny na stronie PDF, modyfikując właściwości pliku`TextStamp` obiekt. Kod podany w samouczku pokazuje, jak ustawić właściwości, takie jak margines, wyrównanie i położenie w pionie.

#### P: Czy mogę dodać wiele znaczników daty i godziny do różnych stron tego samego dokumentu PDF?

 Odp.: Tak, możesz dodać wiele znaczników daty i godziny do różnych stron tego samego dokumentu PDF. Po prostu powtórz proces tworzenia pliku`TextStamp` obiekt i konfigurowanie jego właściwości dla każdej żądanej strony.

#### P: Jak mogę zmienić czcionkę, rozmiar lub kolor tekstu znacznika daty i godziny?

 O: Aby zmodyfikować czcionkę, rozmiar lub kolor tekstu znacznika daty i godziny, możesz dostosować właściwości pliku`DefaultAppearance` obiekt używany do tworzenia`TextStamp`. Dostosuj nazwę czcionki, rozmiar i wartości kolorów, aby uzyskać pożądany wygląd.

#### P: Czy można dodać inne typy adnotacji lub stempli do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, Aspose.PDF dla .NET zapewnia szeroką gamę typów adnotacji, które można dodawać do dokumentów PDF, w tym adnotacje tekstowe, stemple, linie, kształty i inne. Dalsze szczegóły dotyczące pracy z adnotacjami można znaleźć w dokumentacji Aspose.PDF.

#### P: Czy istnieją jakieś ograniczenia lub uwagi dotyczące dodawania znacznika daty i godziny do dokumentu PDF?

O: Chociaż dodanie sygnatury daty i godziny jest proste, należy wziąć pod uwagę takie czynniki, jak układ dokumentu i istniejąca zawartość. Upewnij się, że umieszczenie stempla nie zasłania ważnych informacji i nie wpływa na czytelność dokumentu.

#### P: Jak mogę zintegrować tę metodę z moimi własnymi projektami, aby dodać znaczniki daty i godziny do dokumentów PDF?

O: Aby zintegrować tę metodę, postępuj zgodnie z podanymi krokami i dostosuj kod tak, aby pasował do struktury projektu. Do istniejących dokumentów PDF można dodawać znaczniki daty i godziny, aby zwiększyć ich użyteczność i zapewnić przejrzysty harmonogram zmian.

#### P: Czy mogę zautomatyzować proces dodawania znaczników daty i godziny do wielu dokumentów PDF?

O: Tak, możesz zautomatyzować proces dodawania znaczników daty i godziny do wielu dokumentów PDF, tworząc skrypt lub program, który przegląda listę dokumentów i stosuje ten sam proces stemplowania w przypadku każdego z nich.