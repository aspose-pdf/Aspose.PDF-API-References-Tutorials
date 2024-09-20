---
title: Obrázek V Záhlaví
linktitle: Obrázek V Záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném návodu se dozvíte, jak přidat obrázek do záhlaví PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 140
url: /cs/net/programming-with-stamps-and-watermarks/image-in-header/
---
## Zavedení

V tomto tutoriálu se ponoříme do něčeho velmi užitečného pro vaše soubory PDF – přidání obrázku do záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET. Ať už jde o firemní logo nebo vodoznak, tato funkce může být neuvěřitelně cenná pro branding a přizpůsobení dokumentů. A nebojte se, provedu vás celým procesem krok za krokem, se spoustou podrobností, takže jeho sledování bude velmi snadné!

Na konci této příručky budete moci bez námahy vkládat obrázky do záhlaví PDF jako profesionál. Začněme, ano?

## Předpoklady

Než se pustíme do zábavných věcí, ujistěte se, že máme všechny nástroje na svém místě. Zde je to, co budete potřebovat:

1.  Aspose.PDF pro .NET – Knihovnu si můžete stáhnout z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/).
2. Visual Studio nebo jakékoli jiné IDE podle vašeho výběru pro psaní a kompilaci vašeho kódu C#.
3.  Platnou licenci Aspose – získejte a[dočasná licence zde](https://purchase.aspose.com/temporary-license/) nebo se podívejte na[možnosti nákupu](https://purchase.aspose.com/buy).
4. Ukázkový soubor PDF, kam přidáme záhlaví obrázku.
5. Soubor obrázku (např. logo ve formátu JPG nebo PNG), který chcete vložit do záhlaví.

Jakmile budete mít tyto věci připravené, můžeme vyrazit!

## Importujte balíčky

Než napíšeme jakýkoli kód, musíme se ujistit, že jsme importovali potřebné jmenné prostory. Ty nám umožní přístup ke všem třídám a metodám, které potřebujeme pro práci s PDF a obrázky.

Zde jsou klíčové jmenné prostory, které budeme používat:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a že tyto jmenné prostory importujete do svého projektu.

## Krok 1: Nastavte projekt a vytvořte dokument PDF

Nejprve založíme nový projekt. Pokud jste to ještě neudělali, otevřete Visual Studio, vytvořte novou konzolovou aplikaci a přidejte potřebné odkazy na knihovnu Aspose.PDF for .NET.

Můžete buď načíst existující soubor PDF, nebo vytvořit nový. V tomto příkladu načteme existující dokument, který chceme upravit.

Jak na to:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete existující dokument PDF
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

 Používáme`Document` k načtení souboru PDF z vašeho adresáře. Pokud nemáte soubor s názvem`ImageinHeader.pdf`, můžete jej nahradit vlastním názvem souboru PDF.

## Krok 2: Přidejte obrázek do záhlaví

Nyní, když máme načtený dokument PDF, přejdeme k přidání obrázku do záhlaví každé stránky.

### Krok 2.1: Vytvořte obrázkové razítko
 Pro vložení obrázku do záhlaví použijeme něco, čemu se říká an`ImageStamp`. Umožňuje nám umístit obrázek do libovolné části PDF a v tomto případě jej umístíme do sekce záhlaví.

Zde je kód pro vytvoření razítka:

```csharp
// Vytvořte záhlaví s obrázkem
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 V tomto úryvku načítáme obrázek (v tomto případě logo) z`dataDir` adresář. Ujistěte se, že máte soubor s obrázkem uložený ve správném adresáři, nebo podle toho upravte cestu.

### Krok 2.2: Upravte vlastnosti razítka
Dále upravíme polohu a zarovnání obrázku v záhlaví. Chcete, aby to vypadalo dokonale, že?

```csharp
// Nastavte vlastnosti razítka
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;
```

- TopMargin: Řídí, jak daleko je obrázek od horní části stránky.
- HorizontalAlignment: Obrázek jsme zarovnali na střed, ale můžete jej také zarovnat doleva nebo doprava.
- VerticalAlignment: Umístili jsme jej na začátek stránky, aby fungoval jako záhlaví.

## Krok 3: Aplikujte razítko na všechny stránky

Nyní, když je obrázek připraven a umístěn, aplikujme jej na každou stránku v dokumentu PDF.

Zde je návod, jak můžete procházet všechny stránky a na každou z nich použít razítko obrázku:

```csharp
// Přidejte záhlaví na všechny stránky
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(imageStamp);
}
```

Tato jednoduchá smyčka zajišťuje, že obrázek bude přidán na každou stránku ve vašem PDF. Pokud chcete obrázek pouze na konkrétních stránkách, můžete smyčku odpovídajícím způsobem upravit.

## Krok 4: Uložte aktualizované PDF

Konečně jsme s úpravou PDF hotovi! Posledním krokem je uložení aktualizovaného dokumentu.

```csharp
// Uložte aktualizovaný dokument s hlavičkou obrázku
dataDir = dataDir + "ImageinHeader_out.pdf";
pdfDocument.Save(dataDir);
```

Soubor bude uložen pod novým názvem (`ImageinHeader_out.pdf`) ve vašem adresáři. Podle potřeby můžete změnit název nebo cestu.

## Krok 5: Potvrďte úspěch

Chcete-li to zabalit, můžete zahrnout zprávu konzoly, která potvrdí, že záhlaví obrázku bylo úspěšně přidáno.

```csharp
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);
```

A je to! Úspěšně jste přidali obrázek do záhlaví vašeho dokumentu PDF pomocí Aspose.PDF pro .NET.

## Závěr

Přidání obrázku do záhlaví PDF je jednoduchý úkol, když používáte Aspose.PDF pro .NET. Nejen, že zvyšuje vizuální přitažlivost vašich dokumentů, ale také pomáhá při budování značky, zejména pokud potřebujete přidat logo společnosti.

## FAQ

### Mohu přidat různé obrázky na různé stránky v PDF?
Ano, můžete! Namísto použití stejného obrázku na všechny stránky můžete přidat podmíněnou logiku a použít různé obrázky pro konkrétní stránky.

### Jaké další vlastnosti mohu upravit pro obrazové razítko?
 Můžete ovládat vlastnosti, jako je krytí, rotace a měřítko. Zkontrolujte[Dokumentace Aspose.PDF](https://reference.aspose.com/pdf/net/) pro více možností.

### Je Aspose.PDF for .NET zdarma k použití?
 Ne, je to placená knihovna. Můžete však získat a[zkušební verze zdarma](https://releases.aspose.com/) nebo a[dočasná licence](https://purchase.aspose.com/temporary-license/)vyzkoušet jeho vlastnosti.

### Mohu pro záhlaví použít obrázky PNG místo JPG?
 Absolutně! The`ImageStamp` třída podporuje různé formáty jako JPG, PNG a BMP.

### Jak vložím text spolu s obrázkem do záhlaví?
 Můžete použít`TextStamp` třída ve spojení s`ImageStamp` pro vložení textu i obrázků do záhlaví.