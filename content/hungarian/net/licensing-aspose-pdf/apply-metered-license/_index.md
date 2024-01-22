---
title: Konfigurálja a mért licenckulcsokat PDF-fájlban
linktitle: Konfigurálja a mért licenckulcsokat PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a mérőszámos licenckulcsok PDF-fájlban történő beállításához az Aspose.PDF for .NET-hez és a fejlett funkciók előnyeinek kihasználásához.
type: docs
weight: 10
url: /hu/net/licensing-aspose-pdf/configure-metered-license/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük, hogyan állíthat be mérőszámos licenckulcsokat PDF-fájlban az Aspose.PDF for .NET segítségével. A mért licenc lehetővé teszi az Aspose.PDF fejlett funkcióinak használatát a tényleges fogyasztás alapján.

### 1. lépés: A licenckulcsok konfigurálása

A megadott forráskódban meg kell adnia a mért licenc nyilvános és privát kulcsát. Helyettesíteni a "*****" értékeket a saját kulcsaival. Ezeket a kulcsokat akkor kapja meg, amikor mérős licencet vásárol az Aspose-tól.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### 2. lépés: A dokumentum betöltése

 Töltse be a PDF dokumentumot a lemezről a`Document` osztályú Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### 3. lépés: A dokumentum oldalszámának lekérése

 Használja a`Count` tulajdona a`Pages` gyűjtemény, hogy megkapja a dokumentum teljes oldalát.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Forráskód minta a Configure Metered License Aspose.PDF for .NET használatával programhoz 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// állítsa be a mért nyilvános és privát kulcsokat
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
//Hozzáférés a setMeteredKey tulajdonsághoz, és paraméterként adjon át nyilvános és privát kulcsokat
metered.SetMeteredKey("*****", "*****");
// Töltse be a dokumentumot a lemezről.
Document doc = new Document(dataDir + "input.pdf");
//Szerezze meg a dokumentum oldalszámát
Console.WriteLine(doc.Pages.Count);

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan állíthat be mérőszámos licencet az Aspose.PDF segítségével .NET-hez. Méretes licenc használatával kihasználhatja az Aspose.PDF fejlett funkcióit a tényleges használat alapján. Győződjön meg arról, hogy érvényes licenckulcsokat ad meg az Aspose.PDF minden funkciójával együtt történő használatához.

### GYIK a mért licenckulcsok PDF-fájlban történő konfigurálásához

#### K: Mi az a mérsékelt licenc az Aspose.PDF-ben?

V: Az Aspose.PDF számlás licence egy olyan licencmodell, amely lehetővé teszi, hogy fix licencdíj helyett a szolgáltatások tényleges felhasználása alapján fizessen. Lehetővé teszi az Aspose.PDF fejlett funkcióinak használatát, miközben csak azért fizet, amit használ.

#### K: Miért érdemes fizetős licencet használnom az Aspose.PDF fájlhoz?

V: A mért licenc használata költségmegtakarítást és rugalmasságot kínál. Csak a használt funkciókért kell fizetnie, így alkalmas különböző igényű projektekhez. Kiküszöböli az előzetes licencdíjak szükségességét, és lehetővé teszi a fejlett PDF-funkciók elérését.

#### K: Hogyan szerezhetek számlás licenckulcsokat?

V: Ha mérős licencet vásárol az Aspose-tól, kap egy pár nyilvános és privát kulcsot. Ezeket a kulcsokat a rendszer az Aspose.PDF alkalmazás hitelesítésére és mérőszámos licencelésének engedélyezésére fogja használni.

#### K: Hogyan konfigurálhatom a fizetős licenckulcsokat az Aspose.PDF fájlban .NET-hez?

 V: A mért licenckulcsok konfigurálásához használja a`SetMeteredKey` módszere a`Aspose.Pdf.Metered` osztály. Cserélje ki`"PUBLIC_KEY"` és`"PRIVATE_KEY"` a valódi kulcsaiddal.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

#### K: Hogyan tölthetek be PDF-dokumentumot az Aspose.PDF for .NET használatával?

 V: PDF dokumentum lemezről történő betöltéséhez használja a`Document` osztályú Aspose.PDF fájlt, és adja meg a fájl elérési útját.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

#### K: Hogyan kaphatom meg a PDF-dokumentum teljes oldalszámát?

 V: Egy PDF-dokumentum teljes oldalszámának megtekintéséhez használja a`Count` tulajdona a`Pages` Gyűjtemény.

```csharp
int pageCount = doc.Pages.Count;
Console.WriteLine("Total pages: " + pageCount);
```

#### K: Használhatom a mért licencet más Aspose termékekhez?

V: Igen, az Aspose különböző termékeihez elérhető a mérőszámos licenc, amely lehetővé teszi, hogy a szolgáltatások széles skálájáért a használat alapján fizessen.

#### K: Minden típusú projekthez alkalmas a mért licenc?

V: A mért licencelés változó funkcióhasználatú projektekhez alkalmas. Előfordulhat, hogy nem költséghatékony olyan projektek esetén, amelyek következetesen, magas funkciókat használnak.

#### K: Hol találhatok további információt az Aspose.PDF mért licencelésről?

 V: Ha további információra van szüksége a mérőszámos engedélyezésről, az árakról és az előnyökről, keresse fel a[Aspose.PDF mért licenc](https://purchase.aspose.com/pricing/pdf/net) oldalon.

#### K: Hogyan biztosíthatom a mért licenckulcsok biztonságát?

V: A mért licenckulcsokat hitelesítésre használják, és érzékeny információk. Ügyeljen arra, hogy ezeket bizalmasan kezelje, és ne ossza meg nyilvánosan.

#### K: Válthatok a hagyományos és a mért engedélyezés között?

V: Igen, a projekt követelményei alapján válthat az Aspose.PDF hagyományos és mért licencelése között.

#### K: Használhatok próbaverziót a mérőszámos licenc vásárlása előtt?

 V: Igen, kipróbálhatod a[ingyenes próbaverzió](https://products.aspose.com/pdf/net) Az Aspose.PDF-ből, hogy értékelje szolgáltatásait és funkcionalitását, mielőtt megvásárolná a fizetős licencet.

#### K: Milyen gyakran kell konfigurálnom a mért licenckulcsokat?

V: A mért licenckulcsokat csak egyszer kell konfigurálnia, amikor az alkalmazás elindul. Hozzáférést biztosít a speciális funkciókhoz az alkalmazás teljes futási ideje alatt.

#### K: Alkalmazhatok mérőszámos licencelést egy meglévő alkalmazásra?

V: Igen, integrálhatja a mért licencelést egy meglévő Aspose.PDF alkalmazásba, hogy kihasználja annak előnyeit.