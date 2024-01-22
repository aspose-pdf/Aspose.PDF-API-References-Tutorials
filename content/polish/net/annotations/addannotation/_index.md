---
title: Dodaj adnotację PDF
linktitle: Dodaj adnotację
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać tekstowe adnotacje PDF za pomocą Aspose.PDF dla .NET, używając tego kodu źródłowego C#. Dostosuj swoje adnotacje, dodając określone szczegóły i ikony.
type: docs
weight: 10
url: /pl/net/annotations/addannotation/
---
Dodawanie adnotacji do dokumentów PDF to zaawansowana funkcja, która może usprawnić procesy współpracy i recenzji. Aspose.PDF dla .NET ułatwia programowe dodawanie adnotacji do dokumentów PDF przy użyciu języka C#. W tym przewodniku wyjaśnimy krok po kroku, jak używać Aspose.PDF dla .NET do dodawania adnotacji do dokumentu PDF.

## Krok 1: Utwórz nowy projekt i zainstaluj Aspose.PDF dla .NET

Zanim zaczniemy pisać kod do dodawania adnotacji, musimy stworzyć nowy projekt i zainstalować Aspose.PDF dla .NET. Aby zainstalować Aspose.PDF dla .NET, wykonaj następujące kroki:

1. Otwórz program Visual Studio i utwórz nowy projekt C#.
2. Kliknij projekt prawym przyciskiem myszy w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i wybierz „Zainstaluj”.

Po zakończeniu instalacji możemy przystąpić do pisania kodu.

## Krok 2: Otwórz dokument PDF

Pierwszym krokiem dodawania adnotacji jest otwarcie dokumentu PDF. Do otwarcia dokumentu możemy użyć następującego kodu:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

W tym kodzie określamy ścieżkę do dokumentu PDF, który chcemy otworzyć. Pamiętaj, aby zastąpić „TWÓJ KATALOG DANYCH” rzeczywistą ścieżką do katalogu danych.

## Krok 3: Utwórz adnotację

 Aby dodać adnotację, musimy utworzyć nową instancję pliku`TextAnnotation` klasa. Możemy użyć następującego kodu, aby utworzyć nową adnotację tekstową:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

W tym kodzie tworzymy nową adnotację tekstową na drugiej stronie dokumentu PDF. Ustawiamy także tytuł, temat, stan, zawartość, otwarcie i właściwości ikony adnotacji.

## Krok 4: Dostosuj adnotację

 Możemy dostosować wygląd adnotacji za pomocą`Border` klasa. Możemy użyć następującego kodu, aby dostosować obramowanie adnotacji:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 W tym kodzie tworzymy nowy`Border`obiekt i ustaw jego właściwości szerokości i kreski. Następnie ustawiamy`Border` właściwość adnotacji do nowego`Border` obiekt. Na koniec ustawiamy`Rect` właściwość adnotacji, aby określić jej położenie i rozmiar.

## Krok 5: Dodaj adnotację do dokumentu PDF

Po utworzeniu i dostosowaniu adnotacji musimy dodać ją do dokumentu PDF. Aby dodać adnotację do dokumentu PDF, możemy użyć następującego kodu:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

W tym kodzie dodajemy adnotację do kolekcji adnotacji na drugiej stronie dokumentu PDF.

## Krok 6: Zapisz plik wyjściowy

Na koniec musimy zapisać dokument PDF z dodaną adnotacją. Możemy użyć następującego kodu, aby zapisać plik wyjściowy:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Przykładowy kod źródłowy dodawania adnotacji przy użyciu Aspose.PDF dla .NET


```csharp   
 // Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DATA DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Utwórz adnotację
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Dodaj adnotację w kolekcji adnotacji na stronie
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Zapisz plik wyjściowy
pdfDocument.Save(dataDir);
```
Ten kod pokazuje, jak dodać adnotację tekstową z określonym tytułem, tematem, stanem, zawartością i ikoną do strony PDF przy użyciu Aspose.PDF dla .NET. Możesz zmodyfikować ten kod zgodnie ze swoimi wymaganiami dotyczącymi dodawania adnotacji do dokumentów PDF. Pamiętaj tylko o zastąpieniu KATALOGU DANYCH rzeczywistą ścieżką katalogu, w którym znajduje się plik PDF i gdzie chcesz zapisać plik wyjściowy.

## Wniosek

Dodawanie adnotacji do dokumentów PDF za pomocą Aspose.PDF dla .NET oferuje cenne narzędzie usprawniające współpracę nad dokumentami i procesy recenzowania. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym artykule, programiści mogą bezproblemowo integrować funkcje adnotacji z aplikacjami C#.

### Często zadawane pytania

#### P: Jakie typy adnotacji można dodać za pomocą Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET obsługuje różne typy adnotacji, w tym adnotacje tekstowe, znaczki, łącza, kształty i inne. Programiści mogą dostosować wygląd i właściwości tych adnotacji do swoich konkretnych potrzeb.

#### P: Czy mogę dodać adnotacje do określonych stron wielostronicowego dokumentu PDF?

O: Tak, Aspose.PDF dla .NET pozwala określić stronę, na której chcesz dodać adnotację. W razie potrzeby możesz wybrać konkretną stronę lub dodać adnotacje do wielu stron.

#### P: Jak dostosować wygląd adnotacji?

Odp.: Adnotacje można dostosowywać za pomocą takich właściwości, jak szerokość obramowania, kolor, styl kreski, styl tekstu i inne. Aspose.PDF dla .NET zapewnia bogaty zestaw opcji umożliwiających dostosowanie wyglądu adnotacji.

#### P: Czy można dodawać hiperłącza jako adnotacje przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, możesz dodawać hiperłącza jako adnotacje do dokumentów PDF przy użyciu Aspose.PDF dla .NET. Adnotacji hiperłączy można używać do tworzenia łączy do zewnętrznych adresów URL lub określonych lokalizacji w tym samym dokumencie.

#### P: Czy można dodawać adnotacje do istniejących dokumentów PDF bez zmiany oryginalnej zawartości?

O: Tak, Aspose.PDF dla .NET dodaje adnotacje jako dodatkowe elementy bez zmiany oryginalnej zawartości dokumentu PDF. Oryginalna zawartość pliku PDF pozostaje nienaruszona.