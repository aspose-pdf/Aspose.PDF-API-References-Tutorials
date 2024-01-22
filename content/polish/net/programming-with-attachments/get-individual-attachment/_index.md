---
title: Uzyskaj indywidualny załącznik w pliku PDF
linktitle: Uzyskaj indywidualny załącznik w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak uzyskać indywidualny załącznik w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 60
url: /pl/net/programming-with-attachments/get-individual-attachment/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby uzyskać indywidualny załącznik pliku PDF za pomocą Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

### Krok 1: Konfiguracja katalogu dokumentów

W dostarczonym kodzie źródłowym należy określić katalog, w którym znajduje się plik PDF, z którego ma zostać pobrany indywidualny załącznik. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Otwórz istniejący dokument PDF

Otwieramy istniejący dokument PDF, korzystając z określonej ścieżki.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Krok 3: Uzyskanie konkretnego załącznika

Pobieramy konkretny załącznik z kolekcji załączników dokumentu. W tym przykładzie pierwszy załącznik otrzymujemy przy użyciu indeksu 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Krok 4: Uzyskaj właściwości pliku

Wyświetlamy właściwości załącznika, takie jak nazwa, opis, typ MIME, skrót kontrolny, data utworzenia, data modyfikacji i rozmiar.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Sprawdź, czy parametry obiektu zawierają dodatkowe informacje
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Krok 5: Pobierz załącznik i zapisz w pliku

Pobieramy treść załącznika i zapisujemy ją do pliku tekstowego. W tym przykładzie plik jest zapisywany pod nazwą „test_out.txt”.

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Przykładowy kod źródłowy dla opcji Pobierz indywidualny załącznik przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Pobierz konkretny osadzony plik
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Pobierz właściwości pliku
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//Sprawdź, czy obiekt parametrów zawiera parametry
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
// Pobierz załącznik i zapisz do pliku lub strumienia
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak uzyskać indywidualny załącznik z pliku PDF za pomocą Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do wyodrębniania i zapisywania załączników z plików PDF.

### Często zadawane pytania dotyczące pobierania indywidualnego załącznika w pliku PDF

#### P: Jaki jest cel pobierania pojedynczego załącznika z dokumentu PDF?

O: Pobranie pojedynczego załącznika umożliwia wyodrębnienie i zapisanie określonego osadzonego pliku w pliku PDF, co może być przydatne do dalszej analizy lub manipulacji.

#### P: W jaki sposób mogę skorzystać z tego samouczka podczas wykonywania zadań związanych z plikami PDF?

Odp.: Ten samouczek zawiera instrukcje krok po kroku i kod źródłowy C# umożliwiający pobranie i zapisanie określonego załącznika z dokumentu PDF przy użyciu Aspose.PDF dla .NET.

#### P: Do jakich właściwości załączników mogę uzyskać dostęp, korzystając z tego samouczka?

O: Możesz uzyskać dostęp do właściwości załącznika, takich jak nazwa, opis, typ MIME, skrót kontrolny, data utworzenia, data modyfikacji i rozmiar konkretnego załącznika.

#### P: Czy mogę zmodyfikować kod, aby uzyskać załączniki inne niż pierwszy załącznik?

 O: Oczywiście, możesz dostosować indeks (np.`pdfDocument.EmbeddedFiles[1]`), aby pobrać załączniki o różnych indeksach w pliku PDF.

#### P: Jak zapisać pobrany załącznik do pliku?

Odp.: Ten samouczek zawiera kod umożliwiający pobranie zawartości załącznika i zapisanie jej w pliku tekstowym o określonej nazwie.

#### P: Jakie jest znaczenie właściwości „Sprawdź skrót” w informacjach o załącznikach?

O: Właściwość „Sprawdź hash” reprezentuje wartość skrótu kontrolnego załącznika, której można użyć do sprawdzenia integralności załącznika.

#### P: Czy mogę rozszerzyć tę wiedzę, aby wyodrębnić załączniki według określonych kryteriów, takich jak typ pliku?

O: Tak, możesz ulepszyć kod, aby filtrować załączniki na podstawie określonych kryteriów, takich jak typ pliku lub inne właściwości.

#### P: W jaki sposób Aspose.PDF dla .NET upraszcza proces wyodrębniania poszczególnych załączników?

Odp.: Aspose.PDF dla .NET zapewnia przyjazny dla użytkownika interfejs API, który ułatwia wyodrębnianie i manipulowanie załącznikami w dokumentach PDF.

#### P: Czy ten samouczek dotyczy również plików PDF chronionych hasłem?

O: Tak, możesz zastosować podobne techniki pobierania poszczególnych załączników z plików PDF chronionych hasłem przy użyciu Aspose.PDF dla .NET.
