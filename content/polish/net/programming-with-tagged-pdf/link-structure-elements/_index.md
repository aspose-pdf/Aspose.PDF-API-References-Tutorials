---
title: Elementy struktury linków
linktitle: Elementy struktury linków
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku dotyczący korzystania z elementów struktury linków w Aspose.PDF dla .NET. Twórz hiperłącza w dokumentach PDF.
type: docs
weight: 120
url: /pl/net/programming-with-tagged-pdf/link-structure-elements/
---
W tym przewodniku krok po kroku pokażemy Ci, jak używać elementów struktury linków z Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która pozwala programowo tworzyć i manipulować dokumentami PDF. Elementy struktury linków pozwalają Ci dodawać hiperłącza do dokumentu PDF, umożliwiając użytkownikom klikanie łączy i nawigowanie do zasobów online.

Przyjrzyjmy się bliżej kodowi i dowiedzmy się, jak używać elementów struktury linków w Aspose.PDF dla platformy .NET.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

1. Zainstalowano bibliotekę Aspose.PDF dla .NET.
2. Podstawowa znajomość języka programowania C#.

## Krok 1: Konfigurowanie środowiska

Aby rozpocząć, otwórz środowisko programistyczne C# i utwórz nowy projekt. Upewnij się, że dodałeś odwołanie do biblioteki Aspose.PDF dla .NET w swoim projekcie.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Krok 2: Tworzenie dokumentu

 Pierwszym krokiem jest utworzenie nowego dokumentu PDF przy użyciu`Document` klasa.

```csharp
// Utwórz dokument PDF
Document document = new Document();
```

## Krok 3: Praca z oznaczoną treścią

Następnie otrzymujemy oznaczoną zawartość dokumentu, z którą możemy pracować.

```csharp
// Pobierz oznaczoną zawartość dokumentu
ITaggedContent taggedContent = document.TaggedContent;
```

## Krok 4: Ustaw tytuł i język dokumentu

Teraz możemy ustawić tytuł i język dokumentu.

```csharp
// Zdefiniuj tytuł i język dokumentu
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Krok 5: Dodaj elementy struktury linków

Teraz dodajmy elementy struktury linków do naszego dokumentu. Utworzymy różne typy linków, w tym proste linki tekstowe, linki do obrazów i linki wielowierszowe.
```csharp
// Pobierz element struktury głównej (element struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;

// Dodaj akapit z hiperłączem
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Dodaj akapit z hiperłączem zawierającym bogaty tekst
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Dodaj akapit z hiperłączem zawierającym częściowo sformatowany tekst
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Dodaj akapit z hiperłączem wielowierszowym
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Dodaj akapit z hiperłączem zawierającym obraz
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Krok 6: Zapisz oznaczony dokument PDF

Na koniec zapisujemy oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document. Save(outFile);
```

## Krok 7: Sprawdź zgodność PDF/UA

 Możemy również sprawdzić zgodność dokumentu z PDF/UA, korzystając z`Validate` metoda`Document` klasa.

```csharp
// Sprawdź zgodność PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Przykładowy kod źródłowy dla elementów struktury linków przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Dokument tworzenia i uzyskiwania oznaczonych treści PDF
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Ustawianie tytułu i języka natury dla dokumentu
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Pobieranie elementu struktury głównej (element struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Zapisz oznaczony dokument PDF
document.Save(outFile);

// Sprawdzanie zgodności PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Wniosek

Gratulacje! Nauczyłeś się, jak używać elementów struktury linków w Aspose.PDF dla .NET. Teraz możesz tworzyć hiperłącza w dokumentach PDF, umożliwiając użytkownikom nawigację do zasobów online. Eksperymentuj i odkrywaj więcej funkcji Aspose.PDF, aby tworzyć interaktywne i wzbogacone dokumenty PDF.

### Najczęściej zadawane pytania

#### P: Czym są elementy struktury linków w dokumencie PDF i w jaki sposób zwiększają one interaktywność dokumentu?

A: Elementy struktury linków w dokumencie PDF służą do tworzenia hiperłączy, które umożliwiają użytkownikom nawigację do zasobów online lub określonych lokalizacji w dokumencie. Elementy te zwiększają interaktywność, zapewniając klikalne łącza, które umożliwiają użytkownikom dostęp do powiązanych treści lub zewnętrznych witryn internetowych.

#### P: W jaki sposób elementy struktury linków mogą być przydatne w dokumencie PDF?

A: Elementy struktury linków poprawiają wrażenia użytkownika, czyniąc dokument PDF interaktywnym. Zapewniają szybki dostęp do dodatkowych informacji, powiązanych treści, zewnętrznych stron internetowych lub określonych sekcji w dokumencie, usprawniając nawigację i ułatwiając wyszukiwanie informacji.

#### P: Czy w pliku Aspose.PDF dla platformy .NET mogę tworzyć różne typy hiperłączy, używając elementów struktury łączy?

A: Tak, możesz tworzyć różne typy hiperłączy, używając elementów struktury linków. Aspose.PDF dla .NET umożliwia tworzenie hiperłączy z tekstem zwykłym, tekstem sformatowanym, obrazami i opisami wielowierszowymi, oferując wszechstronność w sposobie łączenia się z treścią zewnętrzną lub lokalizacjami w dokumencie.

#### P: Jak skonfigurować i zainicjować elementy struktury łączy w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

 A: Aby użyć elementów struktury linków, najpierw musisz utworzyć nowy dokument PDF, korzystając z`Document` klasa. Następnie uzyskaj oznaczoną zawartość za pomocą`TaggedContent`właściwość dokumentu. Stamtąd możesz tworzyć i dostosowywać elementy struktury linków i dodawać je do elementu struktury głównej.

#### P: W jaki sposób mogę utworzyć prosty hiperłącze tekstowe, używając elementów struktury linków?
 A: Możesz utworzyć prosty hiperłącze tekstowe, tworząc`LinkElement` i ustawiając jego`Hyperlink` nieruchomość do`WebHyperlink` z adresem URL, do którego chcesz linkować. Możesz również ustawić tekst wyświetlany linku, używając`SetText` metoda.

#### P: Czy można tworzyć hiperłącza z obrazami używając elementów struktury linków?

 A: Tak, możesz tworzyć hiperłącza z obrazami, używając elementów struktury linków. Utworzyłbyś`LinkElement` a następnie dodaj`FigureElement` z obrazem. Pozwala to na utworzenie hiperłącza opartego na obrazie.

#### P: Jak mogę mieć pewność, że mój dokument PDF zawierający hiperłącza jest zgodny ze standardem dostępności PDF/UA?

 A: Aspose.PDF dla platformy .NET umożliwia sprawdzenie zgodności dokumentu PDF ze standardem PDF/UA przy użyciu`Validate` metoda`Document`Klasa. Zapewnia to, że hiperłącza dokumentu są dostępne dla użytkowników niepełnosprawnych.

#### P: Jakie są alternatywne opisy elementów struktury linków i dlaczego są ważne?

A: Alternatywne opisy (alt text) dla elementów struktury linków zapewniają tekstowe opisy hiperłączy. Te opisy są niezbędne dla dostępności, pozwalając użytkownikom z wadami wzroku zrozumieć cel linku i jego miejsce docelowe.

#### P: Czy mogę dostosować wygląd i zachowanie hiperłączy utworzonych za pomocą elementów struktury linków?

A: Podczas gdy elementy struktury linków skupiają się głównie na tworzeniu hiperłączy, możesz dostosować wygląd i zachowanie hiperłączy dalej, korzystając z innych funkcji oferowanych przez Aspose.PDF dla .NET. Obejmuje to określanie kolorów, stylów i akcji linków.

#### P: W jaki sposób elementy struktury linków przyczyniają się do tego, że dokumenty PDF są bardziej interaktywne i przyjazne dla użytkownika?

A: Elementy struktury linków przekształcają statyczne dokumenty PDF w interaktywne doświadczenia poprzez dodawanie klikalnych hiperłączy. Ta interaktywność poprawia zaangażowanie użytkownika, umożliwia płynną nawigację między powiązanymi treściami i zwiększa ogólną użyteczność dokumentu.