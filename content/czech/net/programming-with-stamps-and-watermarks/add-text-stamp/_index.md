---
title: Přidat textové razítko do souboru PDF
linktitle: Přidat textové razítko do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat textové razítko do souboru PDF pomocí Aspose.PDF for .NET s naším podrobným průvodcem a pozvedněte své prezentace dokumentů.
type: docs
weight: 50
url: /cs/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Zavedení

dnešní digitální době jsou soubory PDF běžným formátem pro sdílení a doručování dokumentů. Ať už jste vývojář, tvůrce obsahu nebo jen někdo, kdo chce vylepšit své soubory PDF, znalost, jak programově manipulovat s PDF, může změnit hru. Jedna šikovná funkce, kterou možná budete chtít využít, je možnost přidávat do souborů PDF textová razítka. Přidání textového razítka může dodat vašim dokumentům profesionální nádech nebo zprostředkovat důležité informace, jako je „Vzorek“, „Důvěrné“ nebo dokonce vodoznak.

## Předpoklady

Než se pustíme do kódu, existuje několik předpokladů, které zajistí, že máte vše správně nastaveno. Zde je to, co budete potřebovat:

1.  Aspose.PDF for .NET: Ujistěte se, že máte ve svém projektu nainstalovanou knihovnu Aspose.PDF. Pokud jste to ještě neudělali, můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/).
2. Visual Studio nebo kompatibilní IDE: K psaní a spouštění kódu .NET budete potřebovat vývojové prostředí. Visual Studio je nejběžnější volbou mezi vývojáři.
3. Základní znalost C#: Znalost C# a principů objektově orientovaného programování vám pomůže lépe porozumět příkladům.
4. Ukázkový soubor PDF: Měli byste mít připravený soubor PDF, se kterým budete pracovat. K otestování funkčnosti můžete vytvořit základní PDF nebo použít jakýkoli existující PDF.

Jakmile máte tyto předpoklady vyřešené, můžeme přejít ke kódování!

## Importujte balíčky

Nyní naimportujeme potřebné balíčky. Tento krok je zásadní, protože zpřístupňuje třídy a metody z knihovny Aspose ve vašem projektu.

### Importovat sestavu Aspose.PDF

Chcete-li začít, musíte importovat jmenný prostor Aspose.PDF. V horní části souboru C# přidejte následující pomocí direktivy:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

To vám umožní přístup ke třídám, které jsou nezbytné pro vytváření a manipulaci s dokumenty PDF.

Nyní se pustíme do jádra tutoriálu. Proces rozdělíme do jasných a stručných kroků. Každý krok vás provede kódem pro přidání textového razítka do souboru PDF.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte vytvořit adresář, kde je uložen váš dokument PDF. To znamená, že váš kód musí vědět, kde najít soubor PDF, který chcete upravit.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vysvětlení: Vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde je váš soubor PDF (`AddTextStamp.pdf`) je uložen. Tato cesta se později použije k otevření a uložení upraveného PDF.

## Krok 2: Otevřete dokument PDF

 Dále otevřeme dokument PDF pomocí`Document` třídy ze jmenného prostoru Aspose.PDF.

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Vysvětlení: Zde vytváříme instanci souboru`Document` třídy a předání cesty k našemu souboru PDF. Tím se načte PDF, abychom s ním mohli manipulovat.

## Krok 3: Vytvořte textové razítko

Nyní vytvoříme textové razítko, které později použijeme na náš dokument PDF.

```csharp
// Vytvořte textové razítko
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Vysvětlení: The`TextStamp` objekt je vytvořen s textem, který chcete zobrazit. V tomto případě používáme jako text pro naše razítko "Vzorové razítko".

## Krok 4: Nastavte vlastnosti razítka

Pro přizpůsobení razítka můžeme nastavit různé vlastnosti, jako je barva pozadí, poloha a otočení. Udělejme to teď:

```csharp
// Nastavte, zda je razítko pozadí
textStamp.Background = true;

// Nastavit původ
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Otočit razítko
textStamp.Rotate = Rotation.on90;
```

Vysvětlení:
- Pozadí: Nastavení na`true` znamená, že razítko se objeví za obsahem PDF.
- XIndent & YIndent: Tyto vlastnosti určují pozici razítka na stránce. V tomto příkladu bude razítko umístěno 100 jednotek od levého a horního okraje stránky.
- Otočit: Otočí razítko o 90 stupňů. Můžete si vybrat různé možnosti rotace na základě vašich požadavků na design.

## Krok 5: Přizpůsobte vlastnosti textu

Dále pojďme být kreativní přizpůsobením vzhledu textu v našem razítku:

```csharp
// Nastavte vlastnosti textu
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Vysvětlení:
- Písmo: Používáme písmo Arial a děláme ho tučným písmem a kurzívou.
- Velikost písma: Je nastavena na 14 bodů.
- ForegroundColor: Pomocí RGB nastavte barvu textu na Aqua. Neváhejte a změňte barvu, aby vyhovovala vašim potřebám značky nebo designu!

## Krok 6: Přidejte razítko na stránku PDF

Nyní je čas přidat razítko na konkrétní stránku dokumentu PDF.

```csharp
// Přidejte razítko na konkrétní stránku
pdfDocument.Pages[1].AddStamp(textStamp);
```

Vysvětlení: V tomto příkladu je razítko přidáno na první stránku PDF (stránky jsou indexovány po 1). Upravte číslo stránky podle potřeby dokumentu.

## Krok 7: Uložte upravený PDF

Nakonec dokument uložme s nově přidaným textovým razítkem.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Uložit výstupní dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Vysvětlení: Definujeme novou cestu pro výstupní soubor a poté uložíme upravený dokument. Po uložení se cesta vytiskne do konzole a potvrdí úspěšnou operaci.

## Závěr

Gratuluji! Úspěšně jste přidali textové razítko do souboru PDF pomocí Aspose.PDF for .NET. Tato metoda vám umožňuje efektivně anotovat vaše dokumenty, čímž se zvyšuje jejich profesionalita a použitelnost. Ať už přidáváte vodoznaky, podpisy nebo jednoduché poznámky, knihovna Aspose poskytuje výkonné nástroje pro snadnou manipulaci s vašimi PDF.

## FAQ

### Co je textové razítko v PDF?
Textové razítko je grafický překryv obsahující text, který lze umístit na dokument PDF, často používaný pro anotace nebo vodoznaky.

### Mohu upravit razítko pomocí obrázků?
Ano, Aspose.PDF podporuje také přidávání obrazových razítek, což poskytuje větší flexibilitu návrhu.

### Jaké programovací jazyky mohu používat s Aspose.PDF?
Aspose.PDF je primárně zaměřen na .NET, ale jsou k dispozici verze pro jiné jazyky, jako je Java a Python.

### Jak získám dočasnou licenci pro Aspose.PDF?
 O dočasnou licenci můžete požádat na adrese[odkaz na nákup](https://purchase.aspose.com/temporary-license/) na jejich webových stránkách.

### Kde najdu podporu pro Aspose.PDF?
 Na jejich stránkách je k dispozici podpora pro Aspose.PDF[fórum podpory](https://forum.aspose.com/c/pdf/10).