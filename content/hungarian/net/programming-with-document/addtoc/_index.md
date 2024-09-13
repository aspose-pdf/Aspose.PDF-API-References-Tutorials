---
title: TOC hozzáadása PDF fájlhoz
linktitle: TOC hozzáadása PDF fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá tartalomjegyzéket PDF-fájlhoz az Aspose.PDF for .NET használatával. Ez a lépésenkénti útmutató leegyszerűsíti a folyamatot, és biztosítja a könnyű navigációt a dokumentumok között.
type: docs
weight: 40
url: /hu/net/programming-with-document/addtoc/
---
## Bevezetés

Előfordult már, hogy végtelenségig görgetett egy hosszú PDF-fájlt, és azt kívánta, bárcsak jól szervezett tartalomjegyzéke lenne? Nos, ez a szerencsés napod! Ebből az oktatóanyagból megtudhatja, hogyan adhat hozzá tartalomjegyzéket PDF-fájljához az Aspose.PDF for .NET használatával. Legyen szó összetett jelentésről, e-könyvről vagy üzleti javaslatról, a TOC professzionális, navigálható remekművé változtathatja dokumentumát.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjünk meg arról, hogy mindent megvan, amire szüksége van:

1. Aspose.PDF for .NET: Győződjön meg arról, hogy letöltötte és telepítette az Aspose.PDF könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
   
2. Fejlesztői környezet: Győződjön meg arról, hogy a számítógépén be van állítva egy .NET fejlesztői környezet, például a Visual Studio.

3.  Licenc: Ha nem rendelkezik licenccel, ingyenes próbaverziót kaphat, vagy ideiglenes licencet kérhet[itt](https://purchase.aspose.com/temporary-license/).

## Csomagok importálása

A kezdéshez feltétlenül importálja a szükséges névtereket a kódfájl elejére. Íme, hogyan:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ezek a névterek lehetővé teszik a PDF-specifikus funkciók elérését és a dokumentum szöveges elemeinek kezelését.

Bontsuk ezt a feladatot falatnyi lépésekre. Minden lépés végigvezeti Önt a TOC létrehozásának és a PDF-dokumentumba történő beillesztésének folyamatán.

## 1. lépés: Töltse be a PDF-dokumentumot

Az első dolog, amit tennünk kell, hogy betöltsük a meglévő PDF-fájlt, amelyhez hozzá szeretnénk adni a TOC-t.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 Ebben a lépésben megadjuk a dokumentumkönyvtár elérési útját, és betöltjük a PDF-fájlt a`Document` objektum. Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a fájl tényleges elérési útjával.

## 2. lépés: Szúrjon be egy új oldalt a TOC-hoz

Ezután beszúrunk egy új oldalt a PDF dokumentum elejére. Ezen az oldalon található a Tartalomjegyzék.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

A TOC oldal elejére történő beszúrásával biztosítjuk, hogy az elsőként jelenjen meg a PDF-ben.

## 3. lépés: Hozzon létre egy TOC információs objektumot

Most hozzunk létre egy objektumot, amely képviseli a TOC információkat. A TOC-hoz egy címet is adunk, hogy kiemelkedjen.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Itt a tartalomjegyzék címét "Tartalomjegyzék"-re adtuk, megnöveltük a betűméretet, és félkövérré tettük a kiemelés érdekében.

## 4. lépés: Határozza meg a TOC elemeket

Ebben a lépésben meghatározzuk azokat az elemeket (vagy címsorokat), amelyek megjelennek a TOC-ban. Ezek az elemek segítenek az olvasóknak eligazodni a dokumentum bizonyos részeihez.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Létrehoztunk egy sor karakterláncot, amely tartalomjegyzék-elemként fog szolgálni, a PDF különböző oldalainak megfelelően.

## 5. lépés: Hozzon létre TOC címsorokat

Most jön a döntő rész – fejlécek hozzáadása a TOC-hoz és linkelésük a megfelelő oldalukhoz.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Íme, mi történik:
- Címsor: Létrehozunk a`Heading` objektumot, és add hozzá a`TextSegment` hozzá.
- Céloldal: Beállítjuk azt az oldalt, amelyre minden címsor hivatkozni fog.
- Legfelső pozíció: Meghatározzuk azt a pozíciót az oldalon, ahová a címsor mutat.
- Szöveg: Minden címsor megkapja a megfelelő címet a korábban létrehozott tömbből.

Ez a ciklus címsorokat hoz létre a tartalomjegyzék első két eleméhez, és összekapcsolja őket a megfelelő oldalakkal.

## 6. lépés: Mentse el a PDF-fájlt a tartalomjegyzékkel

Végül, miután az összes TOC elemet hozzáadtuk, ideje elmenteni a frissített PDF-et.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

A fájl most a PDF-hez hozzáadott tartalomjegyzékkel kerül mentésre. Gratulálunk – sikeresen hozzáadta a tartalomjegyzéket!

## 7. lépés: Megerősítő üzenet

Annak érdekében, hogy a felhasználó tudja, hogy a folyamat befejeződött, egy egyszerű üzenetet jelenítünk meg a konzolon.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Következtetés

És megvan! Az Aspose.PDF for .NET segítségével tartalomjegyzék hozzáadása a PDF-hez nem csak egyszerű, hanem testreszabható is. Akár egyszerű navigációs hivatkozásokat, akár összetett struktúrákat kell létrehoznia, ez az eszköz mindent megtalál. Tehát, ha legközelebb hosszadalmas PDF-en dolgozik, ne felejtse el hozzáadni a TOC-t ehhez a professzionális érintéshez!

## GYIK

### Testreszabhatom a TOC megjelenését az Aspose.PDF-ben?  
Igen, teljes mértékben testreszabhatja a tartalomjegyzék megjelenését, beleértve a betűstílust, -méretet és az igazítást.

### Hogyan adhatok alcímeket a tartalomjegyzékhez?  
 Alcímeket adhat hozzá a`Heading` szinten (pl.`Heading(2)`) hierarchikus tartalomjegyzék létrehozásához.

### Lehetséges a TOC automatikus frissítése, ha a dokumentum megváltozik?  
Nem, a tartalomjegyzék nem frissül automatikusan. Újra kell létrehoznia, ha a dokumentum szerkezete megváltozik.

### Összekapcsolhatom a TOC bejegyzéseket külső dokumentumokkal?  
Igen, hiperhivatkozások segítségével tartalomjegyzék-bejegyzéseket külső PDF-ekhez vagy URL-ekhez kapcsolhat.

### Az Aspose.PDF támogatja a többszintű tartalomjegyzékeket?  
Igen, az Aspose.PDF támogatja a többszintű tartalomjegyzéket az alszakaszokkal rendelkező összetett dokumentumokhoz.