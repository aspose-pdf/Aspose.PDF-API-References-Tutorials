---
title: Přidat Java Script do souboru PDF
linktitle: Přidat soubor PDF Java Script
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat JavaScript do souboru PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce s výukovým programem kódu pro skriptování na úrovni dokumentu a stránky.
type: docs
weight: 10
url: /cs/net/programming-with-document/addjavascripttopage/
---
## Zavedení

Přemýšleli jste někdy o tom, jak vylepšit své soubory PDF o interaktivní prvky, jako jsou vyskakovací upozornění nebo funkce automatického tisku? Dobrá zpráva – můžete! Pomocí Aspose.PDF pro .NET můžete do dokumentů PDF bez problémů přidávat JavaScript. Ať už automatizujete úlohy nebo vytváříte dynamické uživatelské prostředí, vkládání JavaScriptu do souborů PDF dává vašim souborům další úroveň funkčnosti.

## Předpoklady

Než se pustíme do části kódování, je potřeba nastavit několik věcí:

-  Aspose.PDF pro .NET: Stáhněte si knihovnu z[Aspose Releases](https://releases.aspose.com/pdf/net/) nebo získat a[zkušební verze zdarma](https://releases.aspose.com/).
- Vývojové prostředí: Jakékoli IDE kompatibilní s .NET, jako je Visual Studio.
- Základní znalosti C#: Tato příručka předpokládá, že jste obeznámeni se základní syntaxí C#.
-  Dočasná licence (volitelné): Můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) pokud se chcete během svého vývoje vyhnout omezením.

## Importujte balíčky

Než začnete psát kód, budete muset importovat potřebné jmenné prostory z knihovny Aspose.PDF. Tyto jmenné prostory vám umožní snadno manipulovat s PDF a přidávat akce JavaScriptu.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Nyní, když jste importovali správné jmenné prostory, jste připraveni začít kódovat.

## Krok 1: Načtěte existující PDF

První věci – musíte načíst dokument PDF, do kterého chcete přidat JavaScript. Tento krok připraví půdu pro všechny další úpravy. Představte si, že máte PDF, které chcete vylepšit o dynamické funkce, jako je automatický tisk dokumentu po otevření.

Tento soubor PDF můžete načíst takto:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubor PDF
Document doc = new Document(dataDir + "input.pdf");
```

 V tomto fragmentu kódu používáme`Document` třídy k načtení existujícího souboru PDF ze zadaného adresáře. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu souboru PDF.

## Krok 2: Přidejte JavaScript na úrovni dokumentu

Nyní přidáme nějaký JavaScript, který se spustí při otevření dokumentu. V tomto příkladu napíšeme skript, který otevře dialogové okno tisku, jakmile uživatel otevře PDF.

JavaScript na úrovni dokumentu je ideální pro akce, které chcete aplikovat na celý PDF. Představte si to jako nastavení globálního pravidla pro váš dokument.

Zde je kód:

```csharp
// Přidání JavaScriptu na úrovni dokumentu
// Okamžitě aktivujte JavascriptAction s požadovaným příkazem JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Přiřaďte objekt JavascriptAction k OpenAction dokumentu
doc.OpenAction = javaScript;
```

 V tomto kroku vytvoříme a`JavascriptAction` objekt, který definuje funkci JavaScriptu pro otevření tiskového dialogu při otevření dokumentu. The`doc.OpenAction` vlastnosti je pak přiřazena tato akce JavaScriptu.

## Krok 3: Přidejte JavaScript na úrovni stránky

Ne každá akce musí ovlivnit celý dokument. Někdy chcete, aby při otevření nebo zavření určitých stránek došlo ke konkrétním akcím. Zde nastavíme akce JavaScriptu při otevření a zavření konkrétní stránky (řekněme stránka 2).

JavaScript na úrovni stránky je užitečný pro cílené interakce. Může to být cokoli od zobrazení zprávy, když uživatel přejde na stránku, až po vlastní akce, jako je automatické vyplňování polí formuláře.

Jak na to:

```csharp
// Přidání JavaScriptu na úrovni stránky
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Do tohoto fragmentu kódu přidáváme dvě akce JavaScriptu:
1. Akce při otevření: Zobrazí upozornění „Stránka 2 otevřena“, když uživatel otevře stránku 2.
2. Akce OnClose: Zobrazí upozornění „Stránka 2 uzavřena“, když uživatel opustí stránku 2.

To do vašeho PDF přidá vrstvu interaktivity. Představte si, že uživatele provedete řadou kroků na různých stránkách s upozorněními, která se objeví, když vstoupí na stránku nebo ji opustí.

## Krok 4: Uložte dokument PDF

Nyní jste přidali JavaScript do dokumentu i konkrétních stránek. Posledním krokem je uložení upraveného PDF do požadovaného umístění. Tato část je jednoduchá, ale zásadní – nezapomeňte si práci uložit!

Zde je kód:

```csharp
// Zadejte cestu k výstupnímu souboru
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Uložte aktualizovaný dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 V tomto úryvku uložíme aktualizovaný dokument s přidaným JavaScriptem do nového souboru s názvem`"JavaScript-Added_out.pdf"`. Tím zajistíte, že nepřepíšete svůj původní soubor, a získáte zálohu, se kterou můžete pracovat.

## Závěr

Přidání JavaScriptu do souborů PDF pomocí Aspose.PDF for .NET je účinný způsob, jak vytvářet interaktivní, dynamické soubory PDF. Ať už automatizujete úkoly, jako je tisk nebo vytváříte vlastní upozornění, díky možnosti vložit JavaScript do vašeho PDF budou vaše dokumenty poutavější a funkčnější.

## FAQ

### Mohu přidat více akcí JavaScriptu na různé stránky v PDF?
Ano, jednotlivým stránkám nebo celému dokumentu můžete přiřadit různé akce JavaScriptu.

### Je možné odstranit JavaScript z PDF po jeho přidání?
Ano, existující akce JavaScriptu můžete odstranit nebo upravit vymazáním`Actions` vlastnosti dokumentu nebo stránky.

### Jaké funkce JavaScriptu mohu použít v PDF?
Můžete použít jakýkoli JavaScript podporovaný jádrem JavaScriptu Adobe Acrobat, jako je tisk, upozornění a manipulace s formuláři.

### Funguje JavaScript ve všech prohlížečích PDF?
Většina akcí JavaScriptu bude fungovat v prohlížečích PDF, které podporují interaktivní soubory PDF, jako je Adobe Acrobat. Některé základní čtečky PDF však nemusí podporovat JavaScript.

### Mohu spustit akce JavaScriptu na základě uživatelského vstupu v PDF?
Ano, JavaScript můžete svázat s poli formuláře a spouštět akce na základě vstupu uživatele.