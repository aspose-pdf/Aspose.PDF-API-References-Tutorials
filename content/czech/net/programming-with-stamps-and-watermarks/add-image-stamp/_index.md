---
title: Přidat razítko obrázku do souboru PDF
linktitle: Přidat razítko obrázku do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat obrázkové razítko do souborů PDF pomocí Aspose.PDF for .NET s podrobnými pokyny a ukázkovým kódem.
type: docs
weight: 20
url: /cs/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## Zavedení

Pokud jde o manipulaci se soubory PDF, jen málo nástrojů je tak robustních a uživatelsky přívětivých jako Aspose.PDF pro .NET. Ať už chcete přidat anotace, vytvořit formuláře nebo obrázky razítka, tato knihovna poskytuje rozsáhlé funkce, které uspokojí různé potřeby manipulace s PDF. V tomto tutoriálu se zaměříme na konkrétní úkol: přidání obrazového razítka do souboru PDF. Nejedná se pouze o plácnutí obrázku na stránku; jde o vylepšení vašich dokumentů značkou a vizuální přitažlivostí!

## Předpoklady

Než se ponoříte do toho nejhrubšího kódu, ujistěte se, že máte vše, co potřebujete. Zde je to, co budete potřebovat:

1. Visual Studio nebo jakékoli .NET IDE: K implementaci úryvků kódu potřebujete vývojové prostředí .NET.
2.  Aspose.PDF for .NET Library: Toto je hlavní nástroj, který budeme používat. Nejnovější verzi knihovny si můžete stáhnout z[Aspose release page](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Základní znalost programování C# vám pomůže hladce procházet kódem.
4. Soubor obrázku: Potřebujete soubor obrázku, který chcete použít jako razítko. Ujistěte se, že je v podporovaném formátu (jako JPEG, PNG atd.).
5. Existující soubor PDF: Připravte si vzorový soubor PDF, do kterého přidáte razítko obrázku.

Nyní, když jsme vše připraveni, pojďme se vrhnout na kód!

## Importujte balíčky

Nejdříve – než něco uděláte, musíte importovat potřebné jmenné prostory. V kódu C# to můžete provést přidáním následujícího příkazu pomocí příkazu v horní části souboru:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

To vám umožní přístup k různým třídám a metodám poskytovaným knihovnou Aspose.PDF.

## Krok 1: Nastavte adresář dokumentů

 Prvním krokem je zadání cesty k vašim dokumentům. Budete chtít uložit dokument a obrázky do dobře definovaného adresáře. Pro jednoduchost deklarujte proměnnou`dataDir` takhle:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ve vašem systému.

## Krok 2: Otevřete dokument PDF

Dále musíme otevřít dokument PDF, který chceme upravit. To je místo, kde Aspose.PDF září! Potřebujete jen pár řádků kódu:

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

 Tento řádek vytvoří nový`Document`objekt načtením zadaného souboru PDF. Ujistěte se, že soubor existuje ve vámi určeném adresáři; jinak narazíte na chybu nenalezen soubor!

## Krok 3: Vytvořte obrazové razítko

Nyní přichází ta zábavná část – přidání obrazového razítka! Nejprve musíme vytvořit objekt razítka obrázku pomocí souboru obrázku:

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 Tento řádek inicializuje`ImageStamp` objekt, který představuje obrázek, který chcete přidat. Je důležité zkontrolovat, zda je cesta k souboru obrázku správná.

## Krok 4: Konfigurace vlastností razítka obrázku

Zde můžete být kreativní a upravit si razítko. Můžete nastavit vlastnosti, jako je poloha, velikost, otočení a krytí. Zde je příklad, jak to udělat:

```csharp
imageStamp.Background = true; // Nastavte na hodnotu true, pokud chcete, aby bylo razítko na pozadí
imageStamp.XIndent = 100; // Pozice zleva
imageStamp.YIndent = 100; // Umístěte shora
imageStamp.Height = 300; // Nastavte výšku razítka
imageStamp.Width = 300; // Nastavte šířku razítka
imageStamp.Rotate = Rotation.on270; // V případě potřeby otočte
imageStamp.Opacity = 0.5; // Nastavte neprůhlednost
```

Neváhejte a upravte tyto hodnoty podle svých požadavků! Toto přizpůsobení vám umožní umístit razítko přesně tam, kam chcete.

## Krok 5: Přidejte razítko na konkrétní stránku

Nyní, když máme naše razítko nakonfigurované, dalším krokem je určit, kam ho chceme v dokumentu PDF umístit. V tomto příkladu jej přidáme na první stránku:

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Tento fragment kódu říká Aspose, aby přidal razítko na první stránku dokumentu.

## Krok 6: Uložte dokument

Jakmile je razítko aplikováno, je čas uložit změny. Musíte zadat cestu pro výstupní soubor PDF:

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

Váš dokument je nyní uložen s novým razítkem obrázku!

## Krok 7: Potvrďte změnu

Nakonec je vždy dobré potvrdit, že vaše operace byla úspěšná. Můžete to udělat pomocí jednoduché zprávy konzoly:

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

Tato zpráva vás upozorní, že bylo přidáno razítko obrázku, a bude vás informovat o tom, kde najdete svůj nově upravený soubor PDF.

## Závěr

Gratuluji! Právě jste přidali razítko obrázku do PDF pomocí Aspose.PDF pro .NET. Na první pohled se to může zdát složité, ale s trochou cviku si můžete své PDF dokumenty přizpůsobit nesčetnými způsoby. Klíčem je zde experimentování s různými vlastnostmi, které Aspose nabízí – limitem je vaše představivost.

## FAQ

### Je Aspose.PDF for .NET zdarma k použití?  
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro další používání po zkušební době je vyžadována licence. Můžete se podívat na[cenové možnosti zde](https://purchase.aspose.com/buy).

### Mohu do jednoho PDF přidat více razítek?  
 Absolutně! Můžete vytvořit více`ImageStamp` objekty a přidejte je na libovolnou stránku v PDF.

### Jaké formáty obrázků jsou podporovány pro razítka?  
Aspose.PDF podporuje různé formáty obrázků, včetně JPEG, PNG a BMP.

### Jak mohu otočit obrazové razítko?  
 Můžete nastavit`Rotate` vlastnictvím`ImageStamp` objekt pro otočení obrázku v požadovaném úhlu. Možnosti zahrnují`Rotation.on90`, `Rotation.on180`atd.

### Kde najdu další dokumentaci na Aspose.PDF?  
 Můžete prozkoumat kompletní referenční API a dokumentaci[zde](https://reference.aspose.com/pdf/net/).