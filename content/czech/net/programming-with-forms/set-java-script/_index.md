---
title: Nastavte Java Script
linktitle: Nastavte Java Script
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat Aspose.PDF for .NET k nastavení JavaScriptu v polích formuláře v souborech PDF.
type: docs
weight: 270
url: /cs/net/programming-with-forms/set-java-script/
---
V této příručce vysvětlíme krok za krokem, jak používat knihovnu Aspose.PDF pro .NET k definování JavaScriptu v poli formuláře dokumentu PDF. Ukážeme vám, jak nakonfigurovat akce JavaScriptu pro provádění konkrétních operací v textovém poli.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Vývojové prostředí .NET nainstalované ve vašem systému.
- Knihovna Aspose.PDF pro .NET. Můžete si jej stáhnout z oficiálních stránek Aspose.

## Krok 1: Konfigurace adresáře dokumentů

 Prvním krokem je konfigurace adresáře dokumentu, kde se nachází soubor PDF, se kterým chcete pracovat. Můžete použít`dataDir` proměnnou k určení cesty k adresáři.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Načtení vstupního souboru PDF

 V tomto kroku načteme vstupní soubor PDF pomocí`Document` třída Aspose.PDF.

```csharp
// Načíst vstupní soubor PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Ujistěte se, že se vstupní soubor PDF nachází v zadaném adresáři dokumentů.

## Krok 3: Přístup k poli TextBox

 Abychom mohli použít JavaScript na konkrétní textové pole, musíme k tomuto poli nejprve přistupovat. V tomto příkladu předpokládáme, že textové pole se nazývá "textbox1". Použijte`doc.Form["textbox1"]` způsob, jak získat odpovídající`TextBoxField` objekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Ujistěte se, že zadané textové pole existuje ve vstupním souboru PDF.

## Krok 4: Nakonfigurujte akce JavaScriptu

 Nyní, když jsme vstoupili do textového pole, můžeme nakonfigurovat akce JavaScriptu spojené s tímto polem. V tomto příkladu použijeme dvě akce:`OnModifyCharacter` a`OnFormat` . Tyto akce budou definovány pomocí`JavascriptAction` objektů.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Nezapomeňte upravit akce JavaScriptu podle svých potřeb.

## Krok 5: Nastavení počáteční hodnoty pole

Před uložením výsledného PDF můžeme nastavit počáteční hodnotu textového pole. V tomto příkladu nastavíme pro pole hodnotu "123".

```csharp
field.Value = "123";
```

Upravte tuto hodnotu podle svých potřeb.

## Krok 6: Uložení výsledného PDF

 Nyní, když jsme dokončili nastavení textového pole a akcí JavaScriptu, můžeme výsledné PDF uložit pomocí`Save` metoda`Document` třída.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Uložit výsledné PDF
doc.Save(dataDir);
```

Nezapomeňte zadat úplnou cestu a název souboru pro výsledný soubor PDF.


### Ukázkový zdrojový kód pro Set Java Script pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načíst vstupní soubor PDF
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 číslice za bodem
// Žádný oddělovač
// Neg styl = mínus
// Žádná měna
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Nastavte počáteční hodnotu pole
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Uložit výsledné PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Závěr

této příručce jsme se naučili používat knihovnu Aspose.PDF pro .NET k nastavení JavaScriptu v poli formuláře dokumentu PDF. Podle uvedených kroků můžete přizpůsobit akce JavaScriptu pro provádění různých operací s textovými poli. Neváhejte dále prozkoumat funkce Aspose.PDF pro .NET, abyste rozšířili možnosti manipulace se soubory PDF.


### FAQ

#### Otázka: Mohu použít Aspose.PDF pro .NET k přidání JavaScriptu do jiných prvků formuláře, jako jsou zaškrtávací políčka a přepínače?

 Odpověď: Ano, Aspose.PDF pro .NET vám umožňuje přidávat JavaScript do různých prvků formuláře, včetně zaškrtávacích políček, přepínačů a rozevíracích seznamů. Můžete použít`JavascriptAction` třídy k definování akcí JavaScriptu pro různé prvky formuláře.

#### Otázka: Je možné ověřit uživatelský vstup pomocí JavaScriptu v polích formuláře?

 Odpověď: Ano, můžete použít JavaScript k ověření uživatelského vstupu do polí formuláře. Definováním akcí JavaScriptu, jako je`OnBlur` nebo`OnKeystroke` pro pole formuláře můžete ověřit zadaná data a v případě potřeby zobrazit chybová hlášení.

#### Otázka: Mohu spouštět složité funkce JavaScriptu pomocí Aspose.PDF pro .NET?

 Odpověď: Ano, složité funkce JavaScriptu můžete spouštět pomocí Aspose.PDF pro .NET. Máte flexibilitu definovat vlastní funkce JavaScriptu a volat je v rámci`JavascriptAction`.

#### Otázka: Podporuje Aspose.PDF for .NET jiné události JavaScriptu než ty, které jsou uvedeny v tomto kurzu?

 Odpověď: Ano, Aspose.PDF pro .NET podporuje širokou škálu událostí JavaScript, včetně`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` a`OnMouseUp`, mimo jiné. Tyto události můžete použít ke spouštění akcí JavaScriptu na základě interakcí uživatelů.

#### Otázka: Mohu použít Aspose.PDF for .NET k extrahování kódu JavaScript z existujících dokumentů PDF?

 Odpověď: Aspose.PDF for .NET poskytuje možnost extrahovat kód JavaScript z existujících dokumentů PDF. Můžete použít`JavascriptAction` třídy a dalších relevantních metod pro přístup a analýzu akcí JavaScriptu ve formě PDF.