---
title: Extrahujte informace o podpisu
linktitle: Extrahujte informace o podpisu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat digitální podpisy a informace o certifikátech z dokumentů PDF pomocí Aspose.PDF for .NET. Kompletní průvodce krok za krokem pro vývojáře C#.
type: docs
weight: 80
url: /cs/net/programming-with-security-and-signatures/extract-signature-info/
---
## Zavedení

dnešním digitálním světě je zásadní zajistit bezpečnost a integritu dokumentů. Jednou z běžných metod používaných k zabezpečení souborů PDF je přidání digitálního podpisu. Získání a ověření podrobností podpisu však může být někdy problém, zvláště když máte co do činění s různými certifikáty. V této příručce vás provedeme procesem extrahování informací o podpisu z dokumentů PDF pomocí Aspose.PDF pro .NET, díky čemuž bude tento úkol hračkou. Dozvíte se, jak získat přístup k podpisovým polím, extrahovat informace o certifikátu a uložit je do souboru.

## Předpoklady

Než začneme, ujistěte se, že máte vše připraveno, abyste mohli začít.

-  Aspose.PDF for .NET Library: Pokud ji ještě nemáte, můžete si ji stáhnout z[Stránka pro stahování Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/). 
- Vývojové prostředí .NET: Budete potřebovat IDE jako Visual Studio.
- Základní znalost C#: Znalost C# je užitečná pro pochopení úryvků kódu v tomto tutoriálu.
- Dokument PDF s digitálním podpisem: Pro účely testování se ujistěte, že máte soubor PDF, který obsahuje alespoň jeden digitální podpis.

## Import požadovaných jmenných prostorů

Než skočíte do kódu, je důležité importovat potřebné jmenné prostory. Tyto jmenné prostory vám umožní přístup k funkci Aspose.PDF a práci s dokumenty PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Nyní, když jste nastavili základy, přejděme ke skutečnému procesu extrahování informací o podpisu z PDF.

## Krok 1: Nastavení adresáře dokumentů

 Než začnete pracovat na dokumentu PDF, musíte určit umístění souboru, který budete používat. Můžete vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde jsou uloženy vaše PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Zde uvedeme adresář obsahující soubor PDF a samotný název souboru. Ujistěte se, že soubor v tomto adresáři existuje!

## Krok 2: Načtení dokumentu PDF

 Nyní, když jste nastavili svůj adresář, je dalším krokem načtení dokumentu PDF pomocí`Document` třídy z Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Zpracujte PDF zde.
}
```

 Tento řádek kódu inicializuje a`Document`objekt, který představuje soubor PDF. The`using` příkaz zajišťuje, že prostředky jsou po zpracování dokumentu vyčištěny.

## Krok 3: Přístup k polím formuláře

V tomto kroku projdeme všechna pole formuláře v dokumentu PDF. Protože podpisy jsou obvykle uloženy jako pole formuláře, tento krok nám pomůže identifikovat pole podpisu.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Zde identifikujte pole podpisu.
}
```

 Iterací přes`Form` vlastnictví`Document` objekt, můžeme prozkoumat každé pole formuláře a zkontrolovat, zda se jedná o pole podpisu.

## Krok 4: Identifikace polí podpisu

 Jakmile vstoupíte do polí formuláře, dalším krokem je určit, která z nich jsou pole podpisu. Můžeme to udělat přetypováním každého pole na a`SignatureField` objekt.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Extrahujte informace o podpisu.
}
```

 Zde používáme`as` klíčové slovo pro pokus o přetypování každého pole formuláře na a`SignatureField`. Pokud je obsazení úspěšné, víme, že pole je podpis.

## Krok 5: Vyjmutí certifikátu

Nyní, když jste identifikovali pole podpisu, je dalším úkolem extrahovat certifikát z podpisu. Certifikáty obsahují zásadní informace o podepisovateli a platnosti podpisu.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 The`ExtractCertificate` metoda vrací a`Stream` objekt obsahující data certifikátu. Tento proud lze použít k uložení certifikátu pro další analýzu nebo uložení.

## Krok 6: Uložení certifikátu do souboru

 Po rozbalení certifikátu je posledním krokem jeho uložení do souboru. V tomto případě certifikát uložíme jako a`.cer` soubor.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

V tomto bloku kódu:

1. Zkontrolujte, zda stream certifikátů není null.
2. Načtěte data certifikátu do bajtového pole.
3.  Zapište bajtové pole do a`.cer` soubor v adresáři dokumentů.

## Závěr

Extrahování digitálních podpisů a souvisejících informací o certifikátech z dokumentů PDF pomocí Aspose.PDF pro .NET je poměrně jednoduché, když je rozděleno do jednoduchých kroků. Ať už kontrolujete dokumenty, ověřujete podpisy nebo jen uchováváte certifikáty pro úschovu, tento tutoriál vás vybaví znalostmi, jak to udělat efektivně. Pamatujte, že zabezpečení a ověřování dokumentů je v dnešním digitálním světě zásadní a používání nástrojů jako Aspose.PDF pro .NET usnadňuje manipulaci.

## FAQ

### Mohu extrahovat více podpisů z PDF pomocí Aspose.PDF pro .NET?
Ano, kód prochází všechna pole formuláře v dokumentu, což vám umožňuje extrahovat více podpisů, pokud existují.

### Co se stane, když v PDF není nalezen žádný podpis?
Pokud nejsou přítomna žádná pole podpisu, kód je jednoduše přeskočí, aniž by vyvolal chybu.

### Mohu tento přístup použít k ověření platnosti podpisu?
když certifikát můžete extrahovat, ověření platnosti podpisu vyžaduje další kroky, jako je kontrola řetězce důvěryhodnosti certifikátu.

### Je možné extrahovat další data pole formuláře pomocí Aspose.PDF pro .NET?
Ano, Aspose.PDF vám umožňuje přistupovat a manipulovat s různými typy polí formulářů v PDF, nejen s poli podpisů.

### Jak mohu zobrazit podrobnosti o extrahovaném certifikátu?
 Jakmile je certifikát uložen jako a`.cer` soubor, můžete jej otevřít pomocí libovolného prohlížeče certifikátů nebo jej importovat do systémového úložiště certifikátů pro další kontrolu.