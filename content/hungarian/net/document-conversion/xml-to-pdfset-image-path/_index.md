---
title: XML to PDFSet Image Path
linktitle: XML to PDFSet Image Path
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a kép elérési útjának beállításához, amikor XML-t PDF-be konvertál az Aspose.PDF for .NET segítségével.
type: docs
weight: 340
url: /hu/net/document-conversion/xml-to-pdfset-image-path/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük, hogyan állíthatja be a kép elérési útját XML-fájl PDF formátumba konvertálásakor az Aspose.PDF könyvtár .NET-hez használatával. Részletesen bemutatjuk a megadott C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe. Az oktatóanyag végére könnyedén megadhatja a kép elérési útját, amikor XML-t PDF-be konvertál.

## 1. lépés: Állítsa be a fájl elérési útját
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Határozza meg a bemeneti XML-fájlok elérési útját, a használandó képet és a kimeneti PDF-fájlt. Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal az elérési úttal, ahová a fájljait mentette.

## 2. lépés: Példányosítson egy dokumentumobjektumot
```csharp
Document doc = new Document();
```
Hozzon létre egy példányt a Dokumentum objektumból.

## 3. lépés: Kapcsolja össze a forrás XML-fájlt
```csharp
doc. BindXml(inXml);
```
Összekapcsolja a forrás XML-fájlt a dokumentummal.

## 4. lépés: Állítsa be a kép elérési útját
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Szerezze le az Image objektum hivatkozást az XML-ből az azonosítójával, és állítsa be a használni kívánt kép elérési útját.

## 5. lépés: Mentse el a kapott PDF-fájlt
```csharp
doc.Save(outFile);
```
Mentse el a kapott PDF-fájlt a megadott könyvtárba.

### Példa forráskód XML-hez PDF-be Állítsa be a kép elérési útját az Aspose.PDF for .NET használatával

```csharp
try
{
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet beállítani egy kép elérési útját az XML PDF-formátumba konvertálásakor az Aspose.PDF könyvtár .NET-hez segítségével. A megadott lépések követésével könnyedén megadhatja a kép elérési útját a saját XML-ben PDF konverziókká.

### GYIK

#### K: Mi a célja a kép elérési útjának beállításának az XML PDF formátumba konvertálásakor?

V: Az XML PDF-be konvertálásakor a kép elérési útjának beállítása lehetővé teszi az XML-ben hivatkozott kép helyének megadását. Ez biztosítja, hogy a kép helyesen jelenjen meg az eredményül kapott PDF-dokumentumban.

#### K: Használhatok képeket különböző könyvtárakból?

 V: Igen, használhat különböző könyvtárakból származó képeket, ha minden egyes képhez megadja a megfelelő fájl elérési utat. A megadott kódban a`inFile` változó tartalmazza a képfájl elérési útját, és frissítheti, hogy a különböző könyvtárakban lévő képekre mutasson.

#### K: Használhatok képeket távoli URL-ről?

V: Igen, használhat távoli URL-ről származó képeket, ha helyi fájl elérési út helyett az URL-t adja meg. Győződjön meg arról, hogy az alkalmazás rendelkezik internet-hozzáféréssel a kép lekéréséhez a távoli URL-ről.

#### K: Milyen formátumú legyen a bemeneti XML fájl?

V: A bemeneti XML-fájlnak olyan szerkezettel kell rendelkeznie, amely egy azonosító segítségével hivatkozik a képre. A megadott kódban a "testImg" azonosító szolgál a képre való hivatkozásra.

#### K: Hozzáadhatok több képet a PDF-hez?

V: Igen, több képet is hozzáadhat a PDF-hez, ha az XML-fájlban különböző azonosítókkal hivatkozik rájuk, és ennek megfelelően állítja be a fájl elérési útját.