---
title: Skrytý Textový Blok V Souboru PDF
linktitle: Skrytý Textový Blok V Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet skryté textové bloky v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 230
url: /cs/net/programming-with-text/hidden-text-block/
---
V tomto tutoriálu vysvětlíme, jak vytvořit skrytý textový blok v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Skrytý textový blok je plovoucí text, který se zviditelní, když kurzor myši najede na určitou oblast. Projdeme si krok za krokem proces vytvoření skrytého textového bloku pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve je potřeba nastavit cestu k adresáři, kam chcete vygenerovaný PDF soubor uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir`proměnnou s cestou k požadovanému adresáři.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte vzorový dokument

V tomto kroku vytvoříme vzorový dokument PDF a přidáme do něj fragment textu. Textový fragment bude sloužit jako spouštěč pro zobrazení skrytého textového bloku.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Krok 3: Otevřete dokument

 Nyní otevřeme dříve vytvořený dokument pomocí`Document` třída.

```csharp
Document document = new Document(outputFile);
```

## Krok 4: Najděte textový fragment

 Používáme a`TextFragmentAbsorber` objekt k nalezení fragmentu textu, který spustí zobrazení bloku skrytého textu. V tomto případě hledáme přesný text „Přesuňte kurzor myši sem pro zobrazení plovoucího textu“.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Krok 5: Vytvořte skryté textové pole

 Vytváříme a`TextBoxField` objekt, který bude reprezentovat skryté textové pole. Toto pole bude obsahovat text, který se zobrazí, když kurzor myši najede na text spouště.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Krok 6: Přidejte do dokumentu skryté textové pole

Skryté textové pole přidáme do kolekce formulářů dokumentu.

```csharp
document.Form.Add(floatingField);
```

## Krok 7: Vytvořte neviditelné tlačítko

Vytvoříme neviditelné tlačítkové pole, které bude umístěno nad fragmentem spouštěcího textu. Toto pole tlačítka bude mít akce spojené s událostmi vstupu a výstupu myší.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Krok 8: Uložte dokument

Nakonec upravený dokument uložíme se skrytým textovým blokem.

```csharp
document. Save(outputFile);
```

### Ukázka zdrojového kódu pro skrytý textový blok pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Vytvořte vzorový dokument s textem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Otevřete dokument s textem
Document document = new Document(outputFile);
// Vytvořte objekt TextAbsorber a najděte všechny fráze odpovídající regulárnímu výrazu
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Přijměte absorbér pro stránky dokumentu
document.Pages.Accept(absorber);
// Získejte první extrahovaný textový fragment
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Vytvořte skryté textové pole pro plovoucí text v určeném obdélníku stránky
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Nastavte text, který se zobrazí jako hodnota pole
floatingField.Value = "This is the \"floating text field\".";
// Pro tento scénář doporučujeme vytvořit pole „pouze pro čtení“.
floatingField.ReadOnly = true;
// Nastavte příznak 'skrytý', aby bylo pole při otevření dokumentu neviditelné
floatingField.Flags |= AnnotationFlags.Hidden;
// Nastavení jedinečného názvu pole není nutné, ale povoleno
floatingField.PartialName = "FloatingField_1";
// Nastavení charakteristik vzhledu pole není nutné, ale zlepšuje to
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Přidejte do dokumentu textové pole
document.Form.Add(floatingField);
// Vytvořit neviditelné tlačítko na pozici fragmentu textu
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Vytvořte novou akci skrytí pro zadané pole (poznámku) a příznak neviditelnosti.
//(Můžete také odkazovat na plovoucí pole názvem, pokud jste jej uvedli výše.)
// Přidejte akce při vstupu/výstupu myší do pole neviditelného tlačítka
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Přidejte do dokumentu pole tlačítka
document.Form.Add(buttonField);
// Uložit dokument
document.Save(outputFile);
```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit skrytý textový blok pomocí knihovny Aspose.PDF for .NET. Podle podrobného průvodce můžete vygenerovat dokument PDF se skrytým textovým polem, které se zviditelní, když kurzor myši najede na určitou oblast. Vzhled a chování bloku skrytého textu si můžete přizpůsobit podle svých požadavků.

### FAQ

#### Otázka: Jaký je účel výukového programu „Skrytý textový blok v souboru PDF“?

Odpověď: Výukový program „Skrytý textový blok v souboru PDF“ vysvětluje, jak vytvořit skrytý textový blok v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Skrytý textový blok je plovoucí text, který se zviditelní, když kurzor myši najede na určitou oblast. Tento tutoriál poskytuje podrobného průvodce pomocí zdrojového kódu C#.

#### Otázka: Proč bych měl chtít vytvořit skrytý textový blok v souboru PDF?

Odpověď: Vytvoření skrytého textového bloku může být užitečné pro interaktivní dokumenty PDF, kde chcete poskytnout další informace nebo kontext, které se zviditelní pouze tehdy, když uživatel najede kurzorem myši na určenou oblast.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kam chcete vygenerovaný PDF soubor uložit.

#### Otázka: Jak vytvořím vzorový dokument a přidám do něj fragment textu?

A: V tutoriálu používáte`Document` třídy k vytvoření ukázkového dokumentu PDF a přidání fragmentu textu. Tento fragment textu slouží jako spouštěč pro zobrazení bloku skrytého textu.

#### Otázka: Jak najdu fragment textu, který spouští blok skrytého textu?

 Odpověď: Tutoriál ukazuje, jak používat a`TextFragmentAbsorber` objekt k nalezení fragmentu textu, který spouští zobrazení bloku skrytého textu. Vyhledá konkrétní textový řetězec v dokumentu PDF.

#### Otázka: Jak vytvořím a přizpůsobím skryté textové pole?

 A: Vytvoříte a`TextBoxField` objekt, který bude reprezentovat skryté textové pole. Kurz poskytuje kód pro nastavení různých vlastností, jako je poloha, hodnota, vzhled a chování skrytého textového pole.

#### Otázka: Jak vytvořím neviditelné tlačítko spojené se skrytým textovým blokem?

 Odpověď: Pole neviditelného tlačítka je vytvořeno pomocí`ButtonField` třída. Toto tlačítkové pole je umístěno nad fragmentem textu spouštěče a má akce spojené s událostmi vstupu a výstupu myší. Tyto akce řídí viditelnost skrytého textového bloku.

#### Otázka: Mohu upravit vzhled bloku skrytého textu a oblasti spouštění?

Odpověď: Ano, můžete přizpůsobit různé vlastnosti skrytého textového pole i neviditelného tlačítka, včetně písma, barvy, velikosti a umístění.

#### Otázka: Jak uložím upravený dokument se skrytým textovým blokem?

 Odpověď: Výukový program ukazuje, jak uložit upravený dokument pomocí`Save` metoda`Document` třída.