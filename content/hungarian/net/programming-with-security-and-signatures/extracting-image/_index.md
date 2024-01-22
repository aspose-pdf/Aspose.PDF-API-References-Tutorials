---
title: Kép kibontása
linktitle: Kép kibontása
second_title: Aspose.PDF for .NET API Reference
description: Könnyen kivonat képeket PDF dokumentumokból az Aspose.PDF for .NET segítségével.
type: docs
weight: 70
url: /hu/net/programming-with-security-and-signatures/extracting-image/
---
A képek PDF-dokumentumból való kinyerése sok esetben hasznos lehet. Az Aspose.PDF for .NET segítségével könnyedén kibonthatja a képeket a következő forráskód használatával:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Íme a szükséges import irányelvek:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia annak a PDF-fájlnak az elérési útját, amelyből a képet ki szeretné bontani. Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 3. lépés: Kivonja a képet a PDF dokumentumból

Most kivonjuk a képet a PDF-dokumentumból a következő kóddal:

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

Ebben a példában végigfutjuk a PDF-dokumentum űrlapjának minden mezőjét. Ha találunk aláírási mezőt, kibontjuk a kapcsolódó képet, és elmentjük JPEG fájlba.

### Minta forráskód a kép kibontásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
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

## Következtetés

Gratulálok ! Most egy lépésről lépésre bemutatja a képeket PDF-dokumentumokból az Aspose.PDF for .NET használatával. Ezt a kódot integrálhatja saját projektjeibe, hogy kivonja a képeket, és szükség szerint felhasználja azokat.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt, ha további információra van szüksége a fejlett képkivonási és PDF-dokumentumkezelési funkciókról.


### GYIK

#### K: Az Aspose.PDF for .NET megfelelő kezdőknek?

V: Bár a C# programozásban való némi jártasság hasznos, oktatóanyagunkat úgy terveztük, hogy kezdőbarát legyen, és végigvezeti Önt az egyes lépéseken.

#### K: Kibonthatok több képet egyszerre?

V: Abszolút! A hurkok megvalósításával és a megadott kód adaptálásával több képet is kivonhat egyetlen PDF-dokumentumból.

#### K: Az Aspose.PDF for .NET az egyetlen megoldás a képkinyerésre?

V: Bár más eszközök is rendelkezésre állnak, az Aspose.PDF for .NET híres hatékonyságáról és átfogó szolgáltatásairól.

#### K: Használhatom a kivont képeket kereskedelmi célokra?

V: Igen, a kibontás után a képeket az Öné használhatja szükség szerint, beleértve a kereskedelmi projekteket is.

#### K: Hol találok további forrásokat az Aspose.PDF segítségével történő PDF-kezeléssel kapcsolatban?

V: Tekintse meg hivatalos dokumentációnkat, ahol rengeteg erőforrást és betekintést kaphat az Aspose.PDF for .NET segítségével történő fejlettebb PDF-kezelésről.