---
title: Szöveg kibontása szövegeszközzel
linktitle: Szöveg kibontása szövegeszközzel
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthat ki szöveget PDF-dokumentumból az Aspose.PDF for .NET szövegeszközével.
type: docs
weight: 210
url: /hu/net/programming-with-text/extract-text-using-text-device/
---
Ez az oktatóanyag végigvezeti Önt a PDF-dokumentumból a szöveg kinyerésének folyamatán az Aspose.PDF for .NET fájlban található Text Device segítségével. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelybe szöveget szeretne kivonni, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Nyissa meg a PDF dokumentumot
 Nyisson meg egy meglévő PDF dokumentumot a`Document`konstruktort, és átadja a bemeneti PDF-fájl elérési útját.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 5. lépés: Szöveg kibontása a Text Device segítségével
 Hozzon létre egy`StringBuilder` objektum a kivont szöveg tárolására. Ismételje meg a dokumentum minden oldalát, és használja a a`TextDevice` hogy kinyerjük a szöveget minden oldalról.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## 6. lépés: Mentse el a kicsomagolt szöveget
 Adja meg a kimeneti fájl elérési útját, és mentse a kibontott szöveget egy szövegfájlba a segítségével`File.WriteAllText` módszer.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Minta forráskód a szöveg kibontásához szövegeszközzel az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Karakterlánc a kivont szöveg tárolására
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Szövegeszköz létrehozása
		TextDevice textDevice = new TextDevice();
		// Szövegkivonási beállítások megadása – szövegkivonási mód beállítása (nyers vagy tiszta)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konvertálja az adott oldalt, és mentse el a szöveget az adatfolyamba
		textDevice.Process(pdfPage, textStream);
		// Konvertálja az adott oldalt, és mentse el a szöveget az adatfolyamba
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Memóriafolyam bezárása
		textStream.Close();
		// Szöveg lekérése a memóriafolyamból
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Mentse el a kibontott szöveget szövegfájlba
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Következtetés
Sikeresen kibontotta a szöveget egy PDF-dokumentumból az Aspose.PDF for .NET szövegeszközével. A kivont szöveget a rendszer a megadott kimeneti fájlba mentette.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ez az oktatóanyag útmutatást ad a szöveg PDF-dokumentumból történő kibontásához az Aspose.PDF for .NET szövegeszköz funkciójával. A mellékelt C# forráskód bemutatja a feladat végrehajtásához szükséges lépéseket.

#### K: Milyen névtereket kell importálnom?

V: Abba a kódfájlba, amelybe szöveget kíván kivonni, a fájl elején direktívák használatával adja meg a következőket:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: Keresse meg a kódban azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan nyithatok meg egy meglévő PDF-dokumentumot?

 V: A 4. lépésben megnyit egy meglévő PDF-dokumentumot a`Document` konstruktort, és megadja a bemeneti PDF-fájl elérési útját.

#### K: Hogyan bonthatok ki szöveget a szöveges eszközzel?

 V: Az 5. lépés az a`StringBuilder` objektum a kivont szöveg tárolására. Ezután a dokumentum minden oldalát végig kell ismételni, és a a`TextDevice` együtt`TextExtractionOptions` hogy minden oldalról szöveget vonjunk ki.

#### K: Hogyan menthetem el a kicsomagolt szöveget fájlba?

 V: A 6. lépésben adja meg a kimeneti fájl elérési útját, és használja a`File.WriteAllText`módszer a kivont szöveg szövegfájlba mentésére.

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan használhatja ki az Aspose.PDF for .NET-ben található Text Device funkcióját, hogy szöveget vonjon ki egy PDF-dokumentumból. A kibontott szöveget a rendszer egy megadott kimeneti fájlba menti, lehetővé téve a kibontott tartalom szükség szerinti kezelését és felhasználását.