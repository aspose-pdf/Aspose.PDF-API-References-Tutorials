---
title: Pobierz wszystkie załączniki w pliku PDF
linktitle: Pobierz wszystkie załączniki w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak uzyskać wszystkie załączniki w pliku PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku ułatwiający obsługę.
type: docs
weight: 40
url: /pl/net/programming-with-attachments/get-all-the-attachments/
---
tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby pobrać wszystkie załączniki w pliku PDF przy użyciu Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

### Krok 1: Konfiguracja katalogu dokumentów

W dostarczonym kodzie źródłowym musisz określić katalog, w którym znajduje się plik PDF, z którego chcesz pobrać załączniki. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Otwórz istniejący dokument PDF

Otwieramy istniejący dokument PDF, korzystając z określonej ścieżki.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Krok 3: Uzyskanie kolekcji załączników

Otrzymujemy zbiór załączników z dokumentu.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Krok 4: Pobieranie załączników

Przeglądamy kolekcję, aby pobrać wszystkie załączniki i wyświetlić zawarte w nich informacje. Załączniki zapisujemy także w pojedynczych plikach.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Sprawdź, czy parametry obiektu zawierają dodatkowe informacje
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Pobierz załącznik i zapisz w pliku
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Przykładowy kod źródłowy dla Pobierz wszystkie załączniki przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Pobierz osadzoną kolekcję plików
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Uzyskaj liczbę osadzonych plików
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Przejrzyj kolekcję w pętli, aby uzyskać wszystkie załączniki
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak pobrać wszystkie załączniki z pliku PDF za pomocą Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do wyodrębniania załączników z plików PDF i manipulowania nimi.

## Często zadawane pytania dotyczące pobierania wszystkich załączników w pliku PDF

#### P: Dlaczego miałbym pobierać wszystkie załączniki z dokumentu PDF?

O: Pobieranie załączników umożliwia dostęp do dodatkowych plików osadzonych w pliku PDF i manipulowanie nimi, co może być przydatne do archiwizowania, udostępniania lub dalszego przetwarzania.

#### P: Jakie typy plików można załączyć do dokumentu PDF?

Odp.: Dokumenty PDF mogą zawierać szeroką gamę załączonych plików, w tym obrazy, dokumenty, arkusze kalkulacyjne, pliki audio i inne.

#### P: W jaki sposób ten samouczek pomaga mi odzyskać załączniki z pliku PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Ten samouczek zawiera instrukcje krok po kroku i kod źródłowy C# umożliwiający uzyskiwanie dostępu do wszystkich załączników w dokumencie PDF i pobieranie ich.

#### P: Czy za pomocą tego samouczka mogę pobrać określone załączniki zamiast wszystkich?

Odp.: Tak, możesz zmodyfikować dostarczony kod, aby selektywnie pobierać załączniki w zależności od wymagań.

#### P: Jakie informacje na temat każdego załącznika mogę uzyskać, korzystając z tego samouczka?

O: W tym samouczku pokazano, jak pobrać i wyświetlić szczegóły, takie jak nazwa załącznika, opis, typ MIME, data utworzenia, data modyfikacji i rozmiar.

#### P: W jaki sposób zapisywane są pobrane załączniki, korzystając z tego samouczka?

O: Samouczek przeprowadzi Cię przez proces zapisywania każdego pobranego załącznika jako osobnego pliku w określonym katalogu.

#### P: Czy mogę wykorzystać tę wiedzę do wyodrębnienia załączników z plików PDF chronionych hasłem?

Odp.: Tak, możesz zastosować podobne zasady do pobierania załączników z plików PDF chronionych hasłem przy użyciu Aspose.PDF dla .NET.

#### P: W jaki sposób Aspose.PDF dla .NET ułatwia odzyskiwanie załączników?

Odp.: Aspose.PDF dla .NET zapewnia intuicyjny interfejs API, który umożliwia łatwy dostęp do załączników w dokumentach PDF i manipulowanie nimi.

#### P: Czy istnieją szczególne scenariusze, w których zalecane jest pobieranie załączników?

O: Odzyskiwanie załączników jest przydatne, gdy trzeba uzyskać dostęp do plików osadzonych w pliku PDF, np. wyodrębnić obrazy, pliki audio lub dodatkowe dokumenty.