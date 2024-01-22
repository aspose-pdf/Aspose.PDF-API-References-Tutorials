---
title: Lägg till Ta bort Javascript till PDF-dokument
linktitle: Lägg till Ta bort Javascript till Doc
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till och tar bort JavaScript till PDF-dokument med Aspose.PDF för .NET. Steg-för-steg-guide med kodhandledning för skript på dokumentnivå.
type: docs
weight: 30
url: /sv/net/programming-with-document/addremovejavascripttodoc/
---
För att lägga till och ta bort JavaScript till PDF-dokument kommer vi att använda Aspose.PDF för .NET-biblioteket. Detta kraftfulla bibliotek låter oss manipulera PDF-filer i .NET-applikationer. Följ steg-för-steg-instruktionerna nedan för att lägga till och ta bort JavaScript med Aspose.PDF för .NET.

## Steg 1: Skapa ett nytt PDF-dokument

 Börja med att skapa en ny instans av`Document` klass tillhandahållen av Aspose.PDF för .NET. Detta kommer att fungera som PDF-dokumentet där vi lägger till JavaScript.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Steg 2: Lägg till JavaScript på dokumentnivå

 För att lägga till JavaScript på dokumentnivå, använd`JavaScript` egendom av`Document` klass. Tilldela JavaScript-funktioner till nycklar i JavaScript-ordboken.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 I den här handledningen har vi lagt till två JavaScript-funktioner,`func1` och`func2`, till PDF-dokumentet.

## Steg 3: Ta bort JavaScript på dokumentnivå

 För att ta bort JavaScript på dokumentnivå, ladda PDF-dokumentet och öppna`JavaScript`lexikon. Iterera över tangenterna och ta bort den önskade JavaScript-funktionen.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 I den här handledningen tar vi bort`func1` JavaScript-funktion från PDF-dokumentet.

## Steg 4: Spara och verifiera ändringar

Spara det ändrade PDF-dokumentet och verifiera ändringarna.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Denna kod sparar det ändrade PDF-dokumentet och visar framgångsmeddelandet.

### Exempel på källkod för Lägg till Ta bort Javascript från PDF-dokument med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Ta bort JavaScript på dokumentnivå
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Slutsats

I den här artikeln har vi tillhandahållit en steg-för-steg-guide för att lägga till och ta bort JavaScript från PDF-dokument med Aspose.PDF för .NET. Genom att följa instruktionerna och använda de medföljande kodhandledningarna kan du enkelt infoga JavaScript i dina PDF-dokument och ta bort det när det behövs. JavaScript möjliggör dynamisk funktionalitet och interaktivitet i dina PDF-filer, vilket förbättrar användarupplevelsen.


### Vanliga frågor för att lägga till ta bort javascript till PDF-dokument

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett kraftfullt bibliotek som tillåter utvecklare att effektivt manipulera PDF-filer i .NET-applikationer. Den tillhandahåller omfattande funktioner för att arbeta med PDF-dokument programmatiskt.

#### F: Hur kan jag lägga till JavaScript i ett PDF-dokument med Aspose.PDF för .NET?

 S: Du kan lägga till JavaScript på dokumentnivå med hjälp av`JavaScript` egendom av`Document` klass. Tilldela helt enkelt JavaScript-funktioner till nycklar i JavaScript-ordboken.

#### F: Kan jag ta bort JavaScript från ett PDF-dokument med Aspose.PDF för .NET?

 S: Ja, du kan ta bort JavaScript från ett PDF-dokument genom att öppna`JavaScript` ordbok och ta bort den önskade JavaScript-funktionen.

#### F: Är Aspose.PDF för .NET lämplig för professionella projekt?

S: Absolut, Aspose.PDF för .NET används i stor utsträckning i professionella projekt för PDF-manipulering och genereringsuppgifter. Den erbjuder hög prestanda och pålitlig funktionalitet.

#### F: Vilka fördelar ger det att lägga till JavaScript i ett PDF-dokument?

S: Genom att lägga till JavaScript i ett PDF-dokument kan du skapa interaktiva och dynamiska PDF-filer. Du kan implementera formulärvalidering, utföra beräkningar och lägga till olika interaktivitetsfunktioner för att förbättra användarupplevelsen.