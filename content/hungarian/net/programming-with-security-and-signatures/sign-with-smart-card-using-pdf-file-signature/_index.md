---
title: Jelentkezzen intelligens kártyával PDF fájl aláírással
linktitle: Jelentkezzen intelligens kártyával PDF fájl aláírással
second_title: Aspose.PDF for .NET API Reference
description: Biztonságosan írja alá PDF fájljait intelligens kártyával az Aspose.PDF for .NET segítségével.
type: docs
weight: 110
url: /hu/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Az intelligens kártyával történő digitális aláírás a PDF fájlok aláírásának biztonságos módja. Az Aspose.PDF for .NET segítségével egyszerűen aláírhat egy PDF-fájlt intelligens kártyával a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Íme a szükséges import irányelvek:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia az aláírni kívánt PDF-fájlt tartalmazó mappa elérési útját. Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. lépés: Töltse be a PDF dokumentumot

Most betöltjük az aláírandó PDF dokumentumot a következő kóddal:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 4. lépés: Végezze el az aláírást az intelligens kártyával

 Ebben a lépésben az intelligens kártyával történő aláírást hajtjuk végre a`PdfFileSignature` osztályból a`Facades`könyvtár. Kiválasztjuk az intelligens kártya tanúsítványát a Windows tanúsítványtárolóból, és megadjuk a szükséges aláírási információkat. Itt van a megfelelő kód:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Válassza ki a tanúsítványt az üzletben
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 5. lépés: Az aláírás ellenőrzése

 Végül ellenőrizzük az aláírt PDF fájl aláírását a`PdfFileSignature` osztály. Megkapjuk az aláírásneveket, és egyenként ellenőrizzük őket. Ha az aláírás ellenőrzése sikertelen, a rendszer kivételt dob. Itt van a megfelelő kód:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Forráskód minta az intelligens kártyával történő aláíráshoz PDF-fájl használatával Aláírás az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Aláírja a tanúsítvány kiválasztását a Windows tanúsítványtárolójában
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Manuálisan válassza ki a tanúsítványt az üzletben
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Következtetés

Gratulálunk! Mostantól lépésről lépésre olvashat egy PDF-fájl intelligens kártyával történő aláírásáról az Aspose.PDF for .NET használatával. Ezzel a kóddal biztonságos digitális aláírásokat adhat PDF-dokumentumaihoz.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a fejlett digitális aláírási és tanúsítványkezelési funkciókkal kapcsolatos további információkért.

### GYIK

#### K: Miért érdemes megfontolnom a PDF-fájlok intelligens kártyával történő aláírását?

V: A PDF-fájlok intelligens kártyával történő aláírása növeli a biztonságot azáltal, hogy biztosítja a dokumentum hitelességét és integritását. Az intelligens kártya alapú aláírások magasabb szintű bizalmat és megfelelőséget biztosítanak.

#### K: Hogyan működik az intelligens kártya alapú digitális aláírás?

V: Az intelligens kártya alapú digitális aláírás magában foglalja az intelligens kártyán tárolt kriptográfiai kulcs használatát egyedi digitális aláírás létrehozásához. Ez az aláírás a PDF-fájlhoz van csatolva, lehetővé téve a címzettek számára a dokumentum eredetének és sértetlenségének ellenőrzését.

#### K: Mi a szerepe az Aspose.PDF for .NET-nek az intelligens kártya alapú aláírásban?

V: Az Aspose.PDF for .NET eszközök és könyvtárak átfogó készletét kínálja a PDF fájlok intelligens kártya alapú digitális aláírásának megkönnyítésére. Leegyszerűsíti a folyamatot és biztosítja a biztonságos dokumentum-aláírást.

#### K: Választhatok egy adott intelligens kártya tanúsítványt az aláíráshoz?

V: Igen, kiválaszthat egy adott intelligenskártya-tanúsítványt a Windows tanúsítványtárolóból aláíráshoz. Az Aspose.PDF for .NET lehetővé teszi a tanúsítványkiválasztás zökkenőmentes integrálását az alkalmazásba.

#### K: Hogyan kezeli a megadott forráskód az intelligens kártya alapú aláírást?

V: A forráskód bemutatja, hogyan kell PDF-dokumentumot kötni, kiválasztani az intelligens kártya tanúsítványát, megadni az aláírási információkat és létrehozni egy digitális aláírást. Azt is bemutatja, hogyan ellenőrizhető az aláírás érvényessége.

#### K: Alkalmazhatok több aláírást intelligens kártyákkal egyetlen PDF-fájlban?

V: Természetesen több intelligens kártya alapú aláírást is alkalmazhat egyetlen PDF-fájlhoz. Minden aláírás egyedi, és hozzájárul a dokumentum általános biztonságához.

#### K: Mi a teendő, ha az aláírás ellenőrzése meghiúsul az ellenőrzési lépés során?

V: Ha egy aláírás ellenőrzése sikertelen, a rendszer kivételt dob, jelezve, hogy az aláírás érvénytelen. Ez biztosítja, hogy csak érvényes és megbízható aláírásokat fogadjon el.

#### K: Az intelligens kártya alapú aláírás kompatibilis minden típusú PDF dokumentummal?

V: Igen, az intelligens kártya alapú aláírás minden típusú PDF dokumentummal kompatibilis. Digitális aláírást alkalmazhat különféle típusú PDF-fájlokhoz, beleértve az űrlapokat, jelentéseket és egyebeket.

#### K: Hogyan tudhatok meg többet a fejlett digitális aláírásról és tanúsítványkezelésről?

V: Fedezze fel a hivatalos Aspose.PDF dokumentációt, ahol részletes betekintést kaphat a fejlett digitális aláírási funkciókba, a tanúsítványkezelésbe, valamint a dokumentumok biztonságának biztosítására vonatkozó bevált gyakorlatokba.

#### K: Hol találhatok további segítséget vagy támogatást az intelligens kártya alapú aláírás megvalósításához?

V: További útmutatásért és támogatásért forduljon az Aspose.PDF közösségi fórumokhoz, vagy tekintse meg a dokumentációt az intelligens kártya alapú aláírással kapcsolatos átfogó információkért.