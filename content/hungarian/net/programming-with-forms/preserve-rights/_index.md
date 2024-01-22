---
title: Jogok megőrzése
linktitle: Jogok megőrzése
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével megőrizheti az űrlapjogokat PDF-dokumentumaiban.
type: docs
weight: 210
url: /hu/net/programming-with-forms/preserve-rights/
---
Ebben az oktatóanyagban bemutatjuk, hogyan őrizheti meg az űrlapjogokat egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Nyissa meg a dokumentumot

 Nyissa meg a PDF forrásdokumentumot az a`FileStream` olvasási és írási engedéllyel:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 3. lépés: Szerkessze az űrlapmezőket

Menjen végig a dokumentum összes űrlapmezőjén, és hajtsa végre a szükséges módosításokat. Ebben a példában egy olyan űrlapmező értékét változtatjuk meg, amelynek nevében az "A1" szerepel:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## 4. lépés: Mentse el a frissített dokumentumot

Mentse el a módosított PDF dokumentumot:

```csharp
pdfDocument.Save();
```

##  5. lépés: Zárja be a`FileStream`

 Ne felejtse el bezárni a`FileStream` objektum, ha végzett:

```csharp
fs. Close();
```

### Preserve Rights minta forráskódja az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Olvassa el a forrás PDF űrlapot a FileAccess of Read and Write segítségével.
// ReadWrite engedélyre van szükségünk, mert a módosítás után
// A frissített tartalmat ugyanabba a dokumentumba/fájlba kell mentenünk.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Példányos dokumentum példány
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Értékek lekérése az összes mezőből
foreach (Field formField in pdfDocument.Form)
{
	// Ha a mező teljes neve A1-et tartalmaz, hajtsa végre a műveletet
	if (formField.FullName.Contains("A1"))
	{
		// Szövegdobozként leadott űrlapmező
		TextBoxField textBoxField = formField as TextBoxField;
		// Módosítsa a mező értékét
		textBoxField.Value = "Testing";
	}
}
// Mentse el a frissített dokumentumot a FileStream mentésében
pdfDocument.Save();
// Zárja be a File Stream objektumot
fs.Close();
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan őrizhetjük meg egy PDF-dokumentumban lévő űrlap jogait az Aspose.PDF for .NET használatával. Ha követi ezeket a lépéseket, könnyedén elérheti az űrlapmezőket, és végrehajthat konkrét módosításokat, miközben megőrzi a hozzáférési és írási engedélyeket.


### GYIK

#### K: Megőrizhetem bizonyos űrlapmezők jogait anélkül, hogy ez másokat érintene a PDF-dokumentumban?

 V: Igen, a`FullName` Az űrlapmezők tulajdonságával megcélozhat bizonyos űrlapmezőket megőrzés céljából, miközben másokat nem érint.

#### K: Megőrizhetem az űrlap jogait egy jelszóval védett PDF dokumentumban?

V: Igen, az Aspose.PDF for .NET lehetővé teszi az űrlapok jogainak megőrzését még a jelszóval védett PDF dokumentumokban is, amennyiben megadja a megfelelő jelszót a fájl eléréséhez és módosításához.

#### K: Mi történik, ha az űrlapmezőket a megfelelő hozzáférési jogok nélkül próbálom meg módosítani?

V: Ha megfelelő hozzáférési jogok nélkül próbálja meg módosítani az űrlapmezőket, a módosítások nem kerülnek mentésre a PDF dokumentumban, és kivételt vagy hibaüzenetet kaphat.

#### K: Az Aspose.PDF for .NET kompatibilis a .NET Framework összes verziójával?

V: Igen, az Aspose.PDF for .NET kompatibilis a .NET Framework összes verziójával, beleértve a .NET Core-t és a .NET Standardot is.

#### K: Megőrizhetem-e az űrlapjogokat egy PDF-dokumentumban programozottan a C#-on kívül más programozási nyelveken is?

V: Igen, az Aspose.PDF for .NET a C# mellett különböző programozási nyelveket is támogat, mint például a VB.NET és az ASP.NET.