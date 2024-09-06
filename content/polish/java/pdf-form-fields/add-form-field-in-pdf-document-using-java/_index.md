---
title: Dodaj pole formularza w dokumencie PDF za pomocą Java
linktitle: Dodaj pole formularza w dokumencie PDF za pomocą Java
second_title: Aspose.PDF Java PDF Processing API
description: Dowiedz się, jak dodawać interaktywne pola formularzy do dokumentów PDF za pomocą Java i Aspose.PDF dla Java. Twórz przyjazne dla użytkownika formularze PDF z łatwością.
type: docs
weight: 10
url: /pl/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## Wstęp

Dodawanie pól formularza do dokumentu PDF zwiększa jego funkcjonalność, umożliwiając użytkownikom wprowadzanie danych bezpośrednio do dokumentu. Może to być niezwykle przydatne w różnych celach, takich jak tworzenie formularzy do wypełnienia, ankiet lub raportów z treścią generowaną przez użytkowników.

Będziemy używać Aspose.PDF dla Java, potężnej biblioteki, która upraszcza manipulację PDF w aplikacjach Java. Dzięki Aspose.PDF możesz łatwo tworzyć, modyfikować i manipulować dokumentami PDF, w tym dynamicznie dodawać pola formularzy.

## Konfigurowanie środowiska

Zanim zagłębimy się w kod, musisz skonfigurować środowisko programistyczne. Wykonaj następujące kroki:

1.  Pobierz Aspose.PDF dla Java: Odwiedź witrynę Aspose i pobierz najnowszą wersję Aspose.PDF dla Java. Możesz ją znaleźć[Tutaj](https://releases.aspose.com/pdf/java/).

2. Zainstaluj Aspose.PDF: Po pobraniu zainstaluj Aspose.PDF, postępując zgodnie z instrukcjami instalacji podanymi na stronie internetowej.

3. Utwórz projekt Java: Utwórz nowy projekt Java w preferowanym zintegrowanym środowisku programistycznym (IDE) i dołącz do niego bibliotekę Aspose.PDF.

## Tworzenie nowego dokumentu PDF

Zacznijmy od utworzenia nowego dokumentu PDF. W tym przykładzie utworzymy prosty plik PDF z tytułem i kilkoma instrukcjami.

```java
// Importuj bibliotekę Aspose.PDF
import com.aspose.pdf.*;

public class AddFormFieldPDF {
    public static void main(String[] args) {
        // Utwórz nowy dokument PDF
        Document doc = new Document();

        // Dodaj stronę do dokumentu
        Page page = doc.getPages().add();

        // Dodaj nagłówek
        TextFragment title = new TextFragment("Feedback Form");
        title.getTextState().setFontSize(18);
        title.getTextState().setFont(FontRepository.findFont("Arial"));
        page.getParagraphs().add(title);

        // Dodaj instrukcje
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // Zapisz dokument do pliku
        doc.save("FeedbackForm.pdf");
    }
}
```

tym fragmencie kodu tworzymy nowy dokument PDF, dodajemy stronę, wstawiamy nagłówek i kilka instrukcji.

## Dodawanie pól formularza

Teraz przejdźmy do dodawania pól formularza do naszego dokumentu PDF. Dołączymy pola tekstowe, pola wyboru i przyciski radiowe, aby utworzyć interaktywny formularz opinii.

### Pola tekstowe

Pola tekstowe pozwalają użytkownikom na wprowadzanie tekstu. Oto jak możesz dodać pole tekstowe:

```java
// Utwórz pole tekstowe
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // Ustaw styl obramowania
textField.setPartialName("txtName"); // Ustaw nazwę pola
textField.setMultiline(false); // Wyłącz wieloliniowość
page.getAnnotations().add(textField);
```

### Pola wyboru

Pola wyboru są używane do opcji binarnych (np. pytania typu tak/nie). Oto jak dodać pole wyboru:

```java
// Utwórz pole wyboru
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // Ustaw nazwę pola
checkboxField.setChecked(false); // Początkowo niezaznaczone
page.getAnnotations().add(checkboxField);
```

### Przyciski radiowe

Przyciski radiowe są używane, gdy użytkownicy muszą wybrać jedną opcję z grupy. Każda opcja jest oddzielnym przyciskiem radiowym, ale należą do tej samej grupy. Oto jak dodać przyciski radiowe:

```java
// Utwórz przyciski radiowe
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // Ustaw nazwę pola dla opcji 1
option2.setPartialName("optNo"); // Ustaw nazwę pola dla opcji 2

//Dodaj opcje do grupy przycisków radiowych
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

Za pomocą tych przykładów kodu możesz dodać pola tekstowe, pola wyboru i przyciski radiowe do dokumentu PDF. Upewnij się, że dostosowujesz ich właściwości w razie potrzeby, takie jak nazwy pól i wartości domyślne.

## Dostosowywanie pól formularza

Dostosowywanie pól formularza pozwala kontrolować ich wygląd i zachowanie. Możesz zmieniać właściwości, takie jak rozmiar czcionki, kolor tekstu, styl obramowania i inne.

### Zmiana właściwości pola

Załóżmy, że chcesz zmienić rozmiar czcionki i kolor tekstu pola tekstowego:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### Walidacja pola

Możesz również ustawić reguły walidacji dla pól formularza. Na przykład możesz wymagać od użytkowników wprowadzenia prawidłowego adresu e-mail w polu tekstowym:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## Ustawianie wartości pól

Aby wstępnie wypełnić pola formularza danymi, możesz ustawić ich wartości domyślne programowo. Jest to przydatne do tworzenia szablonów lub wstępnego wypełniania znanych informacji.

```java
textField.setValue("John Doe"); // Ustaw wartość domyślną dla pola tekstowego
checkboxField.setChecked(true); // Zaznacz pole wyboru domyślnie
```

## Wysyłanie i walidacja formularza

Dodanie pól formularza to tylko połowa sukcesu. Będziesz także potrzebować

 aby umożliwić przesyłanie formularzy i ich sprawdzanie.

### Złożenie formularza

Aby umożliwić użytkownikom przesyłanie danych formularza, musisz określić działanie, takie jak wysłanie wiadomości e-mail lub przesłanie do serwera WWW. Oto przykład, jak skonfigurować przycisk przesyłania:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit", SubmitFormActionType.URL, "FeedbackForm.pdf"));
page.getAnnotations().add(submitButton);
```

### Walidacja formularza

Walidacja zapewnia, że dane wejściowe użytkownika spełniają określone kryteria. Na przykład możesz zweryfikować pole numeru telefonu, aby akceptowało tylko cyfry:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## Zapisywanie i eksportowanie

Po utworzeniu i dostosowaniu dokumentu PDF za pomocą pól formularza nadszedł czas na jego zapisanie lub wyeksportowanie. Aspose.PDF udostępnia różne opcje w tym celu.

### Zapisz do pliku lokalnego

Aby zapisać dokument PDF w pliku lokalnym, użyj następującego kodu:

```java
doc.save("FeedbackForm.pdf");
```

### Zapisz do strumienia

 Aby zapisać dokument PDF do strumienia, możesz użyć`OutputStream` klasa:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## Wniosek

tym kompleksowym przewodniku przyjrzeliśmy się sposobowi dodawania pól formularza do dokumentu PDF przy użyciu Java i Aspose.PDF dla Java. Nauczyłeś się, jak tworzyć pola tekstowe, pola wyboru i przyciski radiowe, dostosowywać ich właściwości, ustawiać wartości domyślne, włączać przesyłanie i walidację formularza oraz zapisywać/eksportować dokument PDF.

## Często zadawane pytania

### Jak mogę utworzyć listę rozwijaną w formularzu PDF?

 Aby utworzyć listę rozwijaną (pole kombi) w formularzu PDF, możesz użyć`ComboBoxField` klasa dostarczona przez Aspose.PDF dla Java. Postępuj podobnie jak w przypadku innych pól formularza i dostosuj opcje za pomocą`AddItem` metoda. Szczegółową dokumentację na ten temat można znaleźć na stronie internetowej Aspose.

### Czy Aspose.PDF for Java jest kompatybilny z innymi bibliotekami i frameworkami Java?

Tak, Aspose.PDF for Java jest kompatybilny z różnymi bibliotekami i frameworkami Java. Możesz zintegrować go ze swoimi aplikacjami Java, niezależnie od tego, czy używasz Spring, JavaFX, czy innych popularnych frameworków. Upewnij się, że sprawdziłeś dokumentację i zasoby, aby uzyskać szczegółowe wytyczne dotyczące integracji.

### Czy mogę zabezpieczyć hasłem formularz PDF utworzony za pomocą Aspose.PDF dla Java?

Oczywiście! Aspose.PDF for Java pozwala dodać ochronę hasłem do dokumentów PDF, w tym formularzy. Możesz ustawić hasła na poziomie użytkownika i właściciela, aby ograniczyć dostęp i uprawnienia. Zapoznaj się z dokumentacją, aby uzyskać szczegółowe instrukcje dotyczące implementacji tej funkcji bezpieczeństwa.

### Jak mogę wyodrębnić dane przesłane za pomocą formularza PDF?

Aby wyodrębnić dane przesłane za pomocą formularza PDF, musisz obsłużyć przesłanie formularza na serwerze lub w zapleczu aplikacji. Gdy użytkownik prześle formularz, możesz odebrać dane i przetworzyć je w razie potrzeby. Aspose.PDF udostępnia narzędzia do programowego wyodrębniania danych formularza z dokumentu PDF po stronie serwera.

### Czy mogę dynamicznie generować formularze PDF na podstawie danych wprowadzonych przez użytkownika?

Tak, możesz dynamicznie generować formularze PDF na podstawie danych wejściowych użytkownika, używając Aspose.PDF dla Java. W zależności od danych wejściowych użytkownika lub logiki aplikacji możesz tworzyć dokumenty PDF z różnymi polami formularzy i układami. Ta elastyczność umożliwia generowanie niestandardowych formularzy dostosowanych do konkretnych potrzeb lub scenariuszy użytkownika.