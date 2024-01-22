---
title: Okno Získat dokument
linktitle: Okno Získat dokument
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat funkci GetDocumentWindow Aspose.PDF for .NET k načtení informací o vlastnostech okna dokumentu PDF.
type: docs
weight: 170
url: /cs/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF for .NET je výkonná knihovna pro manipulaci s PDF, která umožňuje vývojářům vytvářet, upravovat a převádět soubory PDF v jejich aplikacích .NET. Jednou z funkcí, které tato knihovna nabízí, je možnost získat informace o vlastnostech okna dokumentu. Tento tutoriál vás provede kroky použití`GetDocumentWindow` funkce Aspose.PDF for .NET k načtení informací o vlastnostech okna dokumentu PDF.

## Krok 1: Nainstalujte Aspose.PDF pro .NET

 Chcete-li používat Aspose.PDF pro .NET ve svých aplikacích .NET, musíte nejprve nainstalovat knihovnu. Nejnovější verzi knihovny si můžete stáhnout z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net).

Po stažení knihovny rozbalte obsah souboru ZIP do složky v počítači. Poté budete muset přidat odkaz na Aspose.PDF for .NET DLL ve vašem projektu .NET.

## Krok 2: Načtěte dokument PDF

Jakmile nainstalujete Aspose.PDF pro .NET a přidáte odkaz na knihovnu DLL ve svém projektu .NET, můžete začít používat`GetDocumentWindow` funkce pro načtení informací o vlastnostech okna dokumentu PDF.

Prvním krokem při použití této funkce je načtení dokumentu PDF, o kterém chcete získat informace. Chcete-li to provést, můžete použít následující kód:

```csharp
// Cesta k dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otevřete dokument PDF
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Ve výše uvedeném kódu nahraďte`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde se nachází váš dokument PDF. Tento kód načte dokument PDF do a`Document` objekt, který pak můžete použít k načtení informací o vlastnostech okna dokumentu.

## Krok 3: Načtěte vlastnosti okna dokumentu

Chcete-li získat informace o vlastnostech okna dokumentu PDF, můžete použít následující kód:

```csharp
// Načtěte vlastnosti okna dokumentu
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Ve výše uvedeném kódu každý řádek načte jinou vlastnost okna dokumentu PDF a odešle ji do konzoly. Tento kód můžete přizpůsobit tak, aby získal pouze vlastnosti, které vás zajímají.

### Příklad zdrojového kódu pro okno získat dokument PDF souboru pomocí Aspose.PDF pro .NET 

 Zde je úplný zdrojový kód pro načtení vlastností okna dokumentu PDF pomocí`GetDocumentWindow` funkce Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Získejte různé vlastnosti dokumentu
// Poloha okna dokumentu - Výchozí: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Převažující pořadí čtení; určuje pozici stránky
// Při zobrazení vedle sebe - Výchozí: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Zda má záhlaví okna zobrazovat název dokumentu
// Pokud je nastavena hodnota false, v záhlaví se zobrazí název souboru PDF – výchozí: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Zda se má změnit velikost okna dokumentu tak, aby odpovídalo velikosti
// První zobrazená stránka – Výchozí: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Zda se má skrýt panel nabídek aplikace prohlížeče - Výchozí: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Zda skrýt panel nástrojů aplikace prohlížeče - Výchozí: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Zda se mají skrýt prvky uživatelského rozhraní, jako jsou posuvníky
// A ponechání zobrazený pouze obsah stránky - Výchozí: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Režim stránky dokumentu. Jak zobrazit dokument při ukončení režimu celé obrazovky.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Vzhled stránky, tj. jedna stránka, jeden sloupec
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Jak by se měl dokument zobrazit při otevření
// Tj. zobrazit miniatury, celou obrazovku, zobrazit panel příloh
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak používat Aspose.PDF pro .NET k načtení informací o vlastnostech okna dokumentu PDF. Načtením dokumentu PDF a přístupem k jeho vlastnostem okna můžete získat informace o tom, jak by se měl dokument zobrazit při otevření v aplikaci prohlížeče. Aspose.PDF for .NET poskytuje výkonnou sadu funkcí pro programovou práci se soubory PDF, což z něj činí cenný nástroj pro manipulaci s PDF v aplikacích .NET.

### FAQ

#### Otázka: Jaký je účel načítání vlastností okna dokumentu PDF?

Odpověď: Načtení vlastností okna dokumentu PDF vám umožní získat informace o tom, jak by se měl dokument PDF zobrazit při otevření v aplikaci prohlížeče. Tyto vlastnosti řídí různé aspekty, jako je poloha okna, režim zobrazení a viditelnost prvků uživatelského rozhraní.

#### Otázka: Jak mohu nainstalovat Aspose.PDF for .NET do svého projektu .NET?

 A: Chcete-li nainstalovat Aspose.PDF pro .NET, musíte si stáhnout knihovnu z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net). Po stažení rozbalte obsah souboru ZIP a přidejte odkaz na Aspose.PDF for .NET DLL ve vašem projektu .NET.

#### Otázka: Mohu upravit kód tak, aby získal pouze specifické vlastnosti okna?

Odpověď: Ano, kód můžete upravit tak, aby získal specifické vlastnosti okna zakomentováním řádků, které nepotřebujete. Každý řádek v kódu odpovídá určité vlastnosti okna, takže můžete vlastnosti zahrnout nebo vyloučit na základě vašich požadavků.

#### Otázka: Jaké typy vlastností okna mohu získat pomocí Aspose.PDF pro .NET?

Odpověď: Pomocí Aspose.PDF for .NET můžete získat různé vlastnosti okna dokumentu PDF, včetně vystředění okna, nastavení rozvržení stránky, ovládání zobrazení panelů nástrojů a pruhů nabídek a další.