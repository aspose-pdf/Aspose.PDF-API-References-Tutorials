---
title: Pobierz pole formularza w kolejności kart
linktitle: Pobierz pole formularza w kolejności kart
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak pobierać pola formularza w kolejności tabulacji przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 240
url: /pl/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Podczas pracy z dokumentami PDF w języku C# przy użyciu Aspose.PDF dla .NET możesz natknąć się na scenariusz, w którym musisz pobrać pola formularza w określonej kolejności tabulacji. Może to być przydatne, gdy chcesz wykonać operacje na polach formularza w oparciu o ich kolejność tabulacji. W tym samouczku krok po kroku pokażemy, jak pobrać pola formularza w kolejności tabulacji przy użyciu Aspose.PDF dla .NET.

## Wymagania

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:

- Visual Studio zainstalowane w Twoim systemie
- Zainstalowano bibliotekę Aspose.PDF dla .NET

Teraz przyjrzyjmy się krokom pobierania pól formularza w kolejności kart.

## Krok 1: Ustawianie katalogu dokumentów

 Na początek musisz ustawić katalog dokumentu, w którym znajduje się Twój dokument PDF. Możesz to zrobić, określając ścieżkę do katalogu w`dataDir` zmienny.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie dokumentu PDF

 W tym kroku załadujemy dokument PDF przy użyciu Aspose.PDF dla .NET.`Document` Klasa umożliwia ładowanie i manipulowanie dokumentami PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Tutaj,`"Test2.pdf"`jest nazwą dokumentu PDF, który chcesz załadować. Upewnij się, że dokument znajduje się w określonym katalogu dokumentów.

## Krok 3: Pobieranie pól formularza w kolejności kart

 Aby pobrać pola formularza w kolejności tabulacji, musimy uzyskać dostęp do`FieldsInTabOrder` własność`Page` Klasa. Ta właściwość zwraca listę pól formularza posortowanych według kolejności kart.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

W powyższym fragmencie kodu pobieramy pola formularza z drugiej strony (`doc.Pages[1]` ) i przejrzyj każde pole, aby połączyć ich częściowe nazwy w`s` zmienna. Możesz zmodyfikować ten fragment kodu w oparciu o swoje specyficzne wymagania.

## Krok 4: Modyfikowanie kolejności kart

 Jeśli chcesz zmienić kolejność kart pól formularza, możesz to zrobić, uzyskując dostęp do`TabOrder` właściwość każdego pola i przypisanie nowej wartości kolejności kart. Oto przykład:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

W powyższym fragmencie kodu przypisujemy nowe wartości kolejności kart do trzech pól formularza (`doc.Form[3]`, `doc.Form[1]` , I`doc.Form[2]`). Dostosuj indeksy pól i wartości kolejności kart zgodnie ze swoimi konkretnymi wymaganiami.

## Krok 5: Zapisywanie zmodyfikowanego dokumentu

 Po zmodyfikowaniu kolejności zakładek pól formularza, musisz zapisać zmodyfikowany dokument. Możesz to zrobić za pomocą`Save` metoda`Document` klasa.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Tutaj,`"39522_out.pdf"` jest nazwą pliku wyjściowego, w którym zostanie zapisany zmodyfikowany dokument. Określ żądaną nazwę i lokalizację pliku wyjściowego.

### Przykładowy kod źródłowy dla funkcji Pobierz pole formularza w kolejności kart przy użyciu Aspose.PDF dla .NET 
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

W tym samouczku nauczyliśmy się, jak pobierać pola formularza w kolejności tabulacji za pomocą Aspose.PDF dla .NET. Omówiliśmy kroki związane z ładowaniem dokumentu PDF, pobieraniem pól formularza w kolejności tabulacji, modyfikowaniem kolejności tabulacji i zapisywaniem zmodyfikowanego dokumentu. Postępując zgodnie z tymi krokami, możesz wydajnie pracować z polami formularza i dostosowywać ich kolejność tabulacji zgodnie ze swoimi wymaganiami.


### Najczęściej zadawane pytania

#### P: W jaki sposób mogę wykorzystać pobrane pola formularza w kodzie C# w celu dalszego przetwarzania?

 A: Możesz użyć pobranych pól formularza w kodzie C#, uzyskując dostęp do ich właściwości, takich jak`Value`, `Name`, `Rect`itd. Właściwości te umożliwiają odczytywanie i modyfikowanie danych w polach formularza według potrzeb.

#### P: Czy mogę pobrać pola formularza ze wszystkich stron dokumentu PDF w kolejności tabulacji?

 O: Tak, możesz pobrać pola formularza ze wszystkich stron dokumentu PDF, przechodząc przez każdą stronę i uzyskując dostęp do`FieldsInTabOrder` właściwość, jak pokazano w samouczku. Spowoduje to, że pola formularza zostaną posortowane według kolejności kart na wszystkich stronach.

#### P: Czy można pobierać tylko określone typy pól formularza, takie jak pola tekstowe lub pola wyboru, w kolejności tabulatorów?

A: Tak, możesz filtrować pola formularza na podstawie ich typów, takich jak pola tekstowe lub pola wyboru, po pobraniu ich w kolejności tabulacji. Możesz użyć instrukcji warunkowych, aby sprawdzić typ każdego pola formularza i odpowiednio je przetworzyć.

#### P: Czy mogę pobierać pola formularza na podstawie ich nazw, a nie kolejności tabulatorów?

 O: Tak, możesz pobrać pola formularza na podstawie ich nazw, korzystając z`doc.Form` kolekcja i określenie nazwy pola jako indeksu. Na przykład,`doc.Form["fieldName"]`pobierze pole formularza o określonej nazwie.

#### P: Czy Aspose.PDF dla .NET obsługuje pracę z zaszyfrowanymi dokumentami PDF?

A: Tak, Aspose.PDF dla .NET zapewnia obsługę pracy z zaszyfrowanymi dokumentami PDF. Możesz ładować i manipulować zaszyfrowanymi plikami PDF, używając odpowiednich parametrów hasła.