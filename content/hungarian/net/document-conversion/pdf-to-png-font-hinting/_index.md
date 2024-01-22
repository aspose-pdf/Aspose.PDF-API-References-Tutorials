---
title: PDF-ből PNG-be font tippelés
linktitle: PDF-ből PNG-be font tippelés
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató PDF-formátum PNG-formátumba konvertálásához font-utalással az Aspose.PDF for .NET használatával.
type: docs
weight: 160
url: /hu/net/document-conversion/pdf-to-png-font-hinting/
---
Ebben az oktatóanyagban végigvezetjük a PDF-fájlok PNG-képekké konvertálásának folyamatán az Aspose.PDF for .NET használatával, miközben engedélyezi a betűtípus-hivatkozást. A betűtípus-hivatkozás egy olyan technika, amely javítja a kis betűtípusok olvashatóságát. Az alábbi lépések követésével a PDF minden oldalát PNG-képpé konvertálhatja betűtípus-utalással.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: Nyissa meg a PDF forrásdokumentumot
Ebben a lépésben megnyitjuk a forrás PDF-fájlt az Aspose.PDF for .NET használatával. Kövesse az alábbi kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol a PDF-fájl található.

## 2. lépés: Engedélyezze a betűtípus utalást
PDF fájl megnyitása után engedélyezzük a betűtípus utalást a renderelési beállítások segítségével. Használja a következő kódot:

```csharp
// Hozzon létre renderelési beállításokat a betűtípus utalás engedélyezéséhez
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## 3. lépés: PNG-képek konvertálása
Most a PDF-fájl minden oldalát PNG-képpé konvertáljuk, betűtípus utalással. Használja a következő kódot:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Hozzon létre egy PNGDevice objektumot a megadott attribútumokkal
         // Szélesség, magasság, felbontás, minőség
         // Minőség [0-100], 100 a maximum
         // Hozzon létre egy Resolution objektumot
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Állítson be előre meghatározott megjelenítési beállításokat
         pngDevice.RenderingOptions = opts;

         // Konvertálja az adott oldalt, és mentse a képet a streambe
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Zárd be a patakot
         imageStream.Close();
     }
}
```

A fenti kód a PDF-fájl minden oldalát PNG-képpé konvertálja betűtípus utalással, és minden képet külön PNG-fájlként ment.

### Példa forráskód PDF-hez PNGFont-hitelesítéshez az Aspose.PDF for .NET használatával

```csharp
try
{
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Nyissa meg a dokumentumot
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Hozzon létre Aspose.Pdf.RenderingOptions-t a betűtípus-hivatkozás engedélyezéséhez
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// PNG-eszköz létrehozása megadott attribútumokkal
			// Szélesség, magasság, felbontás, minőség
			// Minőség [0-100], 100 a maximum
			// Hozzon létre Resolution objektumot
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Állítson be előre meghatározott megjelenítési beállításokat
			pngDevice.RenderingOptions = opts;

			//Konvertálja az adott oldalt, és mentse a képet adatfolyamba
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Folyamat bezárása
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés
Ebben az oktatóanyagban lépésről lépésre bemutattuk a PDF PNG-képek konvertálásának folyamatát betűtípus-utalással az Aspose.PDF for .NET használatával. A fent ismertetett utasításokat követve most már képesnek kell lennie arra, hogy a PDF-fájl minden oldalát PNG-képpé konvertálja font-utalással. Ez a funkció akkor hasznos, ha meg akarja őrizni a kis betűtípusok olvashatóságát PNG-képekké konvertáláskor.

### GYIK

#### K: Mi az a betűtípus-hivatkozás, és miért fontos a PDF PNG-re konvertálásakor?

V: A betűtípus-hivatkozás egy olyan technika, amelyet a kis betűtípusok olvashatóságának javítására használnak formájuk és elhelyezkedésük módosításával. A PDF PNG-képekké konvertálásakor a betűtípus utalás engedélyezése biztosítja, hogy a kapott PNG-képek szövege olvasható és tiszta maradjon, különösen kis betűméretek esetén. Ez fontos a szöveg minőségének és olvashatóságának megőrzéséhez a PDF-dokumentumok képpé konvertálásakor.

#### K: Hogyan befolyásolja a betűtípus utalása a PNG konverziós folyamatot?

V: A betűtípus utalása befolyásolja a szöveg megjelenítési módját a kapott PNG-képekben a PDF-ből PNG-be konvertálási folyamat során. A betűtípus utalás engedélyezésével az Aspose.PDF könyvtár úgy állítja be a betűtípus megjelenítését, hogy a kis betűtípusok megőrizzék tisztaságukat és olvashatóságukat, így a PNG-képek látványosabbá és olvashatóbbá válnak.

#### K: Módosíthatom a betűtípus utalás beállításait a PNG-konverzió testreszabásához?

 V: Igen, az Aspose.PDF for .NET könyvtár lehetőséget biztosít a PNG-konverziós folyamat testreszabására, beleértve a betűtípus-hivatkozás beállításait. A megadott kódpéldában a`UseFontHinting` tulajdona a`RenderingOptions` objektumra van beállítva`true` a betűtípus utalás engedélyezéséhez. Tovább finomíthatja az átalakítási folyamatot, ha más tulajdonságokat állít be a`RenderingOptions` osztály az Ön igényei szerint.

#### K: Hogyan kerülnek mentésre a PNG képek a PNG átalakítási folyamat során?

V: A megadott kódpéldában a PDF-dokumentum minden oldala külön PNG-képpé lesz konvertálva. A PNG-képeket a rendszer külön fájlokként menti, a következő fájlnevekkel: „image{pageCount}_ out.png", ahol`{pageCount}` a konvertálandó oldal száma. Minden PNG-kép az eredeti PDF-dokumentum egy oldalát képviseli.