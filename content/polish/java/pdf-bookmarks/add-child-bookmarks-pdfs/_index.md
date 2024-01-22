---
title: Dodaj zakładki podrzędne do plików PDF
linktitle: Dodaj zakładki podrzędne do plików PDF
second_title: Aspose.PDF Interfejs API przetwarzania plików Java w formacie Java
description: Dowiedz się, jak ulepszać dokumenty PDF za pomocą zakładek podrzędnych przy użyciu Aspose.PDF dla Java. Przewodnik krok po kroku z przykładami kodu ułatwiającymi nawigację i organizację.
type: docs
weight: 11
url: /pl/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Wprowadzenie do dodawania zakładek podrzędnych do plików PDF

W tym artykule przyjrzymy się, jak dodawać zakładki podrzędne do dokumentów PDF przy użyciu Aspose.PDF dla Java. Zakładki podrzędne to wygodny sposób organizowania i poruszania się po zawartości dokumentu PDF, ułatwiający użytkownikom znajdowanie określonych sekcji lub tematów w dokumencie.

## Warunki wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java zainstalowane w Twoim systemie.
-  Aspose.PDF dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/pdf/java/).

## Konfigurowanie środowiska

1. Pobierz bibliotekę Aspose.PDF dla Java, korzystając z podanego łącza.
2. Dodaj bibliotekę do swojego projektu Java.

Zacznijmy teraz od utworzenia nowego dokumentu PDF i krok po kroku dodawania do niego zakładek podrzędnych.

## Tworzenie nowego dokumentu PDF

Na początek musimy zainicjować dokument PDF i dodać do niego strony. Oto fragment kodu, od którego możesz zacząć:

```java
// Zainicjuj dokument PDF
Document pdfDocument = new Document();

// Dodaj strony do pliku PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

W tym przykładzie utworzyliśmy nowy dokument PDF i dodaliśmy do niego dwie strony.

## Dodawanie zakładek nadrzędnych

Zakładki nadrzędne służą jako główne sekcje lub kategorie w dokumencie PDF. Utwórzmy kilka zakładek nadrzędnych:

```java
// Utwórz zakładki nadrzędne
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Dodaliśmy dwie zakładki nadrzędne: „Zakładka nadrzędna 1” i „Zakładka nadrzędna 2”.

## Dodawanie zakładek podrzędnych

Teraz czas dodać zakładki podrzędne do zakładek nadrzędnych, które utworzyliśmy wcześniej. Zakładki podrzędne reprezentują określone tematy lub podsekcje w obrębie każdej zakładki nadrzędnej. Oto jak możesz to zrobić:

```java
// Dodaj zakładki podrzędne do zakładki nadrzędnej 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Dodaj zakładki podrzędne do zakładki nadrzędnej 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Dodaliśmy zakładki podrzędne zarówno do „Zakładki nadrzędnej 1”, jak i „Zakładki nadrzędnej 2”.

## Dostosowywanie wyglądu zakładek

Możesz dostosować wygląd zakładek, zmieniając ich tekst i styl. Dodatkowo możesz dodawać ikony do zakładek, aby uzyskać lepszą reprezentację wizualną. Oto przykład, jak to zrobić:

```java
// Dostosuj wygląd zakładki
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

W tym przykładzie ustawiliśmy zakładkę nadrzędną kursywą, zmieniliśmy kolor tekstu zakładki podrzędnej na zielony i dodaliśmy ikonę kursywy do zakładki podrzędnej.

## Obsługa zdarzeń

Z zakładkami mogą być także powiązane działania. Możesz na przykład dodać akcje uruchamiane, gdy użytkownik kliknie zakładkę. Oto jak możesz obsługiwać zdarzenia kliknięcia zakładki:

```java
// Dodaj akcję do zakładki
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

W tym kodzie dodaliśmy akcję „Przejdź do” do zakładki podrzędnej, która po kliknięciu przeniesie użytkownika na drugą stronę pliku PDF.

## Zapisywanie pliku PDF

Po dodaniu wszystkich niezbędnych zakładek i dostosowaniu ich wyglądu i działań możesz zapisać zmodyfikowany dokument PDF:

```java
// Zapisz dokument PDF
pdfDocument.save("output.pdf");
```

Twój dokument PDF z zakładkami podrzędnymi jest już gotowy.

## Kompletny kod źródłowy

Oto kompletny kod źródłowy umożliwiający dodawanie zakładek podrzędnych do dokumentu PDF przy użyciu Aspose.PDF dla Java:

```java
// Zainicjuj dokument PDF
Document pdfDocument = new Document();

// Dodaj strony do pliku PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Utwórz zakładki nadrzędne
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Dodaj zakładki podrzędne do zakładki nadrzędnej 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Dodaj zakładki podrzędne do zakładki nadrzędnej 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Dostosuj wygląd zakładki
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Dodaj akcję do zakładki
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Zapisz dokument PDF
pdfDocument.save("output.pdf");
```

## Wniosek

Dodawanie zakładek podrzędnych do plików PDF przy użyciu Aspose.PDF dla Java to potężna funkcja, która usprawnia nawigację i organizację dokumentów. Wykonując czynności opisane w tym artykule, możesz tworzyć dobrze zorganizowane pliki PDF z zakładkami nadrzędnymi i podrzędnymi, dostosowywać ich wygląd, a nawet dodawać akcje poprawiające wygodę użytkownika.

## Często zadawane pytania

### Jak mogę pobrać Aspose.PDF dla Java?

 Możesz pobrać Aspose.PDF dla Java ze strony internetowej[Tutaj](https://releases.aspose.com/pdf/java/).

### Czy zakładki podrzędne są obsługiwane we wszystkich przeglądarkach plików PDF?

Tak, zakładki podrzędne są obsługiwane w większości nowoczesnych przeglądarek plików PDF i zapewniają użytkownikowi lepszą nawigację po dokumentach PDF.

### Czy mogę bardziej dostosować wygląd zakładek?

Tak, możesz dostosować wygląd zakładek, dostosowując style tekstu, kolory i ikony do projektu dokumentu.

### Jakie inne akcje mogę dodać do zakładek?

Oprócz akcji „GoTo” możesz dodać akcje, takie jak akcje „URI” umożliwiające otwieranie łączy internetowych lub akcje „JavaScript” umożliwiające wykonywanie niestandardowych skryptów po kliknięciu zakładki.

### Czy Aspose.PDF dla Java nadaje się do projektów komercyjnych?

Tak, Aspose.PDF dla Java nadaje się zarówno do projektów osobistych, jak i komercyjnych i oferuje szeroką gamę funkcji do manipulowania i generowania plików PDF.