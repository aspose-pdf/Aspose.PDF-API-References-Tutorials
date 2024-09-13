---
title: Dodaj obrócony tekst w pliku PDF za pomocą Java
linktitle: Dodaj obrócony tekst w pliku PDF za pomocą Java
second_title: Aspose.PDF Java PDF Processing API
description: Dowiedz się, jak wstawiać obrócony tekst do dokumentu PDF za pomocą Java. Postępuj zgodnie z tym szczegółowym przewodnikiem krok po kroku z przykładami kodu, aby ulepszyć swoje pliki PDF za pomocą obróconego tekstu.
type: docs
weight: 14
url: /pl/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## Wstęp

W tym kompleksowym samouczku zagłębimy się w proces dodawania obróconego tekstu do dokumentu PDF za pomocą Javy. Niezależnie od tego, czy musisz oznaczyć diagramy, utworzyć znaki wodne, czy dodać efekty specjalne do swoich plików PDF, ten przewodnik przeprowadzi Cię przez kolejne kroki. Użyjemy Aspose.PDF for Java, potężnej biblioteki do manipulacji plikami PDF, aby zademonstrować ten proces.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowana Java.

2.  Aspose.PDF dla Java: Pobierz i dołącz bibliotekę Aspose.PDF do swojego projektu Java. Link do pobrania znajdziesz[Tutaj](https://releases.aspose.com/pdf/java/).

## Krok 1: Utwórz nowy dokument PDF

Zacznijmy od utworzenia nowego dokumentu PDF za pomocą Aspose.PDF. Ten dokument będzie służył jako płótno dla naszego obróconego tekstu.

```java
// Zainicjuj dokument PDF
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## Krok 2: Dodaj stronę

Następnie dodaj stronę do dokumentu PDF, na której chcesz wstawić obrócony tekst:

```java
//Dodaj nową stronę do dokumentu
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## Krok 3: Zdefiniuj tekst obrócony

Teraz zdefiniujmy tekst, który chcesz wstawić i obrócić. Możesz dostosować tekst, czcionkę i kąt obrotu zgodnie ze swoimi wymaganiami:

```java
// Zdefiniuj zawartość tekstową
String text = "Rotated Text Example";

// Utwórz obiekt TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Ustaw rozmiar i styl czcionki
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Zdefiniuj kąt obrotu (w stopniach)
textFragment.setTextRotation(45);
```

W tym przykładzie ustawiliśmy tekst na „Przykład obróconego tekstu”, wybraliśmy czcionkę Arial, ustawiliśmy rozmiar czcionki na 12 i obróciliśmy tekst o 45 stopni. Dostosuj te parametry, aby dopasować je do swoich konkretnych wymagań.

## Krok 4: Umieść obrócony tekst

Określ położenie na stronie, w którym chcesz umieścić obrócony tekst:

```java
// Ustaw pozycję tekstu
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Tutaj umieściliśmy tekst na współrzędnych (100, 200) na stronie. Zmień te współrzędne, aby umieścić tekst dokładnie tam, gdzie go potrzebujesz.

## Krok 5: Dodaj obrócony tekst do strony

Teraz dodaj obrócony tekst do strony:

```java
// Dodaj obrócony tekst do strony
page.getParagraphs().add(textFragment);
```

## Krok 6: Zapisz plik PDF

Na koniec zapisz dokument PDF z obróconym tekstem:

```java
// Zapisz dokument PDF
pdfDocument.save("output.pdf");
```

## Wniosek

W tym samouczku zbadaliśmy proces dodawania obróconego tekstu do dokumentu PDF przy użyciu Java i Aspose.PDF dla Java. Nauczyłeś się, jak utworzyć nowy plik PDF, zdefiniować obrócony tekst za pomocą niestandardowych stylów, umieścić go na stronie i zapisać zmodyfikowany plik PDF.

Obrócony tekst może być cennym dodatkiem do plików PDF i może być wykorzystywany do różnych celów, np. do etykietowania diagramów, tworzenia znaków wodnych lub dodawania kreatywnych elementów do dokumentów.

Ulepsz swoje dokumenty PDF, z łatwością dodając obrócony tekst dzięki możliwościom Aspose.PDF dla Java.

---

## FAQ (najczęściej zadawane pytania)

### 1. Czy mogę obracać tekst pod różnymi kątami w tym samym pliku PDF?
   Tak, możesz dodać wiele wystąpień obróconego tekstu pod różnymi kątami do tego samego dokumentu PDF. Po prostu powtórz proces opisany w tym samouczku dla każdego fragmentu obróconego tekstu.

### 2. Jak mogę zmienić kolor obróconego tekstu?
    Aby zmienić kolor tekstu, użyj`textFragment.getTextState().setForegroundColor` i określ kolor w formacie RGB. Na przykład, aby ustawić kolor tekstu na czerwony, użyj`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Czy Aspose.PDF dla Java jest darmową biblioteką?
   Aspose.PDF for Java to potężna komercyjna biblioteka, ale oferuje bezpłatną wersję próbną do testowania i oceny. W zależności od wymagań projektu możesz wybrać odpowiednią opcję licencjonowania.

### 4. Czy mogę obrócić tekst o 90 stopni, aby utworzyć tekst pionowy?
   Tak, możesz obrócić tekst o 90 stopni, aby utworzyć tekst pionowy. Wystarczy ustawić kąt obrotu na 90 stopni, a tekst pojawi się pionowo na stronie.

### 5. Czy istnieją inne biblioteki do pracy z plikami PDF w Javie?
   Tak, kilka bibliotek, takich jak iText i PDFBox, jest dostępnych do manipulacji PDF w Javie. Każda biblioteka ma swoje unikalne funkcje i możliwości, więc wybierz tę, która najlepiej odpowiada potrzebom Twojego projektu.