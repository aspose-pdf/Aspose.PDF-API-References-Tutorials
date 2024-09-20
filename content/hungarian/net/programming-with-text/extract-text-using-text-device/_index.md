---
title: Szöveg kibontása szövegeszközzel
linktitle: Szöveg kibontása szövegeszközzel
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthat ki szöveget PDF-dokumentumból az Aspose.PDF for .NET szövegeszközével.
type: docs
weight: 210
url: /hu/net/programming-with-text/extract-text-using-text-device/
---
## Bevezetés

szöveg kinyerése PDF-ből bonyolult lehet, különösen akkor, ha különféle formátumú, beágyazott betűtípusú vagy összetett elrendezésű dokumentumokkal foglalkozik. De az Aspose.PDF for .NET használatával ez a folyamat gyerekjáték lesz! Függetlenül attól, hogy egy PDF-fájl oldalait egyszerű szöveggé szeretné konvertálni további elemzés céljából, vagy egyszerűen csak bizonyos szakaszokat szeretne kivonatolni, az Aspose.PDF mindenre kiterjed. Ebben az oktatóanyagban lépésről lépésre lebontjuk, hogyan lehet szöveget kivonni PDF-ből az Aspose.PDF TextDevice osztályával. Világos magyarázatokat is adunk, így könnyedén alkalmazhatja ugyanazokat a módszereket saját projektjeinél.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjön meg arról, hogy minden a helyén van a követéshez. Íme, amire szüksége lesz:

1.  Aspose.PDF for .NET: Töltse le a legújabb verziót a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net/).
2. Fejlesztői környezet: Visual Studio vagy bármely más C# fejlesztői környezet.
3. .NET-keretrendszer: Győződjön meg arról, hogy a projektje a .NET-keretrendszer 4.x vagy újabb verzióját célozza meg.
4. Beviteli PDF-fájl: PDF-fájl, amelyet szövegkivonathoz használhat. Helyezze el ezt egy könyvtárba a gépén (ezt úgy fogjuk hivatkozni, mint`YOUR DOCUMENT DIRECTORY`).

## Csomagok importálása

A kód tetején importálnia kell a szükséges névtereket az Aspose.PDF használatához:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## 1. lépés: Töltse be a PDF-dokumentumot

 A szöveg kibontása előtt be kell töltenünk a PDF dokumentumot a memóriába. Ebben a lépésben az Aspose.PDF használatával nyissa meg a PDF-fájlt`Document` osztály. Ezzel elérheti a fájl összes oldalát és tartalmát.

```csharp
// Határozza meg a PDF-dokumentum elérési útját
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Töltse be a PDF dokumentumot
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Itt használjuk`Document pdfDocument = new Document(dataDir + "input.pdf");` a PDF betöltéséhez. A`dataDir` változó tartalmazza a PDF-fájl könyvtárának elérési útját. Ez hozzáférést biztosít számunkra a teljes dokumentumhoz, lehetővé téve az oldalak közötti hurokolást és a tartalom kibontását.

## 2. lépés: Állítson be egy String Buildert a szövegtároláshoz

 Most, hogy a dokumentum betöltődött, szükségünk van egy módra a kivont szöveg tárolására. Ehhez használjuk a`StringBuilder` amely lehetővé teszi a hatékony karakterlánc-összefűzést.

```csharp
// StringBuilder a kivont szöveg tárolására
StringBuilder builder = new StringBuilder();
```

 Inicializáljuk a`StringBuilder`példány, amely összegyűjti az egyes oldalakról kivont szöveget. Hatékonyabb módja a nagy karakterláncok kezelésének, mint a hurokban történő szokásos karakterlánc-összefűzés.

## 3. lépés: Lapozzon át PDF-oldalakon

 Ezután végigpörgetjük a PDF-dokumentum minden oldalát a szöveg kinyeréséhez. Minden oldalt egyenként dolgozunk fel a`TextDevice` osztály, amely a PDF tartalom szöveges formátumba konvertálásáért felelős.

```csharp
// Lapozzon végig a PDF összes oldalán
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Minden oldal feldolgozása szövegkivonathoz
}
```

Ez a ciklus végigmegy a PDF minden oldalán (`pdfDocument.Pages` ). Minden oldalról kivonjuk a szöveget, és hozzáadjuk a mi oldalunkhoz`StringBuilder`.

## 4. lépés: Szöveg kibontása minden oldalról

 Most minden oldalhoz beállítjuk a szövegkivonási folyamatot. Itt létrehozunk egy`TextDevice` objektumot, és használja a PDF-oldalak feldolgozásához. A`TextDevice` nyers vagy formázott szöveget bont ki az általunk beállított kinyerési beállítások alapján.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Hozzon létre egy szövegeszközt szövegkivonathoz
    TextDevice textDevice = new TextDevice();
    
    // Állítsa a szövegkivonási beállításokat „Tiszta” módra
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Szöveg kibontása az aktuális oldalról, és mentse a memóriafolyamba
    textDevice.Process(pdfPage, textStream);

    // Memóriafolyam átalakítása szöveggé
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // A kibontott szöveg hozzáfűzése a StringBuilderhez
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : A`TextDevice` osztályt használjuk a szöveg kinyerésére a PDF-ből.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Ez az opció kivonja a nyers szöveget anélkül, hogy megtartana bármilyen formázást, például betűtípusokat vagy pozíciókat. Használhatod is`TextFormattingMode.Raw` ha nagyobb ellenőrzésre van szüksége a formázás felett.
- `textDevice.Process(pdfPage, textStream);` : Ez feldolgozza a PDF minden oldalát, és a kivonatolt szöveget a`MemoryStream`.
-  Végül konvertáljuk a szöveget a`MemoryStream` egy karakterlánchoz, és fűzze hozzá a`StringBuilder`.

## 5. lépés: A kibontott szöveg mentése fájlba

 Az összes oldal feldolgozása után a szöveg a`StringBuilder`. Az utolsó lépés a kibontott szöveg mentése egy fájlba.

```csharp
// Határozza meg a szövegfájl kimeneti útvonalát
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Mentse el a kicsomagolt szöveget egy fájlba
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Ez írja a teljes tartalmát`StringBuilder` szöveges fájlba.
- A kimeneti fájl elérési útját egy fájlnév (`"input_Text_Extracted_out.txt"` ) a`dataDir` útvonal.

## Következtetés

szöveg kinyerése PDF-ből az Aspose.PDF for .NET használatával egyszerű és hatékony folyamat. Az ebben az útmutatóban ismertetett lépések követésével könnyedén megnyithat PDF-dokumentumokat, lapozhat az oldalakon, és szöveget szövegfájlba bonthat ki. Ez különösen hasznos nagy mennyiségű PDF-adat feldolgozásához, szövegelemzéshez vagy dokumentumok további manipulációhoz való konvertálásához.

Az Aspose.PDF segítségével nem korlátozódhat a szövegkivonatokra – kezelheti a megjegyzéseket, manipulálhat képeket, vagy akár PDF-eket konvertálhat más formátumokba, például HTML- vagy Word-formátumba. A könyvtár rugalmassága és teljesítménye felbecsülhetetlen értékű eszközzé teszi a .NET-alkalmazások PDF-kezeléséhez.

## GYIK

### Az Aspose.PDF ki tudja bontani a szöveget képalapú PDF-ekből?
Nem, az Aspose.PDF-et arra tervezték, hogy szöveget kinyerjen a tartalomalapú PDF-ekből. Kép alapú PDF-ekhez OCR technológia szükséges.

### Az Aspose.PDF megőrzi a formázást a szöveg kibontásakor?
Alapértelmezés szerint a szöveg formázás nélkül kerül kibontásra, de módosíthatja a kivonatolási beállításokat, ha meg szeretné tartani a formázást.

### Kivonhatok szöveget egy adott oldaltartományból?
Igen, módosíthatja a kódot úgy, hogy az összes oldal helyett egy adott oldaltartományon futjon át.

### Melyek az Aspose.PDF szövegkivonási módjai?
Az Aspose.PDF két módot kínál: nyers és tiszta. A Nyers mód megpróbálja megőrizni az eredeti elrendezést, míg a Pure mód csak a szöveget bontja ki formázás nélkül.

### Az Aspose.PDF for .NET kompatibilis a .NET Core programmal?
Igen, az Aspose.PDF for .NET teljes mértékben kompatibilis a .NET Core és a .NET Framework programmal.