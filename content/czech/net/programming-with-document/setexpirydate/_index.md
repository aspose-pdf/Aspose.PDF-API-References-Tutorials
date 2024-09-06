---
title: Nastavte datum vypršení platnosti v souboru PDF
linktitle: Nastavte datum vypršení platnosti v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit datum vypršení platnosti v souboru PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce.
type: docs
weight: 300
url: /cs/net/programming-with-document/setexpirydate/
---
Aspose.PDF for .NET je výkonná knihovna, která poskytuje různé funkce pro práci se soubory PDF. Jednou z takových funkcí je možnost nastavit datum vypršení platnosti dokumentu PDF. V tomto tutoriálu vás provedeme procesem nastavení data vypršení platnosti dokumentu PDF pomocí Aspose.PDF pro .NET. 

## Krok 1: Nastavte cestu k adresáři dokumentů

Než začneme, musíme nastavit cestu k adresáři, kde se nachází náš PDF dokument. Tuto cestu uložíme do proměnné s názvem „dataDir“.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvoření nového dokumentu PDF

 Chcete-li vytvořit nový dokument PDF, musíme vytvořit instanci nového`Aspose.Pdf.Document` objekt. Můžeme to udělat pomocí následujícího kódu:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Krok 3: Přidání nové stránky do dokumentu PDF

Jakmile vytvoříme dokument PDF, můžeme do něj přidat novou stránku. Můžeme to udělat pomocí následujícího kódu:

```csharp
doc.Pages.Add();
```

## Krok 4: Přidání textu do dokumentu PDF

 Po přidání stránky do dokumentu PDF do něj můžeme přidat text pomocí`Paragraphs` sbírka. Můžeme to udělat pomocí následujícího kódu:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Krok 5: Nastavení data vypršení platnosti PDF pomocí JavaScriptu

Chcete-li nastavit datum vypršení platnosti PDF, musíme vytvořit objekt JavaScript. Můžeme to udělat pomocí následujícího kódu:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Nastavit JavaScript jako akci otevření PDF
doc.OpenAction = javaScript;
```

V tomto kódu nastavujeme datum vypršení platnosti na květen 2017.

## Krok 6: Uložte soubor PDF

 Po nastavení data vypršení platnosti je třeba uložit soubor PDF. Chcete-li to provést, můžete použít`Save` metoda`Document` objekt a předejte cestu k místu, kam chcete uložit aktualizovaný soubor PDF.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);
```

### Příklad zdrojového kódu pro Set Expiry Date pomocí Aspose.PDF for .NET

Zde je úplný příklad zdrojového kódu pro nastavení data vypršení platnosti pomocí Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objekt okamžitého dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Přidat stránku do kolekce stránek souboru PDF
doc.Pages.Add();
// Přidejte fragment textu do kolekce odstavců objektu stránky
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Vytvořte objekt JavaScript pro nastavení data vypršení platnosti PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Nastavit JavaScript jako akci otevření PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);
```

## Závěr

Nastavení data vypršení platnosti dokumentu PDF pomocí Aspose.PDF pro .NET je užitečná funkce, která zajistí, že dokument bude platný pouze po určitou dobu. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno nastavit datum vypršení platnosti a vytvářet soubory PDF s časově omezenou platností. Tato funkce může být užitečná zejména pro dokumenty, které je třeba zpřístupnit nebo distribuovat po omezenou dobu.

### Časté dotazy pro nastavení data vypršení platnosti v souboru PDF

#### Otázka: Mohu pro dokument PDF nastavit jiné datum vypršení platnosti?

 Odpověď: Ano, můžete nastavit jiné datum vypršení platnosti dokumentu PDF úpravou kódu JavaScript v kroku 5. V uvedeném příkladu je datum vypršení platnosti nastaveno na květen 2017. Chcete-li nastavit jiné datum vypršení platnosti, musíte upravit`year` a`month` proměnné v kódu JavaScript na požadovaný rok a měsíc.

#### Otázka: Co se stane, když platnost dokumentu PDF vyprší?

Odpověď: Když vypršela platnost dokumentu PDF, jak je uvedeno v kódu JavaScript, prohlížeč zobrazí varovnou zprávu oznamující, že platnost souboru vypršela a že uživatel potřebuje nový. Tato výstražná zpráva se zobrazí při otevření PDF.

#### Otázka: Mohu pro datum vypršení platnosti použít konkrétní čas namísto pouhého data?

 Odpověď: Ano, v kódu JavaScript můžete nastavit konkrétní čas pro datum vypršení platnosti. Úpravou`expiry` proměnnou v kódu JavaScript zahrnout požadovaný čas, můžete nastavit konkrétní čas pro datum vypršení platnosti.