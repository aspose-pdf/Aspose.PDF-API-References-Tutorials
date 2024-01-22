---
title: Dodaj obrócony tekst w formacie PDF przy użyciu języka Java
linktitle: Dodaj obrócony tekst w formacie PDF przy użyciu języka Java
second_title: Aspose.PDF Interfejs API przetwarzania plików Java w formacie Java
description: Dowiedz się, jak wstawić obrócony tekst do dokumentu PDF przy użyciu języka Java. Postępuj zgodnie z tym szczegółowym przewodnikiem krok po kroku z przykładami kodu, aby wzbogacić swoje pliki PDF o obrócony tekst.
type: docs
weight: 14
url: /pl/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## Wstęp

W tym obszernym samouczku zagłębimy się w proces dodawania obróconego tekstu do dokumentu PDF za pomocą języka Java. Niezależnie od tego, czy chcesz oznaczyć diagramy etykietami, utworzyć znaki wodne czy dodać efekty specjalne do plików PDF, ten przewodnik przeprowadzi Cię przez kolejne kroki. Aby zademonstrować proces, użyjemy Aspose.PDF dla Java, potężnej biblioteki do manipulacji plikami PDF.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Środowisko programistyczne Java: Upewnij się, że masz zainstalowaną Javę w swoim systemie.

2.  Aspose.PDF dla Java: Pobierz i dołącz bibliotekę Aspose.PDF do swojego projektu Java. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/pdf/java/).

## Krok 1: Utwórz nowy dokument PDF

Zacznijmy od utworzenia nowego dokumentu PDF przy użyciu Aspose.PDF. Dokument ten posłuży jako płótno dla obróconego tekstu.

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

## Krok 3: Zdefiniuj obrócony tekst

Teraz zdefiniujmy tekst, który chcesz wstawić i obrócić. Możesz dostosować tekst, czcionkę i kąt obrotu zgodnie ze swoimi wymaganiami:

```java
// Zdefiniuj treść tekstu
String text = "Rotated Text Example";

// Utwórz obiekt TextFragment
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Ustaw rozmiar i styl czcionki
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Zdefiniuj kąt obrotu (w stopniach)
textFragment.setTextRotation(45);
```

W tym przykładzie ustawiliśmy tekst na „Przykład obróconego tekstu”, wybraliśmy czcionkę Arial, ustawiliśmy rozmiar czcionki na 12 i obróciliśmy tekst o 45 stopni. Dostosuj te parametry, aby odpowiadały Twoim konkretnym wymaganiom.

## Krok 4: Ustaw obrócony tekst

Określ pozycję na stronie, w której chcesz umieścić obrócony tekst:

```java
// Ustaw położenie tekstu
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Tutaj umieściliśmy tekst pod współrzędnymi (100, 200) na stronie. Zmodyfikuj te współrzędne, aby umieścić tekst dokładnie tam, gdzie jest potrzebny.

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

W tym samouczku omówiliśmy proces dodawania obróconego tekstu do dokumentu PDF przy użyciu języka Java i Aspose.PDF dla języka Java. Wiesz już, jak utworzyć nowy plik PDF, zdefiniować obrócony tekst za pomocą niestandardowych stylów, umieścić go na stronie i zapisać zmodyfikowany plik PDF.

Obrócony tekst może być cennym dodatkiem do plików PDF do różnych celów, takich jak diagramy etykiet, znak wodny lub dodawanie kreatywnych elementów do dokumentów.

Ulepsz swoje dokumenty PDF, z łatwością dodając obrócony tekst, dzięki możliwościom Aspose.PDF dla Java.

---

## Często zadawane pytania (często zadawane pytania)

### 1. Czy mogę obracać tekst pod różnymi kątami w tym samym pliku PDF?
   Tak, możesz dodać wiele wystąpień obróconego tekstu pod różnymi kątami do tego samego dokumentu PDF. Po prostu powtórz proces opisany w tym samouczku dla każdego obróconego tekstu.

### 2. Jak mogę zmienić kolor obróconego tekstu?
    Aby zmienić kolor tekstu, użyj opcji`textFragment.getTextState().setForegroundColor` metodę i określ kolor w formacie RGB. Na przykład, aby ustawić kolor tekstu na czerwony, użyj`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Czy Aspose.PDF dla Java jest bezpłatną biblioteką?
   Aspose.PDF dla Java to potężna biblioteka komercyjna, ale oferuje bezpłatną wersję próbną do testowania i oceny. W zależności od wymagań Twojego projektu możesz wybrać odpowiednią opcję licencjonowania.

### 4. Czy mogę obrócić tekst o 90 stopni, aby utworzyć tekst pionowy?
   Tak, możesz obrócić tekst o 90 stopni, aby utworzyć tekst pionowy. Wystarczy ustawić kąt obrotu na 90 stopni, a tekst na stronie pojawi się pionowo.

### 5. Czy istnieją inne biblioteki do pracy z plikami PDF w Javie?
   Tak, do manipulacji plikami PDF w Javie dostępnych jest kilka bibliotek, takich jak iText i PDFBox. Każda biblioteka ma swoje unikalne funkcje i możliwości, więc wybierz tę, która najlepiej odpowiada potrzebom Twojego projektu.