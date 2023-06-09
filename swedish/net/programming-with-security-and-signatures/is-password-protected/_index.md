---
title: Är lösenordsskyddad
linktitle: Är lösenordsskyddad
second_title: Aspose.PDF för .NET API Referens
description: Kontrollera enkelt om ett PDF-dokument är lösenordsskyddat med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-security-and-signatures/is-password-protected/
---

Det är ofta viktigt att veta om ett PDF-dokument är lösenordsskyddat innan det bearbetas. Med Aspose.PDF för .NET kan du enkelt kontrollera om ett PDF-dokument är skyddat med hjälp av följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är de nödvändiga importdirektiven:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill kontrollera. Byta ut`"YOUR DOCUMENTS DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 3: Ladda käll-PDF-dokument

Nu kommer vi att ladda käll-PDF-dokumentet och kontrollera om det är lösenordsskyddat med hjälp av följande kod:

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## Steg 4: Kontrollera om PDF:en är skyddad

 I det här steget kommer vi att avgöra om PDF-dokumentet är lösenordsskyddat med hjälp av`IsEncrypted` metod för`PdfFileInfo` objekt. Här är motsvarande kod:

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## Steg 5: Visa krypteringsstatus

 Slutligen kan vi visa den aktuella krypteringsstatusen för PDF:en med hjälp av`Console.WriteLine` metod. Här är motsvarande kod:

```csharp
Console.WriteLine(encrypted.ToString());
```

Meddelandet som visas visar om PDF-dokumentet är lösenordsskyddat eller inte.

### Exempel på källkod för är lösenordsskyddad med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda käll-PDF-dokumentet
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Bestäm att käll-PDF-filen är krypterad med lösenord
bool encrypted = fileInfo.IsEncrypted;
// MessageBox visar aktuell status relaterad till PDF-kryptering
Console.WriteLine(encrypted.ToString());
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att kontrollera om ett PDF-dokument är lösenordsskyddat med Aspose.PDF för .NET. Du kan integrera den här koden i dina egna projekt för att utföra specifika operationer beroende på PDF:ens skyddsstatus.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerad PDF-dokumentsäkerhet och lösenordshanteringsfunktioner.