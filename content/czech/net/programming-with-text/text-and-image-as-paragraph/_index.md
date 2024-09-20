---
title: Text A Obrázek Jako Odstavec V Souboru PDF
linktitle: Text A Obrázek Jako Odstavec V Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Vytvářejte soubory PDF s textem a obrázky pomocí Aspose.PDF for .NET. Naučte se přidávat text a vložené obrázky krok za krokem.
type: docs
weight: 530
url: /cs/net/programming-with-text/text-and-image-as-paragraph/
---
## Zavedení

V dnešním digitálním světě jsou PDF univerzálním formátem dokumentů, se kterým se většina z nás denně setkává. Ať už se jedná o zprávu, e-knihu nebo obchodní fakturu, soubory PDF usnadňují sdílení informací na různých platformách. Ale co když chcete upravit PDF programově? To je místo, kde vstupuje Aspose.PDF for .NET. V tomto tutoriálu vás provedeme vkládáním textu a obrázků jako vložených odstavců do souboru PDF pomocí Aspose.PDF for .NET.

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte vše, co potřebujete, abyste mohli hladce postupovat:

-  Aspose.PDF for .NET Library: Budete muset nainstalovat Aspose.PDF for .NET. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/).
- Visual Studio: Každá verze, která podporuje .NET, bude fungovat dobře.
- Základní porozumění C#: Určitá znalost C# bude užitečná, ale nebojte se – provedu vás každým krokem!
- Dokument PDF připraven: Pokud chcete přidat vlastní obrázek, mějte jej připravený.

 Můžete také získat bezplatnou zkušební verzi knihovny[zde](https://releases.aspose.com/) , nebo pokud pracujete na rozsáhlém projektu, zvažte jeho koupi[zde](https://purchase.aspose.com/buy) . Potřebujete další podrobnosti? Podívejte se na dokumentaci[zde](https://reference.aspose.com/pdf/net/).

## Importujte balíčky

Chcete-li začít s Aspose.PDF pro .NET, musíte importovat požadované jmenné prostory. Tyto jmenné prostory umožňují vašemu kódu C# interakci s funkcemi Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Jednoduché, že? Nyní pojďme k zábavnější části – vytvoření vlastního souboru PDF.

## Podrobný průvodce: Vytvoření PDF s textem a vloženým obrázkem

Pojďme si to rozebrat do stravitelných, snadno pochopitelných kroků. Představte si, že skládáte puzzle; každý krok je jako najít a umístit správný kus.

## Krok 1: Inicializujte dokument PDF

Prvním krokem je inicializace nového dokumentu PDF pomocí Aspose.PDF. Tento dokument bude sloužit jako základ pro přidávání textu a obrázků.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancia dokumentu instance
Document doc = new Document();
```

 co se tu děje? Jednoduše vytváříme nový dokument pomocí`Document`třídy a definování adresáře, kam chcete PDF uložit. Je to jako otevřít nové plátno pro své mistrovské dílo!

## Krok 2: Přidejte stránku do svého PDF

Dokument není bez stránek k ničemu, že? Pojďme do dokumentu přidat prázdnou stránku.

```csharp
// Přidejte stránku do kolekce stránek instance dokumentu
Page page = doc.Pages.Add();
```

Tento fragment kódu přidá novou stránku do kolekce stránek vašeho dokumentu. Představte si to jako otevření prázdné stránky v poznámkovém bloku.

## Krok 3: Přidejte text jako odstavec

Dále přidáme textový odstavec. Zde můžete vložit svou zprávu nebo nadpis.

```csharp
// Vytvořte TextFragment
TextFragment text = new TextFragment("Hello World.. ");
// Přidejte fragment textu do kolekce odstavců objektu Page
page.Paragraphs.Add(text);
```

 Zde vytvoříme a`TextFragment` objekt podržet text "Hello World..", který je poté přidán na stránku jako odstavec. Je to jako napsat první větu v dokumentu PDF.

## Krok 4: Přidejte obrázek jako vložený odstavec

Když už máme text, pojďme to okořenit přidáním obrázku jako vloženého odstavce. Vložený odstavec jednoduše znamená, že se obrázek objeví hned za textem, podobně jako se obrázky zobrazují v dokumentech aplikace Word.

```csharp
// Vytvořte instanci obrázku
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Nastavte obrázek jako vložený odstavec tak, aby se objevil hned za ním
// Předchozí objekt odstavce (TextFragment)
image.IsInLineParagraph = true;
// Zadejte cestu k souboru obrázku
image.File = dataDir + "aspose-logo.jpg";
```

 V tomto úryvku vytvoříme`Image` objekt, řekněte mu, aby se zarovnal s textem, a zadejte cestu k souboru obrázku. Jedná se o ekvivalent vložení obrázku hned za větu v dokumentu. Můžete vyměnit "aspose-logo.jpg" za požadovaný obrázek.

## Krok 5: Nastavte velikost obrázku (volitelné)

Chcete změnit velikost obrázku? Žádný problém. Aspose.PDF vám dává možnost upravit výšku a šířku obrázku před jeho přidáním do dokumentu.

```csharp
// Nastavit výšku obrázku (volitelné)
image.FixHeight = 30;
// Nastavit šířku obrázku (volitelné)
image.FixWidth = 100;
```

Tato část je volitelná, ale pomáhá vám řídit, jak velký nebo malý se obrázek ve vašem PDF zobrazí. Je to jako změnit velikost fotografie před tiskem.

## Krok 6: Přidejte obrázek do kolekce odstavců

Připravili jsme obrázek. Nyní jej vložíme do dokumentu jako vložený odstavec.

```csharp
// Přidejte obrázek do kolekce odstavců objektu stránky
page.Paragraphs.Add(image);
```

Tento řádek přidá obrázek hned za text v kolekci odstavců. Je to jako stisknout tlačítko "Vložit obrázek" v textovém editoru.

## Krok 7: Přidejte další vložený textový odstavec

Co když chcete přidat další text hned za obrázek? Udělejme to vložením dalšího vloženého textového fragmentu.

```csharp
// Znovu inicializujte objekt TextFragment s jiným obsahem
text = new TextFragment(" Hello Again..");
// Nastavte TextFragment jako vložený odstavec
text.IsInLineParagraph = true;
// Přidejte nově vytvořený TextFragment do kolekce odstavců stránky
page.Paragraphs.Add(text);
```

 Znovu používáme`TextFragment`objekt sem s novým textem ("Ahoj znovu.."") a vložením do řádku hned za obrázek. To dává vašemu PDF plynulý a soudržný vzhled.

## Krok 8: Uložte dokument PDF

Už jsme skoro hotovi! Nyní uložíme dokument do určeného adresáře.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Tento poslední krok uloží soubor do vašeho adresáře s názvem "TextAndImageAsParagraph_out.pdf". Gratulujeme – vytvořili jste PDF s textem i vloženými obrázky!

## Závěr

A tady to máte – vytvoření PDF s textem a obrázky jako vloženými odstavci pomocí Aspose.PDF for .NET je tak jednoduché, že budete postupovat podle těchto kroků. Pomocí několika řádků kódu můžete do svých souborů PDF přidat dynamický obsah, díky čemuž budou vizuálně přitažlivější a profesionálnější. Ať už jde o obchodní zprávu nebo e-knihu, kontrola nad rozložením vašich PDF může znamenat velký rozdíl.

## FAQ

### Mohu přidat více obrázků jako vložené odstavce?  
 Ano, můžete přidat více obrázků vytvořením samostatných`Image` objektů a jejich přidání do kolekce odstavců.

### Mohu ovládat polohu textu a obrázku v PDF?  
Ano, pomocí vlastností, jako jsou okraje, můžete ovládat přesné umístění textu a obrázků.

### Je Aspose.PDF pro .NET zdarma?  
 Ne, je to licencovaný produkt, ale můžete získat a[zkušební verze zdarma](https://releases.aspose.com/) nebo koupit licenci[zde](https://purchase.aspose.com/buy).

### Mohu do textu přidat hypertextové odkazy?  
 Ano, Aspose.PDF vám umožňuje přidávat hypertextové odkazy do textových fragmentů. Zkontrolujte[dokumentace](https://reference.aspose.com/pdf/net/) pro více podrobností.

### Mohu přizpůsobit písmo a styl textu?  
Absolutně! Můžete snadno přizpůsobit písma, barvy a další vlastnosti stylů fragmentů textu.