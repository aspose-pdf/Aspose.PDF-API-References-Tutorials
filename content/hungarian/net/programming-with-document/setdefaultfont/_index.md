---
title: Állítsa be az alapértelmezett betűtípust a PDF-fájlban
linktitle: Állítsa be az alapértelmezett betűtípust a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan állíthatja be az alapértelmezett betűtípust egy PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 280
url: /hu/net/programming-with-document/setdefaultfont/
---
Ha PDF-dokumentumokkal dolgozik .NET-ben, akkor előfordulhat, hogy a PDF-fájlban használt betűtípus nem érhető el azon a rendszeren, ahol megtekinti vagy kinyomtatja. Ez azt eredményezheti, hogy a szöveg hibásan vagy egyáltalán nem jelenik meg. Az Aspose.PDF for .NET megoldást kínál erre a problémára, mivel lehetővé teszi a dokumentum alapértelmezett betűtípusának beállítását. Ebben a példában az alapértelmezett betűtípus beállítása az Aspose.PDF for .NET használatával.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

be kell állítanunk annak a könyvtárnak az elérési útját, ahol a PDF dokumentumunk található. Ezt az elérési utat egy "dataDir" nevű változóban tároljuk.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a PDF dokumentumot

 Kezdjük azzal, hogy betöltünk egy meglévő PDF-dokumentumot, amelyből hiányoznak a betűtípusok. Ebben a példában feltételezzük, hogy a PDF-dokumentum a által megadott könyvtárban található`dataDir` változó.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kód ide megy
}
```

## 3. lépés: Állítsa be az alapértelmezett betűtípust

 Ezután beállítjuk a PDF-dokumentum alapértelmezett betűtípusát a`PdfSaveOptions` osztály. Ebben a példában az alapértelmezett betűtípust "Arial"-ra állítjuk.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 4. lépés: Mentse el a frissített dokumentumot

Végül elmentjük a frissített dokumentumot egy új fájlba. Ebben a példában a frissített dokumentumot egy „output_out.pdf” nevű fájlba mentjük, amely ugyanabban a könyvtárban található, mint a bemeneti fájl.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Példa forráskódra az alapértelmezett betűtípus beállításához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Töltsön be egy meglévő PDF-dokumentumot hiányzó betűtípussal
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Adja meg az alapértelmezett betűtípus nevét
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Következtetés

A PDF-dokumentumok alapértelmezett betűtípusának beállítása az Aspose.PDF for .NET használatával egyszerű és hatékony módja annak, hogy a szöveg helyesen jelenjen meg, még akkor is, ha az eredeti betűtípusok nem állnak rendelkezésre. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők egyszerűen beállíthatják az alapértelmezett betűtípust, és olyan PDF-fájlokat hozhatnak létre, amelyek konzisztens és megbízható megtekintési élményt kínálnak a különböző környezetekben. Ez a funkció különösen hasznos olyan esetekben, amikor a PDF-fájlokat különböző rendszereken tekintik meg vagy nyomtatják ki, amelyekre eltérő betűkészletek vannak telepítve.

### GYIK az alapértelmezett betűtípus beállításához PDF-fájlban

#### K: Miért fontos az alapértelmezett betűtípus beállítása a PDF dokumentumokban?

V: Az alapértelmezett betűtípus beállítása a PDF-dokumentumokban azért fontos, mert ez biztosítja, hogy a szöveg akkor is helyesen jelenjen meg, ha az eredeti betűtípusok nem állnak rendelkezésre azon a rendszeren, ahol a PDF-t nézik vagy nyomtatják. Segít megelőzni az olyan problémákat, mint a hiányzó vagy torz szöveg, így biztosítva a következetes és megbízható megtekintési élményt.

#### K: Kiválaszthatok bármilyen betűtípust alapértelmezett betűtípusként az Aspose.PDF for .NET használatával?

 V: Igen, az Aspose.PDF for .NET használatával bármely, a rendszerben elérhető betűtípust kiválaszthatja alapértelmezett betűtípusként. Egyszerűen adja meg a betűtípus nevét a`DefaultFontName` tulajdona a`PdfSaveOptions` osztály.

#### K: Mi történik, ha a megadott alapértelmezett betűtípus nem érhető el a rendszeren?

V: Ha a megadott alapértelmezett betűtípus nem érhető el a rendszeren, a PDF-megtekintő tartalék betűtípust használ a szöveg megjelenítéséhez. A különböző rendszerek közötti kompatibilitás biztosítása érdekében tanácsos egy általánosan elérhető betűtípust választani, például az Arial vagy a Times New Roman.