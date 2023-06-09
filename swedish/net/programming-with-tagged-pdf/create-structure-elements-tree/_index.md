---
title: Skapa strukturelementträd
linktitle: Skapa strukturelementträd
second_title: Aspose.PDF för .NET API Referens
description: Skapa en struktur av trädelement med Aspose.PDF för .NET. Steg för steg guide för att skapa ett strukturerat PDF-dokument.
type: docs
weight: 70
url: /sv/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
I denna steg-för-steg-guide kommer vi att förklara källkoden i C# för att skapa en struktur av trädelement med Aspose.PDF för .NET. Vi kommer att visa dig hur du skapar ett PDF-dokument med strukturerade element och hur du organiserar dem hierarkiskt. Att använda Aspose.PDF-biblioteket förenklar manipuleringen av PDF-element avsevärt och ger avancerad funktionalitet för att arbeta med strukturerade dokument.

## Steg 1: Sätta upp miljön
Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.PDF för .NET. Se också till att sökvägen till din dokumentkatalog är inställd i`dataDir` variabel.

## Steg 2: Skapa ett PDF-dokument
 Till att börja med skapar vi ett nytt PDF-dokument med hjälp av`Document` klass tillhandahållen av Aspose.PDF. Här är koden för detta steg:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett PDF-dokument
Document document = new Document();
```

## Steg 3: Få innehåll att fungera med TaggedPdf
 Aspose.PDF-biblioteket tillåter att arbeta med strukturerade PDF-dokument med konceptet Tagged PDF. För detta måste vi få en referens till det taggade innehållsobjektet med hjälp av dokumentets`TaggedContent` fast egendom. Här är koden för detta steg:

```csharp
// Få innehåll att fungera med TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## Steg 4: Ställ in dokumentets titel och språk
 Innan vi börjar skapa strukturen för elementen måste vi definiera titeln och språket för dokumentet. Detta kan göras med hjälp av`SetTitle` och`SetLanguage` metoder för`taggedContent` objekt. Här är koden för detta steg:

```csharp
// Definiera dokumentets titel och språk
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## Steg 5: Skapa logiska strukturelement
Nu när vi har ställt in vårt dokument och ställt in titeln och språket kan vi börja skapa logiska strukturelement. Dessa element kommer att organiseras hierarkiskt för att bilda strukturträdet. Här är koden för detta steg:

```csharp
// Skaffa rotstrukturelementet (dokument)
StructureElement rootElement = taggedContent.RootElement;

// Skapa den logiska strukturen
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## Steg 6: Spara det taggade PDF-dokumentet
 När vi har skapat elementstrukturen kan vi spara PDF-dokumentet. Använd`Save` metod för`document` objekt för att ange sökvägen och namnet på PDF-filen som ska sparas. Här är koden för detta steg:

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StructureElementsTree.pdf");
```

### Exempel på källkod för Create Structure Elements Tree med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa pdf-dokument
Document document = new Document();
// Skaffa innehåll för arbetet med TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Ställ in titel och språk för Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Hämta rotstrukturelement (dokument)
StructureElement rootElement = taggedContent.RootElement;
// Skapa logisk struktur
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
// Spara taggat pdf-dokument
document.Save(dataDir + "StructureElementsTree.pdf");

```

## Slutsats
Du har lärt dig hur man skapar en struktur av trädelement med Aspose.PDF för .NET. Den här guiden har visat dig stegen som behövs för att skapa ett PDF-dokument, skapa logiska strukturelement och spara det slutliga dokumentet. Genom att använda Aspose.PDF kan du enkelt manipulera PDF-element och skapa strukturerade dokument.
