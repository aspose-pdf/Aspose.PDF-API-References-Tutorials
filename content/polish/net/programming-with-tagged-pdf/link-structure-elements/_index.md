---
title: Elementy struktury łącza
linktitle: Elementy struktury łącza
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący używania elementów struktury łącza w Aspose.PDF dla .NET. Twórz hiperłącza w dokumentach PDF.
type: docs
weight: 120
url: /pl/net/programming-with-tagged-pdf/link-structure-elements/
---
W tym przewodniku krok po kroku pokażemy, jak używać elementów struktury łączy w Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która pozwala programowo tworzyć i manipulować dokumentami PDF. Elementy struktury łączy umożliwiają dodawanie hiperłączy do dokumentu PDF, umożliwiając użytkownikom klikanie łączy i nawigację do zasobów online.

Zagłębmy się w kod i nauczmy się używać elementów struktury łączy w Aspose.PDF dla .NET.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Zainstalowana biblioteka Aspose.PDF dla .NET.
2. Podstawowa znajomość języka programowania C#.

## Krok 1: Konfigurowanie środowiska

Aby rozpocząć, otwórz środowisko programistyczne C# i utwórz nowy projekt. Upewnij się, że w swoim projekcie dodałeś odniesienie do biblioteki Aspose.PDF dla .NET.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Krok 2: Tworzenie dokumentu

 Pierwszym krokiem jest utworzenie nowego dokumentu PDF za pomocą`Document` klasa.

```csharp
// Utwórz dokument PDF
Document document = new Document();
```

## Krok 3: Pracuj z oznakowaną treścią

Następnie otrzymujemy otagowaną treść dokumentu, z którą możemy pracować.

```csharp
// Pobierz oznaczoną treść dokumentu
ITaggedContent taggedContent = document.TaggedContent;
```

## Krok 4: Ustaw tytuł i język dokumentu

Możemy teraz ustawić tytuł i język dokumentu.

```csharp
// Zdefiniuj tytuł i język dokumentu
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Krok 5: Dodaj elementy struktury łącza

Dodajmy teraz do naszego dokumentu elementy struktury linków. Stworzymy różne typy linków, w tym proste linki tekstowe, linki graficzne i linki wielowierszowe.
```csharp
// Uzyskaj element struktury głównej (element struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;

// Dodaj akapit z hiperłączem
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Dodaj akapit z hiperłączem zawierającym tekst sformatowany
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Dodaj akapit z hiperłączem zawierającym częściowo sformatowany tekst
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Dodaj akapit z wielowierszowym hiperłączem
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Dodaj akapit z hiperłączem zawierającym obraz
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
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

## Krok 7: Sprawdź zgodność z PDF/UA

 Możemy również sprawdzić dokument pod kątem zgodności z PDF/UA za pomocą pliku`Validate` metoda`Document` klasa.

```csharp
// Sprawdź zgodność z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Przykładowy kod źródłowy elementów struktury łącza przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Tworzenie dokumentu i pobieranie oznaczonej zawartości PDF
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Ustawianie tytułu i języka natury dokumentu
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Pobieranie elementu struktury root (element struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
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
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
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

// Sprawdzanie zgodności z PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Wniosek

Gratulacje! Nauczyłeś się, jak używać elementów struktury łączy w Aspose.PDF dla .NET. Teraz możesz tworzyć hiperłącza w dokumentach PDF, umożliwiając użytkownikom nawigację do zasobów online. Eksperymentuj i odkrywaj więcej funkcji Aspose.PDF, aby tworzyć interaktywne i wzbogacone dokumenty PDF.

### Często zadawane pytania

#### P: Czym są elementy struktury łączy w dokumencie PDF i w jaki sposób poprawiają interaktywność dokumentu?

Odp.: Elementy struktury łączy w dokumencie PDF służą do tworzenia hiperłączy umożliwiających użytkownikom nawigację do zasobów online lub określonych lokalizacji w dokumencie. Elementy te zwiększają interaktywność, udostępniając klikalne linki, które umożliwiają użytkownikom dostęp do powiązanych treści lub zewnętrznych stron internetowych.

#### P: W jaki sposób elementy struktury łączy mogą być przydatne w dokumencie PDF?

Odp.: Elementy struktury linków poprawiają wygodę użytkownika, czyniąc dokument PDF interaktywnym. Zapewniają szybki dostęp do dodatkowych informacji, powiązanych treści, zewnętrznych stron internetowych czy określonych sekcji dokumentu, usprawniając nawigację i ułatwiając wyszukiwanie informacji.

#### P: Czy mogę tworzyć różne typy hiperłączy, używając elementów struktury łączy w Aspose.PDF dla .NET?

Odp.: Tak, możesz tworzyć różne typy hiperłączy, korzystając z elementów struktury linków. Aspose.PDF dla .NET umożliwia tworzenie hiperłączy zawierających zwykły tekst, tekst sformatowany, obrazy i opisy wielowierszowe, oferując wszechstronność w sposobie łączenia z treściami zewnętrznymi lub lokalizacjami w dokumencie.

#### P: Jak skonfigurować i zainicjować elementy struktury łączy w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

 Odp.: Aby użyć elementów struktury linków, musisz najpierw utworzyć nowy dokument PDF za pomocą`Document` klasa. Następnie uzyskaj otagowaną treść za pomocą`TaggedContent`własność dokumentu. Stamtąd możesz tworzyć i dostosowywać elementy struktury łączy oraz dodawać je do głównego elementu struktury.

#### P: Jak mogę utworzyć proste hiperłącze tekstowe przy użyciu elementów struktury łącza?
 Odp.: Możesz utworzyć proste hiperłącze tekstowe, tworząc plik`LinkElement` i ustawienie jego`Hyperlink` własność A`WebHyperlink` z adresem URL, do którego chcesz utworzyć łącze. Możesz także ustawić wyświetlany tekst łącza za pomocą`SetText` metoda.

#### P: Czy możliwe jest tworzenie hiperłączy z obrazami przy użyciu elementów struktury linków?

 Odp.: Tak, możesz tworzyć hiperłącza z obrazami, korzystając z elementów struktury linków. Stworzyłbyś`LinkElement` a następnie dołącz a`FigureElement` z obrazem. Umożliwia to utworzenie hiperłącza opartego na obrazie.

#### P: Jak mogę się upewnić, że mój dokument PDF z hiperłączami jest zgodny ze standardem dostępności PDF/UA?

 Odp.: Aspose.PDF dla .NET umożliwia sprawdzenie zgodności dokumentu PDF ze standardem PDF/UA przy użyciu`Validate` metoda`Document`klasa. Dzięki temu hiperłącza zawarte w dokumencie będą dostępne dla użytkowników niepełnosprawnych.

#### P: Jakie są alternatywne opisy elementów struktury łącza i dlaczego są one ważne?

Odp.: Opisy alternatywne (tekst alternatywny) elementów struktury linków zapewniają tekstowe opisy hiperłączy. Opisy te są niezbędne dla dostępności, umożliwiając użytkownikom z wadami wzroku zrozumienie celu łącza i jego miejsca docelowego.

#### P: Czy mogę dostosować wygląd i zachowanie hiperłączy utworzonych przy użyciu elementów struktury linków?

Odp.: Chociaż elementy struktury łączy skupiają się głównie na tworzeniu hiperłączy, możesz dodatkowo dostosować wygląd i zachowanie hiperłączy, korzystając z innych funkcji oferowanych przez Aspose.PDF dla .NET. Obejmuje to określanie kolorów, stylów i działań na łączach.

#### P: W jaki sposób elementy struktury łączy przyczyniają się do uczynienia dokumentów PDF bardziej interaktywnymi i przyjaznymi dla użytkownika?

Odp.: Elementy struktury łączy przekształcają statyczne dokumenty PDF w interaktywne doświadczenia, dodając klikalne hiperłącza. Ta interaktywność poprawia zaangażowanie użytkownika, umożliwia płynną nawigację pomiędzy powiązanymi treściami i zwiększa ogólną użyteczność dokumentu.