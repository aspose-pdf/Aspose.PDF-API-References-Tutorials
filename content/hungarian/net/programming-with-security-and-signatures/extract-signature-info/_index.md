---
title: Kivonat aláírási információ
linktitle: Kivonat aláírási információ
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan nyerhet ki digitális aláírásokat és tanúsítványadatokat PDF-dokumentumokból az Aspose.PDF for .NET használatával. Egy teljes, lépésről lépésre útmutató a C# fejlesztőknek.
type: docs
weight: 80
url: /hu/net/programming-with-security-and-signatures/extract-signature-info/
---
## Bevezetés

mai digitális világban a dokumentumok biztonságának és sértetlenségének biztosítása kulcsfontosságú. A PDF-ek védelmére használt egyik általános módszer a digitális aláírás hozzáadása. Az aláírás adatainak lekérése és ellenőrzése azonban néha kihívást jelenthet, különösen, ha különféle tanúsítványokkal van dolgunk. Ebben az útmutatóban végigvezetjük az aláírási információk PDF-dokumentumokból történő kinyerésének folyamatán az Aspose.PDF for .NET használatával, így a feladatot gyerekjáték könnyíti meg. Megtanulja, hogyan férhet hozzá az aláírási mezőkhöz, hogyan bonthatja ki a tanúsítvány adatait, és hogyan mentheti azokat fájlba.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg arról, hogy minden készen áll a kezdéshez.

-  Aspose.PDF for .NET Library: Ha még nem rendelkezik vele, letöltheti a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net/). 
- .NET fejlesztői környezet: Szüksége lesz egy IDE-re, például a Visual Studiora.
- Alapvető C# ismeretek: A C# ismerete segít megérteni az oktatóanyagban szereplő kódrészleteket.
- PDF-dokumentum digitális aláírással: Tesztelési célokra győződjön meg arról, hogy rendelkezik egy PDF-fájllal, amely legalább egy digitális aláírást tartalmaz.

## Kötelező névterek importálása

Mielőtt belevágna a kódba, fontos, hogy importálja a szükséges névtereket. Ezek a névterek lehetővé teszik az Aspose.PDF funkció elérését és a PDF dokumentumok kezelését.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Most, hogy beállította a lényeget, folytassuk az aláírási adatok PDF-ből való kinyerésének tényleges folyamatát.

## 1. lépés: A dokumentumkönyvtár beállítása

 Mielőtt egy PDF-dokumentumon dolgozna, meg kell adnia a használni kívánt fájl helyét. Cserélheted`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a PDF-eket tárolják.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Itt adjuk meg a PDF fájlt tartalmazó könyvtárat és magát a fájlnevet. Győződjön meg arról, hogy a fájl létezik ebben a könyvtárban!

## 2. lépés: A PDF-dokumentum betöltése

 Most, hogy beállította a könyvtárat, a következő lépés a PDF-dokumentum betöltése a`Document` osztály az Aspose.PDF-ből.

```csharp
using (Document pdfDocument = new Document(input))
{
    // A PDF feldolgozása itt.
}
```

 Ez a kódsor inicializálja a`Document`objektum, amely a PDF-fájlt képviseli. A`using` nyilatkozat biztosítja, hogy a dokumentum feldolgozása után az erőforrások megtisztuljanak.

## 3. lépés: Hozzáférés az űrlapmezőkhöz

Ebben a lépésben végigfutjuk a PDF dokumentum összes űrlapmezőjét. Mivel az aláírásokat általában űrlapmezőkként tároljuk, ez a lépés segít azonosítani az aláírási mezőket.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Itt azonosíthatja az aláírási mezőket.
}
```

 Iterációval a`Form` tulajdona a`Document` objektumot, megvizsgálhatjuk az egyes űrlapmezőket, hogy ellenőrizzük, hogy aláírásmező-e.

## 4. lépés: Az aláírási mezők azonosítása

 Miután elérte az űrlapmezőket, a következő lépés az, hogy azonosítsa, melyek az aláírási mezők. Ezt úgy tehetjük meg, hogy az egyes mezőket a-ba öntjük`SignatureField` objektum.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Kivonat aláírási információkat.
}
```

 Itt használjuk a`as` kulcsszó, amellyel az egyes űrlapmezőket a`SignatureField`. Ha a leadás sikeres, tudjuk, hogy a mező egy aláírás.

## 5. lépés: A tanúsítvány kibontása

Most, hogy azonosította az aláírásmezőt, a következő feladat a tanúsítvány kibontása az aláírásból. A tanúsítványok lényeges információkat tartalmaznak az aláíróról és az aláírás érvényességéről.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 A`ExtractCertificate` metódus visszaadja a`Stream` a tanúsítvány adatait tartalmazó objektum. Ez az adatfolyam használható a tanúsítvány mentésére további elemzés vagy tárolás céljából.

## 6. lépés: A tanúsítvány mentése fájlba

 Miután kicsomagolta a tanúsítványt, az utolsó lépés az, hogy elmenti egy fájlba. Ebben az esetben a tanúsítványt a`.cer` fájlt.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Ebben a kódblokkban mi:

1. Ellenőrizze, hogy a tanúsítványfolyam nem nulla-e.
2. Olvassa be a tanúsítvány adatait egy bájttömbbe.
3.  Írja a bájttömböt a-ba`.cer` fájlt a dokumentumkönyvtárban.

## Következtetés

digitális aláírások és a kapcsolódó tanúsítványinformációk kinyerése PDF-dokumentumokból az Aspose.PDF for .NET használatával meglehetősen egyszerű, ha egyszerű lépésekre bontja le. Függetlenül attól, hogy dokumentumokat auditál, aláírásokat ellenőriz, vagy csak tanúsítványokat tárol megőrzés céljából, ez az oktatóanyag felvértezi Önt a hatékony végrehajtáshoz szükséges ismeretekkel. Ne feledje, hogy a dokumentumok védelme és ellenőrzése kritikus fontosságú a mai digitális világban, és az olyan eszközök használata, mint az Aspose.PDF for .NET, sokkal könnyebbé teszi a kezelést.

## GYIK

### Kivonhatok több aláírást egy PDF-ből az Aspose.PDF for .NET használatával?
Igen, a kód végigfut a dokumentum összes űrlapmezőjén, lehetővé téve több aláírás kinyerését, ha vannak ilyenek.

### Mi történik, ha nem található aláírás a PDF-ben?
Ha nincsenek aláírási mezők, a kód egyszerűen átugorja őket anélkül, hogy hibát okozna.

### Használhatom ezt a megközelítést az aláírás érvényességének ellenőrzésére?
Bár a tanúsítványt kibonthatja, az aláírás érvényességének ellenőrzéséhez további lépésekre van szükség, például a tanúsítvány bizalmi láncának ellenőrzésére.

### Kivonható-e más űrlapmezőadatokat az Aspose.PDF for .NET használatával?
Igen, az Aspose.PDF lehetővé teszi különböző típusú űrlapmezők elérését és kezelését a PDF-ben, nem csak az aláírási mezőket.

### Hogyan nézhetem meg a kivont tanúsítvány részleteit?
 Miután a tanúsítványt a`.cer` fájlt, megnyithatja bármelyik tanúsítványnézegetővel, vagy importálhatja a rendszertanúsítványtárolóba további ellenőrzés céljából.