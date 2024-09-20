---
title: Elementy struktury linków
linktitle: Elementy struktury linków
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak tworzyć elementy struktury linków w pliku PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący dodawania dostępnych linków, obrazów i walidacji zgodności.
type: docs
weight: 120
url: /pl/net/programming-with-tagged-pdf/link-structure-elements/
---
## Wstęp

Tworzenie i zarządzanie elementami struktury linków w pliku PDF może mieć kluczowe znaczenie dla dokumentów wymagających dostępności i płynnej nawigacji. W tym samouczku przeprowadzimy Cię przez proces wykonywania tego przy użyciu Aspose.PDF dla .NET. Jeśli jesteś nowy w Aspose.PDF lub ogólnie w manipulowaniu plikami PDF, nie martw się. Wyjaśnię każdy krok szczegółowo, abyś mógł łatwo śledzić!

## Wymagania wstępne  

Zanim zagłębimy się w kodowanie, najpierw wyjaśnijmy kilka spraw. Oto podstawowe wymagania, które zapewnią płynne środowisko programistyczne.

1.  Aspose.PDF dla .NET: Możesz pobrać najnowszą wersję[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne .NET: Niezależnie od tego, czy jest to Visual Studio, czy dowolne środowisko IDE zgodne z platformą .NET, należy je zainstalować i mieć je gotowe.
3.  Licencja Aspose: Możesz korzystać z bezpłatnej wersji próbnej Aspose.PDF[Tutaj](https://releases.aspose.com/) lub nabyć[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).
4. Podstawowa wiedza o języku C#: Będziemy pracować z kodem w języku C#, dlatego zrozumienie podstaw znacznie ułatwi sprawę.

## Importuj pakiety

Musisz zaimportować kilka pakietów przed napisaniem kodu dla elementów struktury linków. Zacznij od odwołania się do niezbędnych bibliotek Aspose.PDF w swoim projekcie:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dzięki importom możemy pracować z dokumentami PDF, dodawać tagi i zarządzać elementami struktury.

Teraz utworzymy dokument PDF z różnymi typami struktur linków. Każdy krok zostanie rozbity na części, aby pomóc Ci w pełnym zrozumieniu procesu.

## Krok 1: Zainicjuj dokument  

Zacznijmy od utworzenia nowego dokumentu PDF i skonfigurowania oznaczonych treści pod kątem ułatwień dostępu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Utwórz nowy dokument PDF
Document document = new Document(); 

// Pobierz interfejs TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Tutaj inicjujemy`Document` obiekt, który reprezentuje nasz plik PDF. Pobieramy również`TaggedContent` interfejs umożliwiający dodawanie elementów struktury, takich jak akapity, linki i obrazy.

## Krok 2: Ustaw tytuł i język  

Każdy plik PDF powinien mieć tytuł i ustawienia języka, zwłaszcza jeśli zależy Ci na zgodności ze standardami PDF/UA.

```csharp
// Ustaw tytuł i język dokumentu
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Ten krok zapewnia, że Twój plik PDF ma znaczący tytuł i ustawia język na angielski (`en-US`). Jest to krytyczne dla dostępności i zapewnia, że czytniki ekranu lub inne technologie wspomagające będą mogły poprawnie interpretować Twój dokument.

## Krok 3: Tworzenie i dodawanie akapitów  

W tym kroku dodamy akapity zawierające elementy linków.

```csharp
// Utwórz element główny
StructureElement rootElement = taggedContent.RootElement;

// Utwórz akapit i dodaj go do elementu głównego
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Tworzymy element struktury głównej, który jest zasadniczo kontenerem najwyższego poziomu dla wszystkich innych elementów. Następnie tworzymy akapit (`p1`) i dodaj go do elementu głównego.

## Krok 4: Dodaj prosty link  

Teraz dodajmy podstawowy hiperłącze kierujące do Google.

```csharp
// Utwórz element linku i dodaj go do akapitu
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Ustaw hiperłącze i tekst dla łącza
link1.Hyperlink = new WebHyperlink("http://");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
tym kroku utworzyliśmy element linku, ustawiliśmy jego hiperłącze na „http://google.com” i podaliśmy tekst („Google”) dla linku. Dodaliśmy również alternatywny opis, aby zapewnić dostępność.

## Krok 5: Dodawanie łącza z rozpiętościami  

Możemy również tworzyć linki o różnej długości tekstu.

```csharp
// Utwórz kolejny akapit
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Utwórz łącze z elementem span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Tutaj użyliśmy elementu span, aby umieścić część tekstu wewnątrz linku, co pozwoliło nam dostosować sposób wyświetlania poszczególnych fragmentów linku.

## Krok 6: Łącze wieloliniowe  

Co jeśli tekst Twojego linku jest za długi? Nie martw się, możesz podzielić go na wiele wierszy.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
W tym przypadku utworzyliśmy łącze wielowierszowe, po prostu ustawiając długą wartość tekstową, a tekst automatycznie zawinie się w wiele wierszy.

## Krok 7: Dodaj obraz do linku  

Można także dodawać obrazy wewnątrz linku.

```csharp
// Utwórz nowy akapit i element łącza
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://");

// Dodaj obraz do linku
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Ten krok pokazuje, jak możesz ulepszyć swoje linki za pomocą obrazu. W tym przypadku dodaliśmy ikonę Google wewnątrz linku. Zapewniliśmy również dostępność, ustawiając alternatywny tekst dla obrazu.

## Krok 8: Sprawdź zgodność pliku PDF  

Jeśli zależy Ci na zgodności dokumentu ze standardem PDF/UA (standardem dostępności), warto go zweryfikować.

```csharp
// Zapisz dokument PDF
document.Save(outFile);

// Sprawdź zgodność dokumentu ze standardem PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Zapisaliśmy dokument i sprawdziliśmy jego zgodność ze standardem PDF/UA, co gwarantuje, że plik PDF spełnia wymagania dotyczące dostępności.

## Wniosek  

W tym samouczku omówiliśmy, jak tworzyć ustrukturyzowane dokumenty PDF przy użyciu Aspose.PDF dla .NET. Od dodawania podstawowych hiperłączy do bardziej złożonych struktur, takich jak spans, łącza wielowierszowe, a nawet obrazy, ten przewodnik zapewnia solidne podstawy do manipulowania elementami linków w plikach PDF. Dzięki dodatkowej korzyści zgodności z PDF/UA jesteś teraz wyposażony, aby tworzyć dostępne i łatwe do nawigacji pliki PDF.

## Najczęściej zadawane pytania

### Czy mogę dodać bardziej złożone struktury, np. tabele, wewnątrz linków?  
Nie, linki służą głównie do przechowywania tekstu i obrazów, ale w ich pobliżu można osadzać złożone elementy.

### Czy walidacja PDF/UA jest obowiązkowa?  
Nie zawsze, ale jest to zdecydowanie zalecane, jeśli martwisz się o dostępność.

### Co się stanie, jeśli ścieżka do pliku obrazu będzie nieprawidłowa?  
Dokument nie wyświetli obrazu i może wystąpić błąd podczas renderowania.

### Czy mogę stylizować tekst w linku?  
Tak, można stosować style tekstu za pomocą elementów span.

### Czy można tworzyć wewnętrzne linki do dokumentów?  
Oczywiście! Możesz linkować do konkretnych sekcji w tym samym dokumencie.