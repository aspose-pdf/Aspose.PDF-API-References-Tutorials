---
title: Określ stronę podczas przeglądania
linktitle: Określ stronę podczas przeglądania
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak określić stronę podczas przeglądania pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Dowiedz się, jak określić stronę podczas przeglądania pliku PDF przy użyciu Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.

## Krok 1: Konfigurowanie środowiska

Upewnij się, że skonfigurowałeś środowisko programistyczne z projektem C# i odpowiednimi odniesieniami do Aspose.PDF.

## Krok 2: Ładowanie pliku PDF

Ustaw ścieżkę katalogu swoich dokumentów i prześlij plik PDF, korzystając z następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Załaduj plik PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Krok 3: Określenie strony docelowej

Pobierz instancję strony docelowej, używając następującego kodu:

```csharp
Page page2 = doc.Pages[2];
```

 Można dostosować indeks`[2]` aby wybrać żądaną stronę.

## Krok 4: Konfiguracja ustawienia powiększenia

Utwórz zmienną, aby ustawić współczynnik powiększenia strony docelowej:

```csharp
double zoom = 1;
```

Możesz dostosować wartość powiększenia do swoich potrzeb.

## Krok 5: Utwórz akcję nawigacji

Utwórz instancję akcji nawigacyjnej, korzystając z określonej strony docelowej:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Krok 6: Ustawianie celu

Ustaw miejsce docelowe, aby przejść do strony docelowej za pomocą współrzędnych i powiększenia:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Krok 7: Konfiguracja akcji otwierania dokumentu

Ustaw akcję otwierania dokumentu za pomocą utworzonej akcji nawigacyjnej:

```csharp
doc. OpenAction = action;
```

## Krok 8: Zapisz zaktualizowany dokument

 Zapisz zaktualizowany dokument za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Przykładowy kod źródłowy dla opcji Określ stronę podczas przeglądania przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj plik PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Pobierz instancję drugiej strony dokumentu
Page page2 = doc.Pages[2];
// Utwórz zmienną, aby ustawić współczynnik powiększenia strony docelowej
double zoom = 1;
// Utwórz instancję GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Przejdź do strony 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Ustaw akcję otwierania dokumentu
doc.OpenAction = action;
// Zapisz zaktualizowany dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

## Wniosek

Gratulacje! Teraz wiesz, jak określić stronę podczas przeglądania pliku PDF przy użyciu Aspose.PDF dla .NET. Skorzystaj z tej wiedzy, aby dostosować sposób przeglądania dokumentów PDF przez użytkownika.

Teraz, gdy ukończyłeś ten przewodnik, możesz zastosować te koncepcje do własnych projektów i dokładniej poznać funkcje oferowane przez Aspose.PDF dla .NET.

### Często zadawane pytania 

#### P: Jaki jest cel określenia strony docelowej podczas przeglądania pliku PDF?

O: Określenie strony docelowej pozwala kontrolować, która strona dokumentu PDF będzie wyświetlana po otwarciu pliku. Może to poprawić komfort użytkownika, kierując go na konkretną, interesującą stronę.

#### P: W jaki sposób określenie strony docelowej może być przydatne w dokumentach PDF?

O: Określenie strony docelowej jest korzystne, gdy chcesz poprowadzić użytkowników do określonej sekcji lub treści dokumentu PDF bez konieczności ręcznego poruszania się po stronach.

#### P: W jaki sposób Aspose.PDF dla .NET ułatwia określenie strony docelowej do przeglądania?

Odp.: Aspose.PDF dla .NET udostępnia interfejsy API, które pozwalają ustawić początkowy widok dokumentu PDF, w tym stronę docelową, poziom powiększenia i inne właściwości wyświetlania.

#### P: Czy mogę określić dowolną stronę jako stronę docelową?

O: Tak, możesz określić dowolną stronę dokumentu PDF jako stronę docelową do przeglądania. Wystarczy użyć odpowiedniego indeksu, aby wybrać żądaną stronę.

#### P: Jakie jest znaczenie współczynnika powiększenia przy określaniu strony docelowej?

Odp.: Współczynnik powiększenia określa poziom powiększenia zastosowanego do strony docelowej po otwarciu dokumentu PDF. Kontroluje ilość treści wyświetlaną w rzutni.

#### P: Czy mogę ustawić różne współczynniki powiększenia dla różnych stron docelowych?

O: Tak, możesz ustawić różne współczynniki powiększenia dla różnych stron docelowych, tworząc osobne strony`GoToAction` instancji i odpowiednio konfigurując ich miejsca docelowe.

#### P: Czy istnieją jakieś ograniczenia w określaniu strony docelowej?

Odp.: Określenie strony docelowej ogranicza się do kontrolowania widoku początkowego po otwarciu pliku PDF. Nie ma to wpływu na interakcje użytkownika ani nawigację po wyświetleniu pliku PDF.

#### P: Czy mogę używać tej funkcji do tworzenia prezentacji w dokumencie PDF?

O: Tak, możesz użyć tej funkcji, aby stworzyć w dokumencie PDF prezentację przypominającą prezentację, prowadząc użytkowników przez różne sekcje lub tematy.

#### P: Czy mogę dostosować inne aspekty widoku początkowego, takie jak układ strony?

O: Tak, Aspose.PDF dla .NET zapewnia właściwości umożliwiające dostosowanie innych aspektów widoku początkowego, w tym układu strony, trybu strony i innych.

#### P: Jak mogę sprawdzić, czy określona strona docelowa i współczynnik powiększenia działają zgodnie z oczekiwaniami?

O: Po zastosowaniu dostarczonego kodu w celu określenia strony docelowej i współczynnika powiększenia otwórz zmodyfikowany plik PDF i sprawdź, czy otwiera się z prawidłową stroną i poziomem powiększenia.