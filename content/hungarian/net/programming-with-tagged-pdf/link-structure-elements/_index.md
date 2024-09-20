---
title: Link szerkezeti elemek
linktitle: Link szerkezeti elemek
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre hivatkozásszerkezeti elemeket PDF-ben az Aspose.PDF for .NET használatával. Lépésről lépésre útmutató elérhető hivatkozások, képek hozzáadásához és a megfelelőség ellenőrzéséhez.
type: docs
weight: 120
url: /hu/net/programming-with-tagged-pdf/link-structure-elements/
---
## Bevezetés

A hivatkozásszerkezet elemeinek létrehozása és kezelése PDF-ben kulcsfontosságú lehet a hozzáférhetőséget és gördülékeny navigációt igénylő dokumentumok esetében. Ebben az oktatóanyagban végigvezetjük, hogyan teheti ezt meg az Aspose.PDF for .NET használatával. Ha még nem ismeri az Aspose.PDF vagy általában a PDF-kezelést, ne aggódjon. Minden lépést részletesen elmagyarázok, hogy könnyen követhesd!

## Előfeltételek  

Mielőtt belemerülnénk a kódolásba, tegyünk néhány dolgot az útból. Ezek az alapvető követelmények a zökkenőmentes fejlesztési élmény biztosításához.

1.  Aspose.PDF for .NET: Letöltheti a legújabb verziót[itt](https://releases.aspose.com/pdf/net/).
2. .NET fejlesztői környezet: Legyen szó Visual Studio-ról vagy bármilyen .NET-kompatibilis IDE-ről, telepítse és készen áll.
3.  Aspose Licenc: Használhatja az Aspose.PDF ingyenes próbaverzióját[itt](https://releases.aspose.com/) vagy megszerezni a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).
4. Alapvető C# ismerete: Néhány C# kóddal fogunk dolgozni, így az alapok megértése sokkal könnyebbé teszi a dolgokat.

## Csomagok importálása

Importálnia kell néhány csomagot, mielőtt megírná a hivatkozásszerkezet elemeinek kódját. Kezdje a szükséges Aspose.PDF könyvtárak hivatkozásával a projektben:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ezek az importálások lehetővé teszik számunkra, hogy PDF-dokumentumokkal dolgozzunk, címkéket adjunk hozzá, és kezeljük a szerkezeti elemeket.

Most létrehozunk egy PDF-dokumentumot különböző típusú hivatkozási struktúrákkal, és minden lépést lebontunk, hogy segítsünk Önnek a folyamat alapos megértésében.

## 1. lépés: Inicializálja a dokumentumot  

Kezdjük egy új PDF-dokumentum létrehozásával, és állítsa be a címkézett tartalmat a hozzáférhetőség érdekében.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Hozzon létre egy új PDF dokumentumot
Document document = new Document(); 

// A TaggedContent felület lekérése
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Itt inicializáljuk a`Document` objektum, amely a mi PDF fájlunkat képviseli. Mi is lekérjük a`TaggedContent` felület, amely lehetővé teszi számunkra, hogy szerkezeti elemeket, például bekezdéseket, hivatkozásokat és képeket adjunk hozzá.

## 2. lépés: Állítsa be a címet és a nyelvet  

Minden PDF-nek rendelkeznie kell címmel és nyelvi beállítással, különösen, ha a PDF/UA szabványoknak való megfelelést szeretné elérni.

```csharp
// Állítsa be a dokumentum címét és nyelvét
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Ez a lépés biztosítja, hogy a PDF-nek értelmes címe legyen, és a nyelvet angolra állítja (`en-US`). Ez kritikus a hozzáférhetőség szempontjából, és biztosítja, hogy a képernyőolvasók vagy más segítő technológiák helyesen tudják értelmezni a dokumentumot.

## 3. lépés: Bekezdések létrehozása és hozzáfűzése  

Ebben a lépésben bekezdéseket adunk hozzá a hivatkozási elemek megtartásához.

```csharp
// Hozd létre a gyökérelemet
StructureElement rootElement = taggedContent.RootElement;

// Hozzon létre egy bekezdést, és adja hozzá a gyökérelemhez
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Létrehozunk egy gyökérstruktúra elemet, amely lényegében az összes többi elem legfelső szintű tárolója. Ezután létrehozunk egy bekezdést (`p1`), és fűzze a gyökérelemhez.

## 4. lépés: Egyszerű hivatkozás hozzáadása  

Most adjunk hozzá egy alapvető hivatkozást, amely a Google-ra mutat.

```csharp
// Hozzon létre egy hivatkozáselemet, és adja hozzá a bekezdéshez
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Állítson be hiperhivatkozást és szöveget a hivatkozáshoz
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
Ebben a lépésben létrehoztunk egy linkelemet, hiperhivatkozását a „http://google.com” értékre állítottuk, és szöveget („Google”) adtunk meg a hivatkozáshoz. A hozzáférhetőség biztosítása érdekében egy alternatív leírást is hozzáadtunk.

## 5. lépés: Hivatkozás hozzáadása spanokkal  

Különböző szöveghosszúságú hivatkozásokat is létrehozhatunk.

```csharp
// Hozzon létre egy másik bekezdést
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Hozzon létre egy hivatkozást span elemmel
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Itt egy span elemet használtunk a szöveg egy részének a hivatkozáson belüli bezárására, lehetővé téve számunkra, hogy testreszabjuk, hogyan jelenjenek meg a hivatkozás egyes részei.

## 6. lépés: Többsoros kapcsolat  

Mi van, ha a link szövege túl hosszú? Ne aggódjon, több sorra is feloszthatja.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
Ebben az esetben egy többsoros hivatkozást hoztunk létre egyszerűen egy hosszú szöveg értékének megadásával, és a szöveg automatikusan több sorba kerül.

## 7. lépés: Adjon hozzá egy képet a hivatkozáshoz  

Végül képeket is hozzáadhat egy hivatkozáson belül.

```csharp
// Hozzon létre egy új bekezdést és hivatkozáselemet
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Kép hozzáadása a linkhez
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Ez a lépés bemutatja, hogyan javíthatja a linkeket képpel. Ebben az esetben hozzáadtunk egy Google ikont a linken belül. A hozzáférhetőséget a képhez alternatív szöveg beállításával is biztosítottuk.

## 8. lépés: Érvényesítse a PDF megfelelőségét  

Ha a PDF/UA megfelelőségre (kisegítő lehetőségek) való megfelelésre törekszik, jó gyakorlat a dokumentum érvényesítése.

```csharp
// Mentse el a PDF dokumentumot
document.Save(outFile);

// Érvényesítse a dokumentumot a PDF/UA megfelelőség szempontjából
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
A dokumentumot elmentettük, és a PDF/UA szabvány szerint érvényesítettük, ami biztosítja, hogy a PDF megfeleljen a kisegítő lehetőségek követelményeinek.

## Következtetés  

Ebben az oktatóanyagban bemutattuk, hogyan hozhat létre strukturált PDF dokumentumokat az Aspose.PDF for .NET használatával. Ez az útmutató az alapvető hiperhivatkozások hozzáadásával bonyolultabb struktúrákig, például spanokhoz, többsoros hivatkozásokig és még képekig is szilárd alapot biztosít a PDF-fájlok hivatkozáselemeinek kezeléséhez. A PDF/UA-megfelelőség további előnyével most már készen áll arra, hogy hozzáférhető és navigálható PDF-fájlokat készítsen.

## GYIK

### Hozzáadhatok összetettebb struktúrákat, például táblázatokat a hivatkozásokon belül?  
Nem, a hivatkozások elsősorban szöveget és képeket tartalmaznak, de a közelben beágyazhat összetett elemeket is.

### Kötelező a PDF/UA érvényesítése?  
Nem mindig, de erősen ajánlott, ha aggódik a kisegítő lehetőségek miatt.

### Mi történik, ha a képfájl elérési útja helytelen?  
A dokumentum nem jeleníti meg a képet, és hibát okozhat a renderelés során.

### Stílusozhatom a szöveget a linken belül?  
Igen, alkalmazhat szövegstílusokat a span elemekkel.

### Lehetséges belső dokumentumhivatkozásokat létrehozni?  
Teljesen! Ugyanazon dokumentumon belül meghatározott szakaszokra hivatkozhat.