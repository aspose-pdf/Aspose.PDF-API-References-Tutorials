---
title: Rejtett szöveg hozzáadása és keresése PDF-fájlban
linktitle: Rejtett szöveg hozzáadása és keresése PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanuljon meg rejtett szöveget hozzáadni és keresni PDF dokumentumokban az Aspose.PDF for .NET segítségével. Lépésről lépésre útmutató kódpéldákkal.
type: docs
weight: 20
url: /hu/net/programming-with-text/add-and-search-hidden-text/
---
## Bevezetés

Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá rejtett szöveget és kereshet meg egy PDF-fájlban az Aspose.PDF for .NET használatával. Akár tapasztalt fejlesztő, akár újonc, aki szeretné fejleszteni programozási készségeit, ez a cikk betekintést nyújt a rejtett szöveges funkciók beépítéséhez az alkalmazásaiba.

## Előfeltételek

Mielőtt belemerülne a kódolási részbe, van néhány előfeltétel, amire ügyelnie kell:

### Követelmény ellenőrző lista
- Visual Studio: Győződjön meg arról, hogy telepítve van a Visual Studio. Ez az oktatóanyag feltételezi, hogy .NET-keretrendszert használ.
-  Aspose.PDF for .NET: rendelkeznie kell az Aspose.PDF for .NET könyvtárral. Letöltheti[itt](https://releases.aspose.com/pdf/net/).
- C# alapismeretei: A C# programozás ismerete segít a kódrészletek jobb megértésében.

## Csomagok importálása

Mielőtt elkezdené a kód használatát, meg kell győződnie arról, hogy importálja a szükséges Aspose.PDF névtereket. Íme, hogyan kell csinálni:

### Állítsa be projektjét
1. Nyissa meg a Visual Studio-t, és hozzon létre egy új C#-projektet, vagy használjon egy meglévőt.
2.  Telepítse az Aspose.PDF fájlt a NuGet csomag hozzáadásával. Ezt úgy teheti meg, hogy navigál a NuGet Package Managerhez, és rákeres a következőre`Aspose.PDF`. 
3.  Alternatív megoldásként közvetlenül letöltheti a könyvtárat innen[itt](https://releases.aspose.com/pdf/net/) és adja hozzá referenciaként a projekthez.

### Importálja a szükséges névtereket
A C# fájl tetején importálja a következő névtereket:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ez a lépés kulcsfontosságú, mivel ezek a névterek tartalmazzák a PDF-dokumentumok kezeléséhez szükséges osztályokat és módszereket.

## PDF dokumentum készítése rejtett szöveggel

Most, hogy elkészült, végezzük el a látható és láthatatlan szöveget egyaránt tartalmazó PDF-dokumentum létrehozásának lépéseit.

### 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a PDF mentési útvonalát. Itt kezdődik a varázslat!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Módosítsa ezt a saját könyvtárára
```

 Ez a sor határozza meg, hogy hol kerüljön tárolásra a létrehozott PDF. Ne felejtse el cserélni`YOUR DOCUMENT DIRECTORY` a valódi utaddal.

### 2. lépés: Hozzon létre egy PDF-dokumentumot
Ezután hozzunk létre egy új PDF-dokumentumot, és adjunk hozzá oldalakat.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Itt inicializálunk egy új dokumentumot, és hozzáadunk egy oldalt, ahol elhelyezzük a szövegrészleteket.

### 3. lépés: Adjon hozzá látható és rejtett szöveget
Most látható és láthatatlan szöveget is hozzáadunk a PDF-hez.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Ebben a részletben`frag1` látható lesz, míg`frag2` legközelebb láthatatlanra lesz állítva.

### 4. lépés: Állítsa a szöveget láthatatlanra
 A szöveg elkészítéséhez`frag2` láthatatlan, egyszerűen módosíthatja`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Ennek a tulajdonságnak a beállításával bármely szöveg, amelyhez társított`frag2` nem jelenik meg a PDF megtekintésekor.

### 5. lépés: Szövegtöredékek hozzáadása az oldalhoz
Végül hozzáadjuk ezeket a szövegrészleteket az oldalhoz, és elmentjük a PDF-et.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

kód ezen része hozzáadja a szövegrészleteinket az oldalhoz. Ezt követően a dokumentumot megfelelően elmentjük és megsemmisítjük.

## Rejtett szöveg keresése a PDF-ben

Most, hogy elkészítettük a látható és rejtett szöveget is tartalmazó PDF-fájlt, hogyan keressük meg ezt a rejtett szöveget? Bontsuk szét.

### 1. lépés: Töltse be a PDF-dokumentumot
Szöveg kereséséhez a PDF-ben először be kell töltenünk az éppen létrehozott dokumentumot.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### 2. lépés: Hozzon létre egy szövegtöredék-elnyelőt
 használni fogjuk`TextFragmentAbsorber` hogy rögzítse az összes szövegrészletet a PDF-ben.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Itt megadjuk, hogy az összes szövegrészletet az első oldalról szeretnénk felvenni.

### 3. lépés: Ismétlés a töredékeken keresztül
Most ismételhetjük az összegyűjtött szövegrészleteket, hogy megtudjuk, melyek láthatók és melyek rejtettek.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Ez a ciklus minden egyes szövegrészletet ellenőriz, és kinyomtatja annak tartalmát, valamint a helyzetét és láthatósági állapotát. Ha`fragment.TextState.Invisible` igazra van állítva, ez azt jelenti, hogy a szöveg el van rejtve!

### 4. lépés: Dobja ki a dokumentumot
Végül ne felejtse el újra kidobni a dokumentumot, ha végzett.

```csharp
doc.Dispose();
```

## Következtetés

Ebben az oktatóanyagban végigjártuk a rejtett szöveg hozzáadásának és keresésének izgalmas folyamatát PDF-fájlokban az Aspose.PDF for .NET használatával. Megtanultuk, hogyan készítsünk látható és rejtett szöveget egyaránt tartalmazó PDF-dokumentumot, és hogyan keressük meg a rejtett szöveget programozottan. Ez a képesség hihetetlenül hasznos lehet különféle alkalmazásokban, akár bizalmas információkat kell tárolnia, akár egyedi felhasználói élményt kell biztosítania a dokumentumokon belül.

Ahogy egyre jobban megismeri az ASPose.PDF-et, a lehetőségek végtelenné válnak. Kísérletezzen tovább, és feszegesse a határait, hogy mit érhet el PDF-dokumentumaival!

## GYIK

### Az Aspose.PDF képes kezelni a titkosított PDF fájlokat?  
Igen, az Aspose.PDF támogatja a PDF dokumentumok titkosítását és visszafejtését. Könnyedén megvédheti PDF-fájljait jelszavakkal.

### Elérhető az Aspose.PDF próbaverziója?  
 Teljesen! Az ingyenes próbaverziót innen töltheti le[itt](https://releases.aspose.com/).

### Milyen programozási nyelveket támogat az Aspose.PDF?  
Az Aspose.PDF több nyelvet is támogat, beleértve a C#-t, a Java-t és a Python-t.

### Hol találom az Aspose.PDF dokumentációját?  
 Hozzáférhet a dokumentációhoz[itt](https://reference.aspose.com/pdf/net/).

### Hogyan kaphatok támogatást, ha problémákba ütközöm?  
 Támogatásért keresse fel az Aspose fórumait[itt](https://forum.aspose.com/c/pdf/10).