---
title: Vyplnit text tahu v souboru PDF
linktitle: Vyplnit text tahu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak snadno vyplňovat a obrysovat text v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 90
url: /cs/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
tomto tutoriálu vás krok za krokem provedeme, jak vyplnit a načrtnout text v souboru PDF pomocí Aspose.PDF pro .NET. Ukážeme vám, jak pomocí poskytnutého zdrojového kódu C# použít barvy výplně a obrysu na text v souboru PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Vytvoření objektu TextState

Prvním krokem je vytvoření objektu TextState, který předá pokročilé vlastnosti. Zde je postup:

```csharp
// Vytvořte objekt TextState pro přenos pokročilých vlastností
TextState ts = new TextState();

// Nastavit barvu obrysu
ts.StrokingColor = Color.Gray;

// Definujte režim vykreslování textu
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Výše uvedený kód vytvoří nový objekt TextState a nastaví barvu obrysu a také způsob vykreslení textu.

## Krok 3: Načtení dokumentu PDF

Nyní, když je objekt TextState připraven, můžeme načíst dokument PDF, kde chceme použít textovou výplň a obrys. Zde je postup:

```csharp
// Načtěte dokument PDF jako vstup
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Výše uvedený kód načte existující dokument PDF pomocí třídy PdfFileStamp z knihovny Aspose.PDF.Facades.

## Krok 4: Přidejte k textu výplň a tah

Nyní, když je dokument PDF načten, můžeme k textu přidat výplň a obrys. Zde je postup:

```csharp
// Vytvořte razítko (Stamp) s definovaným textem a vlastnostmi
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Svažte objekt TextState
stamp.BindTextState(ts);

// Nastavte počátek X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Přidejte razítko do dokumentu
fileStamp.AddStamp(stamp);
```

Výše uvedený kód vytvoří Razítko se zadaným textem a definovanými vlastnostmi Výplň a Tah.

## Krok 5: Uložte výstupní dokument

Po přidání textového razítka můžeme upravený PDF dokument uložit. Zde je postup:

```csharp
// Uložte upravený dokument
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro text Fill Stroke Text pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte objekt TextState pro přenos pokročilých vlastností
TextState ts = new TextState();

// Nastavte barvu tahu
ts.StrokingColor = Color.Gray;

// Nastavte režim vykreslování textu
ts.RenderingMode = TextRenderingMode.StrokeText;

// Načtěte vstupní dokument PDF
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Svázat TextState
stamp.BindTextState(ts);

// Nastavte počátek X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Přidat razítko
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Závěr

gratuluji! Naučili jste se, jak vyplnit a ohraničit text v dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti použít k přizpůsobení barev výplně a obrysů v dokumentech PDF.

### Nejčastější dotazy k vyplnění textu tahu v souboru PDF

#### Otázka: Co to znamená vyplnit a ohraničit text v dokumentu PDF a kdy to možná budu muset udělat?

Odpověď: Vyplňování a obrysování textu v dokumentu PDF zahrnuje použití barev na vnitřek textových znaků (výplň) a na okraje kolem textu (obrys). To lze použít k vylepšení vizuálního vzhledu textu, vytvoření zvýraznění nebo zvýraznění konkrétního obsahu v PDF.

#### Otázka: Jak poskytnutý zdrojový kód C# zajišťuje vyplnění a nastínění textu v souboru PDF?

 Odpověď: Poskytnutý zdrojový kód ukazuje, jak vytvořit a`TextState` objekt k definování pokročilých vlastností textu, jako je barva obrysu a režim vykreslování. Poté pomocí Aspose.PDF.Facades načte existující dokument PDF, vytvoří razítko obsahující text se zadanými vlastnostmi výplně a tahu a přidá razítko do dokumentu.

####  Otázka: Jaký je účel`TextState` object in the code?

 A:`TextState`objekt se používá k definování pokročilých vlastností textu, včetně barvy obrysu textu (tahu) a režimu vykreslování. Umožňuje vám přizpůsobit, jak se text zobrazí z hlediska tahu a výplně.

#### Otázka: Mohu použít různé barvy výplně a obrysu na různé části stejného textu?

 Odpověď: Ano, kód můžete upravit a vytvořit jiný`TextState` objekty s odlišnou barvou výplně a obrysu a aplikujte je na konkrétní části textu pomocí oddělených`Stamp` objektů.

#### Otázka: Mohu použít barvy výplně a obrysu na text, který je již obsažen v dokumentu PDF?

 Odpověď: Ano, podobné principy můžete použít k aplikaci barev výplně a obrysu na existující text v dokumentu PDF výběrem vhodných textových objektů a jejich přidáním jako razítka s požadovaným`TextState` vlastnosti.

#### Otázka: Jak mohu upravit neprůhlednost a prolnutí vyplněného a obrysového textu?

 Odpověď: Poskytnutý kód vám umožňuje nastavit vlastnosti krytí a prolnutí razítka pomocí`Opacity` a`BlendingSpace`vlastnosti, resp. Tyto hodnoty můžete upravit, abyste dosáhli požadovaného vizuálního efektu.

#### Otázka: Jak mohu použít různé barvy výplně a obrysu na více razítek ve stejném dokumentu PDF?

 A: Můžete vytvořit více`TextState` objekty s různými barvami výplně a obrysu a poté vytvořte samostatné`Stamp` objekty pro každou sadu textu s odlišnými barvami. Přidejte tato razítka do stejného dokumentu PDF pomocí`PdfFileStamp` třída.

#### Otázka: Mohu pro obrysový a vyplněný text použít jiná písma než Arial?

 Odpověď: Ano, písmo můžete změnit úpravou parametru názvu písma v souboru`FormattedText` konstruktoru při vytváření razítka. Můžete použít jakékoli písmo dostupné ve vašem systému.

#### Otázka: Jak mohu upravit úhel otočení obrysového a vyplněného textu?

 A: Poskytnutý kód vám umožňuje nastavit úhel otočení razítka pomocí`Rotation` vlastnictví. Tuto vlastnost můžete upravit a určit požadovaný úhel otočení textu.

#### Otázka: Jak mohu ovládat polohu a velikost obrysového a vyplněného textu na stránce?

 A: Můžete použít`SetOrigin` metoda`Stamp` objekt pro nastavení souřadnic X a Y polohy razítka na stránce. Kromě toho můžete upravit velikost písma v`FormattedText` konstruktor pro ovládání velikosti textu.