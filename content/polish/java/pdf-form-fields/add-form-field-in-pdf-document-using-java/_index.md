---
title: Dodaj pole formularza w dokumencie PDF przy użyciu Java
linktitle: Dodaj pole formularza w dokumencie PDF przy użyciu Java
second_title: Aspose.PDF Interfejs API przetwarzania plików Java w formacie Java
description: Dowiedz się, jak dodawać interaktywne pola formularzy do dokumentów PDF przy użyciu języka Java i Aspose.PDF dla języka Java. Z łatwością twórz przyjazne dla użytkownika formularze PDF.
type: docs
weight: 10
url: /pl/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## Wstęp

Dodanie pól formularza do dokumentu PDF zwiększa jego funkcjonalność, umożliwiając użytkownikom wprowadzanie danych bezpośrednio do dokumentu. Może to być niezwykle przydatne do różnych celów, takich jak tworzenie formularzy do wypełnienia, ankiet lub raportów z treścią generowaną przez użytkowników.

Będziemy używać Aspose.PDF dla Java, potężnej biblioteki, która upraszcza manipulowanie plikami PDF w aplikacjach Java. Dzięki Aspose.PDF możesz łatwo tworzyć, modyfikować i manipulować dokumentami PDF, w tym dynamicznie dodawać pola formularzy.

## Konfigurowanie środowiska

Zanim zagłębimy się w kod, musisz skonfigurować środowisko programistyczne. Wykonaj następujące kroki:

1.  Pobierz Aspose.PDF dla Java: Odwiedź witrynę Aspose i pobierz najnowszą wersję Aspose.PDF dla Java. Możesz to znaleźć[Tutaj](https://releases.aspose.com/pdf/java/).

2. Zainstaluj Aspose.PDF: Po pobraniu zainstaluj Aspose.PDF, postępując zgodnie z instrukcjami instalacji podanymi na stronie internetowej.

3. Utwórz projekt Java: Utwórz nowy projekt Java w preferowanym zintegrowanym środowisku programistycznym (IDE) i dołącz do swojego projektu bibliotekę Aspose.PDF.

## Tworzenie nowego dokumentu PDF

Zacznijmy od utworzenia nowego dokumentu PDF. W tym przykładzie utworzymy prosty plik PDF z tytułem i instrukcjami.

```java
// Zaimportuj bibliotekę Aspose.PDF
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

tym fragmencie kodu tworzymy nowy dokument PDF, dodajemy stronę i wstawiamy nagłówek oraz kilka instrukcji.

## Dodawanie pól formularza

Przejdźmy teraz do dodania pól formularza do naszego dokumentu PDF. Dołączymy pola tekstowe, pola wyboru i przyciski opcji, aby utworzyć interaktywny formularz opinii.

### Pola tekstowe

Pola tekstowe umożliwiają użytkownikom wprowadzanie tekstu. Oto jak dodać pole tekstowe:

```java
// Utwórz pole tekstowe
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // Ustaw styl obramowania
textField.setPartialName("txtName"); // Ustaw nazwę pola
textField.setMultiline(false); // Wyłącz multilinię
page.getAnnotations().add(textField);
```

### Pola wyboru

Pola wyboru są używane w przypadku opcji binarnych (np. pytania tak/nie). Oto jak dodać pole wyboru:

```java
// Utwórz pole wyboru
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // Ustaw nazwę pola
checkboxField.setChecked(false); // Początkowo niezaznaczone
page.getAnnotations().add(checkboxField);
```

### Przyciski radiowe

Przyciski opcji są używane, gdy użytkownicy muszą wybrać jedną opcję z grupy. Każda opcja jest oddzielnym przyciskiem opcji, ale należą one do tej samej grupy. Oto jak dodać przyciski opcji:

```java
// Utwórz przyciski radiowe
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // Ustaw nazwę pola dla opcji 1
option2.setPartialName("optNo"); // Ustaw nazwę pola dla opcji 2

//Dodaj opcje do grupy przycisków opcji
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

Za pomocą tych przykładów kodu możesz dodawać pola tekstowe, pola wyboru i przyciski opcji do dokumentu PDF. Pamiętaj, aby w razie potrzeby dostosować ich właściwości, takie jak nazwy pól i wartości domyślne.

## Dostosowywanie pól formularza

Dostosowywanie pól formularza pozwala kontrolować ich wygląd i zachowanie. Możesz zmieniać właściwości, takie jak rozmiar czcionki, kolor tekstu, styl obramowania i inne.

### Zmiana właściwości pola

Załóżmy, że chcesz zmienić rozmiar czcionki i kolor tekstu w polu tekstowym:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### Walidacja pola

Możesz także ustawić reguły sprawdzania poprawności pól formularza. Na przykład możesz wymagać od użytkowników wprowadzenia prawidłowego adresu e-mail w polu tekstowym:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## Ustawianie wartości pól

Aby wstępnie wypełnić pola formularza danymi, możesz programowo ustawić ich wartości domyślne. Jest to przydatne do tworzenia szablonów lub wstępnego wypełniania znanych informacji.

```java
textField.setValue("John Doe"); // Ustaw wartość domyślną dla pola tekstowego
checkboxField.setChecked(true); // Zaznacz pole wyboru domyślnie
```

## Wysłanie i zatwierdzenie formularza

Dodawanie pól formularzy to tylko połowa historii; ty też będziesz chciał

 aby umożliwić przesłanie i zatwierdzenie formularza.

### Przesyłanie formularza

Aby umożliwić użytkownikom przesyłanie danych z formularza, musisz określić akcję, taką jak wysłanie wiadomości e-mail lub przesłanie na serwer WWW. Oto przykład konfiguracji przycisku przesyłania:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit”, SubmitFormActionType.URL, „FeedbackForm.pdf”));
page.getAnnotations().add(submitButton);
```

### Walidacja formularza

Walidacja zapewnia, że dane wejściowe użytkownika spełniają określone kryteria. Na przykład możesz zweryfikować pole numeru telefonu, aby akceptować tylko numery:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## Zapisywanie i eksportowanie

Po utworzeniu i dostosowaniu dokumentu PDF za pomocą pól formularza nadszedł czas, aby go zapisać lub wyeksportować. Aspose.PDF zapewnia różne opcje w tym zakresie.

### Zapisz w pliku lokalnym

Aby zapisać dokument PDF w pliku lokalnym, użyj następującego kodu:

```java
doc.save("FeedbackForm.pdf");
```

### Zapisz w strumieniu

 Aby zapisać dokument PDF w strumieniu, możesz użyć metody`OutputStream` klasa:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## Wniosek

tym obszernym przewodniku omówiliśmy, jak dodawać pola formularzy do dokumentu PDF przy użyciu języka Java i Aspose.PDF dla języka Java. Wiesz już, jak tworzyć pola tekstowe, pola wyboru i przyciski opcji, dostosowywać ich właściwości, ustawiać wartości domyślne, umożliwiać przesyłanie i sprawdzanie poprawności formularzy oraz zapisywać/eksportować dokument PDF.

## Często zadawane pytania

### Jak skonfigurować listę rozwijaną w formularzu PDF?

 Aby utworzyć listę rozwijaną (pole kombi) w formacie PDF, możesz skorzystać z opcji`ComboBoxField` klasa dostarczona przez Aspose.PDF dla Java. Postępuj podobnie, jak pokazano w przypadku innych pól formularza i dostosuj opcje za pomocą`AddItem` metoda. Szczegółową dokumentację na ten temat można znaleźć na stronie internetowej Aspose.

### Czy Aspose.PDF dla Java jest kompatybilny z innymi bibliotekami i frameworkami Java?

Tak, Aspose.PDF dla Java jest kompatybilny z różnymi bibliotekami i frameworkami Java. Możesz zintegrować go z aplikacjami Java, niezależnie od tego, czy używasz Springa, JavaFX, czy innych popularnych frameworków. Pamiętaj, aby sprawdzić dokumentację i zasoby, aby uzyskać szczegółowe wytyczne dotyczące integracji.

### Czy mogę zabezpieczyć hasłem formularz PDF utworzony za pomocą Aspose.PDF dla Java?

Absolutnie! Aspose.PDF dla Java umożliwia dodanie ochrony hasłem do dokumentów PDF, w tym formularzy. Możesz ustawić hasła na poziomie użytkownika i właściciela, aby ograniczyć dostęp i uprawnienia. Szczegółowe instrukcje dotyczące implementowania tej funkcji zabezpieczeń można znaleźć w dokumentacji.

### Jak mogę wyodrębnić dane przesłane za pomocą formularza PDF?

Aby wyodrębnić dane przesłane za pośrednictwem formularza PDF, musisz obsłużyć przesyłanie formularza na swoim serwerze lub zapleczu aplikacji. Gdy użytkownik prześle formularz, możesz otrzymać dane i przetworzyć je według potrzeb. Aspose.PDF zapewnia narzędzia do programowego wyodrębniania danych formularzy z dokumentu PDF po stronie serwera.

### Czy mogę dynamicznie generować formularze PDF na podstawie danych wprowadzonych przez użytkownika?

Tak, możesz dynamicznie generować formularze PDF na podstawie danych wejściowych użytkownika, używając Aspose.PDF dla Java. W zależności od danych wejściowych użytkownika lub logiki aplikacji można tworzyć dokumenty PDF z różnymi polami formularzy i układami. Ta elastyczność umożliwia generowanie niestandardowych formularzy dostosowanych do konkretnych potrzeb użytkownika lub scenariuszy.