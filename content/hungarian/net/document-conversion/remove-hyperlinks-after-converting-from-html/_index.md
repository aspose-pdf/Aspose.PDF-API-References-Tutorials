---
title: Html-ből való konvertálás után távolítsa el a hiperhivatkozásokat
linktitle: Html-ből való konvertálás után távolítsa el a hiperhivatkozásokat
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató a hiperhivatkozások eltávolításához, miután a HTML-t PDF-be konvertálta az Aspose.PDF for .NET segítségével.
type: docs
weight: 250
url: /hu/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
Ebben az oktatóanyagban végigvezetjük a hiperhivatkozások eltávolításának folyamatán egy HTML-fájlból előállított PDF-fájlból az Aspose.PDF for .NET használatával. A hiperhivatkozások kattintható hivatkozások, amelyek más oldalakra vagy webhelyekre irányíthatnak át. Az alábbi lépések követésével eltávolíthatja a hiperhivatkozásokat a kapott PDF-fájlból.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: HTML-fájl betöltése és a hiperhivatkozások eltávolítása
Ebben a lépésben betöltjük a HTML-fájlt, és eltávolítjuk a hiperhivatkozásokat a kapott PDF-dokumentumból. Használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a HTML-fájlt a HTML-betöltési beállítások segítségével
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Böngésszen a dokumentum első oldalának megjegyzései között
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Ellenőrizze, hogy a megjegyzés hivatkozás-e
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Ellenőrizze, hogy a művelet GoToOURIAction típusú-e
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Használjon szövegtöredék-elnyelőt a megfelelő szövegrészletek megtalálásához
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Keresse át az egyező szövegrészleteket, és távolítsa el az attribútumokat a hiperhivatkozásokból
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Távolítsa el a megjegyzést az oldalról
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol a HTML-fájl található.

## 2. lépés: Mentse el a kapott PDF-fájlt
Végül elmentjük a kapott PDF-fájlt a hiperhivatkozások nélkül. Használja a következő kódot:

```csharp
// Mentse el a kapott PDF-fájlt
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 A fenti kód elmenti az eredményül kapott PDF-fájlt a fájlnévvel`"RemoveHyperlinksFromText_out.pdf"`.

### Példa forráskód a Hiperhivatkozások eltávolítása HTML-ből való konvertálás után az Aspose.PDF for .NET használatával programhoz

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Következtetés
Ebben az oktatóanyagban lépésről lépésre bemutattuk a hiperhivatkozások eltávolításának folyamatát egy HTML-fájlból előállított PDF-fájlból az Aspose.PDF for .NET használatával. A fent leírt utasításokat követve sikeresen eltávolíthatja a hiperhivatkozásokat a létrejövő PDF-fájlból.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF dokumentumokkal dolgozzanak C# alkalmazásokban. A funkciók széles skáláját kínálja, beleértve a HTML-fájlok PDF-formátumba konvertálását és a PDF-tartalom manipulálását.

#### K: Miért szeretném eltávolítani a hiperhivatkozásokat egy PDF-fájlból?

V: Különféle okai vannak a hiperhivatkozások PDF-fájlból való eltávolításának. Előfordulhat például, hogy el szeretné távolítani a külső hivatkozásokat nyomtatási vagy archiválási célból, vagy biztosítania kell, hogy a PDF-tartalom ne legyen navigálható hiperhivatkozásokon keresztül.

#### K: Hogyan tölthetek be egy HTML-fájlt és távolíthatok el hiperhivatkozásokat az Aspose.PDF for .NET használatával?

 V: Egy HTML-fájl betöltéséhez és a hiperhivatkozások eltávolításához használhatja az Aspose.PDF-et .NET-hez.`HtmlLoadOptions` osztály. Ismételje meg a PDF-oldalak megjegyzéseit, hogy megtalálja a hivatkozásokat, és módosítsa azok attribútumait.

#### K: Testreszabhatom a kimeneti fájl nevét az eredményül kapott PDF-hez?

V: Igen, testreszabhatja az eredményül kapott PDF-fájl kimeneti fájlnevét a PDF-dokumentumot mentő kód módosításával. Egyszerűen módosítsa a kívánt fájlnevet a`doc.Save()` módszer.

#### K: Lehetséges a hiperhivatkozások szelektív eltávolítása bizonyos kritériumok alapján?

V: Igen, adott kritériumok alapján szelektíven eltávolíthatja a hiperhivatkozásokat. Dönthet például úgy, hogy csak a külső hivatkozásokat vagy az adott URL-ekre mutató hivatkozásokat távolítsa el.