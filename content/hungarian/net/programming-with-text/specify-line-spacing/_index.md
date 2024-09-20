---
title: Adja meg a sorközt a PDF-fájlban
linktitle: Adja meg a sorközt a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan adhat meg sorközt PDF-ben az Aspose.PDF for .NET használatával. Tökéletes a precíz szövegformázást kereső fejlesztők számára.
type: docs
weight: 510
url: /hu/net/programming-with-text/specify-line-spacing/
---
## Bevezetés

Küzdött már a sortávolság szabályozásával egy PDF-fájlban? Lehet, hogy volt olyan szövege, amely túl zsúfoltnak tűnik, vagy egyszerűen nem néz ki olyan finoman, mint szeretné. Ebben az oktatóanyagban azt mutatjuk be, hogyan adhatja meg egyszerűen a sorközt a PDF-ben az Aspose.PDF for .NET használatával. Egy egyszerű, lépésről lépésre bemutatott útmutatóval elvezetjük Önt az üres PDF-től az egyéni sorközt tartalmazó PDF-hez. Ez tökéletes, ha pontosságra van szüksége a dokumentumok, például jelentések, számlák vagy tanúsítványok szövegelrendezésében.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjünk meg arról, hogy mindent megvan, amire szüksége van:

1.  Aspose.PDF for .NET telepítve. Ha nincs meg, vedd elő a[Aspose.PDF letöltési oldal](https://releases.aspose.com/pdf/net/).
2. .NET fejlesztői környezet (mint például a Visual Studio).
3. Egy TrueType betűtípusfájl (`.ttf` ), amelyet a példában fogunk használni. Bármilyen betűtípust használhat, de ehhez az útmutatóhoz a`HPSimplified.TTF` betűtípus.
4. C# és PDF kezelési alapismeretek.

Ha készen áll, folytassa a szükséges csomagok importálásával.

## Csomagok importálása

C#-projektben importálnia kell az Aspose.PDF névtereket a PDF-funkciók használatához. Íme, hogyan kell ezt megtenni:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Ezek a névterek lehetővé teszik PDF-dokumentumok létrehozását és kezelését, valamint a szövegformázási és betűtípus-beállítások használatát.

Ezt falatnyi lépésekre bontjuk, így könnyedén követheti. Minden lépés a folyamat egy kulcsfontosságú részére összpontosít, a PDF beállításától a sorköz megadásáig.

## 1. lépés: Állítsa be projektjét és határozza meg a dokumentumkönyvtárat

Az első dolog, amit meg kell tennünk, hogy meghatározzuk, hol találhatók a fájljaink. Ez segít a programnak tudni, hogy hol találja meg a betűtípust, és hova mentse az eredményül kapott PDF-et.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 Ebben a lépésben ki kell cserélni`"YOUR DOCUMENT DIRECTORY"` a fájlok tárolási helyének tényleges elérési útjával. Itt helyezheti el a fontfájlt (`HPSimplified.TTF`) és a PDF mentési helyére.

## 2. lépés: Töltse be a PDF-dokumentumot

Most létre kell hoznunk egy új PDF dokumentumot. Ebben az útmutatóban egy üres dokumentummal kezdjük, de szükség esetén betölthet egy meglévő PDF-fájlt is.

```csharp
Document doc = new Document();
```

Ezzel új, üres PDF-dokumentumot hoz létre. Könnyű, igaz?

## 3. lépés: Állítsa be a szövegformázási beállításokat

 Itt történik a varázslat. Megadjuk a sorköz módot a PDF-hez hozzáadni kívánt szöveghez. Az Aspose.PDF számos lehetőséget kínál, de ebben az útmutatóban ezt fogjuk használni`LineSpacingMode.FullSize`, amely biztosítja, hogy a sortávolságot maradéktalanul betartsák.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Ez a kód beállítja a sorköz módot`FullSize` , biztosítva, hogy a szöveg megfelelő szóközzel jelenjen meg. Vannak más lehetőségek is, mint pl`Proportional` ha eltérő térközhasználati viselkedést szeretne, de most maradjunk ennél`FullSize`.

## 4. lépés: Hozzon létre egy szövegrészletet

Most létrehozzuk a tényleges szöveget, amely a PDF-be kerül. Ez a szöveg tiszteletben tartja az általunk meghatározott sorközt.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Létrehoztunk egy szövegrészletet a karakterlánccal`"Hello world"`. Természetesen ezt a szöveget tetszés szerint testreszabhatja.

## 5. lépés: Egyéni betűtípus betöltése és alkalmazása

szöveg kiemelése érdekében egy egyedi TrueType betűtípust fogunk betölteni egy fájlból. Ez a lépés nem kötelező, de professzionális megjelenést kölcsönöz PDF-fájljainak.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Itt betöltjük a fontfájlt, és alkalmazzuk a szövegrészletre. Ha a fájl elérési útja érvényes, akkor a betűtípus kerül felhasználásra. Ellenkező esetben az alapértelmezett betűtípus kerül alkalmazásra.

## 6. lépés: Állítsa be a szöveg pozícióját és formázását

Ezután el kell helyeznünk a szöveget a PDF-ben. Alkalmazzuk a korábban létrehozott formázási beállításokat is.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 A`Position` metódus beállítja azokat a koordinátákat, ahol a szöveg megjelenik az oldalon (ebben az esetben 100 egység balról és 600 egység alulról). Itt alkalmazzák a formázási beállításokat, beleértve a sorköz módot is.

## 7. lépés: Szöveg hozzáadása a PDF-oldalhoz

Most, hogy a szöveg formázása és elhelyezése megtörtént, ideje hozzáadni a PDF dokumentumhoz.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Ez a kód új oldalt hoz létre a PDF-dokumentumban, és hozzáadja a szövegrészletet.

## 8. lépés: Mentse el a PDF-fájlt

Elérkeztünk az utolsó lépéshez! Most, hogy minden be van állítva, mentsük a PDF-fájlt.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Ezzel elmenti a PDF-et a megadott sorközökkel, és a fájl készen áll!

## Következtetés

És ennyi! Létrehozott egy PDF-dokumentumot egyéni sorközzel az Aspose.PDF for .NET használatával. Ez egy hatékony eszköz, amely lehetővé teszi a PDF-fájlok minden aspektusának vezérlését, és ez csak egy példa arra, hogy mit érhet el. A szöveg elhelyezésétől a formázásig a lehetőségek végtelenek.

Ha mélyebbre szeretne merülni a PDF-kezelésben, az Aspose.PDF számos felfedezésre váró funkciót kínál. Ne habozzon kísérletezni, és feszegesse annak határait, hogy mit tehet dokumentumaival!

## GYIK

### Beállíthatom a sorközt más módokhoz?  
 Igen, használhatsz más módokat is, pl`Proportional` vagy`Fixed` igényeitől függően.

### Fájl helyett lehet betűtípusokat betölteni a rendszerből?  
 Igen, betöltheti a rendszer által telepített betűtípusokat a`FontRepository`.

### Használhatom az Aspose.PDF for .NET fájlt más fájlformátumokkal?  
Teljesen! Az Aspose.PDF for .NET számos formátumot támogat, például XML-t, HTML-t stb.

### Szükségem van licencre az Aspose.PDF for .NET használatához?  
Igen, a teljes funkcionalitáshoz licencre lesz szüksége, amelyet beszerezhet[itt](https://purchase.aspose.com/buy).

### Hogyan állíthatom be a sorközt több bekezdéshez?  
 Jelentkezni lehet`TextFormattingOptions` mindegyikhez`TextFragment` vagy`TextParagraph` több sor vagy bekezdés térközének szabályozásához.