---
title: Tekst do pliku PDF
linktitle: Tekst do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Prosta i wydajna konwersja plików tekstowych do formatu PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 300
url: /pl/net/document-conversion/text-to-pdf/
---
Ten samouczek przeprowadzi Cię przez kroki konwersji pliku tekstowego na plik PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF oferuje proste i skuteczne rozwiązanie do konwersji zwykłego tekstu do formatu PDF przy jednoczesnym zachowaniu formatowania i prezentacji tekstu. Aby wykonać tę konwersję, wykonaj poniższe czynności.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Odczyt pliku tekstowego
 Pierwszym krokiem jest odczytanie zawartości pliku tekstowego za pomocą metody`StreamReader` klasa. Użyj następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Przeczytaj plik tekstowy
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` rzeczywistym katalogiem, w którym znajduje się plik tekstowy.

## Krok 2: Tworzenie dokumentu PDF
 Drugim krokiem jest utworzenie`Document` obiekt, który będzie reprezentował ostateczny dokument PDF. Użyj następującego kodu:

```csharp
// Utwórz obiekt Dokument
Document doc = new Document();
```

## Krok 3: Dodaj tekst do dokumentu
Trzecim krokiem jest dodanie przeczytanego tekstu na stronie dokumentu PDF. Użyj następującego kodu:

```csharp
//Dodaj nową stronę do dokumentu
Page page = doc.Pages.Add();

// Utwórz obiekt TextFragment i przekaż przeczytany tekst jako argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Dodaj akapit tekstowy do strony
page.Paragraphs.Add(text);
```

## Krok 4: Zapisywanie pliku PDF
Na koniec zapisz wynikowy plik PDF, określając żądaną ścieżkę i nazwę pliku. Użyj następującego kodu:

```csharp
// Zapisz wynikowy plik PDF
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Pamiętaj, aby określić żądaną ścieżkę i nazwę pliku wynikowego pliku PDF.

### Przykładowy kod źródłowy tekstu do formatu PDF przy użyciu Aspose.PDF dla .NET

```csharp
try
{
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Przeczytaj źródłowy plik tekstowy
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Utwórz instancję obiektu Document, wywołując jego pusty konstruktor
	Document doc = new Document();

	// Dodaj nową stronę w kolekcji Pages w dokumencie
	Page page = doc.Pages.Add();

	// Utwórz instancję TextFragmet i przekaż tekst z obiektu czytnika do jego konstruktora jako argument
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Dodaj nowy akapit tekstowy do kolekcji akapitów i przekaż obiekt TextFragment
	page.Paragraphs.Add(text);

	// Zapisz wynikowy plik PDF
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek
W tym samouczku dowiedzieliśmy się, jak przekonwertować plik tekstowy na plik PDF za pomocą Aspose.PDF dla .NET. Wykonując powyższe kroki, możesz łatwo przeprowadzić tę konwersję. Użyj tej metody, aby przekonwertować pliki tekstowe na format PDF i cieszyć się elastycznością i jakością Aspose.PDF.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Oferuje różne funkcje, w tym konwersję zwykłego tekstu do formatu PDF.

#### P: Dlaczego miałbym chcieć przekonwertować plik tekstowy na plik PDF?

Odp.: Konwersja plików tekstowych do formatu PDF umożliwia lepsze zarządzanie dokumentami, ich udostępnianie i dystrybucję. Pliki PDF oferują spójne formatowanie na różnych urządzeniach i systemach operacyjnych.

#### P: Jak mogę załadować plik tekstowy i przekonwertować go na plik PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Aby załadować plik tekstowy, możesz użyć metody`StreamReader` class do odczytania zawartości pliku. Następnie utwórz plik`Document` obiekt reprezentujący dokument PDF. Dodaj nową stronę i a`TextFragment` zawierający tekst z pliku tekstowego. Na koniec zapisz wynikowy plik PDF za pomocą pliku`Save` metoda`Document` obiekt.

#### P: Czy mogę dostosować wygląd tekstu w pliku PDF?

Odp.: Tak, Aspose.PDF dla .NET zapewnia różne opcje dostosowywania wyglądu tekstu w wynikowym pliku PDF, takie jak styl czcionki, rozmiar, kolor i wyrównanie.

#### P: Czy formatowanie tekstu jest zachowywane w wynikowym pliku PDF?

O: Tak, Aspose.PDF dla .NET zachowuje formatowanie i układ tekstu podczas konwersji tekstu do formatu PDF, zapewniając dokładne odwzorowanie oryginalnej treści.