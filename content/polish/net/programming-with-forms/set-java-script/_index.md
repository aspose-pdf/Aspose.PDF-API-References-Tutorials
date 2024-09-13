---
title: Ustaw skrypt Java
linktitle: Ustaw skrypt Java
second_title: Aspose.PDF dla .NET API Reference
description: Odblokuj moc Aspose.PDF dla .NET. Dowiedz się, jak skonfigurować JavaScript w polach formularza dzięki naszemu przewodnikowi krok po kroku.
type: docs
weight: 270
url: /pl/net/programming-with-forms/set-java-script/
---
## Wstęp

Tworzenie dynamicznych i interaktywnych plików PDF może znacznie poprawić doświadczenia użytkownika, zwłaszcza podczas integrowania formularzy i pól w dokumencie. Jedną z potężnych bibliotek, która to umożliwia, jest Aspose.PDF dla .NET. W tym artykule zagłębimy się w konfigurowanie JavaScript dla pól formularzy za pomocą Aspose.PDF, zapewniając, że Twoje pliki PDF nie tylko dobrze wyglądają, ale także pięknie działają.

## Wymagania wstępne

Zanim przejdziemy do kodowania, upewnijmy się, że masz wszystko, czego potrzebujesz, aby wszystko poszło gładko:

- Visual Studio (lub dowolne środowisko IDE .NET): Upewnij się, że jest ono zainstalowane i poprawnie skonfigurowane.
  
-  Biblioteka Aspose.PDF: Będziesz potrzebować najnowszej wersji tej biblioteki. Możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/).

- Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

-  Pliki PDF: Powinieneś mieć gotowy plik PDF do testowania. W naszym przykładzie użyjemy pliku o nazwie`SetJavaScript.pdf`.

- Twój katalog dokumentów: Dowiedz się, gdzie przechowywane są pliki dokumentów. Będziemy odwoływać się do tej ścieżki w naszym kodzie.

Gdy już będziesz mieć te wymagania wstępne, z jakich narzędzi skorzystamy? Przyjrzyjmy się, co potrafi Aspose.PDF.

## Importuj pakiety

Aby rozpocząć, musisz uwzględnić niezbędne przestrzenie nazw w swoim projekcie C#. Otwórz swój główny plik C# i dodaj następujące polecenia importu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Te przestrzenie nazw zapewniają dostęp do funkcji związanych z plikami PDF i formularzami w bibliotece Aspose.PDF.

Gotowy, aby uczynić swój PDF interaktywnym? Weź czapkę kodera i rozłóżmy to na czynniki pierwsze!

## Krok 1: Zdefiniuj ścieżkę dokumentu

Najpierw musimy określić lokalizację naszego pliku PDF. To przygotowuje grunt pod wszystko, co nastąpi. Oto, jak to zrobić:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się Twój plik PDF. Pomyśl o tym jak o ustawianiu współrzędnych mapy skarbów — musisz wiedzieć, gdzie „X” oznacza to miejsce!

## Krok 2: Załaduj dokument PDF

Po zdefiniowaniu katalogu załadujemy nasz plik PDF. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Ten wiersz otwiera określony plik PDF i przygotowuje go do edycji. 

## Krok 3: Uzyskaj dostęp do pola formularza

Następnie chcemy uzyskać dostęp do pola formularza, w którym zastosujemy kod JavaScript. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Tutaj zakładamy, że w pliku PDF znajduje się pole tekstowe o nazwie`textbox1`. Jeśli nie posiadasz pola o takiej nazwie, możesz je zmienić lub odpowiednio dostosować kod. 

## Krok 4: Skonfiguruj akcje JavaScript

Teraz dodajmy trochę funkcjonalności do naszego pola tekstowego! Skonfigurujemy akcje JavaScript, które będą uruchamiane przy określonych zdarzeniach. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Oto co się dzieje:
- OnModifyCharacter: Ta funkcja JavaScript określa, jak pole powinno się zachowywać, gdy znak jest modyfikowany. W tym przypadku zezwala na dwa miejsca po przecinku po liczbie bez separatora.
- OnFormat: Dzięki temu masz pewność, że gdy użytkownik sformatuje liczbę, będzie ona formatowana według tej samej reguły.

Konfigurując te akcje, w zasadzie nadajemy naszemu polu tekstowemu osobowość — tak jakbyśmy uczyli je jakiegoś ruchu tanecznego!

## Krok 5: Zainicjuj wartość pola

Następnie ustalmy punkt początkowy dla naszego pola tekstowego, ustalając jego wartość początkową. 

```csharp
field.Value = "123";
```

Ten wiersz ustawia „123” jako wstępnie wypełnioną wartość w polu tekstowym. To jak przygotowanie sceny do występu.

## Krok 6: Zapisz zmodyfikowany plik PDF

Na koniec musimy zapisać dokument po wprowadzeniu wszystkich zmian.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Spowoduje to zaktualizowanie oryginalnego pliku o wprowadzone zmiany i zapisanie go jako`Restricted_out.pdf`. Można to postrzegać jako przypieczętowanie losu naszego pliku PDF — po zapisaniu będzie on gotowy do udostępnienia światu!

## Krok 7: Potwierdź powodzenie

Na koniec sprawdźmy czy wszystko poszło gładko. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Wyświetlenie tej wiadomości da ci pewność, że operacja zakończyła się sukcesem – to tak, jakbyś dostał brawa od publiczności po wspaniałym występie.

## Wniosek

Gratulacje! Udało Ci się skonfigurować JavaScript dla pól formularza w pliku PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek nie tylko dał Ci narzędzia do ulepszenia interakcji z użytkownikiem, ale także umożliwił Ci personalizowanie dokumentów jak profesjonalista. Niezależnie od tego, czy pracujesz z formularzami na fakturach, ankietach czy innych interaktywnych plikach PDF, możliwości są naprawdę nieograniczone.

### Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?  
Aspose.PDF to biblioteka przeznaczona do tworzenia, edytowania i manipulowania plikami PDF w aplikacjach .NET, udostępniająca zaawansowane funkcje PDF.

### Czy potrzebuję licencji, aby używać Aspose.PDF?  
 Chociaż dostępna jest bezpłatna wersja próbna, do pełnego wykorzystania bez ograniczeń wymagana jest licencja. Możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy).

### Czy mogę ustawić JavaScript w innych typach pól formularzy?  
Oczywiście! Aspose.PDF pozwala na wykonywanie działań JavaScript na różnych polach formularza, takich jak pola wyboru, przyciski radiowe i listy rozwijane.

### Gdzie mogę uzyskać pomoc w rozwiązaniu problemów z plikiem Aspose.PDF?  
 Możesz uzyskać pomoc techniczną za pośrednictwem ich[forum](https://forum.aspose.com/c/pdf/10) w przypadku jakichkolwiek pytań lub problemów.

### Czy istnieje możliwość przetestowania Aspose.PDF bez konieczności zakupu?  
Tak! Aspose zapewnia[bezpłatny okres próbny](https://releases.aspose.com/) aby przetestować funkcje biblioteki przed podjęciem decyzji o zakupie.