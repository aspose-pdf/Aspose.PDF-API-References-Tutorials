---
title: Rajzolj XForm-ot az oldalra
linktitle: Rajzolj XForm-ot az oldalra
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre XForm űrlap PDF-oldalra történő rajzolásához az Aspose.PDF for .NET használatával. Adja hozzá és helyezze el az űrlapot az oldalon.
type: docs
weight: 10
url: /hu/net/programming-with-operators/draw-xform-on-page/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan rajzolhat XForm-ot egy oldalra az Aspose.PDF for .NET használatával. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását, kezelését és konvertálását. Az Aspose.PDF által biztosított operátorok használatával XForm űrlapot adhat hozzá és helyezhet el egy meglévő PDF-oldalon.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Visual Studio .NET keretrendszerrel telepítve.
2. Az Aspose.PDF könyvtár a .NET-hez.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új projektet a Visual Studióban, és adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz. Letöltheti a könyvtárat az Aspose hivatalos webhelyéről, és telepítheti a gépére.

## 2. lépés: Importálja a szükséges névtereket

A C# kódfájlba importálja az Aspose.PDF által biztosított osztályok és metódusok eléréséhez szükséges névtereket:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 3. lépés: Fájlútvonalak beállítása

Határozza meg a háttérkép, a bemeneti PDF-fájl és a kimeneti PDF-fájl elérési útját:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Feltétlenül adja meg a tényleges fájl elérési utat a gépén.

## 4. lépés: A bemeneti PDF fájl betöltése

A bemeneti PDF fájl betöltéséhez használja a következő kódot:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// A következő kód a GSave/GRestore operátorokat használja
// A kód a ContatenateMatrix operátort használja az XForm pozicionálására
// A kód a Do operátor segítségével rajzolja meg az XForm-ot az oldalon
// A GSave/GRestore operátorok csomagolják a meglévő tartalmat
//ez azért történik, hogy a meglévő tartalom végén megkapjuk a kezdeti grafikus állapotot
// ellenkező esetben nem kívánt átalakítások maradhatnak a meglévő operátorok láncának végén
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Adja hozzá a GSave operátort a grafikus állapot megfelelő visszaállításához az új parancsok után
pageContents. Add(new GSave());

// Hozd létre az XForm-ot
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Állítsa be a kép szélességét és magasságát
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Töltse be a képet egy adatfolyamba
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Adja hozzá a képet az XForm erőforrás képgyűjteményéhez
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// A Do operátor használata: ez az operátor rajzolja meg a képet
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Pozícionálja az XForm-ot x=100 és y=500 koordinátákra
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Rajzolja meg az XForm-ot a Do operátorral
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Helyezze az XForm-ot x=100 és y=300 koordinátákra
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Rajzolja meg az XForm-ot a Do operátorral
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Állítsa vissza a grafikus állapotot a GRestore segítségével a GSave után
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Feltétlenül adja meg a tényleges fájl elérési utat, és szükség szerint állítsa be az oldalszámot és az XForm pozíciókat.

### A Draw XForm On Page minta forráskódja az Aspose.PDF for .NET használatával
 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// A minta bemutatja
	// GSave/GRestore operátorok használata
	// ContatenateMatrix operátor használata xForm pozícióban
	//Használja az operátort az xForm megrajzolásához az oldalon
	// Csomagolja be a meglévő tartalmat a GSave/GRestore operátorpárral
	// ez a kezdeti grafikus állapot elérése a és a meglévő tartalomnál
	// ellenkező esetben a meglévő operátori lánc végén maradhatnak nemkívánatos átalakulások
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// A grafikus állapot mentése operátor hozzáadása az új parancsok utáni grafikus állapot megfelelő törléséhez
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Hozzon létre xForm-ot
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Határozza meg a kép szélességét és magasságát
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Kép betöltése adatfolyamba
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Kép hozzáadása az XForm Resources képgyűjteményéhez
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do operátor használata: ez az operátor képet rajzol
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Helyezze el az űrlapot az x=100 y=500 koordinátákra
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Rajzolj űrlapot a Do operátorral
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Helyezze az űrlapot az x=100 y=300 koordinátákra
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Rajzolj űrlapot a Do operátorral
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Állítsa vissza a grafikus állapotot a GRestore segítségével a GSave után
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan rajzolhat XForm űrlapot PDF-oldalra az Aspose.PDF for .NET használatával. A leírt lépéseket követve hozzáadhat és elhelyezhet egy XForm űrlapot egy meglévő oldalon, így nagyobb rugalmasságot biztosít PDF-dokumentumai számára.

### GYIK az XForm sorsoláshoz a oldalon

#### K: Mi az az XForm az Aspose.PDF-ben?

V: Az XForm egy újrafelhasználható grafikus objektum egy PDF dokumentumban. Lehetővé teszi összetett grafikák, képek vagy szövegek definiálását és rajzolását, amelyeket többször is fel lehet használni különböző oldalakon.

#### K: Hogyan importálhatom a szükséges névtereket az Aspose.PDF fájlhoz?

 V: A C# kódfájlban használja a`using` direktíva az Aspose.PDF által biztosított osztályok és metódusok eléréséhez szükséges névterek importálásához:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### K: Mi a GSave és GRestore operátorok célja?

 V: A`GSave` és`GRestore` Az Aspose.PDF fájl operátorai a grafikus állapot mentésére és visszaállítására szolgálnak. Segítenek abban, hogy a tartalom egy szakaszára alkalmazott átalakítások és beállítások ne legyenek hatással a következő szakaszokra.

#### K: Hogyan definiálhatok egy XFormot az Aspose.PDF használatával?

 V: XForm létrehozásához használja a`XForm.CreateNewForm` módszert, és add hozzá a`Resources.Forms` egy adott oldal gyűjteménye. Ezután tartalmat adhat hozzá az XFormhoz`Contents` ingatlan.

#### K: Hogyan rajzolhatok képet egy XFormban?

V: Töltse be a képet egy adatfolyamba, és adja hozzá a`Resources.Images` az XForm gyűjtemény. Használja a`Do` operátor az XForm-on belül`Contents` megrajzolni a képet.

#### K: Hogyan helyezhetek el egy XFormot egy PDF-oldalon?

 V: Egy XForm oldalra helyezéséhez használja a`ConcatenateMatrix` operátor az oldalon belül`Contents`. Módosítsa a mátrix paramétereit az XForm fordításának (pozíciójának) és skálázásának megadásához.

#### K: Rajzolhatok több XFormot ugyanarra az oldalra?

 V: Igen, több XForm-ot is rajzolhat ugyanarra az oldalra a`ConcatenateMatrix` paramétereket, hogy az egyes XFormokat különböző koordinátákra helyezze.

#### K: Módosíthatom egy XForm tartalmát a létrehozása után?

 V: Igen, a létrehozás után módosíthatja az XForm tartalmát, ha további operátorokat ad hozzá`Contents` ingatlan.

#### K: Mi történik, ha kihagyom a GSave és GRestore operátorokat?

V: A GSave és GRestore operátorok elhagyása nem kívánt átalakításokhoz vagy beállításokhoz vezethet a következő tartalomhoz. Használatuk segít fenntartani a tiszta grafikai állapotot.

#### K: Használhatom újra az XForms-ot a PDF-dokumentum különböző oldalain?

 V: Igen, az XFormokat több oldalon is felhasználhatja, ha hozzáadja ugyanazt az XForm-ot az oldalhoz`Resources.Forms` különböző oldalak gyűjteménye.

#### K: Van-e korlát a létrehozható XForm-ok számának?

V: Bár a létrehozható XFormok számának nincs szigorú korlátozása, ne feledje, hogy a túl sok XForm hatással lehet a teljesítményre és a memóriahasználatra. Használja őket megfontoltan.

#### K: Forgathatok egy XFormot vagy alkalmazhatok más átalakításokat?

 V: Igen, használhatja a`ConcatenateMatrix` operátort, hogy transzformációkat, például elforgatást, skálázást és fordítást alkalmazzon egy XForm-re.
