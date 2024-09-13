---
title: Přidat datum a čas do souboru PDF
linktitle: Přidat datum a čas do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat datum a časové razítko do souborů PDF pomocí Aspose.PDF for .NET, pomocí tohoto podrobného průvodce. Ideální pro zvýšení pravosti dokumentů.
type: docs
weight: 10
url: /cs/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Zavedení

Pokud jde o správu dokumentů, zejména souborů PDF, přidání datumového a časového razítka může změnit hru. Ať už pracujete na právních dokumentech, zprávách o projektech nebo fakturách, časové razítko nejen dodává autentičnost, ale také poskytuje jasný záznam o tom, kdy byl dokument vytvořen nebo upraven. V této příručce vás provedeme procesem přidávání data a času do souboru PDF pomocí knihovny Aspose.PDF pro .NET. 

Tento článek je navržen tak, aby byl přímočarý a snadno se řídil, takže i když jste nováčci v programování nebo v knihovně Aspose.PDF, budete moci tuto funkci s jistotou implementovat. Pojďme se ponořit!

## Předpoklady

Než začneme, je třeba splnit několik předpokladů:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Zde napíšete a spustíte svůj kód.
2. Aspose.PDF pro .NET: Musíte si stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete najít nejnovější verzi[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět příkladům, ale nebojte se, pokud právě začínáte; vše vysvětlíme krok za krokem.
4.  Soubor PDF: Připravte si vzorový soubor PDF. Pro náš příklad použijeme soubor s názvem`AddTextStamp.pdf`.

Jakmile budete mít tyto předpoklady, jste připraveni začít přidávat datum a čas do souborů PDF!

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné jmenné prostory. Jak na to:

### Vytvořit nový projekt

1. Otevřete Visual Studio: Spusťte aplikaci Visual Studio.
2. Vytvořit nový projekt: Na úvodní obrazovce vyberte „Vytvořit nový projekt“.
3. Zvolte Console App: Vyberte "Console App (.NET Framework)" ze seznamu šablon projektu.
4.  Pojmenujte svůj projekt: Pojmenujte svůj projekt, např.`PDFDateTimeStamp`.

### Přidejte odkaz Aspose.PDF

1. Klikněte pravým tlačítkem na Reference: V Průzkumníku řešení klikněte pravým tlačítkem na složku „Reference“ vašeho projektu.
2. Vyberte „Přidat referenci“: Z kontextové nabídky vyberte „Přidat referenci“.
3. Procházet Aspose.PDF: Přejděte do umístění, kam jste stáhli Aspose.PDF, a vyberte jej. Kliknutím na „OK“ jej přidáte do svého projektu.

### Importujte požadované jmenné prostory

 V horní části vašeho`Program.cs` musíte importovat následující jmenné prostory:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Nyní, když máme vše nastaveno, pojďme si rozdělit proces přidávání datumového a časového razítka do souboru PDF do jasných, zvládnutelných kroků.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte určit adresář, kde se nachází váš soubor PDF. To je zásadní, protože kód bude hledat PDF v tomto adresáři.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Nahraďte svou skutečnou cestou
```

 Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` se skutečnou cestou k vašemu souboru PDF.

## Krok 2: Otevřete dokument PDF

Dále otevřete dokument PDF, kam chcete přidat časové razítko. 

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Tento řádek kódu inicializuje`Document` třídy a načte váš soubor PDF do`pdfDocument` objekt.

## Krok 3: Vytvořte datum a čas

Nyní je čas vygenerovat datum a čas. Naformátujete jej tak, aby se zobrazoval specifickým způsobem. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Zde,`DateTime.Now` získá aktuální datum a čas a`ToString` naformátuje jej do požadovaného formátu.

## Krok 4: Vytvořte textové razítko

S připraveným řetězcem data a času můžete nyní vytvořit textové razítko, které bude přidáno do vašeho PDF.

```csharp
// Vytvořte textové razítko
TextStamp textStamp = new TextStamp(annotationText);
```

 Tento řádek vytvoří novou instanci`TextStamp` pomocí formátovaného řetězce data a času.

## Krok 5: Nastavte vlastnosti razítka

Vzhled a polohu razítka si můžete přizpůsobit. Zde je návod, jak nastavit jeho vlastnosti:

```csharp
// Nastavte vlastnosti razítka
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

V tomto kroku nastavíme okraje a zarovnáme razítko k pravému dolnímu rohu stránky PDF.

## Krok 6: Přidejte razítko do PDF

Nyní je čas přidat do dokumentu PDF textové razítko. 

```csharp
// Přidání razítka do sbírky známek
pdfDocument.Pages[1].AddStamp(textStamp);
```

Tento řádek přidá razítko na první stránku PDF. Číslo stránky můžete změnit, pokud ji chcete umístit na jinou stránku.

## Krok 7: Vytvořte anotaci volného textu (volitelné)

Pokud chcete k razítku přidat anotaci, můžete vytvořit a`FreeTextAnnotation` následovně:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Tento volitelný krok vytvoří anotaci volného textu, která může poskytnout další kontext nebo informace o razítku.

## Krok 8: Nakonfigurujte ohraničení anotace

Chcete-li upravit ohraničení své anotace, můžete to udělat také:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Tento úryvek kódu nastaví šířku ohraničení na 0, čímž se stane neviditelným, a přidá do PDF anotaci.

## Krok 9: Uložte dokument PDF

Nakonec je potřeba upravený PDF dokument uložit. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Zadejte název výstupního souboru
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Tento řádek uloží PDF s přidaným časovým razítkem do nového souboru. Můžete zkontrolovat zadaný adresář a zobrazit výstup.

## Závěr

Gratuluji! Úspěšně jste přidali datum a časové razítko do souboru PDF pomocí Aspose.PDF pro .NET. Tato jednoduchá, ale účinná funkce může vylepšit vaše dokumenty, učinit je profesionálnějšími a poskytnout jasný záznam o tom, kdy byly vytvořeny nebo upraveny. 

## FAQ

### Mohu přizpůsobit formát data v časovém razítku?
 Ano, můžete upravit`ToString`způsob změny formátu data podle vašich preferencí.

### Je Aspose.PDF zdarma k použití?
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plné funkce si musíte zakoupit licenci. Můžete získat dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/).

### Mohu do PDF přidat více časových razítek?
 Absolutně! Můžete vytvořit více`TextStamp` instance a přidat je na různé stránky nebo pozice v PDF.

### Co když nemám Visual Studio?
Můžete použít jakýkoli C# IDE nebo textový editor, ale pro spuštění a ladění projektu se doporučuje Visual Studio.

### Kde najdu další příklady použití Aspose.PDF?
 Další příklady a návody můžete prozkoumat v[Dokumentace Aspose.PDF](https://reference.aspose.com/pdf/net/).