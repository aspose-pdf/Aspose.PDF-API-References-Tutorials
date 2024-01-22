---
title: Ustaw właściwość objaśnienia w pliku PDF
linktitle: Ustaw właściwość objaśnienia w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić właściwość objaśnienia w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostosuj adnotacje za pomocą linii objaśnień, koloru tekstu i stylów końcowych.
type: docs
weight: 130
url: /pl/net/annotations/setcalloutproperty/
---
 Aspose.PDF dla .NET to potężna biblioteka do tworzenia, manipulowania i konwertowania dokumentów PDF w języku C#. Jedną z funkcji udostępnianych przez tę bibliotekę jest możliwość ustawienia właściwości objaśnień dla dowolnych adnotacji tekstowych w dokumentach PDF. Można tego dokonać za pomocą`FreeTextAnnotation` class, która umożliwia tworzenie adnotacji z objaśnieniami.

W tym samouczku przeprowadzimy Cię przez proces ustawiania właściwości objaśnień dla adnotacji tekstowej przy użyciu Aspose.PDF dla .NET w C#. Aby rozpocząć, wykonaj poniższe czynności.

## Zainstaluj Aspose.PDF dla .NET

 Jeśli jeszcze tego nie zrobiłeś, będziesz musiał to zrobić[pobierać](https://releases.aspose.com/pdf/net/) i zainstaluj Aspose.PDF dla .NET z wersji Aspose lub za pośrednictwem menedżera pakietów NuGet.

## Krok 1: Utwórz nowy dokument PDF

 Utwórz nowy dokument PDF za pomocą`Document`klasa dostarczona przez Aspose.PDF dla .NET.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Dodaj nową stronę do dokumentu

 Dodaj nową stronę do dokumentu za pomocą`Pages` zbiór`Document` klasa.

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Ustaw domyślny wygląd

 Ustaw domyślny wygląd adnotacji tekstowej, tworząc nową`DefaultAppearance` obiektu i ustawienie jego właściwości, takich jak`TextColor` I`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Krok 4: Utwórz dowolną adnotację tekstową z objaśnieniem

 Utwórz nową adnotację tekstową z objaśnieniem, korzystając z opcji`FreeTextAnnotation` klasa. Ustaw`Intent` własność do`FreeTextIntent.FreeTextCallout` aby określić, że jest to adnotacja objaśniająca. Ustaw`EndingStyle` własność do`LineEnding.OpenArrow` aby określić styl strzałki na końcu objaśnienia. Ustaw`Callout` właściwość do tablicy`Point` obiekty reprezentujące punkty na stronie, w których powinna zostać narysowana linia objaśnienia.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Krok 5: Dodaj dowolną adnotację tekstową do strony

 Dodaj dowolną adnotację tekstową do strony, używając opcji`Annotations` zbiór`Page` klasa.

```csharp
page.Annotations.Add(fta);
```

## Krok 6: Dodaj tekst do adnotacji

 Dodaj tekst do adnotacji, ustawiając opcję`RichText`właściwość na ciąg sformatowany XML. W tym samouczku ustawiamy kolor tekstu na czerwony i rozmiar czcionki na 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Krok 7: zapisz dokument

Teraz zapisz dokument, używając następującego kodu:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Przykładowy kod źródłowy dla Ustaw właściwość objaśnienia przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">To jest przykład</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Wniosek

tym samouczku omówiliśmy, jak ustawić właściwości objaśnień dla dowolnej adnotacji tekstowej w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Adnotacje objaśnień są przydatne do dostarczania dodatkowych informacji lub wyjaśnień związanych z określonymi obszarami dokumentu. Aspose.PDF dla .NET zapewnia szeroką gamę funkcji i możliwości pracy z plikami PDF, w tym tworzenie i dostosowywanie adnotacji, takich jak objaśnienia. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą z łatwością wdrożyć adnotacje w swoich dokumentach PDF, zwiększając użyteczność i przejrzystość swoich dokumentów. Aspose.PDF dla .NET to wszechstronna i niezawodna biblioteka do operacji PDF w aplikacjach .NET, oferująca potężne narzędzia do wydajnej obsługi różnych zadań związanych z plikami PDF.

### Często zadawane pytania dotyczące ustawiania właściwości objaśnień w pliku PDF

#### P: Co to jest adnotacja objaśniająca w dokumencie PDF?

Odp.: Adnotacja objaśniająca w dokumencie PDF to rodzaj adnotacji, który umożliwia utworzenie pola tekstowego z linią odniesienia wskazującą określony obszar w dokumencie. Jest powszechnie używany do podawania dodatkowych informacji lub komentarzy związanych z konkretną sekcją lub elementem dokumentu.

#### P: Czy mogę dostosować wygląd adnotacji objaśnienia za pomocą Aspose.PDF dla .NET?

O: Tak, możesz dostosować różne właściwości adnotacji objaśnienia, takie jak kolor, rozmiar czcionki, wyrównanie tekstu, styl linii, styl strzałki i inne.

#### P: Jak dodać tekst do adnotacji objaśnienia?

 O: Aby dodać tekst do adnotacji objaśnienia, możesz ustawić opcję`RichText` własność`FreeTextAnnotation` obiekt. The`RichText` Właściwość pobiera ciąg znaków w formacie XML reprezentujący tekst wyświetlany w adnotacji objaśnienia.

#### P: Czy mogę dodać wiele adnotacji objaśnień do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 Odp.: Tak, możesz utworzyć wiele adnotacji objaśnień w dokumencie PDF, tworząc wiele wystąpień pliku`FreeTextAnnotation`obiektu i dodając je do różnych stron lub lokalizacji w dokumencie.