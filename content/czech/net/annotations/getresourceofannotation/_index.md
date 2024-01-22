---
title: Získejte zdroj anotace
linktitle: Získejte zdroj anotace
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak získat zdroj anotace pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce.
type: docs
weight: 90
url: /cs/net/annotations/getresourceofannotation/
---
Příklad ukazuje, jak získat zdroj anotace pomocí Aspose.PDF pro .NET. Chcete-li získat zdroj anotace pomocí Aspose.PDF pro .NET, postupujte takto:

## Krok 1: Nastavte cestu k adresáři, kde je dokument umístěn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF, který obsahuje anotaci, jejíž zdroj chcete získat.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Krok 3: Vytvořte anotaci.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Krok 4: Přidejte anotaci na stránku v dokumentu.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Krok 5: Uložte dokument.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Krok 6: Otevřete upravený dokument.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Krok 7: Získejte akci anotace.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Krok 7: Získejte ztvárnění akce.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Krok 8: Získejte mediální klip.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Krok 9: Získejte specifikaci souboru.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Krok 10: Přečtěte si data média.

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

## Krok 11: Vytiskněte název interpretace a operaci vykreslení.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Pomocí následujících kroků můžete snadno získat zdroj anotace v dokumentu PDF pomocí Aspose.PDF for .NET.

### Příklad zdrojového kódu pro Get Resource Of Annotation pomocí Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Vytvořte anotaci
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Uložit dokument
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Otevřete dokument
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Získejte akci anotace
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Získejte vykreslení akce vykreslení
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Mediální klip
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Data médií jsou dostupná ve FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak získat zdroj konkrétní anotace z dokumentu PDF pomocí Aspose.PDF pro .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno přistupovat k anotacím, včetně anotací vykreslení, ve svých dokumentech PDF a spravovat je.

### FAQ

#### Otázka: Co je interpretace v kontextu anotací PDF?

Odpověď: V kontextu anotací PDF je interpretace prezentace multimediálního obsahu. Umožňuje vkládat multimédia, jako je zvuk nebo video, do dokumentu PDF. Anotace ztvárnění specifikuje média, která mají být prezentována, a způsob, jakým se má hrát.

#### Otázka: Mohu získat název mediálního souboru spojeného s anotací interpretace?

Odpověď: Ano, název mediálního souboru spojený s anotací interpretace můžete získat pomocí Aspose.PDF pro .NET. K názvu mediálního souboru lze přistupovat prostřednictvím`FileSpecification` z`MediaClip` objekt.

#### Otázka: Může Aspose.PDF for .NET extrahovat mediální soubory z anotace interpretace?

Odpověď: Ano, Aspose.PDF for .NET může extrahovat mediální data z anotace, která zahrnuje audio nebo video obsah, a uložit je jako samostatný soubor.

#### Otázka: Jak mohu získat přístup k mediálním datům anotace interpretace?

 Odpověď: K mediálním datům anotace ztvárnění lze přistupovat prostřednictvím`FileSpecification.Contents` vlastnictvím`MediaClipData` objekt.

#### Otázka: Mohu pomocí Aspose.PDF for .NET upravit média spojená s anotací interpretace?

Odpověď: Aspose.PDF for .NET poskytuje metody pro přístup a úpravu dat médií souvisejících s anotací interpretace. Můžete aktualizovat nebo nahradit mediální soubor použitý v anotaci interpretace.