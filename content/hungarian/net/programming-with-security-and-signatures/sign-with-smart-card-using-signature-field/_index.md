---
title: Jelentkezzen intelligens kártyával aláírási mező használatával
linktitle: Jelentkezzen intelligens kártyával aláírási mező használatával
second_title: Aspose.PDF for .NET API Reference
description: Biztonságosan írja alá PDF fájljait intelligens kártyával az Aspose.PDF for .NET segítségével.
type: docs
weight: 120
url: /hu/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Az intelligens kártyával történő digitális aláírás a PDF fájlok aláírásának biztonságos módja. Az Aspose.PDF for .NET segítségével könnyen aláírhat egy PDF-fájlt aláírási mező és intelligens kártya használatával a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Íme a szükséges import irányelvek:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia az aláírni kívánt PDF-fájlt tartalmazó mappa elérési útját. Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. lépés: Másolja és nyissa meg a PDF dokumentumot

Most kimásoljuk és megnyitjuk az aláírandó PDF dokumentumot a következő kóddal:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Hozzon létre egy aláírási mezőt
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Válassza ki a tanúsítványt az üzletben
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Hozzon létre egy külső aláírást a szükséges információkkal
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## 4. lépés: Az aláírás ellenőrzése

 Végül ellenőrizzük az aláírt PDF fájl aláírását a`PdfFileSignature` osztály. Megkapjuk az aláírásneveket, és egyenként ellenőrizzük őket. Ha az aláírás ellenőrzése sikertelen, a rendszer kivételt dob. Itt van a megfelelő kód:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Forráskód minta a Sign With Smart Card With Signature Field programhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Aláírja a tanúsítvány kiválasztását a Windows tanúsítványtárolójában
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Manuálisan válassza ki a tanúsítványt az üzletben
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

Gratulálok ! Mostantól lépésről lépésre olvashat egy PDF-fájl intelligens kártyával történő aláírásáról egy aláírási mező használatával az Aspose.PDF for .NET-hez. Ezzel a kóddal biztonságos digitális aláírásokat adhat PDF-dokumentumaihoz.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a fejlett digitális aláírási és tanúsítványkezelési funkciókkal kapcsolatos további információkért.

### GYIK

#### K: Milyen előnyökkel jár az aláírási mező használata intelligens kártyával történő digitális aláíráshoz?

V: Aláírási mező használata intelligens kártyával történő digitális aláíráshoz egy kijelölt területet biztosít a PDF-ben, ahol az aláírást alkalmazzák. Ez javítja a dokumentum tisztaságát és biztosítja az aláírás hitelességét.

#### K: Hogyan teszi lehetővé az Aspose.PDF for .NET könyvtár az intelligens kártya alapú digitális aláírást aláírási mezővel?

V: Az Aspose.PDF for .NET leegyszerűsíti az aláírási mező létrehozásának, az intelligenskártya-tanúsítvány kiválasztásának és a digitális aláírásnak a PDF-dokumentum egy adott területére történő alkalmazásának folyamatát.

#### K: Miért fontos egy adott tanúsítvány kiválasztása az intelligens kártya alapú aláíráshoz?

V: Egy adott tanúsítvány kiválasztása lehetővé teszi az aláíró egyedi azonosítását és az aláírás integritásának biztosítását. Ez elősegíti a bizalom megteremtését és a digitális aláírási szabványoknak való megfelelést.

#### K: Hogyan kezeli a megadott forráskód az intelligens kártya alapú aláírási folyamatot aláírási mezővel?

V: A forráskód bemutatja, hogyan hozhat létre aláírási mezőt, hogyan válasszon ki egy intelligens kártya tanúsítványt, és hogyan alkalmazzon digitális aláírást meghatározott aláírási információkkal. Azt is bemutatja, hogyan ellenőrizhető az aláírás érvényessége.

#### K: Testreszabhatom az aláírási mező megjelenését?

V: Igen, testreszabhatja az aláírási mező megjelenését, például méretét, helyzetét és vizuális megjelenítését, hogy igazodjon a dokumentum elrendezéséhez.

#### K: Mi történik, ha egy aláírás ellenőrzése meghiúsul az ellenőrzési lépés során?

V: Ha egy aláírás ellenőrzése sikertelen, a rendszer kivételt dob, jelezve, hogy az aláírás érvénytelen. Ez biztosítja, hogy csak érvényes és megbízható aláírásokat fogadjon el.

#### K: Alkalmazhatok több aláírási mezőt és intelligens kártya alapú aláírást egyetlen PDF-dokumentumhoz?

V: Természetesen több aláírásmezőt és intelligens kártya alapú aláírást alkalmazhat ugyanannak a PDF-dokumentumnak különböző területein, így több szintű biztonságot nyújt.

#### K: Hogyan javítja az aláírási mező használata az általános dokumentum-aláírási folyamatot?

V: Az aláírási mező használata leegyszerűsíti a dokumentum-aláírási folyamatot, mivel az aláírót arra irányítja, hogy az aláírását egy kijelölt helyre helyezze, így az aláírási folyamat szervezettebbé és felhasználóbarátabbá válik.

#### K: Vannak korlátozások az aláírási mezők használatára intelligens kártya alapú aláírással?

V: Nincsenek eredendő korlátozások az aláírási mezők intelligens kártya alapú aláírással történő használatára vonatkozóan. Fontos azonban annak biztosítása, hogy a kiválasztott aláírási mező helye ne takarja el a fontos dokumentumtartalmat.

#### K: Hol találhatok további segítséget vagy támogatást az intelligens kártya alapú aláírásmezővel történő aláírás megvalósításához?

V: További útmutatásért és támogatásért tekintse meg a hivatalos Aspose.PDF dokumentációt és közösségi fórumokat, amelyek értékes betekintést és megoldásokat kínálnak a biztonságos digitális aláírások megvalósításához.