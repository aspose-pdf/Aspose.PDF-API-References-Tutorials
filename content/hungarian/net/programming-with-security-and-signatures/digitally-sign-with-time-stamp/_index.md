---
title: Digitális aláírás Időbélyeggel PDF Fájlban
linktitle: Digitális aláírás Időbélyeggel PDF Fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan írhat alá digitálisan egy PDF-et időbélyeggel az Aspose.PDF for .NET használatával. Ez a lépésenkénti útmutató az előfeltételeket, a tanúsítvány beállítását, az időbélyegzést és egyebeket ismerteti.
type: docs
weight: 50
url: /hu/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Bevezetés

Szüksége volt már arra, hogy digitálisan aláírjon egy PDF-dokumentumot, és a nagyobb biztonság érdekében időbélyegzőt adjon hozzá? Legyen szó jogi dokumentumokról, szerződésekről vagy bármiről, ami biztonságos hitelesítést igényel, az időbélyeggel ellátott digitális aláírás további hitelességet biztosít. Ebben az oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.PDF for .NET fájlt digitális aláírás és időbélyegző hozzáadására PDF-dokumentumaihoz. Ne aggódj, lépésről lépésre megtesszük!

## Előfeltételek

Mielőtt belemerülnénk a kódba, néhány dolgot be kell állítania a követéshez. Íme egy gyors ellenőrző lista a kezdéshez szükséges előfeltételekről:

-  Aspose.PDF for .NET Library: A projektben telepíteni kell az Aspose.PDF for .NET könyvtárat. Megteheti[töltse le a legújabb verziót innen](https://releases.aspose.com/pdf/net/) vagy adja hozzá a projekthez a NuGet segítségével.
- PDF-dokumentum: Szüksége lesz egy minta PDF-fájlra a munkához. Győződjön meg arról, hogy a projekt könyvtárában van egy fájl, amelyet alá szeretne írni.
-  Digitális tanúsítvány (PFX fájl): Győződjön meg arról, hogy rendelkezik digitális tanúsítvánnyal (a`.pfx` fájl) a dokumentum digitális aláírásához.
- Időbélyegző URL: Ez egy online időbélyegző szolgáltatás, amely időbélyegző csatolására szolgál a digitális aláíráshoz. 
- Alapvető C# ismeretek: Nem kell szakértőnek lenned, de a C# alapjainak ismerete segít megérteni és testreszabni a kódot.

Miután bejelölte ezeket a négyzeteket, készen áll a kódolás megkezdésére!

## Csomagok importálása

kezdéshez importálnia kell a következő névtereket a C# projektbe. Ez biztosítja, hogy hozzáférjen a megfelelő Aspose.PDF osztályokhoz és funkciókhoz.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## 1. lépés: Töltse be a PDF-dokumentumot

Az első dolog, amit tennünk kell, hogy betöltsük az aláírni kívánt PDF-dokumentumot. Íme, hogyan kell ezt megtenni:

```csharp
// Határozza meg a dokumentumkönyvtár elérési útját
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a PDF dokumentumot
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Ez a lépés meglehetősen egyszerű. Egyszerűen meghatározzuk az aláírni kívánt dokumentum elérési útját. A`Document` osztály az Aspose.PDF-ből kezeli a fájl betöltését.

## 2. lépés: Állítsa be a digitális aláírást

Ezután létrehozzuk a digitális aláírást a PKCS7 osztály használatával, és betöltjük a PFX fájlt. Ez a PFX fájl tartalmazza az Ön tanúsítványát és privát kulcsát, amelyek a dokumentum aláírásához szükségesek.

```csharp
// A .pfx fájl elérési útja
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Inicializálja az aláírás objektumot
PdfFileSignature signature = new PdfFileSignature(document);

// Töltse be a PFX fájlt jelszóval
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Ezen a ponton azt mondja az Aspose-nak, hogy használja a digitális tanúsítványt a dokumentum aláírásához. A`PKCS7`Az objektum elvégzi helyetted az összes kriptográfiai munkát, így nem kell aggódnod a finom részletek miatt.

## 3. lépés: Adja hozzá az Időbélyeg beállításait

A robusztus digitális aláírás egyik kulcseleme az időbélyeg. Ez biztosítja, hogy a dokumentum aláírása a tanúsítvány lejárta után is ellenőrizhető legyen. Állítsuk be az időbélyeget egy online időbélyegző hatóság segítségével.

```csharp
// Adja meg az időbélyeg beállításait
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "user:password");

// Adja hozzá az időbélyeg beállításait a PKCS7 objektumhoz
pkcs.TimestampSettings = timestampSettings;
```

Itt adja meg az időbélyegző szolgáltatás URL-címét, amely automatikusan megadja az időpontot és a dátumot az aláírásához. Ez megtehető hitelesítéssel vagy anélkül.

## 4. lépés: Határozza meg az aláírás helyét és megjelenését

Most meghatározzuk, hogy az aláírás hol jelenjen meg a PDF-ben, és annak méreteit. Testreszabhatja az aláírási mező pozícióját az oldalon, valamint a méretét.

```csharp
//Határozza meg az aláírás megjelenését és helyét (1. oldal, megadott téglalappal)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Itt definiálunk egy téglalapot, amely az aláírást a PDF első oldalán koordinátákra (100, 100) helyezi el, szélessége 200 és magassága 100. Ezeket az értékeket módosíthatja, hogy illeszkedjen a tervhez.

## 5. lépés: Aláírja a PDF-dokumentumot

Miután minden be van állítva, itt az ideje, hogy ténylegesen alkalmazza a digitális aláírást a PDF-re. Ez a lépés egyetlen egyszerű parancsban egyesíti a tanúsítványt, az időbélyeget és a pozicionálást.

```csharp
// Az első oldalon írja alá a dokumentumot
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Íme, mi történik:
- 1: Ez azt jelzi, hogy az aláírást az első oldalon kell alkalmazni.
- "Aláírás oka": Itt adhatja meg, hogy miért írja alá a dokumentumot.
- "Kapcsolat": Adja meg az aláíró elérhetőségét.
- „Hely”: Adja meg az aláíró helyét.
- true: Ez a logikai érték azt jelzi, hogy az aláírás látható-e a dokumentumban.
- rect: A korábban definiált téglalap határozza meg az aláírás méretét és helyzetét.
- pkcs: A PKCS7 objektum tartalmazza a digitális tanúsítványt és az időbélyeg beállításait.

## 6. lépés: Mentse el az aláírt PDF-fájlt

A dokumentum aláírása után már csak menteni kell. Választhat új fájlnevet, hogy az eredeti és az aláírt verzió is megmaradjon.

```csharp
// Mentse el az aláírt PDF dokumentumot
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Az újonnan aláírt és időbélyeggel ellátott PDF-fájl most a megadott könyvtárba kerül!

## Következtetés

És megvan! Sikeresen digitálisan aláírt egy PDF-et időbélyeggel az Aspose.PDF for .NET használatával. Ez a folyamat biztosítja a dokumentumok hitelességét és sértetlenségét, nyugalmat biztosítva Önnek és a címzettnek. A digitális aláírások egyre fontosabbá válnak a mai digitális világban, így ennek a folyamatnak az elsajátítása mindenképpen megéri.

## GYIK

### Használhatok más fájlformátumot a tanúsítványhoz?  
Igen, de az oktatóanyag a PFX-fájl használatára összpontosít, amely a digitális tanúsítványok leggyakoribb formátuma.

### Szükségem van internetkapcsolatra az időbélyeg alkalmazásához?  
Igen, mivel az időbélyeget egy online időbélyegző hatóságtól kérik le, internet-hozzáférésre lesz szüksége.

### Aláírhatok több oldalt egy PDF-ben?  
 Teljesen! Módosíthatja a`signature.Sign()` módszer több oldal megcélzására vagy az összes oldal végigjátszására.

### Mi történik, ha a PFX fájl jelszava helytelen?  
Kivételt kap, ha a jelszó rossz, ezért ellenőrizze, hogy helyesen adta-e meg.

### Láthatatlanná tehetem az aláírást?  
 Igen, átmehet`false` a`Sign` metódus láthatósági paramétere, hogy az aláírás láthatatlan legyen.