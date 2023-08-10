---
title: Lägga till olika rubriker i PDF-fil
linktitle: Lägga till olika rubriker i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till olika rubriker till varje sida i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
I den här handledningen tar vi dig steg för steg om hur du lägger till olika rubriker i PDF-filer med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till anpassade rubriker på varje sida i PDF-filen.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna källdokumentet
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa rubrikbuffertar

Nu när du har laddat upp PDF-dokumentet kan du skapa rubrikstämplarna att lägga till. Här är hur:

```csharp
// Skapa tre rubrikbuffertar
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Ovanstående kod skapar tre nya rubrikbuffertar som innehåller den angivna texten.

## Steg 4: Konfigurera rubrikbuffertegenskaper

Innan du lägger till rubrikstämplarna i PDF-dokumentet kan du konfigurera olika egenskaper för varje stämpel, som justering, storlek, färg etc. Så här gör du:

```csharp
// Konfigurera den första rubrikbufferten
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Konfiguration av den andra huvudbufferten
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Konfigurera tredje rubrikbuffert
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Du kan justera dessa egenskaper efter behov för varje rubrikbuffert.

## Steg 5: Lägg till rubrikstämplar till PDF

Nu när rubrikstämplarna är klara kan du lägga till dem på varje specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till rubrikbuffertar på specifika sidor
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Koden ovan lägger till varje rubrikstämpel på motsvarande sida i PDF-dokumentet.

## Steg 6: Spara utdatadokumentet

När du har lagt till rubrikstämplarna kan du spara det redigerade PDF-dokumentet. Här är hur:

```csharp
// Spara det uppdaterade dokumentet
doc.Save(dataDir);
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för att lägga till olika rubriker med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument med öppen källkod
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Skapa tre stämplar
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Ställ in stämpeljustering (placera stämpeln överst på sidan, centrerad horisontellt)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Ange teckensnittsstilen som fetstil
stamp1.TextState.FontStyle = FontStyles.Bold;

// Ställ in textens förgrundsfärginformation som röd
stamp1.TextState.ForegroundColor = Color.Red;

// Ange teckenstorleken som 14
stamp1.TextState.FontSize = 14;

// Nu måste vi ställa in den vertikala justeringen av det andra stämpelobjektet som Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Ställ in information om horisontell justering för stämpeln som Centerjusterad
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Ställ in zoomfaktorn för stämpelobjekt
stamp2.Zoom = 10;

//Ställ in formateringen av det tredje stämpelobjektet
// Ange information om vertikal justering för stämpelobjekt som TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Ställ in information om horisontell justering för stämpelobjekt som Centerjusterad
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Ställ in rotationsvinkeln för stämpelobjektet
stamp3.RotateAngle = 35;

// Ställ in rosa som bakgrundsfärg för stämpeln
stamp3.TextState.BackgroundColor = Color.Pink;

// Ändra teckensnittsinformationen för stämpeln till Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// Första stämpeln läggs till på första sidan;
doc.Pages[1].AddStamp(stamp1);

// Andra stämpeln läggs till på andra sidan;
doc.Pages[2].AddStamp(stamp2);

// Tredje stämpeln läggs till på tredje sidan.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Spara det uppdaterade dokumentet
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till olika rubriker på varje sida i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu tillämpa denna kunskap på dina egna projekt för att anpassa rubriker för dina PDF-dokument.

### Vanliga frågor för att lägga till olika rubriker i PDF-fil

#### F: Vad är syftet med att lägga till olika rubriker i en PDF-fil med Aspose.PDF för .NET?

S: Genom att lägga till olika rubriker till en PDF-fil med Aspose.PDF för .NET kan du anpassa innehållet som visas högst upp på varje sida. Den här funktionen är särskilt användbar för att lägga till titlar, avsnittsnamn, sidnummer och annan information som varierar mellan olika sidor i ett PDF-dokument.

#### F: Kan jag anpassa utseendet på varje rubrik, som justering, teckensnitt, storlek, färg och rotation?

 S: Ja, du kan helt anpassa utseendet på varje rubrikstämpel. Den medföljande C#-källkoden visar hur man ställer in olika egenskaper för`TextStamp` objekt för varje rubrik, inklusive vertikal och horisontell justering, teckensnitt, teckenstorlek, teckensnittsfärg, bakgrundsfärg och rotationsvinkel.

#### F: Är det möjligt att lägga till flera rubrikstämplar på samma sida i ett PDF-dokument?

S: Medan den medföljande handledningen visar hur du lägger till olika rubriker på olika sidor i ett PDF-dokument, kan du anpassa koden för att lägga till flera rubrikstämplar på samma sida. Detta kan vara användbart om du vill visa olika rubriker inom samma avsnitt.

#### F: Hur kan jag säkerställa att rubrikerna inte överlappar huvudinnehållet på PDF-sidorna?

 S: För att förhindra överlappning kan du justera`VerticalAlignment`, `HorizontalAlignment` , och andra egenskaper hos`TextStamp` föremål. Dessa inställningar styr var rubrikerna är placerade på sidan, så att du kan placera dem på ett sätt som inte hindrar huvudinnehållet.

#### F: Kan jag använda den här metoden för att lägga till rubriker i befintliga PDF-dokument med olika antal sidor?

S: Ja, du kan anpassa den medföljande källkoden för att lägga till rubriker i befintliga PDF-dokument med varierande antal sidor. Justera helt enkelt koden för att matcha antalet rubriker du vill lägga till och associera varje rubrik med önskad sida.

#### F: Vad händer om jag vill lägga till rubriker på specifika sidor, inte bara de tre första sidorna?

 S: Handledningen visar hur du lägger till rubriker på de tre första sidorna i illustrativt syfte. För att lägga till rubriker till specifika sidor utöver de tre första, justera koden genom att referera till motsvarande sidindex och skapa`TextStamp` objekt för varje sida.

#### F: Kan jag använda bilder som rubriker istället för text?

 S: Den medföljande handledningen fokuserar på att lägga till textbaserade rubriker. Du kan dock använda en liknande metod för att lägga till bildbaserade rubriker med hjälp av`ImageStamp` föremål istället för`TextStamp` föremål. Detta skulle innebära att skapa och konfigurera`ImageStamp` objekt med önskade egenskaper.

#### F: Hur kan jag tillämpa denna kunskap för att lägga till olika sidfötter på varje sida i ett PDF-dokument?

 S: Samma tillvägagångssätt som visas i den här handledningen kan användas för att lägga till olika sidfötter på varje sida i ett PDF-dokument. Istället för rubriker skulle du skapa och konfigurera`TextStamp` eller`ImageStamp` objekt och lägg till dem längst ned på varje sida med hjälp av`AddStamp` metod.

#### F: Kan jag automatisera processen att lägga till rubriker till flera PDF-dokument i en batch-operation?

S: Ja, du kan automatisera processen att lägga till rubriker till flera PDF-dokument med hjälp av ett skript eller program som itererar genom en lista med dokument och tillämpar rubrikstämplingsprocessen på varje dokument.