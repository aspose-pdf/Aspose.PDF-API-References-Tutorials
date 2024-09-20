---
title: Prvky struktury odkazů
linktitle: Prvky struktury odkazů
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet prvky struktury odkazů v PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce přidáváním přístupných odkazů, obrázků a ověřování souladu.
type: docs
weight: 120
url: /cs/net/programming-with-tagged-pdf/link-structure-elements/
---
## Zavedení

Vytváření a správa prvků struktury odkazů v rámci PDF může být zásadní pro dokumenty vyžadující dostupnost a plynulou navigaci. V tomto tutoriálu vás provedeme tím, jak to provést pomocí Aspose.PDF pro .NET. Pokud jste v Aspose.PDF nebo obecně v práci s PDF nováčky, nemějte obavy. Každý krok vám podrobně vysvětlím, abyste je mohli snadno sledovat!

## Předpoklady  

Než se ponoříme do kódování, uveďme nejprve pár věcí z cesty. Toto jsou základní požadavky pro zajištění hladkého vývoje.

1.  Aspose.PDF pro .NET: Můžete si stáhnout nejnovější verzi[zde](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí .NET: Ať už je to Visual Studio nebo jakékoli IDE kompatibilní s .NET, mějte je nainstalované a připravené.
3.  Licence Aspose: Můžete použít bezplatnou zkušební verzi Aspose.PDF[zde](https://releases.aspose.com/) nebo získat a[dočasná licence](https://purchase.aspose.com/temporary-license/).
4. Základní znalost C#: Budeme pracovat s nějakým kódem C#, takže pochopení základů věci mnohem usnadní.

## Importujte balíčky

Před napsáním kódu pro prvky struktury odkazů budete muset naimportovat několik balíčků. Začněte odkazem na potřebné knihovny Aspose.PDF ve vašem projektu:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tyto importy nám umožňují pracovat s dokumenty PDF, přidávat tagy a spravovat prvky struktury.

Nyní vytvoříme dokument PDF s různými typy struktur odkazů a každý krok bude rozčleněn, aby vám pomohl proces důkladně porozumět.

## Krok 1: Inicializujte dokument  

Začněme vytvořením nového dokumentu PDF a nastavením tagovaného obsahu pro usnadnění.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Vytvořte nový dokument PDF
Document document = new Document(); 

// Načtěte rozhraní TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Zde inicializujeme`Document` objekt, který představuje náš soubor PDF. Načítáme také`TaggedContent` rozhraní, které nám umožňuje přidávat prvky struktury, jako jsou odstavce, odkazy a obrázky.

## Krok 2: Nastavte název a jazyk  

Každý PDF by měl mít název a jazykové nastavení, zvláště pokud usilujete o shodu se standardy PDF/UA.

```csharp
// Nastavte název dokumentu a jazyk
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Tento krok zajistí, že váš PDF bude mít smysluplný název a nastaví jazyk na angličtinu (`en-US`). To je důležité pro usnadnění přístupu a zajišťuje, že čtečky obrazovky nebo jiné pomocné technologie dokážou váš dokument správně interpretovat.

## Krok 3: Vytvořte a připojte odstavce  

V tomto kroku přidáme odstavce, které budou obsahovat prvky odkazu.

```csharp
// Vytvořte kořenový prvek
StructureElement rootElement = taggedContent.RootElement;

// Vytvořte odstavec a přidejte jej do kořenového prvku
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Vytvoříme element kořenové struktury, což je v podstatě kontejner nejvyšší úrovně pro všechny ostatní prvky. Poté vytvoříme odstavec (`p1`) a připojte jej ke kořenovému prvku.

## Krok 4: Přidejte jednoduchý odkaz  

Nyní přidáme základní hypertextový odkaz, který ukazuje na Google.

```csharp
// Vytvořte prvek odkazu a přidejte jej do odstavce
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Nastavte hypertextový odkaz a text pro odkaz
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
tomto kroku jsme vytvořili prvek odkazu, nastavili jeho hypertextový odkaz na „http://google.com“ a poskytli text („Google“) pro odkaz. Také jsme přidali alternativní popis, abychom zajistili dostupnost.

## Krok 5: Přidání odkazu s rozsahy  

Můžeme také vytvářet odkazy s různými rozsahy textu.

```csharp
// Vytvořte další odstavec
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Vytvořte odkaz s prvkem span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Zde jsme použili prvek span k uzavření části textu v odkazu, což nám umožnilo přizpůsobit vzhled určitých částí odkazu.

## Krok 6: Víceřádkové propojení  

Co když je text vašeho odkazu příliš dlouhý? Žádný strach, můžete to rozdělit na více řádků.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
V tomto případě jsme vytvořili víceřádkový odkaz jednoduchým nastavením hodnoty dlouhého textu a text se automaticky zalomí přes více řádků.

## Krok 7: Přidejte obrázek do odkazu  

Nakonec můžete také přidat obrázky do odkazu.

```csharp
// Vytvořte nový odstavec a prvek odkazu
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Přidejte obrázek do odkazu
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Tento krok ukazuje, jak můžete vylepšit své odkazy pomocí obrázku. V tomto případě jsme do odkazu přidali ikonu Google. Přístupnost jsme zajistili také nastavením alternativního textu obrázku.

## Krok 8: Ověřte PDF z hlediska souladu  

Pokud usilujete o shodu s PDF/UA (standard pro usnadnění), je dobré dokument ověřit.

```csharp
// Uložte dokument PDF
document.Save(outFile);

// Ověřte, zda dokument vyhovuje PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Dokument jsme uložili a ověřili podle standardu PDF/UA, který zajišťuje, že PDF splňuje požadavky na přístupnost.

## Závěr  

V tomto tutoriálu jsme probrali, jak vytvořit strukturované dokumenty PDF pomocí Aspose.PDF pro .NET. Od přidávání základních hypertextových odkazů až po složitější struktury, jako jsou rozpětí, víceřádkové odkazy a dokonce i obrázky, tato příručka poskytuje pevný základ pro manipulaci s prvky odkazů ve vašich PDF. S přidanou výhodou kompatibility s PDF/UA jste nyní vybaveni pro vytváření přístupných a procházení PDF.

## FAQ

### Mohu do odkazů přidat složitější struktury, jako jsou tabulky?  
Ne, odkazy jsou primárně určeny pro text a obrázky, ale v blízkosti můžete vložit složité prvky.

### Je ověření PDF/UA povinné?  
Ne vždy, ale důrazně se doporučuje, pokud vám jde o přístupnost.

### Co se stane, když je cesta k souboru obrázku nesprávná?  
Dokument nezobrazí obrázek a při vykreslování může dojít k chybě.

### Mohu upravit styl textu v odkazu?  
Ano, styly textu můžete použít pomocí prvků span.

### Je možné vytvořit interní odkazy na dokumenty?  
Absolutně! Můžete odkazovat na konkrétní sekce ve stejném dokumentu.