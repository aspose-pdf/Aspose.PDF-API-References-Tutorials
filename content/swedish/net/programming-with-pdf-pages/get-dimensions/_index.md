---
title: Hämta PDF-sidans dimensioner
linktitle: Hämta PDF-sidans dimensioner
second_title: Aspose.PDF för .NET API Referens
description: I den här handledningen förklarar vi hur man får PDF-sidadimensioner och utför manipulationer med Aspose.PDF för .NET. Detaljerade steg tillhandahålls för att guida dig genom processen.
type: docs
weight: 60
url: /sv/net/programming-with-pdf-pages/get-dimensions/
---
## Introduktion

Har du någonsin behövt manipulera sidmåtten i ett PDF-dokument? Kanske har du velat ändra storlek på en sida eller rotera den för att passa dina behov? I så fall är du på rätt plats! I den här handledningen går vi igenom hur du hämtar och ändrar PDF-sidedimensioner med Aspose.PDF för .NET. Oavsett om du är nybörjare eller erfaren utvecklare, kommer du att tycka att den här guiden är enkel och lätt att följa.

Aspose.PDF för .NET är ett kraftfullt bibliotek som låter dig skapa, manipulera och transformera PDF-filer utan ansträngning. Det är som att ha en schweizisk armékniv för PDF-filer – du kan justera varje liten detalj för att passa dina exakta krav. Så låt oss dyka in direkt och lära oss hur du hämtar och uppdaterar PDF-sidans dimensioner med detta fantastiska verktyg!

## Förutsättningar

Innan du börjar behöver du några saker på plats för att följa den här handledningen smidigt:

1.  Aspose.PDF för .NET: Du kan[ladda ner den senaste versionen här](https://releases.aspose.com/pdf/net/) . Om du inte har en licens, oroa dig inte! Du kan begära en[gratis provperiod](https://releases.aspose.com/) , eller välj en[tillfällig licens](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: Utvecklingsmiljön du ska använda för att skriva och exekvera koden.
3. Grundläggande kunskap om C#: Även om vi kommer att hålla saker och ting enkla, kommer en viss förtrogenhet med C# att göra processen smidigare.
4. PDF-fil att arbeta med: Ta ett exempel på PDF-fil eller skapa en ny att testa.

## Importera paket

För att arbeta med Aspose.PDF för .NET måste du importera några viktiga namnområden. Detta skapar förutsättningar för interaktion med PDF-dokument. Så här gör du:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dessa importer säkerställer att du har tillgång till de kärnklasser som behövs för att manipulera PDF-filer, särskilt för att hantera sidor och hämta deras dimensioner.

Nu när vi har allt på plats, låt oss dela upp processen i lätta att följa steg.

## Steg 1: Definiera filsökvägen och ladda dokumentet

Det första steget är att ange sökvägen till ditt PDF-dokument och ladda det med Aspose.PDF. Detta gör att du kan interagera med sidorna i PDF-filen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

I det här steget öppnar du i princip PDF-filen du vill arbeta med. Om du någonsin har öppnat en bok på en viss sida är detta ganska likt – men istället öppnar du ett PDF-dokument för att komma åt dess sidor.

## Steg 2: Lägg till en tom sida om det inte finns några sidor

Vad händer om ditt dokument inte har några sidor? Oroa dig inte! Vi kan lägga till en tom sida i dokumentet och arbeta med det. Så här kontrollerar du om en sida finns och lägger till en ny om det behövs:

```csharp
// Lägger till en tom sida till pdf-dokument
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Den här kodraden kontrollerar om det redan finns en sida i dokumentet. Om ja, väljer den första sidan (`Pages[1]`). Annars skapar den en tom sida och lägger till den i PDF:en.

Tänk på det som att öppna en tom anteckningsbok och skriva på första sidan om ingenting finns där – enkelt, eller hur?

## Steg 3: Få information om sidhöjd och bredd

 Nu när vi har en sida att arbeta med, låt oss hämta sidans dimensioner. Vi kommer att använda`GetPageRect()` metod för att få höjd och bredd.

```csharp
// Få information om sidhöjd och bredd
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Här,`GetPageRect(true)` returnerar en rektangel som inkluderar sidans höjd och bredd. Det är som att mäta ett papper med en linjal. Utdata kommer att visas i konsolen och ger dig de aktuella sidmåtten.

## Steg 4: Rotera sidan 90 grader

Vill du rotera sidan? Inga problem! Med en enkel egenskap kan du rotera sidan 90 grader.

```csharp
// Rotera sidan i 90 graders vinkel
page.Rotate = Rotation.on90;
```

Detta steg roterar sidan medurs 90 grader. Föreställ dig att du vänder ett tryckt ark på ditt skrivbord – nu är det i liggande läge!

## Steg 5: Kontrollera siddimensionerna efter rotation igen

Efter att ha roterat sidan är det en bra idé att kontrollera måtten igen. Varför? Eftersom rotation kan påverka hur du tolkar höjden och bredden.

```csharp
// Få information om sidhöjd och bredd
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Nu kommer sidmåtten att uppdateras baserat på den nya orienteringen. Det är som att rotera ett foto på din telefon – plötsligt blir bredden höjden och vice versa.


## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du hämtar och ändrar måtten på en PDF-sida med Aspose.PDF för .NET. Vid det här laget bör du kunna ladda en PDF, kontrollera dess sidmått och till och med rotera sidan om det behövs.

Att manipulera PDF-filer behöver inte vara komplicerat. Med Aspose.PDF är det så enkelt som att följa några steg och använda intuitiva metoder. Så nästa gång du behöver hantera PDF-sidans dimensioner vet du exakt vad du ska göra!

## FAQ's

### Kan jag rotera sidan i andra vinklar än 90 grader?
 Ja, Aspose.PDF låter dig rotera sidor med 0, 90, 180 eller 270 grader med hjälp av`Rotation` egendom.

### Vad händer om min PDF inte har några sidor?
 Om din PDF-fil inte har några sidor kan du lägga till en tom sida med hjälp av`Pages.Add()` metod, som visas i denna handledning.

### Kan jag manipulera flera sidor samtidigt?
Ja, du kan gå igenom flera sidor och tillämpa transformationer, som att ändra storlek eller rotera, på dem alla.

### Påverkar siddimensionerna innehållet i PDF-filen?
Siddimensioner ändrar bara storleken på duken, inte innehållet. Ändrad storlek kan dock ändra hur innehållet visas på sidan.

### Var kan jag hitta mer information om Aspose.PDF för .NET?
 Du kan besöka[dokumentation här](https://reference.aspose.com/pdf/net/) för mer detaljerad information och avancerade användningsfall.