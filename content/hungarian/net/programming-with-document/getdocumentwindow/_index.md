---
title: Dokumentum beszerzése ablak
linktitle: Dokumentum beszerzése ablak
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan használhatja az Aspose.PDF for .NET GetDocumentWindow funkcióját a PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekéréséhez.
type: docs
weight: 170
url: /hu/net/programming-with-document/getdocumentwindow/
---
Az Aspose.PDF for .NET egy hatékony PDF-manipulációs könyvtár, amely lehetővé teszi a fejlesztők számára PDF-fájlok létrehozását, szerkesztését és konvertálását .NET-alkalmazásaikban. A könyvtár által kínált szolgáltatások egyike a dokumentum ablaktulajdonságaival kapcsolatos információk lekérése. Ez az oktatóanyag végigvezeti Önt a használatának lépésein`GetDocumentWindow` Az Aspose.PDF for .NET szolgáltatása a PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekéréséhez.

## 1. lépés: Telepítse az Aspose.PDF for .NET fájlt

 Az Aspose.PDF for .NET használatához .NET-alkalmazásaiban először telepítenie kell a könyvtárat. A könyvtár legújabb verzióját letöltheti a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net).

Miután letöltötte a könyvtárat, bontsa ki a ZIP-fájl tartalmát egy mappába a számítógépén. Ezután hozzá kell adnia egy hivatkozást az Aspose.PDF for .NET DLL-hez a .NET projektben.

## 2. lépés: Töltse be a PDF-dokumentumot

 Miután telepítette az Aspose.PDF for .NET fájlt, és hozzáadott egy hivatkozást a DLL-re a .NET projektben, elkezdheti használni a`GetDocumentWindow`funkció a PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekéréséhez.

A funkció használatának első lépése annak a PDF-dokumentumnak a betöltése, amelyről információkat szeretne lekérni. Ehhez a következő kódot használhatja:

```csharp
// A PDF dokumentum elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a PDF dokumentumot
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 A fenti kódban cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a PDF-dokumentum található. Ez a kód betölti a PDF dokumentumot a`Document` objektumot, amelyet aztán a dokumentum ablaktulajdonságaival kapcsolatos információk lekérésére használhat.

## 3. lépés: Nyerje le a dokumentum ablak tulajdonságait

A PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekéréséhez a következő kódot használhatja:

```csharp
// A dokumentum ablak tulajdonságainak lekérése
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

A fenti kódban minden sor lekéri a PDF dokumentum különböző ablaktulajdonságait, és kiadja azt a konzolnak. Ezt a kódot testreszabhatja úgy, hogy csak az Önt érdeklő tulajdonságokat kérje le.

### Példa forráskódra a PDF-fájl dokumentumablakának lekéréséhez az Aspose.PDF for .NET használatával 

 Itt található a teljes forráskód a PDF-dokumentum ablak tulajdonságainak lekéréséhez a`GetDocumentWindow` Az Aspose.PDF .NET-hez funkciója:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Szerezzen be különböző dokumentumtulajdonságokat
// A dokumentum ablakának helyzete - Alapértelmezés: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Túlnyomó olvasási rend; meghatározza az oldal pozícióját
// Ha egymás mellett jelenik meg - Alapértelmezés: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Meghatározza, hogy az ablak címsorában megjelenjen-e a dokumentum címe
// Ha hamis, a címsorban megjelenik a PDF fájl neve – Alapértelmezés: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Meghatározza, hogy át kell-e méretezni a dokumentum ablakát, hogy illeszkedjen a méretéhez
// Elsőként megjelenített oldal - Alapértelmezés: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// A megjelenítő alkalmazás menüsorának elrejtése - Alapértelmezés: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// A megjelenítő alkalmazás eszköztárának elrejtése - Alapértelmezés: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// El kell-e rejteni a felhasználói felület elemeit, például a görgetősávokat
// És csak az oldal tartalma marad meg – Alapértelmezés: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// dokumentum oldalmódja. A dokumentum megjelenítése a teljes képernyős módból való kilépéskor.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Az oldalelrendezés, azaz egyetlen oldal, egy oszlop
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Hogyan jelenjen meg a dokumentum megnyitáskor
// Azaz miniatűrök megjelenítése teljes képernyőn, mellékletpanel megjelenítése
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan használhatja az Aspose.PDF for .NET fájlt a PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekérésére. A PDF-dokumentum betöltésével és az ablak tulajdonságainak elérésével információkat gyűjthet arról, hogy a dokumentum hogyan jelenjen meg a megjelenítő alkalmazásban való megnyitásakor. Az Aspose.PDF for .NET hatékony funkciókat kínál a PDF-fájlok programozott kezeléséhez, így értékes eszköz a .NET-alkalmazások PDF-kezeléséhez.

### GYIK

#### K: Mi a célja a PDF-dokumentum ablak tulajdonságainak lekérésének?

V: A PDF-dokumentum ablaktulajdonságainak lekérése lehetővé teszi, hogy információkat gyűjtsön arról, hogyan kell megjeleníteni a PDF-dokumentumot, ha egy megjelenítő alkalmazásban megnyitja. Ezek a tulajdonságok különféle szempontokat szabályoznak, például az ablak helyzetét, a megjelenítési módot és a felhasználói felület elemeinek láthatóságát.

#### K: Hogyan telepíthetem az Aspose.PDF for .NET fájlt a .NET projektembe?

 V: Az Aspose.PDF for .NET telepítéséhez le kell töltenie a könyvtárat a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net). A letöltés után bontsa ki a ZIP-fájl tartalmát, és adjon hozzá hivatkozást az Aspose.PDF for .NET DLL-hez a .NET-projektben.

#### K: Testreszabhatom a kódot úgy, hogy csak bizonyos ablaktulajdonságokat kérjen le?

V: Igen, testreszabhatja a kódot, hogy lekérjen bizonyos ablaktulajdonságokat, ha kommentálja azokat a sorokat, amelyekre nincs szüksége. A kód minden sora egy adott ablaktulajdonságnak felel meg, így igénye szerint felvehet vagy kizárhat tulajdonságokat.

#### K: Milyen típusú ablaktulajdonságokat kérhetek le az Aspose.PDF for .NET használatával?

V: Az Aspose.PDF for .NET használatával lekérheti a PDF-dokumentumok különféle ablaktulajdonságait, beleértve az ablak középre állítását, az oldalelrendezés beállítását, az eszköztárak és menüsorok megjelenítésének vezérlését stb.