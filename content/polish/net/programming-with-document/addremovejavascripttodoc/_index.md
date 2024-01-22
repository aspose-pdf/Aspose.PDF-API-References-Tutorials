---
title: Dodaj Usuń JavaScript do dokumentu PDF
linktitle: Dodaj Usuń JavaScript do dokumentu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać i usuwać JavaScript do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku z samouczkami dotyczącymi kodu umożliwiającymi tworzenie skryptów na poziomie dokumentu.
type: docs
weight: 30
url: /pl/net/programming-with-document/addremovejavascripttodoc/
---
Aby dodać i usunąć JavaScript do dokumentu PDF, skorzystamy z biblioteki Aspose.PDF dla .NET. Ta potężna biblioteka pozwala nam manipulować plikami PDF w aplikacjach .NET. Postępuj zgodnie z instrukcjami krok po kroku poniżej, aby dodać i usunąć JavaScript przy użyciu Aspose.PDF dla .NET.

## Krok 1: Utwórz nowy dokument PDF

 Rozpocznij od utworzenia nowej instancji pliku`Document` klasa dostarczona przez Aspose.PDF dla .NET. Będzie to służyć jako dokument PDF, do którego dodamy kod JavaScript.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Krok 2: Dodaj JavaScript na poziomie dokumentu

 Aby dodać JavaScript na poziomie dokumentu, użyj metody`JavaScript` własność`Document` klasa. Przypisz funkcje JavaScript do kluczy w słowniku JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 W tym samouczku dodaliśmy dwie funkcje JavaScript,`func1` I`func2`, do dokumentu PDF.

## Krok 3: Usuń JavaScript na poziomie dokumentu

 Aby usunąć JavaScript na poziomie dokumentu, załaduj dokument PDF i uzyskaj dostęp do`JavaScript`słownik. Iteruj po klawiszach i usuń żądaną funkcję JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 W tym samouczku usuwamy plik`func1` Funkcja JavaScript z dokumentu PDF.

## Krok 4: Zapisz i zweryfikuj zmiany

Zapisz zmodyfikowany dokument PDF i sprawdź zmiany.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Ten kod zapisze zmodyfikowany dokument PDF i wyświetli komunikat o powodzeniu.

### Przykładowy kod źródłowy narzędzia Dodaj Usuń JavaScript z dokumentów PDF przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Usuń JavaScript na poziomie dokumentu
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Wniosek

W tym artykule przedstawiliśmy przewodnik krok po kroku dotyczący dodawania i usuwania kodu JavaScript z dokumentów PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami i korzystając z dostarczonych samouczków dotyczących kodu, możesz łatwo włączyć JavaScript do swoich dokumentów PDF i usunąć go, jeśli zajdzie taka potrzeba. JavaScript umożliwia dynamiczną funkcjonalność i interaktywność w plikach PDF, poprawiając wygodę użytkownika.


### Często zadawane pytania dotyczące dodawania i usuwania javascript do dokumentu PDF

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to potężna biblioteka, która pozwala programistom efektywnie manipulować plikami PDF w aplikacjach .NET. Zapewnia rozbudowane funkcje do programowej pracy z dokumentami PDF.

#### P: Jak mogę dodać JavaScript do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Możesz dodać JavaScript na poziomie dokumentu za pomocą`JavaScript` własność`Document` klasa. Po prostu przypisz funkcje JavaScript do kluczy w słowniku JavaScript.

#### P: Czy mogę usunąć JavaScript z dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz usunąć JavaScript z dokumentu PDF, uzyskując dostęp do pliku`JavaScript` słownik i usunięcie żądanej funkcji JavaScript.

#### P: Czy Aspose.PDF dla .NET nadaje się do profesjonalnych projektów?

O: Oczywiście, Aspose.PDF dla .NET jest szeroko stosowany w profesjonalnych projektach do zadań związanych z manipulacją i generowaniem plików PDF. Oferuje wysoką wydajność i niezawodną funkcjonalność.

#### P: Jakie korzyści zapewnia dodanie JavaScript do dokumentu PDF?

O: Dodanie kodu JavaScript do dokumentu PDF umożliwia tworzenie interaktywnych i dynamicznych plików PDF. Możesz wdrożyć sprawdzanie poprawności formularzy, wykonywać obliczenia i dodawać różne funkcje interaktywne, aby poprawić komfort użytkownika.