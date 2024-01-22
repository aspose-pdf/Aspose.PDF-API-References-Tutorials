---
title: Vložit písmo do souboru PDF
linktitle: Vložit písmo do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vkládat písma do souboru PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce. Ujistěte se, že se vaše dokumenty zobrazují správně na jakémkoli zařízení.
type: docs
weight: 120
url: /cs/net/programming-with-document/embedfont/
---
tomto tutoriálu probereme, jak vložit písma do souboru PDF pomocí Aspose.PDF pro .NET. Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a manipulovat s dokumenty PDF programově. Tato knihovna poskytuje širokou škálu funkcí pro práci s dokumenty PDF, včetně přidávání textu, obrázků, tabulek a mnoha dalších. Vkládání písem do souboru PDF je běžným požadavkem pro vývojáře, kteří chtějí zajistit správné zobrazení souboru PDF na různých zařízeních, bez ohledu na to, zda jsou požadovaná písma na těchto zařízeních nainstalována či nikoli.

## Krok 1: Vytvořte novou aplikaci C# Console
Chcete-li začít, vytvořte novou aplikaci C# Console v sadě Visual Studio. Můžete si to pojmenovat, jak chcete. Jakmile je projekt vytvořen, musíte přidat odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte jmenný prostor Aspose.PDF
Chcete-li importovat jmenný prostor Aspose.PDF, přidejte následující řádek kódu na začátek souboru C#:

```csharp
using Aspose.Pdf;
```

## Krok 3: Načtěte existující soubor PDF
Chcete-li vložit písma do existujícího souboru PDF, musíte tento soubor načíst pomocí třídy Dokument. Následující kód ukazuje, jak načíst existující soubor PDF:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubor PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Projděte všechny stránky
Jakmile načtete soubor PDF, musíte iterovat všechny stránky v dokumentu. U každé stránky musíte zkontrolovat, zda jsou použita nějaká písma, a pokud ano, musíte tato písma vložit. Následující kód ukazuje, jak iterovat všechny stránky v souboru PDF a vložit písma:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Zkontrolujte, zda je písmo již vloženo
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Zkontrolujte objekty formuláře
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Zkontrolujte, zda je písmo vloženo
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Krok 5: Uložte dokument PDF
Jakmile vložíte všechna písma do souboru PDF, musíte dokument uložit. Následující kód ukazuje, jak uložit soubor PDF:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Příklad zdrojového kódu pro Embed Font pomocí Aspose.PDF pro .NET

Zde je úplný zdrojový kód pro vložení písma pomocí Aspose.PDF pro .NET.


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubory PDF
Document doc = new Document(dataDir + "input.pdf");

// Projděte všechny stránky
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Zkontrolujte, zda je písmo již vloženo
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Zkontrolujte objekty formuláře
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Zkontrolujte, zda je písmo vloženo
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Závěr vložit písmo do souboru PDF
tomto článku jsme diskutovali o tom, jak vložit písma do souboru PDF pomocí Aspose.PDF pro .NET. Aspose.PDF for .NET poskytuje jednoduché a snadno použitelné rozhraní API pro práci s dokumenty PDF, včetně přidávání a vkládání písem. Vložení písem do souboru PDF je důležitým krokem k zajištění správného zobrazení dokumentu na různých zařízeních bez ohledu na to, zda jsou na těchto zařízeních nainstalována požadovaná písma.

### FAQ

#### Otázka: Proč je důležité vkládání písem do souboru PDF?

Odpověď: Vložení písem do souboru PDF je nezbytné pro zajištění správného zobrazení dokumentu na různých zařízeních a systémech. Když jsou písma vložena, stanou se součástí souboru PDF, čímž se eliminuje závislost na externích písmech nainstalovaných v zobrazovacím zařízení.

#### Otázka: Mohu vložit všechna písma použitá do souboru PDF?

Odpověď: Ano, můžete vložit všechna písma použitá do souboru PDF. Aspose.PDF for .NET poskytuje přímý přístup k iteraci všech písem používaných v souboru PDF a jejich vkládání, aby bylo zajištěno přesné vykreslování na různých zařízeních.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s různými formáty písem?

Odpověď: Ano, Aspose.PDF pro .NET podporuje různé formáty písem, včetně písem TrueType, OpenType, Type 1 a CFF. Může vkládat písma do souboru PDF bez ohledu na jejich formát.

#### Otázka: Zvětší vkládání písem velikost souboru dokumentu PDF?

Odpověď: Ano, vložení písem do dokumentu PDF může zvětšit velikost souboru, protože data písem jsou obsažena v samotném souboru PDF. Tím je však zajištěno, že vzhled dokumentu zůstane konzistentní bez ohledu na dostupnost písma na zobrazovacím zařízení.

#### Otázka: Mohu přizpůsobit proces vkládání písem?

Odpověď: Ano, Aspose.PDF pro .NET vám umožňuje přizpůsobit proces vkládání písem. Můžete si vybrat, která písma chcete vložit, vyloučit konkrétní písma nebo vložit pouze určité podmnožiny písem, abyste optimalizovali velikost souboru.