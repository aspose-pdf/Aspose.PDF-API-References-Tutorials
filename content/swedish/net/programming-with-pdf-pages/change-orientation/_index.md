---
title: Ändra orientering
linktitle: Ändra orientering
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ändra sidorientering för en PDF med Aspose.PDF för .NET. Lätt att följa och implementera i dina projekt.
type: docs
weight: 10
url: /sv/net/programming-with-pdf-pages/change-orientation/
---
## Introduktion

Har du någonsin funnit dig själv kämpande med en PDF-fil där sidorienteringen bara är... av? Kanske har du att göra med ett dokument som har skannats eller skapats på ett felaktigt sätt, och sidorna måste roteras för att det ska vara meningsfullt. Som tur är för oss erbjuder Aspose.PDF för .NET ett enkelt och kraftfullt sätt att manipulera PDF-filer på nästan alla tänkbara sätt – inklusive att ändra orienteringen på dina sidor. Oavsett om du vill byta från stående till liggande eller vice versa, kommer den här guiden att gå igenom processen steg för steg.

Så, om du är redo att dyka in och rotera dessa PDF-sidor med lätthet, låt oss komma igång!

## Förutsättningar

Innan vi går in på detaljerna för att ändra sidorientering i din PDF, låt oss snabbt ta upp vad du behöver ha på plats:

-  Aspose.PDF för .NET: Se till att du har installerat Aspose.PDF-biblioteket för .NET. Om du inte har det kan du[ladda ner den här](https://releases.aspose.com/pdf/net/).
- En .NET-utvecklingsmiljö: Du kan använda Visual Studio, JetBrains Rider eller någon föredragen IDE för att arbeta med .NET.
- Grundläggande kunskaper om C#: Även om den här guiden är enkel, kommer en viss grundläggande förståelse av C# att göra det ännu lättare att följa.
- En PDF-fil: Exemplet nedan förutsätter att du har en PDF-fil med flera sidor. Om du inte har en till hands, skapa eller ladda ner en exempel-PDF att arbeta med.

 Dessutom, om du precis har börjat kan du prova Aspose.PDF med en[gratis tillfällig licens](https://purchase.aspose.com/temporary-license/) innan du bestämmer dig för det[köp den fullständiga versionen](https://purchase.aspose.com/buy).

## Importera namnområden

Innan du kan manipulera orienteringen på sidorna i din PDF måste du importera de nödvändiga namnrymden i ditt C#-projekt. Se till att du har följande:

```csharp
using System.IO;
using Aspose.Pdf;
```

Med detta importerat, låt oss hoppa in i huvuddelen av handledningen.

## Steg 1: Ladda PDF-dokumentet

 Det första vi behöver göra är att ladda PDF-filen du vill ändra. Du kan använda`Document` klass från Aspose.PDF-namnområdet för att öppna din PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Den här raden laddar PDF-filen från din angivna katalog. Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din fil. De`"input.pdf"` är PDF-filen du vill ändra orienteringen på.

## Steg 2: Gå igenom varje sida

 Nu när vi har laddat dokumentet, låt oss gå igenom varje sida i PDF:en. Vi använder en`foreach` loop för att gå igenom varje sida, vilket gör att vi kan tillämpa orienteringsändringen på dem alla.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipulera varje sida
}
```

Denna loop kommer att iterera genom alla sidor i dokumentet.

## Steg 3: Skaffa sidans MediaBox

 Varje sida i en PDF har en`MediaBox` som definierar sidans gränser. Vi måste komma åt detta för att bestämma den aktuella orienteringen och ändra den.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 De`MediaBox` ger oss sidans mått, till exempel dess bredd, höjd och placering.

## Steg 4: Byt bredd och höjd

För att ändra sidorienteringen från stående till liggande eller liggande till stående byter vi helt enkelt bredd- och höjdvärdena. Detta steg kommer att justera sidans dimensioner.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Den här koden byter höjd och bredd och placerar om det nedre vänstra hörnet (`LLY`) så att innehållet passar snyggt efter rotation.

## Steg 5: Uppdatera MediaBox och CropBox

Nu när vi har den nya höjden och bredden, låt oss tillämpa ändringarna på sidans`MediaBox` och`CropBox` . De`CropBox` är viktigt om originaldokumentet hade en uppsättning, vilket säkerställer att hela sidan visas korrekt.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Det här steget ändrar storleken på sidan baserat på de nya dimensionerna vi just beräknat.

## Steg 6: Rotera sidan

Slutligen ställer vi in sidans rotationsvinkel. Aspose.PDF gör detta superenkelt. Vi kan rotera sidan 90 grader för att växla från stående till liggande eller tvärtom.

```csharp
page.Rotate = Rotation.on90;
```

Denna kod roterar sidan 90 grader och vänder den till önskad orientering.

## Steg 7: Spara PDF-filen

Efter att ha tillämpat orienteringsändringarna på alla sidor sparar vi det ändrade dokumentet i en ny fil. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Se till att du anger ett nytt filnamn (i det här fallet,`ChangeOrientation_out.pdf`) för att spara utdata. På så sätt skriver du inte över din ursprungliga fil.

### Slutsats

Och där har du det! Att ändra sidriktningen för en PDF-fil med Aspose.PDF för .NET är så enkelt som att ladda dokumentet, gå igenom sidorna, justera MediaBox och spara den uppdaterade filen. Oavsett om du har att göra med ett dåligt skannat dokument eller behöver rotera sidor för att matcha dina formateringsbehov, bör den här steg-för-steg-guiden ha dig täckt.

## FAQ's

### Kan jag rotera specifika sidor istället för alla sidor i PDF-filen?  
Ja, du kan ändra loopen så att den riktar in sig på specifika sidor med hjälp av deras index istället för att gå igenom alla sidor.

###  Vad är`MediaBox`?  
 De`MediaBox` definierar storleken och formen på sidan i en PDF-fil. Det är där sidans innehåll placeras.

### Fungerar Aspose.PDF för .NET med andra filformat?  
Ja, Aspose.PDF kan hantera en mängd olika filformat som HTML, XML, XPS och mer.

### Finns det en gratisversion av Aspose.PDF för .NET?  
 Ja, du kan komma igång med en[gratis provperiod](https://releases.aspose.com/) eller begära en[tillfällig licens](https://purchase.aspose.com/temporary-license/).

### Kan jag ångra ändringarna när de har sparats?  
När du har sparat dokumentet är ändringarna permanenta. Se till att arbeta på en kopia eller behåll en säkerhetskopia av originalfilen.