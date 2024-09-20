---
title: Lägg till och sök dold text i PDF-fil
linktitle: Lägg till och sök dold text i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig att lägga till och söka efter dold text i PDF-dokument med Aspose.PDF för .NET. Steg-för-steg-guide med kodexempel ingår.
type: docs
weight: 20
url: /sv/net/programming-with-text/add-and-search-hidden-text/
---
## Introduktion

I den här handledningen tar vi dig genom en steg-för-steg-guide om hur du lägger till och söker efter dold text i en PDF-fil med Aspose.PDF för .NET. Oavsett om du är en erfaren utvecklare eller en nybörjare som vill förbättra dina programmeringsfärdigheter, kommer den här artikeln att ge dig de insikter du behöver för att integrera dold textfunktionalitet i dina applikationer.

## Förutsättningar

Innan du dyker in i kodningsdelen finns det några förutsättningar du måste ta hand om:

### Kravchecklista
- Visual Studio: Se till att du har Visual Studio installerat. Denna handledning förutsätter att du använder .NET Framework.
-  Aspose.PDF för .NET: Du måste ha Aspose.PDF för .NET-biblioteket. Du kan ladda ner den[här](https://releases.aspose.com/pdf/net/).
- Grundläggande kunskaper i C#: Bekantskap med C#-programmering hjälper dig att förstå kodavsnitten bättre.

## Importera paket

Innan du kan komma igång med din kod måste du se till att du importerar de nödvändiga Aspose.PDF-namnrymden. Så här gör du:

### Konfigurera ditt projekt
1. Öppna Visual Studio och skapa ett nytt C#-projekt eller använd ett befintligt.
2.  Installera Aspose.PDF genom att lägga till NuGet-paketet. Du kan göra detta genom att navigera till NuGet Package Manager och söka efter`Aspose.PDF`. 
3.  Alternativt kan du ladda ner biblioteket direkt från[här](https://releases.aspose.com/pdf/net/) och lägg till det som referens i ditt projekt.

### Importera nödvändiga namnområden
Överst i din C#-fil importerar du följande namnområden:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Detta steg är avgörande eftersom dessa namnutrymmen innehåller de klasser och metoder som krävs för att manipulera PDF-dokument.

## Skapa ett PDF-dokument med dold text

Nu när du är klar, låt oss gå igenom stegen för att skapa ett PDF-dokument som innehåller både synlig och osynlig text.

### Steg 1: Definiera dokumentkatalog
Först vill du ställa in sökvägen där PDF:en ska sparas. Det är här magin börjar!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ändra detta till din katalog
```

 Den här raden definierar var din genererade PDF kommer att lagras. Glöm inte att byta ut`YOUR DOCUMENT DIRECTORY` med din faktiska väg.

### Steg 2: Skapa ett PDF-dokument
Låt oss sedan skapa ett nytt PDF-dokument och lägga till sidor i det.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Här initierar vi ett nytt dokument och lägger till en sida där vi ska placera våra textfragment.

### Steg 3: Lägg till synlig och dold text
Nu kommer vi att lägga till både synlig och osynlig text i vår PDF.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 I detta utdrag,`frag1` kommer att synas, medan`frag2` kommer att ställas in på osynlig härnäst.

### Steg 4: Ställ in texten på osynlig
 Att göra texten av`frag2` osynlig, du ändrar helt enkelt den`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Genom att ställa in den här egenskapen kan all text associerad med`frag2` kommer inte att renderas när PDF-filen visas.

### Steg 5: Lägg till textfragment på sidan
Slutligen lägger vi till dessa textfragment på sidan och sparar PDF:en.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Den här delen av koden lägger till våra textfragment på sidan. Därefter sparar vi och kasserar dokumentet på rätt sätt.

## Söker efter dold text i PDF-filen

Nu när vi har skapat vår PDF med både synlig och dold text, hur söker vi efter den dolda texten? Låt oss bryta ner det.

### Steg 1: Ladda PDF-dokumentet
För att söka efter text i PDF:en måste vi först ladda dokumentet vi just skapade.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Steg 2: Skapa en Text Fragment Absorber
 Vi kommer att använda`TextFragmentAbsorber` för att fånga alla textfragment i PDF-filen.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Här anger vi att vi vill ta till oss alla textfragment från första sidan.

### Steg 3: Iterera genom fragmenten
Nu kan vi iterera genom de insamlade textfragmenten för att ta reda på vilka som är synliga och vilka som är dolda.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Denna loop kontrollerar varje textfragment och skriver ut dess innehåll tillsammans med dess position och synlighetsstatus. Om`fragment.TextState.Invisible` är satt till sant betyder det att texten är dold!

### Steg 4: Kassera dokument
Slutligen, kom ihåg att kassera dokumentet igen när du är klar.

```csharp
doc.Dispose();
```

## Slutsats

I den här handledningen gick vi igenom den spännande processen att lägga till och söka efter dold text i PDF-filer med Aspose.PDF för .NET. Vi lärde oss hur man skapar ett PDF-dokument med både synlig och dold text, samt hur man söker efter den dolda texten programmatiskt. Denna förmåga kan vara otroligt användbar i olika applikationer, oavsett om du behöver lagra konfidentiell information eller ge en unik användarupplevelse i dina dokument.

När du blir mer bekant med ASPose.PDF blir möjligheterna oändliga. Fortsätt experimentera och tänja på gränserna för vad du kan uppnå med dina PDF-dokument!

## FAQ's

### Kan Aspose.PDF hantera krypterade PDF-filer?  
Ja, Aspose.PDF stöder kryptering och dekryptering av PDF-dokument. Du kan enkelt säkra dina PDF-filer med lösenord.

### Finns det en testversion tillgänglig för Aspose.PDF?  
 Absolut! Du kan ladda ner den kostnadsfria testversionen från[här](https://releases.aspose.com/).

### Vilka programmeringsspråk stöder Aspose.PDF?  
Aspose.PDF ger stöd för flera språk, inklusive C#, Java och Python.

### Var kan jag hitta dokumentationen för Aspose.PDF?  
 Du kan komma åt dokumentationen[här](https://reference.aspose.com/pdf/net/).

### Hur kan jag få support om jag stöter på problem?  
 För support kan du besöka Aspose-forumen[här](https://forum.aspose.com/c/pdf/10).