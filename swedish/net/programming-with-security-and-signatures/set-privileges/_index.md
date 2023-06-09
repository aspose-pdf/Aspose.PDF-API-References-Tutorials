---
title: Ställ in privilegier
linktitle: Ställ in privilegier
second_title: Aspose.PDF för .NET API Referens
description: Ställ enkelt in åtkomstprivilegier för dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-security-and-signatures/set-privileges/
---

Det är ofta nödvändigt att ställa in specifika åtkomstprivilegier för PDF-filer. Med Aspose.PDF för .NET kan du enkelt ställa in åtkomstprivilegier med följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är de nödvändiga importdirektiven:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill redigera. Byta ut`"YOUR DOCUMENTS DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 3: Ladda käll-PDF-fil

Nu kommer vi att ladda käll-PDF-filen med följande kod:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Steg 4: Ställ in åtkomsträttigheter

 I det här steget kommer vi att instansiera`DocumentPrivilege` objekt för att ställa in önskade åtkomstbehörigheter. Du kan tillämpa begränsningar på alla privilegier med`DocumentPrivilege.ForbidAll` . Om du till exempel bara vill tillåta skärmläsning kan du ställa in`AllowScreenReaders` till`true`. Här är motsvarande kod:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Steg 5: Kryptera och spara dokumentet

 Slutligen kan vi kryptera PDF-dokumentet med ett användar- och ägarlösenord med hjälp av`Encrypt` och specificering av den önskade krypteringsalgoritmen. Sedan sparar vi det uppdaterade dokumentet. Här är motsvarande kod:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Exempel på källkod för Set Privileges med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda en käll-PDF-fil
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instantiera dokumenträttigheter-objekt
	// Tillämpa begränsningar för alla privilegier
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Tillåt endast skärmläsning
	documentPrivilege.AllowScreenReaders = true;
	// Kryptera filen med användar- och ägarelösenord.
	// Behöver ställa in lösenordet, så att när användaren tittar på filen med användarlösenordet,
	//Endast alternativet för skärmläsning är aktiverat
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Spara uppdaterat dokument
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att ställa in åtkomstprivilegier för ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här koden för att tillämpa specifika begränsningar och skydda dina PDF-filer efter behov.

Var noga med att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerad PDF-dokumentsäkerhet och åtkomsthanteringsfunktioner.