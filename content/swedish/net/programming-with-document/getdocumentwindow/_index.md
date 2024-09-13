---
title: Hämta dokumentfönstret
linktitle: Hämta dokumentfönstret
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder GetDocumentWindow-funktionen i Aspose.PDF för .NET för att hämta information om ett PDF-dokuments fönsteregenskaper.
type: docs
weight: 170
url: /sv/net/programming-with-document/getdocumentwindow/
---
# Introduktion

Arbetar du med PDF-filer och vill ha mer kontroll över hur de visas när de öppnas? Oavsett om det är att dölja menyraden eller ändra storlek på fönstret för att passa första sidan, ger Aspose.PDF för .NET dig alla verktyg du behöver för att anpassa hur en PDF-fil beter sig när den öppnas i en visningsprogram. I den här handledningen kommer vi att dela upp hur man hämtar och manipulerar dokumentfönsterinställningar i Aspose.PDF för .NET.


# Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- Aspose.PDF för .NET installerat på din utvecklingsmiljö.
  - [Ladda ner Aspose.PDF för .NET](https://releases.aspose.com/pdf/net/)
-  En giltig licens för Aspose.PDF, eller så kan du få en[gratis provperiod](https://releases.aspose.com/) eller[tillfällig licens](https://purchase.aspose.com/temporary-license/).
- Grundläggande förståelse för .NET och C#.
- Visual Studio eller annan lämplig IDE.

# Importera paket

Innan du börjar skriva någon kod måste du importera de nödvändiga paketen. Öppna ditt projekt och lägg till följande namnområde högst upp i din C#-fil:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Detta ger dig tillgång till alla klasser och metoder som behövs för att manipulera PDF-dokument med Aspose.PDF för .NET.

 Låt oss nu bryta ner processen för att hämta olika dokumentfönsterinställningar. För det här exemplet använder vi ett exempel på en PDF-fil med namnet`GetDocumentWindow.pdf`.

## Steg 1: Ställ in dokumentkatalogsökvägen

Först och främst måste vi definiera sökvägen till vår PDF-fil. Det är viktigt att du har rätt sökväg för att undvika eventuella fel under körningen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Här, byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska katalogen där din PDF-fil finns. Detta är din arbetskatalog där du laddar PDF-dokumentet.

## Steg 2: Öppna PDF-dokumentet

Nu när filsökvägen är inställd är nästa steg att öppna PDF-dokumentet med Aspose.PDF. Detta kommer att ladda dokumentet i minnet, så att du kan hämta dess egenskaper.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Med denna enkla kodrad har du framgångsrikt laddat in din PDF-fil i`pdfDocument` objekt, som nu ger dig tillgång till alla dess egenskaper.

## Steg 3: Hämta fönstercentreringsstatus

 Låt oss sedan kontrollera om dokumentfönstret ska centreras när det öppnas. Standardvärdet för detta är`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Om utgången är`true`, kommer dokumentets fönster att öppnas i mitten av skärmen. Annars öppnas den i sin standardposition.

## Steg 4: Kontrollera textriktningen

En annan avgörande aspekt av en PDFs utseende är textriktningen, som avgör om texten läses från vänster till höger (L2R) eller höger till vänster (R2L). Du kan hämta denna information med följande kod:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Utgången blir`L2R` för text från vänster till höger och`R2L` för text från höger till vänster. Den här inställningen är särskilt användbar för dokument på språk som arabiska eller hebreiska.

## Steg 5: Visa dokumentrubrik i fönstret

Nästa egenskap låter dig styra om dokumenttiteln eller filnamnet ska visas i fönstrets namnlist. Som standard är detta inställt på`false`, vilket betyder att filnamnet kommer att visas.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Om du vill att dokumentets titel ska visas istället för filnamnet måste denna inställning vara aktiverad.

## Steg 6: Ändra storlek på fönstret för att passa den första sidan

Ibland kanske du vill att dokumentfönstret automatiskt ska ändra storlek på sig självt så att det passar den första sidan i PDF-filen när det öppnas. Så här kontrollerar du om den funktionen är aktiverad:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Som standard är detta inställt på`false`, vilket innebär att fönsterstorleken förblir som den är oavsett storleken på den första sidan.

## Steg 7: Göm menyraden

För en mer fokuserad läsupplevelse kanske du vill dölja menyraden i visningsprogrammet. Du kan hämta den här inställningen genom att använda följande rad:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Detta kommer tillbaka`true` om menyraden är dold, och`false` annat.

## Steg 8: Göm verktygsfältet

På samma sätt kanske du också vill dölja verktygsfältet i PDF-visningen för ett renare användargränssnitt. Denna inställning kan hämtas enligt följande:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Om den här inställningen är aktiverad kommer verktygsfältet att döljas när PDF-filen öppnas.

## Steg 9: Dölj rullningslisterna och UI-elementen

Om du bara vill visa sidinnehållet utan några ytterligare UI-element som rullningslister, styr den här inställningen detta beteende:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 När inställd på`true`, kommer PDF-läsaren att dölja rullningslister och andra element i användargränssnittet, och bara dokumentinnehållet lämnas kvar.

## Steg 10: Ställ in sidläge utan helskärm

 Du kan styra hur dokumentet visas när du avslutar helskärmsläget med hjälp av`NonFullScreenPageMode` egendom. Den här inställningen är användbar för att definiera hur användaren ska interagera med dokumentet i icke-helskärmsläge.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Utdata kan ställas in på olika lägen som miniatyrer, konturer eller bilagapanel.

## Steg 11: Definiera sidlayout

Med den här inställningen kan du styra hur dokumentsidorna läggs upp. Du kan till exempel välja en sidvy eller en kontinuerlig kolumnvy:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Detta ger användarna flexibilitet i hur de läser eller ser dokumentinnehållet.

## Steg 12: Ange sidläge

 Slutligen, den`PageMode` egenskapen definierar hur dokumentet ska visas när det öppnas. Alternativen inkluderar att visa miniatyrer, gå in i helskärmsläge eller visa bilagapanelen.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Beroende på dina behov kan du ställa in detta till valfritt läge som passar din PDFs syfte.

## Slutsats

Som du kan se tillhandahåller Aspose.PDF för .NET omfattande verktyg för att manipulera hur dina PDF-dokument visas i olika PDF-visningsprogram. Oavsett om du vill dölja verktygsfältet, centrera fönstret eller styra textriktningen, erbjuder Aspose.PDF flexibiliteten att förbättra användarens visningsupplevelse.

# Vanliga frågor

### Kan jag anpassa den initiala zoomnivån för PDF:en?
Ja, Aspose.PDF låter dig ställa in zoomnivån när dokumentet öppnas.

### Hur kan jag låsa fönsterstorleken på en PDF?
 Du kan ställa in`FitWindow` egenskap för att förhindra att fönstret ändrar storlek.

### Stöder Aspose.PDF olika läslägen?
Ja, det stöder olika lägen som helskärm, miniatyrer och bilagor.

### Är det möjligt att dölja rullningslister i PDF-visningen?
 Absolut, du kan dölja rullningslister genom att ställa in`HideWindowUI` egendom till`true`.

### Kan jag centrera dokumentfönstret när det öppnas?
 Ja, du kan styra detta genom att ställa in`CenterWindow` egendom.