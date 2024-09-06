---
title: Digitális aláírás Időbélyeggel PDF Fájlban
linktitle: Digitális aláírás Időbélyeggel PDF Fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hajthat végre digitális aláírást időbélyeggel PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 50
url: /hu/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Ebben az oktatóanyagban végigvezetjük az időbélyeggel ellátott PDF-fájlba történő digitális aláírás folyamatán az Aspose.PDF for .NET használatával. Az időbélyegzővel ellátott digitális aláírás garantálja a dokumentum hitelességét és sértetlenségét, időbélyegzővel ellátott elektronikus ujjlenyomat hozzáadásával.

## 1. lépés: Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- C# programozási nyelv alapismerete
- A Visual Studio telepítése a gépre
- Aspose.PDF könyvtár a .NET-hez telepítve

## 2. lépés: A környezet beállítása

A kezdéshez kövesse az alábbi lépéseket a fejlesztői környezet beállításához:

1. Nyissa meg a Visual Studio-t, és hozzon létre egy új C#-projektet.
2. Importálja a szükséges névtereket a kódfájlba:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## 3. lépés: Digitális aláírás időbélyeggel

Az első lépés az időbélyeggel ellátott digitális aláírás végrehajtása a PDF-fájlon. A mellékelt kód bemutatja, hogyan érhető el ez az aláírás az Aspose.PDF for .NET segítségével.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Ez a kód betölt egy PDF-fájlt, digitális aláírást hoz létre időbélyeggel egy PFX-fájl (privát kulcs) és a megadott időbélyeg-paraméterek használatával. Az aláírás ezután hozzáadásra kerül a PDF-fájlhoz, és a " utótaggal mentve"_ki".

### Minta forráskód a digitális aláíráshoz időbélyeggel az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // A felhasználó/jelszó elhagyható
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Hozza létre a három aláírástípus bármelyikét
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Mentse a kimeneti PDF fájlt
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Következtetés

Gratulálok ! Sikeresen hajtott végre digitális aláírást időbélyeggel egy PDF-fájlon az Aspose.PDF for .NET használatával. Ez az oktatóanyag az aláírás létrehozásától a frissített PDF-fájl mentéséig lépésről lépésre haladó folyamatot ismertette. Mostantól használhatja ezt a funkciót, hogy digitális aláírásokat adjon időbélyeggel a PDF-fájlokhoz.

### GYIK az időbélyeggel ellátott digitális aláíráshoz PDF-fájlban

#### K: Mi a célja az időbélyeggel történő digitális aláírásnak?

V: Az időbélyeggel ellátott digitális aláírás egy időbélyegzővel ellátott elektronikus ujjlenyomatot ad a PDF-fájlhoz, biztosítva a dokumentum hitelességét és integritását egy adott időpontban.

#### K: Milyen előfeltételek szükségesek az oktatóanyag elindításához?

V: Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a C# programozási nyelv alapvető ismereteivel, telepítette a Visual Studio programot, és telepítette a .NET Aspose.PDF könyvtárát.

#### K: Hogyan állíthatom be a fejlesztői környezetemet?

V: Kövesse a megadott lépéseket a fejlesztői környezet beállításához, beleértve egy új C#-projekt létrehozását a Visual Studióban és a szükséges névterek importálását.

#### K: Hogyan adhatok hozzá időbélyegzővel ellátott digitális aláírást a PDF-hez?

V: A mellékelt mintakód bemutatja, hogyan tölthet be egy PDF-fájlt, hogyan hozhat létre digitális aláírást időbélyeggel egy PFX-fájl (privát kulcs) és meghatározott időbélyeg-beállítások használatával, hogyan adja hozzá az aláírást a PDF-fájlhoz, és hogyan mentheti el a frissített fájlt.

#### K: Mi az a PFX-fájl, és miért használják a példában?

V: A PFX (Personal Exchange Format) fájl privát kulcsot és tanúsítványt tartalmaz. Itt a digitális aláírások kriptográfiai funkcióinak biztosítására használják. Cserélje ki a helyőrzőt a PFX-fájljával és jelszavával.

#### K: Mik azok az időbélyegbeállítások?

V: A TimestampSettings határozza meg az időbélyegzőszerver beállításait, amellyel az elektronikus időbélyegzőt az aláíráshoz adják. Tartalmazza az időbélyeg-kiszolgáló URL-címét és az opcionális felhasználói hitelesítő adatokat.

#### K: Használhatok a példában szereplőtől eltérő időbélyeg-kiszolgálót?
 V: Igen, bármilyen kompatibilis időbélyeg-kiszolgálót használhat. Cserélje ki az URL-t, és ha szükséges, adja meg a megfelelő felhasználói hitelesítő adatokat`TimestampSettings` objektum.

#### K: Mi a célja az aláírási téglalap megadásának?

V: Az aláírási téglalap határozza meg a digitális aláírás megjelenésének helyét és méreteit a PDF oldalon. Módosítsa ezeket az értékeket az aláírás kívánt elhelyezéséhez.

#### K: Mi történik, ha az időbélyeg-szerver nem elérhető az aláírás során?

V: Ha az időbélyeg-kiszolgáló nem érhető el az aláírás során, a folyamat meghiúsulhat vagy tovább tarthat. Győződjön meg arról, hogy időbélyeg-szervere megbízható és hozzáférhető.

#### K: Hogyan ellenőrizhetem az időbélyeg jelenlétét az aláírt PDF-ben?

 V: Megvizsgálhatja az aláírt PDF-fájlt a mellékelt mintakód segítségével. A`TimestampSettings` Az aláíráskor használtnak elérhetőnek kell lennie az aláírási adatok között.

#### K: Az időbélyeggel ellátott digitális aláírások jogilag kötelező érvényűek?

V: Az időbélyeggel ellátott digitális aláírások számos joghatóságban jogi értékkel bírnak, és gyakran megbízhatóbbnak tartják, mint az egyszerű digitális aláírásokat. A konkrét szabályozásokért forduljon az Ön joghatósága szerinti jogi szakértőhöz.

#### K: Hozzáadhatok több digitális aláírást időbélyeggel egy PDF-hez?

V: Igen, több időbélyeggel ellátott digitális aláírást is hozzáadhat egy PDF-fájlhoz, ha többször meghívja az aláírás-létrehozási folyamatot. Minden aláírásnak saját időbélyegzője lesz.