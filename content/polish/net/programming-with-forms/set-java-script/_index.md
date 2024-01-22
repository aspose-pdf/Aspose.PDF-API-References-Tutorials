---
title: Ustaw skrypt Java
linktitle: Ustaw skrypt Java
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET do ustawiania JavaScript w polach formularzy w plikach PDF.
type: docs
weight: 270
url: /pl/net/programming-with-forms/set-java-script/
---
W tym przewodniku wyjaśnimy krok po kroku, jak używać biblioteki Aspose.PDF dla .NET do definiowania JavaScript w polu formularza dokumentu PDF. Pokażemy Ci, jak skonfigurować akcje JavaScript, aby wykonywały określone operacje na polu tekstowym.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Środowisko programistyczne .NET zainstalowane w Twoim systemie.
- Biblioteka Aspose.PDF dla .NET. Można go pobrać z oficjalnej strony Aspose.

## Krok 1: Konfiguracja katalogu dokumentów

 Pierwszym krokiem jest skonfigurowanie katalogu dokumentów, w którym znajduje się plik PDF, nad którym chcesz pracować. Możesz skorzystać z`dataDir` zmienna określająca ścieżkę katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie wejściowego pliku PDF

 tym kroku załadujemy wejściowy plik PDF za pomocą`Document` klasa Aspose.PDF.

```csharp
// Załaduj wejściowy plik PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Upewnij się, że wejściowy plik PDF znajduje się w określonym katalogu dokumentów.

## Krok 3: Dostęp do pola TextBox

 Aby zastosować JavaScript do określonego pola tekstowego, musimy najpierw uzyskać dostęp do tego pola. W tym przykładzie zakładamy, że pole tekstowe nazywa się „textbox1”. Użyj`doc.Form["textbox1"]` metoda uzyskania odpowiedniego`TextBoxField` obiekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Upewnij się, że określone pole tekstowe istnieje w wejściowym pliku PDF.

## Krok 4: Skonfiguruj akcje JavaScript

 Teraz, gdy mamy już dostęp do pola tekstowego, możemy skonfigurować akcje JavaScript powiązane z tym polem. W tym przykładzie użyjemy dwóch akcji:`OnModifyCharacter` I`OnFormat` . Działania te zostaną zdefiniowane za pomocą`JavascriptAction` obiekty.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Pamiętaj, aby dostosować działania JavaScript do swoich potrzeb.

## Krok 5: Ustawienie początkowej wartości pola

Przed zapisaniem powstałego pliku PDF możemy ustawić wartość początkową dla pola tekstowego. W tym przykładzie ustawimy dla pola wartość „123”.

```csharp
field.Value = "123";
```

Dostosuj tę wartość do swoich potrzeb.

## Krok 6: Zapisywanie wynikowego pliku PDF

 Teraz, gdy skończyliśmy konfigurowanie pola tekstowego i akcji JavaScript, możemy zapisać wynikowy plik PDF za pomocą`Save` metoda`Document` klasa.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Zapisz wynikowy plik PDF
doc.Save(dataDir);
```

Pamiętaj, aby podać pełną ścieżkę i nazwę pliku wynikowego pliku PDF.


### Przykładowy kod źródłowy dla Ustaw skrypt Java przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj wejściowy plik PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 cyfry po kropce
// Brak separatora
// Styl negacji = minus
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

tym przewodniku dowiedzieliśmy się, jak używać biblioteki Aspose.PDF dla .NET do ustawiania JavaScript w polu formularza dokumentu PDF. Wykonując opisane kroki, możesz dostosować akcje JavaScript, aby wykonywać różne operacje na polach tekstowych. Zachęcamy do dalszego odkrywania funkcji Aspose.PDF dla .NET, aby rozszerzyć możliwości manipulowania plikami PDF.


### Często zadawane pytania

#### P: Czy mogę użyć Aspose.PDF dla .NET, aby dodać JavaScript do innych elementów formularzy, takich jak pola wyboru i przyciski opcji?

 Odp.: Tak, Aspose.PDF dla .NET umożliwia dodawanie JavaScript do różnych elementów formularzy, w tym pól wyboru, przycisków opcji i list rozwijanych. Możesz skorzystać z`JavascriptAction` class do definiowania akcji JavaScript dla różnych elementów formularza.

#### P: Czy możliwe jest sprawdzanie poprawności danych wprowadzonych przez użytkownika za pomocą JavaScript w polach formularzy?

 O: Tak, możesz używać JavaScriptu do sprawdzania poprawności danych wprowadzonych przez użytkownika w polach formularzy. Definiując akcje JavaScript, takie jak`OnBlur` Lub`OnKeystroke` w przypadku pola formularza możesz sprawdzić wprowadzone dane i w razie potrzeby wyświetlić komunikaty o błędach.

#### P: Czy mogę wykonywać złożone funkcje JavaScript przy użyciu Aspose.PDF dla .NET?

 Odp.: Tak, możesz wykonywać złożone funkcje JavaScript przy użyciu Aspose.PDF dla .NET. Masz możliwość definiowania niestandardowych funkcji JavaScript i wywoływania ich w pliku`JavascriptAction`.

#### P: Czy Aspose.PDF dla .NET obsługuje zdarzenia JavaScript inne niż te wymienione w tym samouczku?

 Odp.: Tak, Aspose.PDF dla .NET obsługuje szeroką gamę zdarzeń JavaScript, w tym`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , I`OnMouseUp`, pośród innych. Możesz użyć tych zdarzeń do wyzwalania akcji JavaScript na podstawie interakcji użytkownika.

#### P: Czy mogę używać Aspose.PDF dla .NET do wyodrębniania kodu JavaScript z istniejących dokumentów PDF?

 Odp.: Aspose.PDF dla .NET zapewnia możliwość wyodrębnienia kodu JavaScript z istniejących dokumentów PDF. Możesz skorzystać z`JavascriptAction` class i inne odpowiednie metody dostępu i analizowania działań JavaScript w formie PDF.