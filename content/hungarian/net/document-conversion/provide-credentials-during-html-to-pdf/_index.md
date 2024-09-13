---
title: Hitelesítő adatok megadása a HTML-hez PDF-be
linktitle: Hitelesítő adatok megadása a HTML-hez PDF-be
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésenkénti útmutatóból megtudhatja, hogyan konvertálhat HTML-t PDF-be az Aspose.PDF for .NET használatával. Tökéletes azoknak a fejlesztőknek, akik egyszerűsíteni szeretnék a dokumentumkészítést.
type: docs
weight: 240
url: /hu/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Bevezetés

A szoftverfejlesztés világában a HTML PDF formátumba konvertálása általános követelmény. Függetlenül attól, hogy jelentéseket, számlákat vagy bármilyen más dokumentumot készít, a feladat elvégzéséhez megbízható könyvtárral sok időt és erőfeszítést takaríthat meg. Írja be az Aspose.PDF for .NET fájlt, egy hatékony könyvtárat, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok egyszerű létrehozását, kezelését és konvertálását. Ebben az oktatóanyagban végigvezetjük az Aspose.PDF használatával a HTML PDF-formátumba konvertálásához, miközben hitelesítési adatokat biztosítunk a biztonságos hozzáféréshez. Szóval, fogd a kódoló kalapot, és merüljünk bele!

## Előfeltételek

Mielőtt elkezdenénk, néhány dolgot meg kell tennie:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Ez lesz a fejlesztési környezetünk.
2.  Aspose.PDF for .NET: Letöltheti a könyvtárat a[weboldal](https://releases.aspose.com/pdf/net/) . Ha először szeretné kipróbálni, beszerezheti a[ingyenes próbaverzió](https://releases.aspose.com/).
3. Alapvető C# ismerete: A C# programozás ismerete segít a példák jobb megértésében.
4. Internet-hozzáférés: Mivel a HTML-tartalmat egy URL-ről fogjuk lekérni, győződjön meg róla, hogy aktív internetkapcsolata van.

## Csomagok importálása

Az Aspose.PDF használatának megkezdéséhez importálnia kell a szükséges csomagokat a projektbe. A következőképpen teheti meg:

1. Nyissa meg a Visual Studio projektet.
2. Kattintson a jobb gombbal a projektre a Solution Explorerben, és válassza a "NuGet-csomagok kezelése" lehetőséget.
3. Keresse meg az "Aspose.PDF" kifejezést, és telepítse a legújabb verziót.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Most, hogy mindent beállítottunk, bontsuk fel kezelhető lépésekre a HTML hitelesítő adatokkal történő PDF formátumba konvertálásának folyamatát.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Mielőtt konvertálhatnánk a HTML-t PDF-be, meg kell adnunk, hogy a kimeneti PDF hova kerüljön mentésre. Ez a dokumentumkönyvtár elérési útjának meghatározásával történik.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahová a PDF-fájlt menteni szeretné. Ez lehet egy mappa az asztalon vagy a rendszer bármely más helye.

## 2. lépés: Hozzon létre egy webes kérelmet

 Ezután létre kell hoznunk egy kérést a HTML-tartalom lekérésére egy adott URL-ről. Itt fogjuk használni a`WebRequest` osztály.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Itt létrehozunk egy kérést arra az URL-re, amely tartalmazza a konvertálni kívánt HTML-kódot. Ügyeljen arra, hogy az URL-t a használni kívánt URL-re cserélje ki.

## 3. lépés: Hitelesítési adatok beállítása (ha szükséges)

Ha a kiszolgálónak hitelesítő adatokra van szüksége a tartalom eléréséhez, be kell állítanunk azokat. Ez a`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Ez a sor biztosítja, hogy a kérés az aktuális felhasználó alapértelmezett hitelesítő adatait használja. Ha konkrét hitelesítési adatokat kell megadnia, létrehozhat újat`NetworkCredential` objektum.

## 4. lépés: Kérje meg a választ

Most, hogy beállítottuk a kérésünket, itt az ideje, hogy megkapjuk a választ a szervertől.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Ez a sor elküldi a kérést, és várja, hogy a szerver válaszoljon. Ha minden jól megy, megkapjuk a szükséges HTML tartalmat.

## 5. lépés: Olvassa el a válaszfolyamot

 Miután megkaptuk a választ, el kell olvasnunk a szerver által visszaadott tartalmat. Ez az a`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Itt a válaszfolyam teljes tartalmát egy karakterlánc-változóba olvassuk be`responseFromServer`. Ne felejtse el bezárni az olvasót és a streamet, hogy forrásokat szabadítson fel.

## 6. lépés: Alakítsa át a HTML-t PDF-be

Most jön az izgalmas rész! A HTML-tartalmat PDF-dokumentummá alakítjuk az Aspose.PDF használatával.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

Ebben a lépésben létrehozunk egy`MemoryStream` a HTML tartalomból és beállításból`HtmlLoadOptions`. Ez lehetővé teszi, hogy megadjuk az alap URL-t minden olyan külső erőforráshoz (például képekhez vagy stíluslapokhoz), amelyekre a HTML hivatkozhat.

## 7. lépés: Mentse el a PDF-dokumentumot

Végül a létrehozott PDF dokumentumot el kell mentenünk a megadott könyvtárba.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Ez a sor menti a PDF fájlt a névvel`ProvideCredentialsDuringHTMLToPDF_out.pdf` a korábban megadott könyvtárban.

## Következtetés

És megvan! Sikeresen konvertálta a HTML-t PDF-be az Aspose.PDF for .NET használatával, miközben hitelesítési adatokat biztosított a biztonságos hozzáféréshez. Ez a nagy teljesítményű könyvtár megkönnyíti a PDF-dokumentumok kezelését, és mindössze néhány sornyi kóddal professzionális megjelenésű PDF-fájlokat hozhat létre HTML-tartalomból. 

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok létrehozását, kezelését és konvertálását .NET-alkalmazásokban.

### Hogyan telepíthetem az Aspose.PDF-et?
 Az Aspose.PDF-et a NuGet Package Manager segítségével telepítheti a Visual Studio alkalmazásban, vagy letöltheti a webhelyről[weboldal](https://releases.aspose.com/pdf/net/).

### Használhatom ingyenesen az Aspose.PDF-et?
Igen, az Aspose ingyenes próbaverziót kínál, amellyel a vásárlás előtt kiértékelheti a könyvtárat.

### Milyen típusú dokumentumokat hozhatok létre az Aspose.PDF segítségével?
Az Aspose.PDF használatával dokumentumok széles skáláját hozhatja létre, beleértve a jelentéseket, számlákat és űrlapokat.

### Hol találok támogatást az Aspose.PDF számára?
 Támogatást találhat és kérdéseket tehet fel a[Aspose támogatási fórum](https://forum.aspose.com/c/pdf/10).