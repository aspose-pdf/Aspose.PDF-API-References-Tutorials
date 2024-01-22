---
title: Állítsa be az alapértelmezett betűtípus nevét
linktitle: Állítsa be az alapértelmezett betűtípus nevét
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató az alapértelmezett betűtípusnév beállításához PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 270
url: /hu/net/document-conversion/set-default-font-name/
---
Ebben az oktatóanyagban bemutatjuk, hogyan állíthatja be az alapértelmezett betűtípusnevet egy PDF-fájlban az Aspose.PDF for .NET használatával. Néha, amikor képeket bont ki egy PDF-fájlból, hiányzó betűtípus-problémák léphetnek fel. Az alapértelmezett betűtípusnév megadásával biztosíthatja, hogy a kivonatolt szöveg megfelelően jelenjen meg. Kövesse az alábbi lépéseket az alapértelmezett betűtípus nevének beállításához egy PDF-fájlban.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: A PDF dokumentum betöltése
 Az első lépés a PDF dokumentum betöltése a`Document` tárgy. Használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Hozzáadandó kód
}
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol a PDF-fájl található.

## 2. lépés: Állítsa be az alapértelmezett betűtípus nevét
 Ezután beállítjuk az alapértelmezett betűtípusnevet a`DefaultFontName` opció a`RenderingOptions` tárgy. Használja a következő kódot:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Hozzáadandó kód
     }
}
```

 Feltétlenül cserélje ki`"Arial"` a kívánt betűtípus nevével.

## 3. lépés: Képkivonás
Ezután kivonjuk a képet a PDF dokumentum megadott oldaláról. Használja a következő kódot:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Ügyeljen arra, hogy a helyes oldalszámot adja meg`pdfDocument.Pages[1]`.

### Példa forráskódra az alapértelmezett betűtípusnév beállításához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatja be az alapértelmezett betűtípusnevet egy PDF-fájlban az Aspose.PDF for .NET használatával. Az alapértelmezett betűtípusnév megadásával biztosíthatja, hogy a kivonatolt szöveg megfelelően jelenjen meg. Ezzel a módszerrel megoldhatja a hiányzó betűtípusokkal kapcsolatos problémákat, amikor képeket bont ki PDF-fájlokból.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF dokumentumokkal dolgozzanak C# alkalmazásokban. Különféle funkciókat kínál, beleértve az alapértelmezett betűtípus nevének beállítását egy PDF-fájlban.

#### K: Miért kell beállítanom az alapértelmezett betűtípusnevet egy PDF-fájlban?

V: Az alapértelmezett betűtípusnév beállítása akkor hasznos, ha szöveget bont ki egy PDF-dokumentumból. Ha a PDF olyan betűtípusú szöveget tartalmaz, amely nem érhető el a kivonatoló gépen, az alapértelmezett betűtípusnév megadása biztosítja a helyes szövegmegjelenítést.

#### K: Hogyan tölthetek be egy PDF-dokumentumot, és állíthatom be az alapértelmezett betűtípusnevet az Aspose.PDF for .NET használatával?

 V: PDF-dokumentum betöltéséhez és az alapértelmezett betűtípusnév beállításához használja a`Document`osztályba a PDF fájl betöltéséhez és a`RenderingOptions.DefaultFontName` tulajdonság megadásához a kívánt alapértelmezett betűtípus nevét.

#### K: Választhatok bármilyen betűtípust alapértelmezett betűtípusnévként?

V: Igen, a kivonatoló gépen elérhető bármely betűtípust kiválaszthatja alapértelmezett betűtípusnévként. A pontos szövegmegjelenítés érdekében használjon olyan betűtípust, amely pontosan megegyezik az eredeti PDF-ben hiányzó betűtípusokkal.

#### K: Az alapértelmezett betűtípusnév beállítása végleges változást jelent a PDF-fájlban?

V: Nem, az alapértelmezett betűtípus nevének beállítása az Aspose.PDF for .NET használatával ideiglenes módosítása a szöveg kibontása során. Nem módosítja az eredeti PDF fájlt.