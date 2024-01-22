---
title: Pobierz wszystkie adnotacje ze strony
linktitle: Pobierz wszystkie adnotacje ze strony
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET do pobierania wszystkich adnotacji ze strony PDF, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 70
url: /pl/net/annotations/getallannotationsfrompage/
---
Ten artykuł poprowadzi Cię przez proces wyodrębniania wszystkich adnotacji ze strony PDF przy użyciu Aspose.PDF dla .NET. Aspose.PDF dla .NET to biblioteka, która umożliwia programistom tworzenie, edytowanie i konwertowanie dokumentów PDF. Za pomocą tego przewodnika będziesz mógł uzyskać wszystkie adnotacje z określonej strony PDF, korzystając z dostarczonego kodu źródłowego C#.

Wykonaj poniższe kroki, jak uzyskać wszystkie adnotacje dla strony PDF przy użyciu Aspose.PDF dla .NET:

## Krok 1: Ścieżka do katalogu dokumentów

Pierwszym krokiem w uzyskaniu wszystkich adnotacji ze strony PDF przy użyciu Aspose.PDF dla .NET jest ustawienie ścieżki do katalogu dokumentów, w którym przechowywane są pliki PDF. Można to zrobić, modyfikując następujący wiersz kodu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Krok 2: Twoje pliki PDF zostaną zapisane

Zastąp „TWOJ KATALOG DOKUMENTÓW” ścieżką do folderu, w którym przechowywane są pliki PDF. Na przykład:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Krok 3: Otwórz dokument

Następnym krokiem jest otwarcie dokumentu PDF zawierającego adnotacje, które chcesz wyodrębnić. Można to zrobić dodając następujący kod:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Ta linia kodu inicjuje nową instancję klasy Document i ładuje dokument PDF „GetAllAnnotationsFromPage.pdf”. Zastąp tę nazwę pliku nazwą pliku PDF.

## Krok 4: Przejrzyj wszystkie adnotacje w pętli

Po otwarciu dokumentu PDF możesz przeglądać wszystkie adnotacje na określonej stronie. Na przykład, aby przejrzeć wszystkie adnotacje na pierwszej stronie dokumentu PDF, dodaj następujący kod:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Kod trafia tutaj
}
```

Ten kod przechodzi przez wszystkie adnotacje na pierwszej stronie dokumentu PDF i przypisuje każdą adnotację do zmiennej „adnotacja”.

## Krok 5: Uzyskaj właściwości adnotacji

Aby wyodrębnić właściwości każdej adnotacji, możesz dodać następujący kod wewnątrz pętli foreach:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Ten kod zapisuje tytuł, temat i treść każdej adnotacji w konsoli.

### Przykładowy kod źródłowy opcji Pobierz wszystkie adnotacje ze strony przy użyciu Aspose.PDF dla .NET

Oto kompletny kod źródłowy do pobierania wszystkich adnotacji ze strony PDF przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Przejrzyj wszystkie adnotacje
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Uzyskaj właściwości adnotacji
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

## Wniosek

tym samouczku omówiliśmy, jak uzyskać wszystkie adnotacje z określonej strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo wyodrębniać adnotacje z dokumentów PDF i zarządzać nimi.

### Często zadawane pytania

#### P: Czym są adnotacje w dokumencie PDF?

Odp.: Adnotacje w dokumencie PDF to interaktywne elementy, które dostarczają dodatkowych informacji, komentarzy lub notatek na temat określonych części dokumentu. Adnotacje mogą zawierać notatki tekstowe, komentarze, wyróżnienia i inne elementy interaktywne.

#### P: Czy mogę uzyskać adnotacje tylko z określonych stron?

Odp.: Tak, dzięki Aspose.PDF dla .NET możesz uzyskać adnotacje z określonych stron lub nawet z całego dokumentu, w zależności od wymagań.

#### P: Czy Aspose.PDF dla .NET obsługuje wyodrębnianie adnotacji z plików PDF chronionych hasłem?

 O: Tak, Aspose.PDF dla .NET obsługuje wyodrębnianie adnotacji z plików PDF chronionych hasłem. Musisz podać prawidłowe hasło podczas ładowania dokumentu PDF za pomocą`Document` klasa.

#### P: Czy mogę filtrować adnotacje na podstawie ich właściwości, takich jak treść lub autor?

O: Tak, Aspose.PDF dla .NET zapewnia metody dostępu i filtrowania adnotacji na podstawie ich właściwości, takich jak treść, autor lub data utworzenia. Możesz przeglądać wszystkie adnotacje i sprawdzać, które właściwości chcesz filtrować.

#### P: Czy Aspose.PDF dla .NET obsługuje wyodrębnianie adnotacji z różnych typów dokumentów PDF?

Odp.: Tak, Aspose.PDF dla .NET zapewnia różne metody wyodrębniania adnotacji z różnych typów dokumentów PDF, w tym adnotacje ze znacznikami tekstowymi, adnotacje z dowolnym tekstem i inne.