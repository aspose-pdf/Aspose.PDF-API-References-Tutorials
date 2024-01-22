---
title: Wyodrębnianie obrazu
linktitle: Wyodrębnianie obrazu
second_title: Aspose.PDF z dokumentacją API .NET
description: łatwością wyodrębnij obrazy z dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/programming-with-security-and-signatures/extracting-image/
---
Wyodrębnianie obrazów z dokumentu PDF może być przydatne w wielu przypadkach. Dzięki Aspose.PDF dla .NET możesz łatwo wyodrębniać obrazy, korzystając z następującego kodu źródłowego:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importowe:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, z którego chcesz wyodrębnić obraz. Zastępować`"YOUR DOCUMENTS DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Krok 3: Wyodrębnij obraz z dokumentu PDF

Teraz wyodrębnimy obraz z dokumentu PDF za pomocą następującego kodu:

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

W tym przykładzie przeglądamy w pętli każde pole formularza w dokumencie PDF. Jeśli zostanie znalezione pole podpisu, wyodrębniamy powiązany obraz i zapisujemy go w pliku JPEG.

### Przykładowy kod źródłowy do wyodrębniania obrazu przy użyciu Aspose.PDF dla .NET 
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

Gratulacje! Teraz masz przewodnik krok po kroku, jak wyodrębnić obrazy z dokumentu PDF za pomocą Aspose.PDF dla .NET. Możesz zintegrować ten kod ze swoimi własnymi projektami, aby wyodrębnić obrazy i wykorzystać je w razie potrzeby.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji ekstrakcji obrazów i manipulacji dokumentami PDF.


### Często zadawane pytania

#### P: Czy Aspose.PDF dla .NET jest odpowiedni dla początkujących?

Odp.: Chociaż pewna znajomość programowania w języku C# jest pomocna, nasz samouczek został zaprojektowany tak, aby był przyjazny dla początkujących i prowadził Cię przez każdy krok.

#### P: Czy mogę wyodrębnić wiele obrazów jednocześnie?

Odp.: Absolutnie! Implementując pętle i dostosowując dostarczony kod, możesz wyodrębnić wiele obrazów z jednego dokumentu PDF.

#### P: Czy Aspose.PDF dla .NET jest jedynym rozwiązaniem do ekstrakcji obrazów?

Odp.: Chociaż dostępne są inne narzędzia, Aspose.PDF dla .NET jest znany ze swojej wydajności i wszechstronnych funkcji.

#### P: Czy mogę używać wyodrębnionych obrazów do celów komercyjnych?

O: Tak, po wyodrębnieniu obrazy są Twoje i możesz ich używać w razie potrzeby, w tym w projektach komercyjnych.

#### P: Gdzie mogę znaleźć więcej zasobów na temat manipulacji plikami PDF za pomocą Aspose.PDF?

Odp.: Odwiedź naszą oficjalną dokumentację, aby uzyskać bogactwo zasobów i spostrzeżeń na temat zaawansowanej manipulacji plikami PDF za pomocą Aspose.PDF dla .NET.