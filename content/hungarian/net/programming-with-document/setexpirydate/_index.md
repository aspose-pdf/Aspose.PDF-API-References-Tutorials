---
title: Állítsa be a lejárati dátumot a PDF-fájlban
linktitle: Állítsa be a lejárati dátumot a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan állíthat be lejárati dátumot PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 300
url: /hu/net/programming-with-document/setexpirydate/
---
Az Aspose.PDF for .NET egy hatékony könyvtár, amely különféle funkciókat biztosít a PDF-fájlok kezeléséhez. Az egyik ilyen funkció a PDF-dokumentum lejárati dátumának beállítása. Ebben az oktatóanyagban végigvezetjük a PDF-dokumentumok lejárati dátumának beállításán az Aspose.PDF for .NET használatával. 

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

Mielőtt elkezdenénk, be kell állítanunk annak a könyvtárnak az elérési útját, ahol a PDF dokumentumunk található. Ezt az elérési utat egy "dataDir" nevű változóban tároljuk.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Új PDF dokumentum létrehozása

 Új PDF dokumentum létrehozásához létre kell hoznunk egy újat`Aspose.Pdf.Document` tárgy. Ezt a következő kóddal tehetjük meg:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 3. lépés: Új oldal hozzáadása a PDF dokumentumhoz

Miután elkészítettük a PDF dokumentumot, új oldalt adhatunk hozzá. Ezt a következő kóddal tehetjük meg:

```csharp
doc.Pages.Add();
```

## 4. lépés: Szöveg hozzáadása a PDF-dokumentumhoz

Miután hozzáadtunk egy oldalt a PDF dokumentumhoz, a segítségével szöveget adhatunk hozzá`Paragraphs` Gyűjtemény. Ezt a következő kóddal tehetjük meg:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## 5. lépés: A PDF lejárati dátumának beállítása JavaScript használatával

A PDF lejárati dátumának beállításához létre kell hoznunk egy JavaScript objektumot. Ezt a következő kóddal tehetjük meg:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Állítsa be a JavaScriptet PDF megnyitási műveletként
doc.OpenAction = javaScript;
```

Ebben a kódban 2017 májusára állítjuk be a lejárati dátumot.

## 6. lépés: Mentse el a PDF-fájlt

 A lejárati dátum beállítása után el kell mentenie a PDF-fájlt. Ehhez használhatja a`Save` módszere a`Document` objektumot, és adja meg azt az elérési utat, ahová a frissített PDF-fájlt menteni szeretné.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF dokumentum mentése
doc.Save(dataDir);
```

### Példa forráskódra a Lejárati dátum beállítása a .NET Aspose.PDF használatával

Íme a teljes példaforráskód a lejárati dátum beállításához az Aspose.PDF for .NET használatával:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum objektum példányosítása
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
doc.Pages.Add();
// Szövegrészlet hozzáadása az oldalobjektum bekezdésgyűjteményéhez
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Hozzon létre JavaScript objektumot a PDF lejárati dátumának beállításához
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Állítsa be a JavaScriptet PDF megnyitási műveletként
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF dokumentum mentése
doc.Save(dataDir);
```

## Következtetés

PDF-dokumentumok lejárati dátumának beállítása az Aspose.PDF for .NET használatával hasznos funkció annak biztosítására, hogy a dokumentum csak meghatározott ideig legyen érvényes. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők egyszerűen beállíthatják a lejárati dátumot, és korlátozott érvényességű PDF-eket hozhatnak létre. Ez a funkció különösen hasznos lehet olyan dokumentumok esetében, amelyeket korlátozott ideig kell elérni vagy terjeszteni.

### GYIK a beállított lejárati dátumhoz PDF fájlban

#### K: Beállíthatok más lejárati dátumot a PDF-dokumentumhoz?

 V: Igen, beállíthat egy másik lejárati dátumot a PDF-dokumentumhoz a JavaScript kód módosításával az 5. lépésben. A bemutatott példában a lejárati dátum 2017 májusa. Más lejárati dátum beállításához módosítania kell a`year` és`month` változókat a JavaScript kódban a kívánt évre és hónapra.

#### K: Mi történik, ha a PDF-dokumentum lejárt?

V: Amikor a PDF-dokumentum lejárt a JavaScript-kódban meghatározottak szerint, a megtekintő figyelmeztető üzenetet jelenít meg, amely jelzi, hogy a fájl lejárt, és a felhasználónak újra van szüksége. Ez a figyelmeztető üzenet a PDF megnyitásakor jelenik meg.

#### K: Használhatok-e konkrét időpontot a lejárati dátum helyett a dátum helyett?

 V: Igen, beállíthat egy konkrét időpontot a lejárati dátumhoz a JavaScript-kódban. Módosítva a`expiry` változót a JavaScript kódban, hogy tartalmazza a kívánt időt, akkor beállíthat egy adott időpontot a lejárati dátumhoz.