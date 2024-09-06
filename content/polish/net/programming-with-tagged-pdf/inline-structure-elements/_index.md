---
title: Elementy struktury liniowej
linktitle: Elementy struktury liniowej
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku dotyczący korzystania z elementów strukturalnych online z Aspose.PDF dla .NET. Organizuj swoje pliki PDF za pomocą nagłówków i akapitów.
type: docs
weight: 110
url: /pl/net/programming-with-tagged-pdf/inline-structure-elements/
---
tym przewodniku krok po kroku pokażemy Ci, jak używać elementów struktury inline z Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która pozwala programowo manipulować dokumentami PDF. Elementy struktury inline pozwalają Ci tworzyć hierarchiczną strukturę w Twoim dokumencie PDF, używając nagłówków różnych poziomów i akapitów.

Przyjrzyjmy się bliżej kodowi i dowiedzmy się, jak używać elementów struktury inline w Aspose.PDF dla platformy .NET.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

1. Zainstalowano bibliotekę Aspose.PDF dla .NET.
2. Podstawowa znajomość języka programowania C#.

## Krok 1: Konfigurowanie środowiska

Aby rozpocząć, otwórz środowisko programistyczne C# i utwórz nowy projekt. Upewnij się, że dodałeś odwołanie do biblioteki Aspose.PDF dla .NET w swoim projekcie.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Krok 5: Dodaj elementy konstrukcyjne online

Teraz dodamy do naszego dokumentu elementy struktury inline, takie jak nagłówki różnych poziomów i akapity.

```csharp
// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;

// Dodaj nagłówki różnych poziomów
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Dodaj treść do każdego nagłówka
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Dodaj akapit
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Dodaj treść do akapitu
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Tutaj tworzymy elementy struktury inline, takie jak nagłówki różnych poziomów i akapit, a następnie dodajemy do nich treść.

## Krok 6: Zapisz oznaczony dokument PDF

Na koniec zapisujemy oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Przykładowy kod źródłowy dla elementów struktury liniowej przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument PDF
Document document = new Document();

// Pobierz zawartość do pracy z TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Ustaw tytuł i język dla dokumentu
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Zapisz oznaczony dokument PDF
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak używać elementów struktury inline w Aspose.PDF dla .NET. Teraz możesz utworzyć hierarchiczną strukturę w swoim dokumencie PDF, używając nagłówków różnych poziomów i akapitów. Poznaj więcej funkcji Aspose.PDF, aby odkryć jego pełny potencjał.

### Najczęściej zadawane pytania

#### P: Czym są elementy struktury inline w dokumencie PDF i w jaki sposób przyczyniają się one do tworzenia struktury hierarchicznej?

A: Elementy struktury inline w dokumencie PDF, takie jak nagłówki różnych poziomów i akapity, służą do tworzenia struktury hierarchicznej, która organizuje i prezentuje treść w sposób ustrukturyzowany. Elementy te umożliwiają ustalenie jasnej hierarchii i przepływu informacji w dokumencie.

#### P: W jaki sposób elementy struktury inline mogą poprawić czytelność i organizację dokumentu PDF?

A: Elementy struktury inline, szczególnie nagłówki i akapity, pomagają poprawić czytelność i organizację dokumentu PDF, zapewniając logiczną strukturę. Nagłówki wskazują różne poziomy ważności i pomagają czytelnikom poruszać się po treści, podczas gdy akapity grupują powiązane informacje.

#### P: W jaki sposób Aspose.PDF dla .NET ułatwia korzystanie z elementów struktury inline?

A: Aspose.PDF dla .NET oferuje klasy i metody tworzenia i manipulowania elementami struktury inline, takimi jak nagłówki i akapity. Elementy te można dostosowywać, organizować hierarchicznie i wzbogacać o treść, aby poprawić prezentację wizualną i dostępność dokumentu.

####  P: Jaki jest cel`taggedContent` object in relation to inline structure elements?

 A: Ten`taggedContent` obiekt, uzyskany z`TaggedContent` własność`Document`, umożliwia pracę ze strukturalnymi elementami, w tym elementami struktury inline. Umożliwia tworzenie, dostosowywanie i organizowanie nagłówków i akapitów w dokumencie.

#### P: W jaki sposób elementy struktury inline pomagają w tworzeniu przejrzystej hierarchii dokumentu?

A: Elementy struktury inline, takie jak nagłówki o różnych poziomach, przyczyniają się do ustanowienia jasnej i dobrze zdefiniowanej hierarchii w dokumencie. Czytelnicy mogą szybko zidentyfikować główne tematy, podtematy i powiązane treści, dzięki czemu dokument jest łatwiejszy w nawigacji i zrozumieniu.

#### P: Czy mogę dostosować wygląd i formatowanie elementów struktury inline za pomocą Aspose.PDF dla .NET?

A: Tak, możesz dostosować wygląd i formatowanie elementów struktury inline. Możesz ustawić właściwości, takie jak style czcionek, rozmiary, kolory, wyrównanie, wcięcia i odstępy, aby uzyskać pożądaną prezentację wizualną nagłówków i akapitów.

#### P: W jaki sposób mogę tworzyć i dodawać nagłówki różnych poziomów do dokumentu PDF za pomocą elementów struktury inline w Aspose.PDF dla platformy .NET?

 A: Możesz tworzyć nagłówki różnych poziomów za pomocą`CreateHeaderElement` a następnie dołącz je do elementu struktury głównej. Następnie możesz dodać treść do każdego elementu nagłówka, używając`CreateSpanElement` metoda tworzenia przedziałów tekstu.

#### P: Czy mogę używać elementów struktury inline do tworzenia list, punktów wypunktowanych lub innych sposobów organizacji treści w dokumencie PDF?

O: Chociaż elementy struktury inline służą przede wszystkim do tworzenia nagłówków i akapitów, można ich używać w połączeniu z innymi funkcjami oferowanymi przez Aspose.PDF dla platformy .NET, aby tworzyć listy, punkty wypunktowane, tabele i inne typy organizacji treści w celu uzyskania kompleksowej struktury dokumentu.

#### P: W jaki sposób elementy struktury inline przyczyniają się do dostępności dokumentu?

A: Elementy struktury inline odgrywają kluczową rolę w zwiększaniu dostępności dokumentu. Prawidłowo ustrukturyzowane nagłówki i akapity zapewniają przejrzystą hierarchię dokumentu, która pomaga czytnikom ekranu i innym technologiom wspomagającym w dokładnym interpretowaniu i przekazywaniu treści użytkownikom niepełnosprawnym.

#### P: Czy mogę poznać bardziej zaawansowane zastosowania elementów struktury inline, np. tworzenie elementów interaktywnych lub osadzanie multimediów?

A: Oczywiście! Podczas gdy ten samouczek koncentruje się na tworzeniu nagłówków i akapitów, Aspose.PDF dla .NET oferuje zaawansowane funkcje do tworzenia interaktywnych elementów, osadzania multimediów, dodawania hiperłączy i nie tylko. Sprawdź dokumentację biblioteki i przykłady, aby zagłębić się w te zaawansowane możliwości.