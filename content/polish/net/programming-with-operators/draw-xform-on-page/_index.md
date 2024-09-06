---
title: Narysuj XForm na stronie
linktitle: Narysuj XForm na stronie
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku dotycząca rysowania formularza XForm na stronie PDF przy użyciu Aspose.PDF dla platformy .NET. Dodaj i umieść formularz na stronie.
type: docs
weight: 10
url: /pl/net/programming-with-operators/draw-xform-on-page/
---
W tym samouczku przedstawimy Ci przewodnik krok po kroku, jak narysować XForm na stronie przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Używając operatorów dostarczonych przez Aspose.PDF, możesz dodać i umieścić formularz XForm na istniejącej stronie PDF.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano program Visual Studio z platformą .NET Framework.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony internetowej Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod udostępnianych przez Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Krok 3: Ustawianie ścieżek plików

Zdefiniuj ścieżki do plików dla obrazu tła, pliku wejściowego PDF i pliku wyjściowego PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Pamiętaj o określeniu rzeczywistych ścieżek plików na swoim komputerze.

## Krok 4: Ładowanie pliku wejściowego PDF

Użyj poniższego kodu, aby załadować plik wejściowy PDF:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Poniższy kod wykorzystuje operatory GSave/GRestore
// Kod wykorzystuje operator ContatenateMatrix do pozycjonowania XForm
// Kod wykorzystuje operator Do do narysowania formularza XForm na stronie
// Operatorzy GSave/GRestore opakowują istniejącą zawartość
//robi się to w celu uzyskania początkowego stanu grafiki na końcu istniejącej zawartości
// w przeciwnym razie na końcu łańcucha istniejących operatorów mogą pozostać niechciane transformacje
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Dodaj operator GSave, aby poprawnie resetować stan grafiki po nowych poleceniach
pageContents. Add(new GSave());

// Utwórz formularz XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Ustaw szerokość i wysokość obrazu
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Załaduj obraz do strumienia
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Dodaj obraz do kolekcji obrazów zasobów XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Używanie operatora Do: ten operator rysuje obraz
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Umieść XForm na współrzędnych x=100 i y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Narysuj XForm za pomocą operatora Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Umieść XForm na współrzędnych x=100 i y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Narysuj XForm za pomocą operatora Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Przywróć stan grafiki za pomocą GRestore po GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Pamiętaj o określeniu rzeczywistych ścieżek plików i dostosowaniu numerów stron oraz pozycji XForm według potrzeb.

### Przykładowy kod źródłowy dla Draw XForm On Page przy użyciu Aspose.PDF dla .NET
 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Próbka pokazuje
	// Użycie operatorów GSave/GRestore
	// Użycie operatora ContatenateMatrix do pozycjonowania xForm
	//Użyj operatora, aby narysować xForm na stronie
	// Zawiń istniejącą zawartość za pomocą pary operatorów GSave/GRestore
	// służy do uzyskania początkowego stanu grafiki na końcu istniejącej zawartości
	// w przeciwnym razie na końcu łańcucha istniejących operatorów mogą pozostać pewne niepożądane transformacje
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Dodaj operator zapisywania stanu grafiki, aby prawidłowo wyczyścić stan grafiki po nowych poleceniach
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Utwórz xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Zdefiniuj szerokość i wysokość obrazu
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Załaduj obraz do strumienia
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Dodaj obraz do kolekcji obrazów zasobów XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Używanie operatora Do: ten operator rysuje obraz
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umieść formularz na współrzędnych x=100 i y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Narysuj formularz za pomocą operatora Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umieść formularz na współrzędnych x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Narysuj formularz za pomocą operatora Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Przywróć stan grafiki za pomocą GRestore po GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Wniosek

W tym samouczku nauczyłeś się, jak narysować formularz XForm na stronie PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z opisanymi krokami, będziesz w stanie dodać i umieścić formularz XForm na istniejącej stronie, co zapewni większą elastyczność Twoim dokumentom PDF.

### FAQ dotyczące rysowania XForm na stronie

#### P: Czym jest XForm w pliku Aspose.PDF?

A: XForm to obiekt graficzny wielokrotnego użytku w dokumencie PDF. Umożliwia definiowanie i rysowanie złożonych grafik, obrazów lub tekstu, które można wielokrotnie wykorzystywać na różnych stronach.

#### P: Jak zaimportować niezbędne przestrzenie nazw dla pliku Aspose.PDF?

 A: W pliku kodu C# użyj`using` Dyrektywa importująca wymagane przestrzenie nazw w celu uzyskania dostępu do klas i metod udostępnianych przez Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### P: Jaki jest cel operatorów GSave i GRestore?

 A: Ten`GSave` I`GRestore` operatorzy w Aspose.PDF służą do zapisywania i przywracania stanu grafiki. Pomagają zapewnić, że transformacje i ustawienia zastosowane do jednej sekcji treści nie wpłyną na kolejne sekcje.

#### P: Jak zdefiniować formularz XForm za pomocą Aspose.PDF?

 A: Aby utworzyć formularz XForm, użyj`XForm.CreateNewForm` metodę i dodaj ją do`Resources.Forms` zbiór określonej strony. Następnie możesz dodać treść do XForm`Contents` nieruchomość.

#### P: Jak mogę narysować obraz w formularzu XForm?

A: Załaduj obraz do strumienia i dodaj go do`Resources.Images` kolekcji XForm. Użyj`Do` operator w XForm`Contents` narysować obraz.

#### P: Jak umieścić formularz XForm na stronie PDF?

 A: Aby umieścić formularz X na stronie, użyj`ConcatenateMatrix` operator w obrębie strony`Contents`. Dostosuj parametry macierzy, aby określić translację (położenie) i skalowanie formularza XForm.

#### P: Czy mogę narysować wiele formularzy XForm na tej samej stronie?

 O: Tak, możesz narysować wiele formularzy XForm na tej samej stronie, dostosowując`ConcatenateMatrix` parametry umożliwiające umiejscowienie każdego formularza XForm na różnych współrzędnych.

#### P: Czy mogę modyfikować zawartość formularza XForm po jego utworzeniu?

 O: Tak, możesz modyfikować zawartość formularza XForm po jego utworzeniu, dodając do niego dodatkowe operatory.`Contents` nieruchomość.

#### P: Co się stanie, jeśli pominę operatory GSave i GRestore?

A: Pominięcie operatorów GSave i GRestore może prowadzić do niechcianych transformacji lub ustawień stosowanych do późniejszej zawartości. Ich użycie pomaga utrzymać czysty stan grafiki.

#### P: Czy mogę ponownie używać formularzy XForm na różnych stronach dokumentu PDF?

 O: Tak, możesz ponownie używać formularzy XForm na wielu stronach, dodając ten sam formularz XForm do`Resources.Forms` zbiór różnych stron.

#### P: Czy liczba formularzy XForm, które mogę utworzyć, jest ograniczona?

A: Chociaż nie ma ścisłego limitu liczby formularzy XForm, które możesz utworzyć, pamiętaj, że zbyt wiele formularzy XForm może mieć wpływ na wydajność i wykorzystanie pamięci. Używaj ich rozważnie.

#### P: Czy mogę obrócić XForm lub zastosować inne przekształcenia?

 A: Tak, możesz użyć`ConcatenateMatrix` operator umożliwiający zastosowanie przekształceń, takich jak obrót, skalowanie i translacja, do formularza XForm.
