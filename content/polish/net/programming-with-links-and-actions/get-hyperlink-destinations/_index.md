---
title: Pobierz miejsca docelowe hiperłączy w pliku PDF
linktitle: Pobierz miejsca docelowe hiperłączy w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić miejsca docelowe hiperłączy w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 60
url: /pl/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF dla .NET to potężna biblioteka do manipulowania i wyodrębniania informacji w pliku PDF przy użyciu języka programowania C#. W tym samouczku skupimy się na wyodrębnianiu miejsc docelowych hiperłączy z pliku PDF przy użyciu Aspose.PDF dla .NET.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.
- Biblioteka Aspose.PDF dla platformy .NET zainstalowana na Twoim komputerze.

## Krok 1: Konfigurowanie środowiska programistycznego

Zanim zaczniesz pisać kod, musisz skonfigurować środowisko programistyczne, tworząc nowy projekt C# w swoim ulubionym środowisku IDE.

## Krok 2: Importuj odniesienia Aspose.PDF

Aby użyć Aspose.PDF dla .NET, musisz dodać odpowiednie odniesienia do swojego projektu. Wykonaj poniższe kroki, aby zaimportować niezbędne odniesienia:

1. W swoim projekcie kliknij prawym przyciskiem myszy „Odniesienia” i wybierz „Dodaj odniesienie”.
2. W oknie „Dodaj odwołanie” zlokalizuj i wybierz pliki DLL Aspose.PDF dla platformy .NET.
3. Kliknij „OK”, aby zaimportować odniesienia do projektu.

## Krok 3: Ładowanie pliku PDF

Zanim będziesz mógł wyodrębnić miejsca docelowe hiperłączy, musisz załadować plik PDF do swojej aplikacji. Użyj następującego kodu, aby załadować plik PDF:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Załaduj plik PDF
Document document = new Document(dataDir + "input.pdf");
```

Pamiętaj o podaniu prawidłowej ścieżki do katalogu dokumentów i pliku PDF, który chcesz przetworzyć.

## Krok 4: Poruszanie się po stronach dokumentu

Teraz, gdy plik PDF jest załadowany, musisz przejrzeć wszystkie strony dokumentu. Pozwoli ci to uzyskać

ir adnotacje hiperłączy obecne na każdej stronie. Użyj następującego kodu, aby przejść przez strony dokumentu:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Pobierz adnotacje linków do konkretnej strony
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Utwórz listę, aby zapisać wszystkie linki
     IList<Annotation> list = selector. Selected;
     // Przejdź przez każdy element na liście
     foreach(LinkAnnotation a in list)
     {
         // Wydrukuj adres URL docelowy
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Ten kod przechodzi przez każdą stronę dokumentu i wybiera adnotacje hiperłączy obecne na każdej stronie. Następnie przechowuje te adnotacje na liście i drukuje adres URL docelowy dla każdego łącza.

## Krok 5: Uzyskiwanie miejsc docelowych hiperłączy

Ostatnim krokiem jest wyodrębnienie miejsc docelowych hiperłączy z adnotacji hiperłączy. Poniższy kod pokazuje, jak to zrobić:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Użyj miejsca docelowego tak, jak chcesz
     }
}
```

W tym kodzie pobieramy każde miejsce docelowe hiperłącza z adnotacji łącza i przechowujemy miejsce docelowe w zmiennej. Następnie możesz użyć tego miejsca docelowego w swojej aplikacji, jak chcesz.

### Przykładowy kod źródłowy dla funkcji Pobierz miejsca docelowe hiperłącza przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj plik PDF
	Document document = new Document(dataDir + "input.pdf");
	// Przeglądaj wszystkie strony pliku PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Pobierz adnotacje linków z konkretnej strony
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Utwórz listę zawierającą wszystkie linki
		IList<Annotation> list = selector.Selected;
		// Iteruj po poszczególnych elementach na liście
		foreach (LinkAnnotation a in list)
		{
			// Wydrukuj adres URL docelowy
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Często zadawane pytania dotyczące pobierania miejsc docelowych hiperłączy w pliku PDF

#### P: Czym jest miejsce docelowe hiperłącza w pliku PDF?

A: Miejsce docelowe hiperłącza w pliku PDF to określona lokalizacja lub cel, do którego hiperłącze wskazuje. Może to być adres URL, strona w tym samym dokumencie lub dokument zewnętrzny.

#### P: W jaki sposób wyodrębnianie miejsc docelowych hiperłączy może pomóc w analizie mojego dokumentu PDF?

A: Wyodrębnianie miejsc docelowych hiperłączy pozwala na identyfikację i katalogowanie wszystkich miejsc docelowych, do których hiperłącza wskazują w dokumencie PDF. Informacje te mogą być przydatne do walidacji treści, weryfikacji linków i analizy danych.

#### P: W jaki sposób Aspose.PDF dla .NET pomaga w wyodrębnianiu miejsc docelowych hiperłączy?

A: Aspose.PDF dla .NET zapewnia potężne API do łatwego wyodrębniania miejsc docelowych hiperłączy. Ten samouczek pokazuje krok po kroku, jak wyodrębnić miejsca docelowe hiperłączy za pomocą języka C#.

#### P: Czy mogę selektywnie wyodrębnić miejsca docelowe hiperłączy w oparciu o określone kryteria?

O: Tak, możesz selektywnie wyodrębnić miejsca docelowe hiperłączy, przeglądając strony dokumentu PDF i filtrując żądane adnotacje hiperłączy na podstawie swoich kryteriów.

#### P: Czy można wyodrębnić hiperłącza z dokumentów PDF chronionych hasłem?

A: Aspose.PDF dla platformy .NET może wyodrębnić docelowe hiperłącza z dokumentów PDF chronionych hasłem, pod warunkiem że podczas otwierania dokumentu podasz wymagane dane uwierzytelniające.

#### P: W jaki sposób mogę wykorzystać wyodrębnione miejsca docelowe hiperłączy w mojej aplikacji?

A: Po wyodrębnieniu miejsc docelowych hiperłączy możesz ich użyć do wykonania różnych czynności, np. sprawdzenia poprawności adresów URL łączy, utworzenia raportów lub wdrożenia niestandardowej nawigacji.

#### P: Czy istnieją jakieś ograniczenia przy wyodrębnianiu miejsc docelowych hiperłączy?

A: Podczas gdy ekstrakcja miejsca docelowego hiperłącza jest wydajna, ważne jest, aby wziąć pod uwagę strukturę dokumentu PDF. Hiperłącza osadzone w złożonych grafikach lub treściach multimedialnych mogą wymagać dodatkowej obsługi.

#### P: Czy mogę wyodrębnić inne atrybuty hiperłączy, np. typy łączy lub współrzędne?

A: Samouczek koncentruje się na wyodrębnianiu miejsc docelowych hiperłączy. Możesz jednak zapoznać się z oficjalną dokumentacją Aspose.PDF, aby poznać zaawansowane funkcje, w tym wyodrębnianie typów łączy i współrzędnych.