---
title: Określ stronę podczas przeglądania
linktitle: Określ stronę podczas przeglądania
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak określić stronę podczas przeglądania pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 110
url: /pl/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Dowiedz się, jak określić stronę podczas przeglądania pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z tego przewodnika krok po kroku.

## Krok 1: Konfigurowanie środowiska

Upewnij się, że skonfigurowałeś środowisko programistyczne z projektem C# i odpowiednimi odniesieniami Aspose.PDF.

## Krok 2: Ładowanie pliku PDF

Ustaw ścieżkę katalogu swoich dokumentów i prześlij plik PDF, korzystając z następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Załaduj plik PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Krok 3: Określanie strony docelowej

Pobierz wystąpienie strony docelowej przy użyciu następującego kodu:

```csharp
Page page2 = doc.Pages[2];
```

 Możesz dostosować indeks`[2]` aby wybrać żądaną stronę.

## Krok 4: Konfigurowanie ustawień powiększenia

Utwórz zmienną, aby ustawić współczynnik powiększenia strony docelowej:

```csharp
double zoom = 1;
```

Możesz dostosować wartość powiększenia do swoich potrzeb.

## Krok 5: Utwórz akcję nawigacyjną

Utwórz wystąpienie akcji nawigacyjnej, używając określonej strony docelowej:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Krok 6: Ustawienie miejsca docelowego

Ustaw cel, aby przejść do strony docelowej za pomocą współrzędnych i powiększenia:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Krok 7: Konfigurowanie akcji otwierania dokumentu

Ustaw akcję otwierania dokumentu za pomocą utworzonej akcji nawigacyjnej:

```csharp
doc. OpenAction = action;
```

## Krok 8: Zapisz zaktualizowany dokument

 Zapisz zaktualizowany dokument za pomocą`Save` metoda:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Przykładowy kod źródłowy dla opcji Określ stronę podczas wyświetlania za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj plik PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Pobierz wystąpienie drugiej strony dokumentu
Page page2 = doc.Pages[2];
// Utwórz zmienną, aby ustawić współczynnik powiększenia strony docelowej
double zoom = 1;
// Utwórz instancję GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Przejdź do 2 strony
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Ustaw akcję otwierania dokumentu
doc.OpenAction = action;
// Zapisz zaktualizowany dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

## Wniosek

Gratulacje! Teraz wiesz, jak określić stronę podczas przeglądania pliku PDF za pomocą Aspose.PDF dla .NET. Wykorzystaj tę wiedzę, aby dostosować sposób przeglądania dokumentów PDF przez użytkownika.

Po zapoznaniu się z tym przewodnikiem możesz zastosować poznane koncepcje we własnych projektach i lepiej poznać funkcje oferowane przez Aspose.PDF dla platformy .NET.

### Najczęściej zadawane pytania 

#### P: Jaki jest cel określania strony docelowej podczas przeglądania pliku PDF?

A: Określenie strony docelowej pozwala kontrolować, która strona dokumentu PDF jest wyświetlana po otwarciu pliku. Może to poprawić wrażenia użytkownika, kierując go do konkretnej strony, która go interesuje.

#### P: W jaki sposób określanie strony docelowej może być przydatne w dokumentach PDF?

A: Określenie strony docelowej jest przydatne, gdy chcesz pokierować użytkowników do konkretnej sekcji lub treści w dokumencie PDF, bez konieczności ręcznego przechodzenia między stronami.

#### P: W jaki sposób Aspose.PDF dla platformy .NET ułatwia określenie strony docelowej do wyświetlenia?

A: Aspose.PDF dla platformy .NET udostępnia interfejsy API umożliwiające ustawienie początkowego widoku dokumentu PDF, obejmującego stronę docelową, poziom powiększenia i inne właściwości wyświetlania.

#### P: Czy mogę wskazać dowolną stronę jako stronę docelową?

A: Tak, możesz określić dowolną stronę w dokumencie PDF jako stronę docelową do przeglądania. Po prostu użyj odpowiedniego indeksu, aby wybrać żądaną stronę.

#### P: Jakie znaczenie ma współczynnik powiększenia przy określaniu strony docelowej?

A: Współczynnik powiększenia określa poziom powiększenia stosowany do strony docelowej po otwarciu dokumentu PDF. Kontroluje on, ile treści jest wyświetlane w obszarze widoku.

#### P: Czy mogę ustawić różne współczynniki powiększenia dla różnych stron docelowych?

O: Tak, możesz ustawić różne współczynniki powiększenia dla różnych stron docelowych, tworząc oddzielne`GoToAction` wystąpień i odpowiednio konfigurując ich miejsca docelowe.

#### P: Czy istnieją jakieś ograniczenia w określaniu strony docelowej?

A: Określenie strony docelowej ogranicza się do kontrolowania początkowego widoku po otwarciu pliku PDF. Nie wpływa to na interakcje użytkownika ani nawigację po wyświetleniu pliku PDF.

#### P: Czy mogę użyć tej funkcji do tworzenia prezentacji w dokumencie PDF?

O: Tak, możesz użyć tej funkcji, aby tworzyć w dokumencie PDF doświadczenia przypominające prezentacje, prowadząc użytkowników przez różne sekcje lub tematy.

#### P: Czy mogę dostosować inne aspekty widoku początkowego, np. układ strony?

O: Tak, Aspose.PDF dla platformy .NET udostępnia właściwości umożliwiające dostosowanie innych aspektów widoku początkowego, w tym układu strony, trybu strony i innych.

#### P: Jak mogę sprawdzić, czy wskazana strona docelowa i współczynnik powiększenia działają zgodnie z oczekiwaniami?

A: Po zastosowaniu dostarczonego kodu w celu określenia strony docelowej i współczynnika powiększenia otwórz zmodyfikowany plik PDF i sprawdź, czy otwiera się on z właściwą stroną i poziomem powiększenia.