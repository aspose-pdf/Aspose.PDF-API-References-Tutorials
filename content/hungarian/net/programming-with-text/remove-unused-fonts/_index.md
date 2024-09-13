---
title: Távolítsa el a nem használt betűtípusokat a PDF-fájlból
linktitle: Távolítsa el a nem használt betűtípusokat a PDF-fájlból
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan távolíthat el nem használt betűtípusokat PDF-fájlból az Aspose.PDF for .NET segítségével.
type: docs
weight: 300
url: /hu/net/programming-with-text/remove-unused-fonts/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan távolíthatja el a nem használt betűtípusokat PDF-fájlból az Aspose.PDF könyvtár segítségével a .NET-hez. Lépésről lépésre végigvesszük a PDF betöltésének folyamatát, a nem használt betűtípusok azonosítását és eltávolítását, valamint a frissített PDF-fájl mentését a mellékelt C# forráskóddal.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.PDF for .NET könyvtár telepítve van.
- A C# programozás alapvető ismerete.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

 Először is be kell állítania annak a könyvtárnak az elérési útját, ahol a PDF-fájlok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó a PDF-fájlok elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a Source PDF fájlt

 Ezután betöltjük a forrás PDF dokumentumot a`Document` osztály az Aspose.PDF könyvtárból.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 3. lépés: A nem használt betűtípusok azonosítása és eltávolítása

 Létrehozunk a`TextFragmentAbsorber` tárgyat a`TextEditOptions` paraméter beállítva`TextEditOptions.FontReplace.RemoveUnusedFonts` . Ez az opció lehetővé teszi számunkra, hogy azonosítsuk és eltávolítsuk a nem használt betűtípusokat a PDF-dokumentumból. Ezután ismételjük az összeset`TextFragments` és állítsa be a betűtípust a kívánt betűtípusra.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 4. lépés: Mentse el a frissített PDF-fájlt

Végül elmentjük a frissített PDF dokumentumot a megadott kimeneti fájlba.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Minta forráskód a nem használt betűtípusok eltávolításához az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Forrás PDF fájl betöltése
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Ismételje meg az összes szövegtöredéket
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Mentse el a frissített dokumentumot
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan távolíthat el nem használt betűtípusokat egy PDF-dokumentumból az Aspose.PDF könyvtár segítségével a .NET-hez. A lépésenkénti útmutató követésével és a mellékelt C#-kód végrehajtásával PDF-fájlt tölthet be, azonosíthatja és eltávolíthatja a nem használt betűtípusokat, valamint mentheti a frissített PDF-fájlt.

### GYIK

#### K: Mi a célja a „Nem használt betűtípusok eltávolítása a PDF-fájlból” oktatóanyagnak?

V: A „Nem használt betűtípusok eltávolítása PDF-fájlból” című oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez a nem használt betűtípusok PDF-dokumentumból való eltávolítására. Az oktatóanyag végigvezeti a PDF betöltésének, a nem használt betűtípusok azonosításának és eltávolításának, valamint a frissített PDF mentésének folyamatán.

#### K: Miért szeretném eltávolítani a nem használt betűtípusokat egy PDF-dokumentumból?

V: A nem használt betűtípusok PDF-dokumentumból való eltávolítása csökkentheti a fájl méretét és optimalizálhatja a dokumentumot a jobb teljesítmény érdekében. Ez különösen akkor hasznos, ha olyan PDF-dokumentumokkal foglalkozik, amelyek olyan beágyazott betűtípusokat tartalmaznak, amelyeket valójában nem használnak a dokumentum tartalmában.

#### K: Hogyan állíthatom be a dokumentumkönyvtárat?

V: A dokumentumkönyvtár beállításához:

1.  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó annak a könyvtárnak az elérési útjával, ahol a PDF-fájlok találhatók.

#### K: Hogyan távolíthatom el a nem használt betűtípusokat egy PDF-dokumentumból az Aspose.PDF könyvtár használatával?

V: Az oktatóanyag lépésről lépésre végigvezeti a folyamaton:

1.  Nyissa meg a PDF dokumentumot a`Document` osztály.
2.  Hozzon létre a`TextFragmentAbsorber` tárgyat`TextEditOptions` beállítva`FontReplace.RemoveUnusedFonts`.
3. Fogadja el az abszorbert a nem használt betűtípusok azonosításához és eltávolításához a PDF-ből.
4.  Iteráljon mindent`TextFragments` és állítsa be a betűtípust a kívánt betűtípusra.
5. Mentse el a frissített PDF dokumentumot.

####  K: Mi a célja a`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 V: A`TextEditOptions.FontReplace.RemoveUnusedFonts` paraméter utasítja a`TextFragmentAbsorber` nem használt betűtípusok azonosítása és eltávolítása a PDF-dokumentumból.

#### K: Lecserélhetem a nem használt betűtípusokat egy általam választott betűtípusra?

V: Igen, módosíthatja a kódot, hogy a fel nem használt betűtípusokat tetszőleges betűtípusra cserélje. A megadott mintakódban az „Arial, Bold” betűtípust használjuk helyettesítőként.

#### K: Hogyan működik a`TextFragmentAbsorber` work to remove unused fonts?

 V: A`TextFragmentAbsorber` -vel van konfigurálva`TextEditOptions.FontReplace.RemoveUnusedFonts` paraméter, amely azonosítja a nem használt betűtípusokat a PDF szövegrészein belül. Felszívódás után ismételheti a`TextFragments` és állítsa be a betűtípusaikat a kívánt helyettesítő betűtípusokra.

#### K: Mi a várt eredménye a megadott kód végrehajtásának?

V: Az oktatóanyag követésével és a mellékelt C# kód futtatásával eltávolítja a nem használt betűtípusokat a bemeneti PDF-dokumentumból, és menti a frissített verziót kimeneti PDF-fájlként.

#### K: Módosíthatom a kódot úgy, hogy csak bizonyos oldalakról vagy területekről távolítsam el a betűtípusokat?

V: A mellékelt kód arra összpontosít, hogy eltávolítsa a nem használt betűtípusokat a teljes PDF-dokumentumból. Ha konkrét oldalakat vagy régiókat szeretne megcélozni a betűtípus eltávolításához, módosítania kell a megközelítést, és összetettebb logikát kell alkalmaznia a nem használt betűtípusok azonosítására ezeken a területeken.