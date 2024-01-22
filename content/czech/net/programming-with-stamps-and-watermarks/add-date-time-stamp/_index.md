---
title: Přidat datum a čas do souboru PDF
linktitle: Přidat datum a čas do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak snadno přidat datum a časové razítko do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
tomto článku vás krok za krokem provedeme, jak přidat datum a časové razítko do souboru PDF pomocí Aspose.PDF pro .NET. Ukážeme vám, jak použít dodaný zdrojový kód C# k přidání data a času do existujícího souboru PDF.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 1: Nastavení prostředí

Než budete moci do dokumentu PDF přidat datum a časové razítko, musíte nastavit vývojové prostředí. Zde jsou následující kroky:

1. Otevřete své oblíbené IDE (Integrated Development Environment).
2. Vytvořte nový projekt C#.
3. Ujistěte se, že jste přidali odkaz na knihovnu Aspose.PDF pro .NET.

## Krok 2: Přidání knihovny Aspose.PDF

Knihovna Aspose.PDF pro .NET je nutná pro práci s dokumenty PDF ve vašem projektu.

## Krok 3: Načtení dokumentu PDF

Prvním krokem k přidání datumového a časového razítka je načtení existujícího dokumentu PDF do vašeho projektu. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 4: Vytvoření razítka data a času

Nyní, když jste nahráli dokument

  PDF, můžete vytvořit datum a časové razítko, které chcete přidat. Jak na to:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Vytvořte textovou vyrovnávací paměť
TextStamp textStamp = new TextStamp(annotationText);
```

Výše uvedený kód vytvoří nový textový buffer obsahující aktuální datum a čas.

## Krok 5: Konfigurace vlastností razítka

Před přidáním razítka do dokumentu PDF můžete nakonfigurovat různé vlastnosti razítka, jako je okraj, vodorovné a svislé zarovnání atd. Zde je návod:

```csharp
// Nastavte vlastnosti vyrovnávací paměti
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Tyto vlastnosti si můžete upravit podle svých potřeb.

## Krok 6: Přidejte razítko do PDF

Nyní, když je datum a čas připraveno, můžete je přidat na konkrétní stránku dokumentu PDF. Zde je postup:

```csharp
// Přidejte razítko do sbírky razítek stránky
pdfDocument.Pages[1].AddStamp(textStamp);
```

Výše uvedený kód přidá razítko na první stránku dokumentu PDF. V případě potřeby můžete zadat jinou stránku.

## Krok 7: Uložte výstupní dokument

Jakmile přidáte datum a časové razítko, můžete upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte výstupní dokument
pdfDocument.Save(dataDir);
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro Přidat datum a čas pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Vytvořte textové razítko
TextStamp textStamp = new TextStamp(annotationText);

// Nastavte vlastnosti razítka
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Přidání razítka do sbírky známek
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Uložit výstupní dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Závěr

gratuluji! Naučili jste se, jak přidat datum a čas pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti aplikovat na své vlastní projekty a přidávat do dokumentů PDF datum a čas.

### Časté dotazy pro přidání datumu a času do souboru PDF

#### Otázka: Jaký je účel přidání datumového a časového razítka do dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Přidání datumového a časového razítka do dokumentu PDF zvyšuje jeho informační hodnotu tím, že uvádí, kdy byl dokument upraven nebo vytvořen. Tato funkce je užitečná pro sledování změn dokumentů a poskytování referenčního bodu pro historii dokumentu.

#### Otázka: Mohu přizpůsobit formát data a času tak, aby odpovídal konkrétním požadavkům?

 Odpověď: Ano, formát data a času si můžete přizpůsobit podle svých preferencí. Poskytnutý zdrojový kód C# používá`DateTime.Now.ToString()` způsob generování časového razítka ve specifickém formátu. Tento kód můžete upravit tak, aby formátoval časové razítko podle potřeby.

#### Otázka: Je možné přidat datum a čas na konkrétní místo na stránce PDF?

 Odpověď: Rozhodně můžete upravit umístění razítka data a času na stránce PDF úpravou vlastností souboru`TextStamp` objekt. Kód poskytnutý v tutoriálu ukazuje, jak nastavit vlastnosti, jako je okraj, zarovnání a vertikální umístění.

#### Otázka: Mohu přidat více razítek data a času na různé stránky stejného dokumentu PDF?

 Odpověď: Ano, na různé stránky stejného dokumentu PDF můžete přidat více razítek data a času. Jednoduše opakujte proces vytváření a`TextStamp` objektu a konfiguraci jeho vlastností pro každou požadovanou stránku.

#### Otázka: Jak mohu změnit písmo, velikost nebo barvu textu datumového a časového razítka?

 Odpověď: Chcete-li upravit písmo, velikost nebo barvu textu datumového a časového razítka, můžete upravit vlastnosti souboru`DefaultAppearance` objekt použitý k vytvoření`TextStamp`. Upravte název písma, velikost a hodnoty barev, abyste dosáhli požadovaného vzhledu.

#### Otázka: Je možné pomocí Aspose.PDF pro .NET přidat do dokumentu PDF jiné typy anotací nebo razítek?

Odpověď: Ano, Aspose.PDF for .NET poskytuje širokou škálu typů anotací, které můžete přidat do dokumentů PDF, včetně textových anotací, razítek, čar, tvarů a dalších. Další podrobnosti o práci s anotacemi naleznete v dokumentaci Aspose.PDF.

#### Otázka: Existují nějaká omezení nebo úvahy při přidávání razítka data a času do dokumentu PDF?

Odpověď: I když je přidání datumového a časového razítka jednoduché, zvažte faktory, jako je rozvržení dokumentu a stávající obsah. Ujistěte se, že umístění razítka nezakrývá důležité informace nebo neovlivňuje čitelnost dokumentu.

#### Otázka: Jak mohu integrovat tuto metodu do svých vlastních projektů a přidat do dokumentů PDF datum a čas?

Odpověď: Chcete-li tuto metodu integrovat, postupujte podle uvedených kroků a upravte kód tak, aby odpovídal struktuře vašeho projektu. Ke stávajícím dokumentům PDF můžete přidat datum a čas, abyste zvýšili jejich užitečnost a poskytli jasnou časovou osu změn.

#### Otázka: Mohu automatizovat proces přidávání razítek data a času do více dokumentů PDF?

Odpověď: Ano, proces přidávání razítek data a času do více dokumentů PDF můžete automatizovat vytvořením skriptu nebo programu, který prochází seznam dokumentů a na každý z nich aplikuje stejný proces razítkování.