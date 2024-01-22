---
title: Cserélje ki a hiányzó betűtípusokat
linktitle: Cserélje ki a hiányzó betűtípusokat
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a hiányzó betűtípusok pótlásához egy PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 260
url: /hu/net/document-conversion/replace-missing-fonts/
---
Ebben az oktatóanyagban végigvezetjük a hiányzó betűtípusok pótlásának folyamatán egy PDF-fájlban az Aspose.PDF for .NET használatával. Amikor megnyit egy PDF-fájlt egy olyan gépen, amelyről hiányzik egy adott betűtípus, előfordulhatnak betűtípus-megjelenítési problémák. Ilyen esetekben lehetőség van a hiányzó betűtípus pótlására a gépen elérhető másik betűtípussal. Az alábbi lépések követésével pótolhatja a hiányzó betűtípusokat egy PDF-fájlban.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: Keresse meg a hiányzó betűtípust
Az első lépés a hiányzó betűtípus megkeresése a PDF-fájlban. Használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Keresse meg az eredeti betűtípust
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // A betűtípus hiányzik a célgépen
     // Egyszerű betűkészlet-helyettesítés hozzáadása
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol a PDF-fájl található.

## 2. lépés: Cserélje ki a hiányzó betűtípust
Ezután a hiányzó betűtípust egy másik elérhető betűtípusra cseréljük. Használja a következő kódot:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Konvertálja a PDF fájlt PDF/A formátumba hibaeltávolítással
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Mentse el a kapott PDF-fájlt
pdf.Save(fileNew.FullName);
```

 Feltétlenül cserélje ki`"input.pdf"` az eredeti PDF-fájl tényleges elérési útjával és`"newfile_out.pdf"` az eredményül kapott PDF-fájl kívánt nevével.

## 3. lépés: Mentse el a kapott PDF-fájlt
Végül elmentjük a kapott PDF-fájlt a lecserélt betűtípussal. Használja a következő kódot:

```csharp
// Mentse el a kapott PDF-fájlt
pdf.Save(fileNew.FullName);
```

Győződjön meg arról, hogy a megfelelő célútvonalat állította be az eredményül kapott PDF-fájlhoz.

### Példa forráskódra a Hiányzó betűtípusok cseréjéhez az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// A célgépről hiányzik a betűtípus
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Következtetés
Ebben az oktatóanyagban lépésről lépésre bemutattuk a hiányzó betűtípusok pótlásának folyamatát egy PDF-fájlban az Aspose.PDF for .NET használatával. A fent vázolt utasítások követésével sikeresen pótolhatja a hiányzó betűtípusokat a PDF-fájlban.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF dokumentumokkal dolgozzanak C# alkalmazásokban. Különféle funkciókat kínál, beleértve a hiányzó betűtípusok pótlását a PDF-fájlokban.

#### K: Miért találok hiányzó betűtípusokat egy PDF-fájlban?

V: A PDF-fájlból hiányozhatnak a betűtípusok, ha a fájlt olyan gépen nyitják meg, amelyen nincsenek telepítve a szükséges betűtípusok. Ez betűtípus-cseréhez vezethet, ami befolyásolja a dokumentum vizuális megjelenését.

#### K: Hogyan találhatom meg és cserélhetem ki a hiányzó betűtípusokat egy PDF-fájlban az Aspose.PDF for .NET használatával?

 V: A hiányzó betűtípusok megkereséséhez és pótlásához használhatja a`FontRepository.FindFont` módszer a szükséges betűtípus meglétének ellenőrzésére. Ha a betűtípus hiányzik, a betűkészlet helyettesítésével a`FontRepository.Substitutions` ingatlan.

#### K: Testreszabhatom a betűtípus-csere folyamatát?

V: Igen, testreszabhatja a betűkészlet-csere folyamatát, ha más betűtípust ad meg a helyettesítéshez. A megadott kódban az Arial-t használtuk a hiányzó "AgencyFB" betűtípus helyettesítőjeként, de választhat más betűtípust is, ízlése szerint.

#### K: Hogyan biztosíthatom a betűkészlet-megjelenítés pontosságát csere után?

V: Az Aspose.PDF for .NET robusztus betűtípus-kezelési képességeket biztosít, biztosítva a pontos betűkészlet-megjelenítést a helyettesítés után. Megtekintheti a kapott PDF-fájl előnézetét a betűtípus cseréjének ellenőrzéséhez.