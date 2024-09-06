---
title: Bekezdések kibontása PDF fájlba
linktitle: Bekezdések kibontása PDF fájlba
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthat ki bekezdéseket PDF-fájlból az Aspose.PDF for .NET segítségével.
type: docs
weight: 160
url: /hu/net/programming-with-text/extract-paragraphs/
---
Ez az oktatóanyag végigvezeti Önt a bekezdések PDF-fájlba történő kibontásán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelybe a bekezdéseket ki szeretné bontani, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Nyissa meg a PDF dokumentumot
 Nyisson meg egy meglévő PDF dokumentumot a`Document` konstruktort, és átadja a bemeneti PDF-fájl elérési útját.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 5. lépés: Bontsa ki a bekezdéseket
 Példányosítsa a`ParagraphAbsorber` osztályt, és használja azt`Visit` módszer a bekezdések kinyerésére a dokumentumból.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## 6. lépés: Ismételje meg a bekezdéseket
Lapozzon át a kibontott bekezdéseken a szövegtartalom eléréséhez. Használjon beágyazott hurkokat az egyes bekezdéseken belüli szakaszok és sorok áthaladásához.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Minta forráskód a bekezdések kibontásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyisson meg egy meglévő PDF-fájlt
Document doc = new Document(dataDir + "input.pdf");
// Példányosítsa a bekezdéselnyelőt
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Következtetés
Sikeresen kibontotta a bekezdéseket egy PDF-dokumentumból az Aspose.PDF for .NET segítségével. A kibontott bekezdések megjelennek a konzol ablakában.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezeti Önt a bekezdések PDF-fájlból való kibontásának folyamatán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód gyakorlati lépéseket ad ennek a feladatnak az eléréséhez.

#### K: Milyen névtereket kell importálnom?

V: Abba a kódfájlba, ahonnan a bekezdéseket ki szeretné bontani, a fájl elején található direktívák használatával adja meg a következőket:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: Keresse meg a vonalat`string dataDir = "YOUR DOCUMENT DIRECTORY";` a kódban, és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan nyithatok meg egy meglévő PDF-dokumentumot?

 V: A 4. lépésben megnyit egy meglévő PDF-dokumentumot a`Document` konstruktort, és megadja a bemeneti PDF-fájl elérési útját.

#### K: Hogyan vonhatok ki bekezdéseket a dokumentumból?

 V: Az 5. lépésben létrehoz egy példányt a`ParagraphAbsorber` osztályt és annak használatát`Visit` módszer a bekezdések kinyerésére a PDF-dokumentumból.

#### K: Hogyan iterálhatom végig a kivonatolt bekezdéseket?

V: A 6. lépés végigvezeti Önt a kibontott bekezdéseken keresztül. A beágyazott hurkok az egyes bekezdéseken belüli szakaszok és sorok áthaladására szolgálnak, végül elérik és megjelenítik a szöveges tartalmat.

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan bonthat ki bekezdéseket egy PDF-dokumentumból az Aspose.PDF for .NET használatával. A kivonatolt bekezdések a konzolablakban jelennek meg, így értékes betekintést nyerhet a dokumentum tartalmi szerkezetébe.