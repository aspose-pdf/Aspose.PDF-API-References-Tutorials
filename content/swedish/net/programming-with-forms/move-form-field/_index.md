---
title: Flytta formulärfält
linktitle: Flytta formulärfält
second_title: Aspose.PDF för .NET API-referens
description: Flytta enkelt runt formulärfält i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 200
url: /sv/net/programming-with-forms/move-form-field/
---
I den här handledningen kommer vi att visa dig hur du flyttar ett formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Ladda det befintliga PDF-dokumentet:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Steg 3: Hämta formulärfältet

Hämta formulärfältet du vill flytta:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Steg 4: Ändra fältets plats

Ändra platsen för formulärfältet genom att definiera ett nytt rektangulärt område:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Steg 5: Spara det redigerade dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Move Form Field med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Skaffa ett fält
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Ändra fältets plats
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Spara ändrat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man flyttar ett formulärfält i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt navigera till ett specifikt fält och ändra dess plats efter behov.


### FAQ's

#### F: Kan jag flytta flera formulärfält inom ett enda PDF-dokument med Aspose.PDF för .NET?

S: Ja, du kan flytta flera formulärfält inom ett enda PDF-dokument med Aspose.PDF för .NET. Upprepa helt enkelt processen för varje formulärfält du vill flytta.

#### F: Kommer att flytta ett formulärfält att påverka dess associerade data eller funktionalitet?

S: Nej, att flytta ett formulärfält påverkar inte dess associerade data eller funktionalitet. Formulärfältet behåller alla sina egenskaper och värden efter att ha flyttats till en ny plats.

#### F: Hur kan jag bestämma de exakta koordinaterna för den nya platsen för formulärfältet?

 S: Du kan ange den nya platsen med hjälp av`Aspose.Pdf.Rectangle` klass, där du definierar X- och Y-koordinaterna för det övre vänstra hörnet och X- och Y-koordinaterna för det nedre högra hörnet av det rektangulära området.

#### F: Är Aspose.PDF för .NET kompatibelt med både Windows- och Linux-miljöer?

S: Ja, Aspose.PDF för .NET är kompatibel med både Windows- och Linux-miljöer, vilket ger flexibilitet för utvecklare att arbeta i sina föredragna operativsystem.