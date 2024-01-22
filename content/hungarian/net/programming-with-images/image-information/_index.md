---
title: Képinformációk PDF fájlban
linktitle: Képinformációk PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: A képinformációk kibontása PDF-fájlba az Aspose.PDF for .NET használatával.
type: docs
weight: 160
url: /hu/net/programming-with-images/image-information/
---
Ez az útmutató lépésről lépésre bemutatja, hogyan nyerhet ki információkat a képekről PDF-fájlban az Aspose.PDF for .NET segítségével. Győződjön meg arról, hogy már beállította a környezetet, és kövesse az alábbi lépéseket:

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 Ügyeljen arra, hogy a megfelelő dokumentumkönyvtárat állítsa be. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban annak a könyvtárnak az elérési útjával, ahol a PDF-dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a forrás PDF-fájlt

 Ebben a lépésben betöltjük a forrás PDF-fájlt a`Document` osztályú Aspose.PDF. Használja a`Document` konstruktort, és adja át a PDF dokumentum elérési útját.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 3. lépés: Állítsa be az alapértelmezett felbontást

Ebben a lépésben beállítjuk a képek alapértelmezett felbontását. A példában az alapértelmezett felbontás 72.

```csharp
int defaultResolution = 72;
```

## 4. lépés: Inicializálja az objektumokat és a számlálókat

Ebben a lépésben inicializáljuk a képinformációk lekéréséhez szükséges objektumokat és számlálókat.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 5. lépés: Váltson végig a dokumentum első oldalán lévő operátorokon

Ebben a lépésben végigjárjuk a dokumentum első oldalán található operátorokat, hogy azonosítsuk a képpel kapcsolatos műveleteket.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 6. lépés: Az operátorok kezelése és a képinformációk kibontása

Ebben a lépésben kezeljük a különböző típusú operátorokat, és kinyerjük a képekre vonatkozó információkat.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Kezelje a GSave és GRestore műveleteket az átalakításokhoz
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Kezelje a ConcatenateMatrix műveletet az átalakításokhoz
else if (opCtm != null)
{
     // Alkalmazza a transzformációs mátrixot
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// A képekhez kezelje a Do műveletet
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Töltse le a képet
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Keresse meg a kép méreteit
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Számítsa ki a felbontást a fenti adatok alapján
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Képinformációk megjelenítése
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Minta forráskód a képinformációkhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Töltse be a forrás PDF-fájlt
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Adja meg a kép alapértelmezett felbontását
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Határozzon meg egy tömblista objektumot, amely a képneveket tartalmazza
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Helyezzen be egy objektumot a halmozáshoz
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Szerezze meg az összes operátort a dokumentum első oldalán
foreach (Operator op in doc.Pages[1].Contents)
{
	// Használja a GSave/GRestore operátorokat az átalakítások visszaállításához az előzőleg beállított értékre
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Példányosítsa a ConcatenateMatrix objektumot, ahogyan az az aktuális transzformációs mátrixot határozza meg.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Hozzon létre Do operátort, amely objektumokat rajzol az erőforrásokból. Űrlapobjektumokat és Képobjektumokat rajzol
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Mentse el az előző állapotot, és tolja a jelenlegi állapotot a verem tetejére
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Dobja el a jelenlegi állapotot, és állítsa vissza az előzőt
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Szorozzuk meg az árammátrixot az állapotmátrixszal
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Abban az esetben, ha ez egy képrajzi operátor
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Hozzon létre XImage objektumot az első pdf-oldal képeinek tárolására
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Szerezze meg a kép méreteit
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Get magassági és szélességi információkat a kép
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Számítsa ki a felbontást a fenti információk alapján
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Az egyes képek méretére és felbontására vonatkozó információk megjelenítése
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Következtetés

Gratulálok ! Most már megtanulta, hogyan bonthat ki képadatokat PDF-fájlból az Aspose.PDF for .NET segítségével. Ezeket az információkat különféle képfeldolgozási feladatokhoz használhatja alkalmazásaiban.

### GYIK a képadatokhoz PDF-fájlban

#### K: Mi a célja a képadatok kinyerésének egy PDF-dokumentumból az Aspose.PDF for .NET használatával?

V: A képinformációk PDF-dokumentumból való kinyerése betekintést nyújt a dokumentumon belüli képek méretébe, felbontásába és egyéb jellemzőibe. Ezek az információk felhasználhatók képfeldolgozási, elemzési vagy optimalizálási feladatokhoz.

#### K: Hogyan segíti az Aspose.PDF for .NET a képinformációk kinyerését egy PDF-dokumentumból?

V: Az Aspose.PDF for .NET eszközöket biztosít a PDF-dokumentumok tartalmának eléréséhez és elemzéséhez, beleértve a képeket. A mellékelt kód bemutatja, hogyan lehet kinyerni és megjeleníteni a képinformációkat különböző operátorok segítségével.

#### K: Milyen képinformáció nyerhető ki ezzel a módszerrel?

V: Ez a módszer lehetővé teszi olyan információk kinyerését és megjelenítését, mint a méretezett méretek, felbontás és képnevek a PDF-dokumentumban lévő képekhez.

#### K: Hogyan azonosítja és dolgozza fel a kód a képpel kapcsolatos operátorokat egy PDF-dokumentumban?

V: A kód az operátorokon keresztül iterál a PDF-dokumentum egy meghatározott oldalán. A képműveletekhez, átalakításokhoz és rendereléshez kapcsolódó operátorokat azonosítja és dolgozza fel.

#### K: Mi a jelentősége az alapértelmezett felbontásnak, és hogyan használják a kódban?

V: Az alapértelmezett felbontás referenciapontként szolgál a képek tényleges felbontásának kiszámításához. A kód kiszámítja az egyes képek felbontását azok méretei és az alapértelmezett felbontási beállítások alapján.

#### K: Hogyan lehet a kinyert képinformációkat hasznosítani valós helyzetekben?

V: A kinyert képinformáció felhasználható olyan feladatokhoz, mint a képminőség értékelése, képoptimalizálás, képbélyegképek generálása és a képpel kapcsolatos döntéshozatali folyamatok megkönnyítése.

#### K: Módosíthatom a kódot további képekkel kapcsolatos attribútumok kinyeréséhez?

V: Igen, testreszabhatja a kódot a képek további attribútumainak, például színterének, pixelmélységének vagy képtípusának kinyeréséhez.

#### K: A képinformáció-kinyerési folyamat erőforrás- vagy időigényes?

V: A képinformáció-kinyerési folyamat hatékony és a teljesítményre optimalizált, minimális hatást biztosítva az erőforrás-felhasználásra és a feldolgozási időre.

#### K: Hogyan profitálhatnak a fejlesztők a képinformációk azonosításából és PDF-dokumentumokból történő kinyeréséből?

V: A fejlesztők betekintést nyerhetnek a PDF-dokumentumokban lévő képek jellemzőibe, lehetővé téve számukra, hogy megalapozott döntéseket hozzanak a képkezeléssel, -feldolgozással és -optimalizálással kapcsolatban.

#### K: Használható ez a módszer képeket tartalmazó PDF dokumentumok kötegelt feldolgozására?

V: Igen, ez a módszer kiterjeszthető kötegelt feldolgozásra több oldal vagy dokumentum iterációjával, képinformációk kinyerésével és képpel kapcsolatos feladatok végrehajtásával.