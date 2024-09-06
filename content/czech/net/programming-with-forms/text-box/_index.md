---
title: Textové pole
linktitle: Textové pole
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit textové pole v dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 290
url: /cs/net/programming-with-forms/text-box/
---
V této příručce si krok za krokem vysvětlíme, jak používat knihovnu Aspose.PDF pro .NET k vytvoření textového pole v dokumentu PDF. Ukážeme vám, jak otevřít dokument, vytvořit textové pole, přizpůsobit jeho vlastnosti a uložit upravený PDF.

## Krok 1: Konfigurace adresáře dokumentů

 Prvním krokem je konfigurace adresáře dokumentu, kde se nachází soubor PDF, se kterým chcete pracovat. Můžete použít`dataDir` proměnnou k určení cesty k adresáři.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Otevření dokumentu PDF

 V tomto kroku otevřeme dokument PDF pomocí`Document` třída Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Ujistěte se, že soubor PDF je přítomen v zadaném adresáři dokumentů.

## Krok 3: Vytvoření textového pole

 Vytvoříme textové pole pomocí`TextBoxField` třída. Můžete zadat souřadnice polohy a velikost pole pomocí`Rectangle` třída.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Podle potřeby upravte souřadnice, velikost, částečný název a hodnotu textového pole.

## Krok 4: Přizpůsobte vlastnosti textového pole

V tomto kroku přizpůsobíme vlastnosti textového pole, jako je ohraničení, barva atd.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Upravte vlastnosti textového pole podle svých preferencí.

## Krok 5: Přidání pole do dokumentu

Nyní, když jsme vytvořili a nakonfigurovali textové pole, můžeme je přidat do dokumentu PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Krok 6: Uložení upraveného PDF

 Nakonec můžeme upravený PDF uložit pomocí`Save` metoda`Document` třída.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Nezapomeňte zadat úplnou cestu a název souboru pro upravený PDF.

### Ukázka zdrojového kódu pro textové pole pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Vytvořte pole
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = new Border(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Přidejte pole do dokumentu
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Uložte upravené PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Závěr

V této příručce jsme se naučili používat knihovnu Aspose.PDF pro .NET k vytvoření textového pole v dokumentu PDF. Pomocí popsaných kroků můžete upravit vlastnosti textového pole a přidat je do dokumentu podle potřeby. Neváhejte dále prozkoumat funkce Aspose.PDF pro .NET, abyste rozšířili možnosti manipulace se soubory PDF.

### FAQ

#### Otázka: Mohu použít Aspose.PDF for .NET k vytvoření více textových polí v jednom dokumentu PDF?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete vytvořit více textových polí v jednom dokumentu PDF. Jednoduše opakujte proces vytváření a přizpůsobení textových polí pro každé požadované místo v dokumentu.

#### Otázka: Jak mohu přizpůsobit vzhled textového pole, jako je velikost a barva písma?

Odpověď: Vzhled textového pole můžete upravit úpravou jeho vlastností, jako je velikost písma, styl písma, barva, styl ohraničení, barva pozadí a další. V poskytnutém ukázkovém zdrojovém kódu jsou přizpůsobeny šířka ohraničení, vzor pomlčky ohraničení a barva textu.

#### Otázka: Je možné extrahovat uživatelem zadaný text z vytvořeného textového pole?

Odpověď: Ano, z vytvořeného textového pole můžete extrahovat text zadaný uživatelem. Poté, co uživatelé vyplní textové pole v dokumentu PDF, můžete programově získat hodnotu pole pomocí Aspose.PDF for .NET.

#### Otázka: Mohu přidat textová pole do existujícího dokumentu PDF, aniž bych vytvořil nový?

Odpověď: Ano, do existujícího dokumentu PDF můžete přidat textová pole, aniž byste museli vytvářet nové. Aspose.PDF for .NET poskytuje možnost upravovat stávající dokumenty PDF, včetně přidávání textových polí, zaškrtávacích políček a dalších prvků formuláře.

#### Otázka: Podporuje Aspose.PDF for .NET další typy polí formuláře, jako jsou zaškrtávací políčka a přepínače?

Odpověď: Ano, Aspose.PDF pro .NET podporuje různé typy polí formulářů, včetně zaškrtávacích políček, přepínačů, rozevíracích seznamů a dalších. Pomocí knihovny můžete pracovat s různými typy prvků formuláře v dokumentech PDF.