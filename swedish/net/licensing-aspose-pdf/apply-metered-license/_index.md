---
title: Konfigurera Metered License
linktitle: Konfigurera Metered License
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in en uppmätt licens med Aspose.PDF för .NET och dra nytta av avancerade funktioner.
type: docs
weight: 10
url: /sv/net/licensing-aspose-pdf/configure-metered-license/
---

I den här handledningen går vi igenom steg-för-steg hur du ställer in en uppmätt licens med Aspose.PDF för .NET. Den uppmätta licensen låter dig använda de avancerade funktionerna i Aspose.PDF baserat på din faktiska förbrukning.

### Steg 1: Konfigurera licensnycklar

I källkoden som tillhandahålls måste du ange de offentliga och privata nycklarna för den uppmätta licensen. Ersätt "*****" värden med dina egna nycklar. Dessa nycklar kommer att ges till dig när du köper en mätlicens från Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Steg 2: Ladda dokumentet

 Ladda PDF-dokumentet från disken med hjälp av`Document`klass av Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Steg 3: Få dokumentsidräkning

 Använd`Count` egendom av`Pages` samling för att få det totala antalet sidor i dokumentet.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Exempel på källkod för Configure Metered License med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ställ in mätta offentliga och privata nycklar
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Gå till egenskapen setMeteredKey och skicka offentliga och privata nycklar som parametrar
metered.SetMeteredKey("*****", "*****");
// Ladda dokumentet från disken.
Document doc = new Document(dataDir + "input.pdf");
//Hämta antalet sidor i dokumentet
Console.WriteLine(doc.Pages.Count);

```

## Slutsats

I den här handledningen förklarade vi hur man ställer in en mätlicens med Aspose.PDF för .NET. Genom att använda en mätlicens kan du dra nytta av de avancerade funktionerna i Aspose.PDF baserat på din faktiska användning. Se till att tillhandahålla giltiga licensnycklar för att använda Aspose.PDF med alla dess funktioner.
