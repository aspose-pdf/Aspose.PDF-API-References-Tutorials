---
title: Szerezze be a megjegyzések forrását
linktitle: Szerezze be a megjegyzések forrását
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan kérheti le a megjegyzések forrását az Aspose.PDF for .NET használatával.
type: docs
weight: 90
url: /hu/net/annotations/getresourceofannotation/
---
példa bemutatja, hogyan szerezhető be annotációs forrás az Aspose.PDF for .NET segítségével. Az Aspose.PDF for .NET használatával a kommentár forrásának lekéréséhez kövesse az alábbi lépéseket:

## 1. lépés: Állítsa be annak a könyvtárnak az elérési útját, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF-dokumentumot, amely tartalmazza azt a megjegyzést, amelynek forrását le szeretné szerezni.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 3. lépés: Hozzon létre egy megjegyzést.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## 4. lépés: Adja hozzá a megjegyzést a dokumentum egyik oldalához.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## 5. lépés: Mentse el a dokumentumot.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 6. lépés: Nyissa meg a módosított dokumentumot.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 7. lépés: Szerezze meg a megjegyzés műveletét.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## 7. lépés: Szerezd meg a művelet megjelenítését.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## 8. lépés: Szerezze be a média klipet.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## 9. lépés: Szerezze meg a fájl specifikációit.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## 10. lépés: Olvassa el az adathordozó adatait.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## 11. lépés: Nyomtassa ki a megjelenítés és a megjelenítési művelet nevét.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Ha követi ezeket a lépéseket, az Aspose.PDF for .NET használatával könnyedén hozzáférhet egy megjegyzés forrásához egy PDF-dokumentumban.

### Példa forráskódra az Aspose.PDF segítségével a .NET-hez készült megjegyzések forrásának lekéréséhez:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Jegyzet létrehozása
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Dokumentum mentése
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Nyissa meg a dokumentumot
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//A megjegyzés művelet végrehajtása
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//A megjelenítési művelet lekérése
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Médiaklip
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//A média adatai a FileSpecification.Contents oldalon érhetők el
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Következtetés

Ebben az oktatóanyagban azt vizsgáltuk, hogyan lehet egy adott megjegyzés forrását lekérni egy PDF-dokumentumból az Aspose.PDF for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt C#-forráskód használatával a fejlesztők könnyen elérhetik és kezelhetik PDF-dokumentumaik megjegyzéseit, beleértve a megjelenítési megjegyzéseket is.

### GYIK

#### K: Mit jelent a megjelenítés a PDF-annotációk kontextusában?

V: A PDF-annotációk kontextusában a megjelenítés egy multimédiás tartalom-prezentáció. Lehetővé teszi multimédia, például hang vagy videó beágyazását a PDF dokumentumba. A megjelenítési megjegyzés meghatározza a megjelenítendő médiát és a lejátszás módját.

#### K: Megtudhatom a megjelenítési megjegyzéshez társított médiafájl nevét?

V: Igen, az Aspose.PDF for .NET használatával lekérheti a megjelenítési megjegyzéshez társított médiafájl nevét. A médiafájl neve a következőn keresztül érhető el`FileSpecification` a`MediaClip` tárgy.

#### K: Az Aspose.PDF for .NET kivonhatja a médiafájlokat egy megjelenítési megjegyzésből?

V: Igen, az Aspose.PDF for .NET ki tudja bontani a médiaadatokat egy olyan megjelenítési megjegyzésből, amely audio- vagy videotartalmat is tartalmaz, és külön fájlként mentheti.

#### K: Hogyan férhetek hozzá a megjelenítési annotáció médiaadataihoz?

 V: A megjelenítési annotáció médiaadatai a következőn keresztül érhetők el`FileSpecification.Contents` tulajdona a`MediaClipData` tárgy.

#### K: Módosíthatom a megjelenítési annotációhoz társított adathordozót az Aspose.PDF for .NET használatával?

V: Az Aspose.PDF for .NET módszereket biztosít a megjelenítési megjegyzésekhez társított médiaadatok eléréséhez és módosításához. Frissítheti vagy lecserélheti a megjelenítési megjegyzés által használt médiafájlt.