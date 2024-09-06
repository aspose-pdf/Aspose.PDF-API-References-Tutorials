---
title: Ustaw skrypt Java
linktitle: Ustaw skrypt Java
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla .NET do ustawiania JavaScript w polach formularzy w plikach PDF.
type: docs
weight: 270
url: /pl/net/programming-with-forms/set-java-script/
---
W tym przewodniku wyjaśnimy krok po kroku, jak używać biblioteki Aspose.PDF dla .NET do definiowania JavaScript w polu formularza dokumentu PDF. Pokażemy, jak skonfigurować akcje JavaScript, aby wykonywać określone operacje na polu tekstowym.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Środowisko programistyczne .NET zainstalowane w Twoim systemie.
- Biblioteka Aspose.PDF dla .NET. Możesz ją pobrać z oficjalnej strony Aspose.

## Krok 1: Konfigurowanie katalogu dokumentów

 Pierwszym krokiem jest skonfigurowanie katalogu dokumentów, w którym znajduje się plik PDF, nad którym chcesz pracować. Możesz użyć`dataDir` zmienna określająca ścieżkę katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie pliku wejściowego PDF

 W tym kroku załadujemy plik wejściowy PDF za pomocą`Document` Klasa Aspose.PDF.

```csharp
// Załaduj plik wejściowy PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Upewnij się, że plik wejściowy PDF znajduje się w określonym katalogu dokumentów.

## Krok 3: Dostęp do pola TextBox

 Aby zastosować JavaScript do określonego pola tekstowego, najpierw musimy uzyskać dostęp do tego pola. W tym przykładzie zakładamy, że pole tekstowe nazywa się „textbox1”. Użyj`doc.Form["textbox1"]` metoda uzyskania odpowiedniego`TextBoxField` obiekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Upewnij się, że określone pole tekstowe istnieje w pliku wejściowym PDF.

## Krok 4: Skonfiguruj akcje JavaScript

 Teraz, gdy uzyskaliśmy dostęp do pola tekstowego, możemy skonfigurować akcje JavaScript powiązane z tym polem. W tym przykładzie użyjemy dwóch akcji:`OnModifyCharacter` I`OnFormat` . Te działania zostaną zdefiniowane za pomocą`JavascriptAction` obiekty.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Pamiętaj, aby dostosować działania JavaScript do swoich potrzeb.

## Krok 5: Ustawienie początkowej wartości pola

Przed zapisaniem wynikowego pliku PDF możemy ustawić wartość początkową dla pola tekstowego. W tym przykładzie ustawimy wartość „123” dla pola.

```csharp
field.Value = "123";
```

Dostosuj tę wartość do swoich potrzeb.

## Krok 6: Zapisywanie wynikowego pliku PDF

 Teraz, gdy zakończyliśmy konfigurację pola tekstowego i akcji JavaScript, możemy zapisać wynikowy plik PDF za pomocą`Save` metoda`Document` klasa.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Zapisz wynikowy plik PDF
doc.Save(dataDir);
```

Pamiętaj o podaniu pełnej ścieżki i nazwy pliku wynikowego PDF.


### Przykładowy kod źródłowy dla Set Java Script using Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj plik wejściowy PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 cyfry po kropce
// Brak separatora
// Styl negatywny = minus
// Brak waluty
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Ustaw początkową wartość pola
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Zapisz wynikowy plik PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Wniosek

tym przewodniku nauczyliśmy się, jak używać biblioteki Aspose.PDF dla .NET, aby ustawić JavaScript w polu formularza dokumentu PDF. Postępując zgodnie z opisanymi krokami, możesz dostosować akcje JavaScript, aby wykonywać różne operacje na polach tekstowych. Możesz swobodnie dalej eksplorować funkcje Aspose.PDF dla .NET, aby rozszerzyć możliwości manipulowania plikami PDF.


### Najczęściej zadawane pytania

#### P: Czy mogę użyć Aspose.PDF dla .NET, aby dodać JavaScript do innych elementów formularza, takich jak pola wyboru i przyciski radiowe?

 A: Tak, Aspose.PDF dla .NET pozwala na dodawanie JavaScript do różnych elementów formularza, w tym pól wyboru, przycisków radiowych i list rozwijanych. Możesz użyć`JavascriptAction` Klasa służąca do definiowania akcji JavaScript dla różnych elementów formularza.

#### P: Czy możliwe jest sprawdzanie poprawności danych wprowadzanych przez użytkownika w polach formularza za pomocą JavaScript?

 A: Tak, możesz użyć JavaScript do walidacji danych wprowadzanych przez użytkownika w polach formularza. Definiując akcje JavaScript, takie jak`OnBlur` Lub`OnKeystroke` w przypadku pola formularza możesz sprawdzić poprawność wprowadzonych danych i w razie potrzeby wyświetlić komunikaty o błędach.

#### P: Czy mogę wykonywać złożone funkcje JavaScript przy użyciu Aspose.PDF dla .NET?

 A: Tak, możesz wykonywać złożone funkcje JavaScript za pomocą Aspose.PDF dla .NET. Masz możliwość definiowania niestandardowych funkcji JavaScript i wywoływania ich w`JavascriptAction`.

#### P: Czy Aspose.PDF dla platformy .NET obsługuje inne zdarzenia JavaScript niż te wymienione w tym samouczku?

 O: Tak, Aspose.PDF dla .NET obsługuje szeroki zakres zdarzeń JavaScript, w tym:`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , I`OnMouseUp`, między innymi. Możesz użyć tych zdarzeń, aby wywołać akcje JavaScript na podstawie interakcji użytkownika.

#### P: Czy mogę użyć Aspose.PDF dla .NET do wyodrębnienia kodu JavaScript z istniejących dokumentów PDF?

 A: Aspose.PDF dla .NET umożliwia wyodrębnianie kodu JavaScript z istniejących dokumentów PDF. Możesz użyć`JavascriptAction` Klasa i inne istotne metody dostępu do akcji JavaScript i ich analizy w formacie PDF.