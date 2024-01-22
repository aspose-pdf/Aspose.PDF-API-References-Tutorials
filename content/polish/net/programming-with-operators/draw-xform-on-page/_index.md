---
title: Narysuj XForm na stronie
linktitle: Narysuj XForm na stronie
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący rysowania formularza XForm na stronie PDF przy użyciu Aspose.PDF dla .NET. Dodaj i umieść formularz na stronie.
type: docs
weight: 10
url: /pl/net/programming-with-operators/draw-xform-on-page/
---
W tym samouczku przedstawimy krok po kroku, jak narysować XForm na stronie przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z operatorów dostarczonych przez Aspose.PDF, możesz dodać i umieścić formularz XForm na istniejącej stronie PDF.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio zainstalowany z platformą .NET.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod dostarczonych przez Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Krok 3: Ustawianie ścieżek plików

Zdefiniuj ścieżki pliku obrazu tła, wejściowego pliku PDF i wyjściowego pliku PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Pamiętaj, aby określić rzeczywiste ścieżki plików na komputerze.

## Krok 4: Ładowanie wejściowego pliku PDF

Użyj poniższego kodu, aby załadować wejściowy plik PDF:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Poniższy kod używa operatorów GSave/GRestore
// W kodzie zastosowano operator ContatenateMatrix do pozycjonowania XForm
// Kod używa operatora Do do narysowania XForm na stronie
// Operatory GSave/GRestore zawijają istniejącą zawartość
// ma to na celu uzyskanie początkowego stanu grafiki na końcu istniejącej treści
// w przeciwnym razie na końcu łańcucha istniejących operatorów mogą pozostać niepożądane przekształcenia
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Dodaj operator GSave, aby poprawnie zresetować stan grafiki po nowych poleceniach
pageContents. Add(new GSave());

// Utwórz XForm
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
// Korzystanie z operatora Do: ten operator rysuje obraz
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Ustaw XForm na współrzędnych x=100 i y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Narysuj XForm za pomocą operatora Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Ustaw XForm na współrzędnych x=100 i y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Narysuj XForm za pomocą operatora Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Przywróć stan grafiki za pomocą GRestore po GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Pamiętaj, aby określić rzeczywiste ścieżki plików i odpowiednio dostosować numer strony i pozycje XForm.

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
	// Wykorzystanie operatorów GSave/GRestore
	// Użycie operatora ContatenateMatrix do pozycjonowania xForm
	// Wykonaj użycie operatora, aby narysować xForm na stronie
	// Zawiń istniejącą zawartość za pomocą pary operatorów GSave/GRestore
	// ma to na celu uzyskanie początkowego stanu graficznego na poziomie istniejącej zawartości
	// w przeciwnym razie na końcu istniejącego łańcucha operatorów mogą pozostać pewne niepożądane przekształcenia
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Dodaj operator zapisu stanu grafiki, aby poprawnie wyczyścić stan grafiki po nowych poleceniach
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
	//Dodaj obraz do kolekcji obrazów w zasobach XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Użycie operatora Do: ten operator rysuje obraz
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umieść formularz we współrzędnych x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Narysuj formularz za pomocą operatora Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umieść formularz we współrzędnych x=100 y=300
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

W tym samouczku nauczyłeś się rysować formularz XForm na stronie PDF przy użyciu Aspose.PDF dla .NET. Wykonując opisane kroki, będziesz mógł dodać i umieścić formularz XForm na istniejącej stronie, zapewniając w ten sposób większą elastyczność swoim dokumentom PDF.

### Często zadawane pytania dotyczące rysowania XForm na stronie

#### P: Co to jest XForm w Aspose.PDF?

O: XForm to obiekt graficzny wielokrotnego użytku w dokumencie PDF. Umożliwia definiowanie i rysowanie złożonych grafik, obrazów lub tekstu, które można wielokrotnie wykorzystać na różnych stronach.

#### P: Jak zaimportować niezbędne przestrzenie nazw dla Aspose.PDF?

 Odp.: W pliku kodu C# użyj rozszerzenia`using` dyrektywa importująca wymagane przestrzenie nazw w celu uzyskania dostępu do klas i metod dostarczonych przez Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### P: Jaki jest cel operatorów GSave i GRestore?

 O:`GSave` I`GRestore`operatory w Aspose.PDF służą do zapisywania i przywracania stanu grafiki. Pomagają zapewnić, że przekształcenia i ustawienia zastosowane w jednej sekcji treści nie będą miały wpływu na kolejne sekcje.

#### P: Jak zdefiniować XForm przy użyciu Aspose.PDF?

 O: Aby utworzyć XForm, użyj`XForm.CreateNewForm` metodę i dodaj ją do`Resources.Forms` zbiór określonej strony. Następnie możesz dodać treść do XForm`Contents` nieruchomość.

#### P: Jak mogę narysować obraz w XForm?

 Odp.: Załaduj obraz do strumienia i dodaj go do pliku`Resources.Images` zbiór XForm. Użyj`Do` operator w XForm`Contents` narysować obraz.

#### P: Jak umieścić formularz XForm na stronie PDF?

 O: Aby umieścić XForm na stronie, użyj metody`ConcatenateMatrix` operator na stronie`Contents`. Dostosuj parametry macierzy, aby określić translację (położenie) i skalowanie XForm.

#### P: Czy mogę narysować wiele formularzy XForm na tej samej stronie?

 O: Tak, możesz narysować wiele XFormów na tej samej stronie, dostosowując opcję`ConcatenateMatrix`parametry, aby ustawić każdy XForm pod różnymi współrzędnymi.

#### P: Czy mogę modyfikować zawartość XForm po jego utworzeniu?

 O: Tak, możesz modyfikować zawartość XForm po utworzeniu, dodając do niego dodatkowe operatory`Contents` nieruchomość.

#### P: Co się stanie, jeśli pominę operatory GSave i GRestore?

Odp.: Pominięcie operatorów GSave i GRestore może prowadzić do niepożądanych przekształceń lub ustawień zastosowanych do późniejszej zawartości. Korzystanie z nich pomaga utrzymać czysty stan grafiki.

#### P: Czy mogę ponownie używać XForms na różnych stronach dokumentu PDF?

 O: Tak, możesz ponownie używać XForm na wielu stronach, dodając ten sam XForm do pliku`Resources.Forms` zbiór różnych stron.

#### P: Czy istnieje ograniczenie liczby formularzy XForm, które mogę utworzyć?

O: Chociaż nie ma ścisłego ograniczenia liczby formularzy XForm, które możesz utworzyć, pamiętaj, że zbyt wiele formularzy XForm może mieć wpływ na wydajność i wykorzystanie pamięci. Używaj ich rozsądnie.

#### P: Czy mogę obrócić XForm lub zastosować inne transformacje?

 Odp.: Tak, możesz użyć`ConcatenateMatrix`operator, aby zastosować transformacje, takie jak obrót, skalowanie i translacja, do XForm.
