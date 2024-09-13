---
title: Lägg till Java-skript till PDF-fil
linktitle: Lägg till Java Script PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till JavaScript till en PDF-fil med Aspose.PDF för .NET. Steg-för-steg-guide med kodhandledning för dokument- och sidnivåskript.
type: docs
weight: 10
url: /sv/net/programming-with-document/addjavascripttopage/
---
## Introduktion

Har du någonsin undrat hur du kan förbättra dina PDF-filer med interaktiva element som popup-varningar eller automatiska utskriftsfunktioner? Tja, goda nyheter - det kan du! Genom att använda Aspose.PDF för .NET kan du sömlöst lägga till JavaScript i dina PDF-dokument. Oavsett om du automatiserar uppgifter eller skapar dynamiska användarupplevelser, ger inbäddning av JavaScript i PDF-filer dina filer en extra nivå av funktionalitet.

## Förutsättningar

Innan vi hoppar in i kodningsdelen finns det några saker du behöver ställa in:

-  Aspose.PDF för .NET: Ladda ner biblioteket från[Aspose släpper](https://releases.aspose.com/pdf/net/) eller skaffa en[gratis provperiod](https://releases.aspose.com/).
- Utvecklingsmiljö: Alla .NET-kompatibla IDE som Visual Studio.
- Grundläggande C#-kunskap: Den här guiden förutsätter att du är bekant med grundläggande C#-syntax.
-  Tillfällig licens (valfritt): Du kan få en[tillfällig licens](https://purchase.aspose.com/temporary-license/) om du vill undvika begränsningar under din utveckling.

## Importera paket

Innan du börjar skriva kod måste du importera de nödvändiga namnrymden från Aspose.PDF-biblioteket. Dessa namnutrymmen låter dig manipulera PDF-filer och enkelt lägga till JavaScript-åtgärder.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Nu när du har importerat rätt namnrymder är du redo att börja koda.

## Steg 1: Ladda en befintlig PDF

Först till kvarn – du måste ladda PDF-dokumentet som du vill lägga till JavaScript. Detta steg sätter scenen för alla ytterligare ändringar. Föreställ dig att du har en PDF som du vill förbättra med dynamisk funktionalitet, som att skriva ut dokumentet automatiskt när det öppnas.

Så här kan du ladda PDF-filen:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda en befintlig PDF-fil
Document doc = new Document(dataDir + "input.pdf");
```

 I det här kodavsnittet använder vi`Document` klass för att ladda en befintlig PDF-fil från den angivna katalogen. Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din PDF-fil.

## Steg 2: Lägg till JavaScript på dokumentnivå

Låt oss nu lägga till lite JavaScript som utlöses när dokumentet öppnas. I det här exemplet kommer vi att skriva ett skript som öppnar utskriftsdialogrutan så snart användaren öppnar PDF-filen.

JavaScript på dokumentnivå är perfekt för åtgärder som du vill tillämpa på hela PDF-filen. Tänk på det som att skapa en global regel för ditt dokument.

Här är koden:

```csharp
// Lägga till JavaScript på dokumentnivå
// Instantiera JavascriptAction med önskad JavaScript-sats
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tilldela JavascriptAction-objektet till OpenAction i dokumentet
doc.OpenAction = javaScript;
```

 I detta steg skapar vi en`JavascriptAction` objekt som definierar en JavaScript-funktion för att öppna utskriftsdialogrutan när dokumentet öppnas. De`doc.OpenAction` egenskapen tilldelas sedan denna JavaScript-åtgärd.

## Steg 3: Lägg till JavaScript på sidnivå

Alla åtgärder behöver inte påverka hela dokumentet. Ibland vill du att specifika åtgärder ska inträffa när vissa sidor öppnas eller stängs. Här kommer vi att ställa in JavaScript-åtgärder för när en viss sida (låt oss säga sida 2) öppnas och stängs.

JavaScript på sidnivå är användbart för riktade interaktioner. Det kan vara allt från att visa ett meddelande när en användare navigerar till en sida, till anpassade åtgärder som att automatiskt fylla i formulärfält.

Så här gör du:

```csharp
// Lägger till JavaScript på sidnivå
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

I det här kodavsnittet lägger vi till två JavaScript-åtgärder:
1. OnOpen Action: Visar en varning som säger "Sida 2 öppnad" när användaren öppnar sida 2.
2. OnClose Action: Visar en varning som säger "Sida 2 stängd" när användaren navigerar bort från sida 2.

Detta lägger till ett lager av interaktivitet till din PDF. Föreställ dig att guida användaren genom en rad steg på olika sidor, med varningar som dyker upp när de går in på eller lämnar en sida.

## Steg 4: Spara PDF-dokumentet

Du har nu lagt till JavaScript i både dokumentet och specifika sidor. Det sista steget är att spara den ändrade PDF-filen på önskad plats. Den här delen är enkel men avgörande – glöm inte att spara ditt arbete!

Här är koden:

```csharp
// Ange sökvägen till utdatafilen
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Spara det uppdaterade PDF-dokumentet
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 I det här utdraget sparar vi det uppdaterade dokumentet med tillagd JavaScript till en ny fil med namnet`"JavaScript-Added_out.pdf"`. Detta säkerställer att du inte skriver över din ursprungliga fil, och det ger dig en säkerhetskopia att arbeta med.

## Slutsats

Att lägga till JavaScript i PDF-filer med Aspose.PDF för .NET är ett kraftfullt sätt att skapa interaktiva, dynamiska PDF-filer. Oavsett om du automatiserar uppgifter som att skriva ut eller skapa anpassade varningar, gör möjligheten att bädda in JavaScript i din PDF dina dokument mer engagerande och funktionella.

## FAQ's

### Kan jag lägga till flera JavaScript-åtgärder på olika sidor i en PDF?
Ja, du kan tilldela olika JavaScript-åtgärder till enskilda sidor eller hela dokumentet.

### Är det möjligt att ta bort JavaScript från en PDF efter att ha lagt till den?
Ja, du kan ta bort eller ändra befintliga JavaScript-åtgärder genom att rensa`Actions` egenskaper för dokumentet eller sidan.

### Vilken typ av JavaScript-funktioner kan jag använda i en PDF?
Du kan använda vilket JavaScript som helst som stöds av Adobe Acrobats JavaScript-motor, till exempel utskrift, varningar och formulärmanipulationer.

### Fungerar JavaScript i alla PDF-läsare?
De flesta JavaScript-åtgärder fungerar i PDF-visningsprogram som stöder interaktiva PDF-filer, som Adobe Acrobat. Vissa grundläggande PDF-läsare kanske inte stöder JavaScript.

### Kan jag utlösa JavaScript-åtgärder baserat på användarinmatning i PDF-filen?
Ja, du kan binda JavaScript till formulärfält för att utlösa åtgärder baserat på användarinmatning.