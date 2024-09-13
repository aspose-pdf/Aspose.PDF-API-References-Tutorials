---
title: Oszlopok szövegének kibontása PDF-fájlban
linktitle: Oszlopok szövegének kibontása PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthatja ki az oszlopok szövegét PDF-fájlból az Aspose.PDF for .NET segítségével.
type: docs
weight: 150
url: /hu/net/programming-with-text/extract-columns-text/
---
Ez az oktatóanyag végigvezeti Önt az oszlopok szövegének PDF-fájlba történő kibontásán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelybe az oszlopok szövegét ki szeretné bontani, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Nyissa meg a PDF dokumentumot
 Nyisson meg egy meglévő PDF dokumentumot a`Document`konstruktort, és átadja a bemeneti PDF-fájl elérési útját.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 5. lépés: Állítsa be a betűméretet
Csökkentse a szövegrészletek betűméretét 0,7-szeresére az olvashatóság javítása és az oszlopos szöveg jobb megjelenítése érdekében.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## 6. lépés: Szöveg kibontása az oszlopokból
 Mentse el a módosított PDF dokumentumot egy memóriafolyamba, és töltse be újra új dokumentumként. Ezután használja a`TextAbsorber` osztályt, hogy kivonja a szöveget az oszlopokból.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## 7. lépés: Mentse el a kicsomagolt szöveget
Mentse a kibontott szöveget egy szövegfájlba a megadott kimeneti fájl elérési útján.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Minta forráskód az Oszlopok szövegének kibontásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// A betűméretet legalább 70%-kal csökkenteni kell
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Következtetés
Sikeresen kinyerte az oszlopok szövegét egy PDF-dokumentumból az Aspose.PDF for .NET használatával. A kivont szöveget a rendszer a megadott kimeneti fájlba mentette.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ez az oktatóanyag lépésről lépésre nyújt útmutatót a szövegoszlopok PDF-fájlból való kibontásához az Aspose.PDF for .NET használatával. A mellékelt C# forráskód gyakorlati bemutatót nyújt a szükséges eljárásokról.

#### K: Milyen névtereket kell importálnom?

V: Abba a kódfájlba, amelybe szövegoszlopokat kíván kivonni, a fájl elejére írja be a következőket direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: Keresse meg a vonalat`string dataDir = "YOUR DOCUMENT DIRECTORY";` a kódban és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan nyithatok meg egy meglévő PDF-dokumentumot?

 V: A 4. lépésben megnyit egy meglévő PDF-dokumentumot a`Document` konstruktort, és megadja a bemeneti PDF-fájl elérési útját.

#### K: Miért van módosítva a betűméret?

V: Az 5. lépésben a szövegrészletek betűméretét 0,7-szeresére csökkentjük. Ez a beállítás javítja az olvashatóságot, és pontosabban jeleníti meg az oszlopos szöveget.

#### K: Hogyan vonhatok ki szöveget az oszlopokból?

 V: A 6. lépésben a módosított PDF-dokumentumot elmenti egy memóriafolyamba, új dokumentumként betölti, majd a`TextAbsorber` osztályt, hogy kivonja a szöveget az oszlopokból.

#### K: Mi a célja a kivont szöveg mentésének?

V: A 7. lépésben a kibontott szöveget a megadott kimeneti fájl elérési útvonalán lévő szövegfájlba menti.

#### K: Miért kell csökkenteni a betűméretet a kibontás előtt?

V: A betűméret csökkentése segít abban, hogy a kivonatolt szöveg megfelelően igazodjon az oszlopokon belülre, így az eredeti elrendezés pontosabb megjelenítése.

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megszerezte azokat az ismereteket és készségeket, amelyek szükségesek ahhoz, hogy szövegoszlopokat bontsanak ki egy PDF-dokumentumból az Aspose.PDF for .NET használatával. Az eredményül kapott szöveget elmentette a megadott kimeneti fájlba.