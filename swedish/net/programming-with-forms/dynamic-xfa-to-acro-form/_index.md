---
title: Dynamisk XFA till Acro Form
linktitle: Dynamisk XFA till Acro Form
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt dynamiska XFA To-formulär till vanliga AcroForm-formulär med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

I den här handledningen kommer vi att visa dig hur du konverterar en XFA till dynamisk form till en AcroForm med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda det dynamiska XFA-formuläret

Ladda det dynamiska XFA-formuläret:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Steg 3: Ställ in Form Type som Standard AcroForm

Ställ in formulärtypen som standard AcroForm:

```csharp
document.Form.Type = FormType.Standard;
```

## Steg 4: Spara den resulterande PDF-filen

Spara den resulterande PDF:en:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Exempel på källkod för Dynamic XFA To Acro Form med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda dynamiskt XFA-formulär
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Ställ in formulärfältstypen som standard AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Spara den resulterande PDF-filen
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen lärde vi oss hur man konverterar en XFA till dynamisk form till en standard AcroForm-form med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt konvertera dina dynamiska XFATo-formulär till AcroForms för mer vanlig användning.