---
title: Pobierz pole formularza w kolejności zakładek
linktitle: Pobierz pole formularza w kolejności zakładek
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak pobierać pola formularzy w kolejności tabulacji przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 240
url: /pl/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Pracując z dokumentami PDF w języku C# przy użyciu Aspose.PDF dla .NET, możesz natknąć się na scenariusz, w którym musisz pobrać pola formularzy w określonej kolejności tabulacji. Może to być przydatne, gdy chcesz wykonywać operacje na polach formularzy w oparciu o ich kolejność tabulacji. W tym samouczku poprowadzimy Cię krok po kroku, jak odzyskać pola formularza w kolejności tabulacji przy użyciu Aspose.PDF dla .NET.

## Wymagania

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

- Program Visual Studio zainstalowany w systemie
- Zainstalowana biblioteka Aspose.PDF dla .NET

Przejdźmy teraz do kroków pobierania pól formularzy w kolejności tabulacji.

## Krok 1: Ustawianie katalogu dokumentów

 Na początek musisz ustawić katalog dokumentów, w którym znajduje się dokument PDF. Można to zrobić podając ścieżkę do katalogu w pliku`dataDir` zmienny.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie dokumentu PDF

 W tym kroku załadujemy dokument PDF przy użyciu Aspose.PDF dla .NET. The`Document` class zapewnia możliwość ładowania i manipulowania dokumentami PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Tutaj,`"Test2.pdf"`to nazwa dokumentu PDF, który chcesz załadować. Upewnij się, że dokument znajduje się w określonym katalogu dokumentów.

## Krok 3: Pobieranie pól formularza w kolejności zakładek

 Aby pobrać pola formularza w kolejności tabulacji, musimy uzyskać dostęp do pliku`FieldsInTabOrder` własność`Page` klasa. Ta właściwość zwraca listę pól formularza posortowaną według kolejności tabulacji.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

W powyższym fragmencie kodu pobieramy pola formularza z drugiej strony (`doc.Pages[1]` ) i wykonaj iterację po każdym polu, aby połączyć ich częściowe nazwy w`s` zmienny. Możesz zmodyfikować ten fragment kodu w zależności od konkretnych wymagań.

## Krok 4: Modyfikowanie kolejności zakładek

 Jeżeli chcesz zmienić kolejność tabulacji w polach formularza, możesz to zrobić wchodząc na stronę`TabOrder` właściwości każdego pola i przypisanie nowej wartości kolejności tabulacji. Oto przykład:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

W powyższym fragmencie kodu przypisujemy nową kolejność tabulacji do trzech pól formularza (`doc.Form[3]`, `doc.Form[1]` , I`doc.Form[2]`). Dostosuj indeksy pól i wartości kolejności tabulacji zgodnie ze swoimi specyficznymi wymaganiami.

## Krok 5: Zapisywanie zmodyfikowanego dokumentu

 Po zmianie kolejności tabulacji pól formularza należy zapisać zmodyfikowany dokument. Można to zrobić za pomocą`Save` metoda`Document` klasa.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Tutaj,`"39522_out.pdf"` to nazwa pliku wyjściowego, w którym zostanie zapisany zmodyfikowany dokument. Określ żądaną nazwę i lokalizację pliku wyjściowego.

### Przykładowy kod źródłowy dla opcji Pobierz pole formularza w kolejności zakładek przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak pobierać pola formularzy w kolejności tabulacji przy użyciu Aspose.PDF dla .NET. Omówiliśmy kroki związane z ładowaniem dokumentu PDF, pobieraniem pól formularza w kolejności tabulacji, modyfikowaniem kolejności tabulacji i zapisywaniem zmodyfikowanego dokumentu. Wykonując poniższe kroki, możesz efektywnie pracować z polami formularzy i dostosowywać kolejność ich zakładek zgodnie ze swoimi wymaganiami.


### Często zadawane pytania

#### P: Jak mogę wykorzystać pobrane pola formularza w kodzie C# do dalszego przetwarzania?

 Odp.: Możesz użyć pobranych pól formularza w kodzie C#, uzyskując dostęp do ich właściwości, takich jak`Value`, `Name`, `Rect`itp. Te właściwości umożliwiają odczytywanie i modyfikowanie danych pól formularza według potrzeb.

#### P: Czy mogę pobrać pola formularzy ze wszystkich stron dokumentu PDF w kolejności tabulacji?

 O: Tak, możesz pobrać pola formularzy ze wszystkich stron dokumentu PDF, przeglądając każdą stronę i uzyskując dostęp do pliku`FieldsInTabOrder` właściwość, jak pokazano w samouczku. Spowoduje to posortowanie pól formularzy według kolejności tabulacji na wszystkich stronach.

#### P: Czy można pobrać tylko określone typy pól formularzy, takie jak pola tekstowe lub pola wyboru, w kolejności tabulacji?

O: Tak, możesz filtrować pola formularzy na podstawie ich typów, takich jak pola tekstowe lub pola wyboru, po pobraniu ich w kolejności tabulacji. Możesz użyć instrukcji warunkowych, aby sprawdzić typ każdego pola formularza i odpowiednio je przetworzyć.

#### P: Czy mogę wyszukiwać pola formularzy na podstawie ich nazw zamiast kolejności tabulacji?

 O: Tak, możesz wyszukiwać pola formularzy na podstawie ich nazw, korzystając z metody`doc.Form` kolekcji i określenie nazwy pola jako indeksu. Na przykład,`doc.Form["fieldName"]`pobierze pole formularza o podanej nazwie.

#### P: Czy Aspose.PDF dla .NET obsługuje pracę z zaszyfrowanymi dokumentami PDF?

O: Tak, Aspose.PDF dla .NET zapewnia obsługę pracy z zaszyfrowanymi dokumentami PDF. Możesz ładować i manipulować zaszyfrowanymi plikami PDF, używając odpowiednich parametrów hasła.