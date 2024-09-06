---
title: Prvky struktury odkazů
linktitle: Prvky struktury odkazů
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce používáním prvků struktury odkazů s Aspose.PDF pro .NET. Vytvářejte hypertextové odkazy ve svých dokumentech PDF.
type: docs
weight: 120
url: /cs/net/programming-with-tagged-pdf/link-structure-elements/
---
V tomto podrobném průvodci vám ukážeme, jak používat prvky struktury odkazů s Aspose.PDF pro .NET. Aspose.PDF je výkonná knihovna, která vám umožní programově vytvářet a manipulovat s dokumenty PDF. Prvky struktury odkazů umožňují přidávat do dokumentu PDF hypertextové odkazy, které uživatelům umožňují klikat na odkazy a procházet online zdroje.

Pojďme se ponořit do kódu a naučit se používat prvky struktury odkazů s Aspose.PDF pro .NET.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Nainstalovaná knihovna Aspose.PDF pro .NET.
2. Základní znalost programovacího jazyka C#.

## Krok 1: Nastavení prostředí

Chcete-li začít, otevřete vývojové prostředí C# a vytvořte nový projekt. Ujistěte se, že jste do svého projektu přidali odkaz na knihovnu Aspose.PDF pro .NET.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Krok 2: Vytvoření dokumentu

 Prvním krokem je vytvoření nového dokumentu PDF pomocí`Document` třída.

```csharp
// Vytvořte dokument PDF
Document document = new Document();
```

## Krok 3: Práce s označeným obsahem

Poté dostaneme označený obsah dokumentu, se kterým můžeme pracovat.

```csharp
// Získejte označený obsah dokumentu
ITaggedContent taggedContent = document.TaggedContent;
```

## Krok 4: Nastavte název dokumentu a jazyk

Nyní můžeme nastavit název dokumentu a jazyk.

```csharp
// Definujte název dokumentu a jazyk
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Krok 5: Přidejte prvky struktury odkazů

Nyní do našeho dokumentu přidáme prvky struktury odkazů. Vytvoříme různé typy odkazů, včetně jednoduchých textových odkazů, obrázkových odkazů a víceřádkových odkazů.
```csharp
// Získejte prvek kořenové struktury (prvek struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;

// Přidejte odstavec s hypertextovým odkazem
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Přidejte odstavec s hypertextovým odkazem obsahujícím formátovaný text
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Přidejte odstavec s hypertextovým odkazem obsahujícím částečně formátovaný text
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Přidejte odstavec s víceřádkovým hypertextovým odkazem
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Přidejte odstavec s hypertextovým odkazem obsahujícím obrázek
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Krok 6: Uložte označený dokument PDF

Nakonec tagovaný dokument PDF uložíme.

```csharp
// Uložte označený dokument PDF
document. Save(outFile);
```

## Krok 7: Zkontrolujte shodu s PDF/UA

 Můžeme také zkontrolovat, zda dokument vyhovuje PDF/UA pomocí`Validate` metoda`Document` třída.

```csharp
// Zkontrolujte shodu s PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Ukázkový zdrojový kód pro prvky Link Structure Elements pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Vytvoření dokumentu a získání tagovaného obsahu PDF
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Nastavení názvu a přirozeného jazyka pro dokument
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Získání prvku kořenové struktury (prvku struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Uložit označený dokument PDF
document.Save(outFile);

// Kontrola shody s PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Závěr

gratuluji! Naučili jste se používat prvky struktury odkazů s Aspose.PDF pro .NET. Nyní můžete ve svých dokumentech PDF vytvářet hypertextové odkazy, které uživatelům umožňují přejít na online zdroje. Experimentujte a prozkoumejte další funkce Aspose.PDF, abyste mohli vytvářet interaktivní a obohacené dokumenty PDF.

### FAQ

#### Otázka: Co jsou prvky struktury odkazů v dokumentu PDF a jak zlepšují interaktivitu dokumentu?

Odpověď: Prvky struktury odkazů v dokumentu PDF se používají k vytvoření hypertextových odkazů, které uživatelům umožňují přejít na online zdroje nebo konkrétní umístění v dokumentu. Tyto prvky zvyšují interaktivitu tím, že poskytují klikací odkazy, které uživatelům umožňují přístup k souvisejícímu obsahu nebo externím webovým stránkám.

#### Otázka: Jak mohou být prvky struktury odkazů užitečné v dokumentu PDF?

Odpověď: Prvky struktury odkazů vylepšují uživatelský zážitek tím, že dokument PDF je interaktivní. Poskytují rychlý přístup k dalším informacím, souvisejícímu obsahu, externím webovým stránkám nebo konkrétním sekcím v dokumentu, zlepšují navigaci a usnadňují vyhledávání informací.

#### Otázka: Mohu vytvořit různé typy hypertextových odkazů pomocí prvků struktury odkazů v Aspose.PDF pro .NET?

Odpověď: Ano, pomocí prvků struktury odkazů můžete vytvářet různé typy hypertextových odkazů. Aspose.PDF for .NET vám umožňuje vytvářet hypertextové odkazy s prostým textem, formátovaným textem, obrázky a víceřádkovými popisy, což nabízí všestrannost ve způsobu, jakým odkazujete na externí obsah nebo umístění v dokumentu.

#### Otázka: Jak mohu nastavit a inicializovat prvky struktury odkazů v dokumentu PDF pomocí Aspose.PDF pro .NET?

 A: Chcete-li použít prvky struktury odkazů, musíte nejprve vytvořit nový dokument PDF pomocí`Document` třída. Poté získejte označený obsah pomocí`TaggedContent`vlastnost dokumentu. Odtud můžete vytvářet a přizpůsobovat prvky struktury odkazů a přidávat je do prvku kořenové struktury.

#### Otázka: Jak mohu vytvořit jednoduchý textový hypertextový odkaz pomocí prvků struktury odkazu?
 Odpověď: Jednoduchý textový hypertextový odkaz můžete vytvořit vytvořením a`LinkElement` a jeho nastavení`Hyperlink` majetek do a`WebHyperlink` s adresou URL, na kterou chcete odkazovat. Můžete také nastavit zobrazovaný text odkazu pomocí`SetText` metoda.

#### Otázka: Je možné vytvářet hypertextové odkazy s obrázky pomocí prvků struktury odkazů?

 Odpověď: Ano, pomocí prvků struktury odkazů můžete vytvářet hypertextové odkazy s obrázky. Vytvořili byste a`LinkElement` a poté připojte a`FigureElement` s obrázkem k tomu. To vám umožní vytvořit hypertextový odkaz založený na obrázku.

#### Otázka: Jak mohu zajistit, aby můj dokument PDF s hypertextovými odkazy odpovídal standardu PDF/UA pro usnadnění?

 Odpověď: Aspose.PDF for .NET poskytuje možnost ověřit shodu vašeho dokumentu PDF se standardem PDF/UA pomocí`Validate` metoda`Document`třída. Tím je zajištěno, že hypertextové odkazy dokumentu jsou přístupné uživatelům se zdravotním postižením.

#### Otázka: Co jsou alternativní popisy prvků struktury odkazů a proč jsou důležité?

Odpověď: Alternativní popisy (alt text) pro prvky struktury odkazů poskytují textové popisy hypertextových odkazů. Tyto popisy jsou nezbytné pro přístupnost a umožňují uživatelům se zrakovým postižením pochopit účel odkazu a jeho cíl.

#### Otázka: Mohu přizpůsobit vzhled a chování hypertextových odkazů vytvořených pomocí prvků struktury odkazů?

Odpověď: Zatímco prvky struktury odkazů se primárně zaměřují na vytváření hypertextových odkazů, můžete si vzhled a chování hypertextových odkazů dále přizpůsobit pomocí dalších funkcí nabízených Aspose.PDF pro .NET. To zahrnuje specifikaci barev, stylů a akcí odkazu.

#### Otázka: Jak přispívají prvky struktury odkazů k tomu, aby byly dokumenty PDF interaktivnější a uživatelsky přívětivější?

Odpověď: Prvky struktury odkazů přeměňují statické dokumenty PDF na interaktivní prostředí přidáním hypertextových odkazů, na které lze kliknout. Tato interaktivita zlepšuje zapojení uživatelů, umožňuje bezproblémovou navigaci mezi souvisejícím obsahem a zlepšuje celkovou použitelnost dokumentu.