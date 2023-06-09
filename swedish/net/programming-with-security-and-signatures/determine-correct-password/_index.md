---
title: Bestäm rätt lösenord
linktitle: Bestäm rätt lösenord
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du bestämmer rätt lösenord för en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-security-and-signatures/determine-correct-password/
---

den här handledningen går vi igenom processen för att bestämma rätt lösenord för en PDF-fil med Aspose.PDF för .NET. Denna funktion låter dig kontrollera om en PDF-fil är lösenordsskyddad och hitta rätt lösenord från en fördefinierad lista.

## Steg 1: Förutsättningar

Innan du börjar, se till att du har följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#
- Installera Visual Studio på din dator
- Aspose.PDF-bibliotek för .NET installerat

## Steg 2: Miljöinställning

För att komma igång, följ dessa steg för att konfigurera din utvecklingsmiljö:

1. Öppna Visual Studio och skapa ett nytt C#-projekt.
2. Importera de nödvändiga namnrymden till din kodfil:

```csharp
using Aspose.Pdf;
```

## Steg 3: Laddar käll-PDF-fil

Det första steget är att ladda upp käll-PDF-filen som du vill verifiera. I det här exemplet antar vi att du har en PDF-fil med namnet "IsPasswordProtected.pdf" i den angivna katalogen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Se till att ersätta platshållarna med de faktiska platserna för din PDF-fil.

## Steg 4: Bestäm källkod för PDF-kryptering

 När du har laddat upp käll-PDF-filen kan du avgöra om den är krypterad med hjälp av`IsEncrypted` metod för`PdfFileInfo` objekt.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Detta uttalande visar om PDF-filen är lösenordsskyddad eller inte.

## Steg 5: Hitta rätt lösenord

Därefter kommer vi att söka efter rätt lösenord med hjälp av en fördefinierad lista med lösenord. Vi går igenom varje lösenord i listan och försöker ladda PDF-dokumentet med det lösenordet.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Denna loop testar varje godkänt ord från listan. Om lösenordet är korrekt visas antalet sidor i dokumentet. Annars visas ett meddelande som indikerar att lösenordet inte är korrekt.


### Exempel på källkod för Bestäm rätt lösenord med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Ladda käll-PDF-fil
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Bestäm om käll-PDF-filen är krypterad
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt bestämt det korrekta lösenordet för en PDF-fil med Aspose.PDF för .NET. Den här handledningen täckte steg-för-steg-processen, från att verifiera filkryptering till att hitta rätt lösenord från en fördefinierad lista. Nu kan du använda den här funktionen för att kontrollera och hitta rätt lösenord för dina PDF-filer.