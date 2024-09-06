---
title: Ekstrakcja obrazu
linktitle: Ekstrakcja obrazu
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe wyodrębnianie obrazów z dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/programming-with-security-and-signatures/extracting-image/
---
Wyodrębnianie obrazów z dokumentu PDF może być przydatne w wielu przypadkach. Dzięki Aspose.PDF dla .NET możesz łatwo wyodrębnić obrazy, korzystając z następującego kodu źródłowego:

## Krok 1: Importuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importu:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, z którego chcesz wyodrębnić obraz. Zastąp`"YOUR DOCUMENTS DIRECTORY"` w poniższym kodzie podaj rzeczywistą ścieżkę do folderu z dokumentami:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Krok 3: Wyodrębnij obraz z dokumentu PDF

Teraz wyodrębnimy obraz z dokumentu PDF, korzystając z następującego kodu:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

W tym przykładzie przechodzimy przez każde pole formularza w dokumencie PDF. Jeśli zostanie znalezione pole podpisu, wyodrębniamy powiązany obraz i zapisujemy go w pliku JPEG.

### Przykładowy kod źródłowy do wyodrębniania obrazu za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku, jak wyodrębnić obrazy z dokumentu PDF za pomocą Aspose.PDF dla .NET. Możesz zintegrować ten kod ze swoimi projektami, aby wyodrębnić obrazy i używać ich w razie potrzeby.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji wyodrębniania obrazów i manipulowania dokumentami PDF.


### Najczęściej zadawane pytania

#### P: Czy Aspose.PDF dla platformy .NET nadaje się dla początkujących?

A: Choć pewna znajomość programowania w języku C# może być pomocna, nasz samouczek został zaprojektowany tak, aby był przyjazny dla początkujących i poprowadził Cię przez każdy krok.

#### P: Czy mogę wyodrębnić kilka obrazów jednocześnie?

A: Oczywiście! Implementując pętle i dostosowując dostarczony kod, możesz wyodrębnić wiele obrazów z jednego dokumentu PDF.

#### P: Czy Aspose.PDF dla platformy .NET to jedyne rozwiązanie umożliwiające wyodrębnianie obrazów?

O: Chociaż dostępne są inne narzędzia, Aspose.PDF dla platformy .NET jest znane ze swojej wydajności i kompleksowych funkcji.

#### P: Czy mogę wykorzystać wyodrębnione obrazy w celach komercyjnych?

O: Tak, po wyodrębnieniu obrazy są Twoją własnością i możesz je wykorzystywać według potrzeb, także w projektach komercyjnych.

#### P: Gdzie mogę znaleźć więcej materiałów na temat manipulowania plikami PDF za pomocą Aspose.PDF?

A: Odwiedź naszą oficjalną dokumentację, aby uzyskać dostęp do licznych zasobów i wskazówek dotyczących zaawansowanej obróbki plików PDF za pomocą Aspose.PDF dla platformy .NET.