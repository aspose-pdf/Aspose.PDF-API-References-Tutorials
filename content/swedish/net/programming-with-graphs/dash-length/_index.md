---
title: Strecklängd
linktitle: Strecklängd
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du anpassar streckmönster i PDF-filer med Aspose.PDF för .NET med vår steg-för-steg-guide. Perfekt för att lägga till stil till dina dokument.
type: docs
weight: 70
url: /sv/net/programming-with-graphs/dash-length/
---
## Introduktion

Vill du lägga till en touch av kreativitet till dina PDF-dokument genom att anpassa linjer med olika streckmönster? Med Aspose.PDF för .NET kan du enkelt ändra linjestilar för att passa ditt dokuments behov. I den här handledningen kommer vi att undersöka hur du justerar strecklängden på rader i ett PDF-dokument med Aspose.PDF för .NET. Oavsett om du siktar på en streckad linje eller ett prickigt mönster, kommer den här guiden att ge dig de verktyg och steg som krävs för att uppnå ditt önskade resultat.

## Förutsättningar

Innan du dyker in i handledningen finns det några saker du behöver:

1. Aspose.PDF för .NET: Se till att du har Aspose.PDF för .NET installerat. Om du inte har installerat det ännu kan du ladda ner det från[Aspose.PDF för .NET](https://releases.aspose.com/pdf/net/).
2. Grundläggande kunskaper om C#: Denna handledning förutsätter att du har en grundläggande förståelse för C#-programmering. Om du är ny på C# kanske du vill fräscha upp grunderna först.
3. Visual Studio: Även om du kan använda vilken IDE som helst, förutsätter den här guiden att du använder Visual Studio för att skriva och köra din C#-kod.
4.  Aspose-konto: För ytterligare resurser och support, se till att du har ett konto hos Aspose. Du kan anmäla dig till en[gratis provperiod](https://releases.aspose.com/) eller köp en licens[här](https://purchase.aspose.com/buy).

## Importera paket

För att börja arbeta med Aspose.PDF för .NET måste du importera de relevanta namnområdena. Så här kan du göra det:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dessa namnområden inkluderar de klasser och metoder som behövs för att arbeta med PDF-dokument, ritningar och linjer.

## Steg 1: Konfigurera ditt projekt

Innan du börjar koda, ställ in ett nytt C#-projekt i Visual Studio. Lägg till Aspose.PDF för .NET-biblioteket till ditt projekt via NuGet eller genom att referera till DLL manuellt. 

## Steg 2: Initiera dokumentet

Börja med att skapa ett nytt PDF-dokument och lägga till en sida till det. Det här är duken som du ska rita dina linjer på.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentinstans
Document doc = new Document();

// Lägg till sida till sidsamling av dokumentobjekt
Page page = doc.Pages.Add();
```

 Här skapar vi en`Document` objekt och lägg till ett nytt`Page` till det. Detta lägger grunden för att rita din linje.

## Steg 3: Skapa ritobjektet

 Skapa sedan en`Graph` objekt som representerar området där du ska rita. Definiera dess dimensioner enligt dina krav.

```csharp
// Skapa ritobjekt med vissa dimensioner
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Lägg till ritobjekt till styckesamling av sidinstanser
page.Paragraphs.Add(canvas);
```

 De`Graph` objektet fungerar som en behållare för dina ritelement. Här är den inställd på en bredd på 100 enheter och en höjd på 400 enheter.

## Steg 4: Definiera linjen

 Nu är det dags att skapa`Line`objekt. Ange start- och slutpunkterna för linjen och anpassa dess stil.

```csharp
// Skapa linjeobjekt
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Denna linje börjar vid koordinater (100, 100) och slutar vid (200, 100). Du kan justera dessa koordinater för att passa dina specifika behov.

## Steg 5: Anpassa linjestilen

Ställ in färg och streckmönster för linjen. Det är här du kan få din linje att sticka ut.

```csharp
// Ställ in färg för linjeobjekt
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Ange streckmatris för linjeobjekt
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Ställ in streckfasen för linjeinstans
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Ställer in färgen på linjen. I det här fallet är det rött.
- `line.GraphInfo.DashArray` : Definierar streckmönstret. Här,`{ 0, 1, 0 }` representerar ett streckat mönster.
- `line.GraphInfo.DashPhase`: Justerar startpunkten för streckmönstret.

## Steg 6: Lägg till linjen i ritningen

 Med din linje stil, lägg till den i`Graph` objekt.

```csharp
// Lägg till linje i formsamlingen av ritobjekt
canvas.Shapes.Add(line);
```

Detta integrerar linjen i din ritduk.

## Steg 7: Spara dokumentet

Slutligen, spara ditt dokument på en angiven sökväg. Det är här PDF-filen kommer att skapas.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// Spara PDF-dokument
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Denna kodrad sparar PDF-dokumentet och ger ett bekräftelsemeddelande som anger var filen har sparats.

## Slutsats

Att anpassa linjestilar i PDF-dokument kan ge dina rapporter, presentationer och andra dokument en professionell touch. Genom att följa denna handledning har du lärt dig hur du justerar strecklängden på linjer med Aspose.PDF för .NET. Oavsett om du skapar enkla streckade linjer eller mer komplexa mönster, ger Aspose.PDF den flexibilitet du behöver för att få dina dokument att sticka ut. Experimentera med olika streckmönster och färger för att hitta den stil som bäst passar dina behov.

## FAQ's

### Hur installerar jag Aspose.PDF för .NET?
 Du kan installera den via NuGet i Visual Studio eller ladda ner den från[Asposes hemsida](https://releases.aspose.com/pdf/net/).

### Kan jag använda Aspose.PDF för .NET gratis?
 Ja, Aspose erbjuder en[gratis provperiod](https://releases.aspose.com/) så att du kan testa dess funktioner innan du köper en licens.

### Vilka andra anpassningar kan jag göra för linjer i en PDF?
 Du kan justera linjetjocklek, färg och streckmönster. Se till[dokumentation](https://reference.aspose.com/pdf/net/) för mer information.

### Hur kan jag få support om jag stöter på problem?
 Du får tillgång till support via[Aspose Forum](https://forum.aspose.com/c/pdf/10).

### Var kan jag köpa en licens för Aspose.PDF för .NET?
Du kan köpa en licens[här](https://purchase.aspose.com/buy).