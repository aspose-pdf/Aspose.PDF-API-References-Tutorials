---
title: Odebrat otevřenou akci
linktitle: Odebrat otevřenou akci
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak odstranit akci otevření z PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 80
url: /cs/net/programming-with-links-and-actions/remove-open-action/
---
Naučte se, jak odstranit akci otevření ze souboru PDF pomocí Aspose.PDF for .NET, pomocí tohoto podrobného průvodce.

## Krok 1: Nastavení prostředí

Ujistěte se, že jste nastavili své vývojové prostředí s projektem C# a příslušnými odkazy Aspose.PDF.

## Krok 2: Načtení souboru PDF

Nastavte cestu k adresáři vašich dokumentů a nahrajte soubor PDF pomocí následujícího kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Otevřete dokument
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Krok 3: Odstranění otevřené akce

 Odeberte akci otevření z dokumentu nastavením`OpenAction` vlastnost na nulu:

```csharp
document. OpenAction = null;
```

## Krok 4: Uložte aktualizovaný dokument

 Uložte aktualizovaný dokument pomocí`Save` metoda:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Krok 5: Zobrazení výsledku

Zobrazte zprávu, že akce otevření byla úspěšně odstraněna, a zadejte umístění uloženého souboru:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Ukázkový zdrojový kód pro Remove Open Action pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Odebrat akci otevření dokumentu
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Uložit aktualizovaný dokument
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Závěr

gratuluji! Nyní víte, jak odstranit akci otevření z PDF pomocí Aspose.PDF pro .NET. Použijte tyto znalosti k přizpůsobení vlastností a chování souborů PDF ve vašich projektech.

Nyní, když jste dokončili tuto příručku, můžete tyto koncepty aplikovat na své vlastní projekty a dále prozkoumat funkce nabízené Aspose.PDF pro .NET.

### FAQ 

#### Otázka: Co je to "otevřená akce" v souboru PDF?

Odpověď: "Akce otevření" v souboru PDF je instrukce, která určuje, co se má stát při otevření PDF. Může zahrnovat akce, jako je navigace na konkrétní stránku nebo umístění v dokumentu, spuštění externí aplikace nebo zobrazení konkrétního zobrazení.

#### Otázka: Proč bych měl chtít odstranit akci otevření ze souboru PDF?

Odpověď: Odstranění akce otevřít může zlepšit zabezpečení, uživatelskou zkušenost a kontrolu nad tím, jak je PDF při otevření prezentováno. Můžete například chtít zabránit automatické navigaci nebo zakázat určité akce při otevření dokumentu.

#### Otázka: Jak Aspose.PDF pro .NET pomáhá při odstraňování otevřené akce?

Odpověď: Aspose.PDF for .NET poskytuje rozhraní API pro manipulaci s různými aspekty souborů PDF. Tento tutoriál ukazuje, jak odstranit akci open pomocí kódu C#.

#### Otázka: Existují nějaká potenciální rizika nebo úvahy při odstraňování otevřené akce?

Odpověď: Odstranění akce otevřít může změnit výchozí chování PDF, takže se ujistěte, že je v souladu se zamýšleným uživatelským prostředím. Upravené PDF důkladně otestujte, abyste se ujistili, že odstranění neovlivní další funkce.

#### Otázka: Mohu přizpůsobit akci otevření k provádění jiných akcí?

Odpověď: Ano, Aspose.PDF for .NET vám umožňuje přizpůsobit akci otevření nastavením na různé typy akcí, jako je navigace na konkrétní stránku nebo spuštění JavaScriptu.

#### Otázka: Mohu odstranit otevřené akce ze souborů PDF chráněných heslem?
Odpověď: Ano, můžete odebrat akce otevření z heslem chráněných PDF, pokud poskytnete příslušná pověření pro přístup a úpravu dokumentu.

#### Otázka: Je odstranění otevřené akce vratné?

Odpověď: Ne, jakmile je akce otevření odstraněna a soubor PDF je uložen, nelze původní akci otevření z upraveného PDF obnovit.

#### Otázka: Jak ověřím, že akce otevřít byla úspěšně odstraněna?

Odpověď: Po odstranění akce otevření pomocí poskytnutého kódu otevřete upravený soubor PDF a potvrďte, že při otevření nedojde k žádné konkrétní akci.

#### Otázka: Mohu odstranit akce otevření z více souborů PDF současně?

Odpověď: Ano, stejný přístup můžete použít k odstranění akcí otevření z více souborů PDF ve scénáři dávkového zpracování.