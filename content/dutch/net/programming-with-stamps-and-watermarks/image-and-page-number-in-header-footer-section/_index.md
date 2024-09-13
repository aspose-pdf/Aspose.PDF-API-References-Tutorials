---
title: Afbeelding en paginanummer in koptekst-voettekstsectie
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer in deze stapsgewijze zelfstudie hoe u een afbeelding en paginanummers toevoegt aan de kop- en voettekst van uw PDF met behulp van Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Invoering

Als het aankomt op het maken van professionele PDF-documenten, is het essentieel om controle te hebben over kleine details zoals kop- en voetteksten. U wilt dat uw documenten er gepolijst en overzichtelijk uitzien, toch? Nou, met Aspose.PDF voor .NET kunt u naadloos afbeeldingen en paginanummers toevoegen aan de kop- en voettekstsecties van uw document. In deze tutorial leiden we u door elke stap, zodat u het gemakkelijk kunt volgen.

## Vereisten

Voordat u zich in de details van deze tutorial verdiept, moet u ervoor zorgen dat u het volgende geregeld hebt:

1. .NET Framework: U moet een versie van het .NET Framework op uw computer geïnstalleerd hebben. Als u het niet hebt, kunt u het eenvoudig downloaden van de Microsoft-website.
2.  Aspose.PDF voor .NET: Omdat we Aspose.PDF gaan gebruiken, zorg ervoor dat u het in uw project hebt geïnstalleerd. U kunt een proefversie downloaden[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Kennis van de basisprogrammering van C# zal u zeker helpen de code zonder al te veel gedoe te begrijpen.
4. Een afbeeldingsbestand: U hebt een afbeelding nodig die u in de header van uw PDF-document wilt plaatsen, zoals een logo. Sla het op in een toegankelijke map. 
5. IDE: Gebruik een Integrated Development Environment (IDE) naar keuze, zoals Visual Studio, om met uw .NET-project te werken.

Zodra u aan de vereisten voldoet, bent u helemaal klaar om een fantastisch PDF-bestand te maken!

## Pakketten importeren

Om Aspose.PDF voor .NET te gaan gebruiken, moet u de benodigde naamruimten importeren. Bovenaan uw C#-bestand voegt u het volgende toe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Deze naamruimten geven u toegang tot de klassen die nodig zijn voor het bewerken van PDF-bestanden.

Laten we nu naar de echte deal gaan! Volg deze stappen om uw PDF-document te maken, waarbij u een afbeelding in de koptekst en paginanummers in de voettekst opneemt.

## Stap 1: Stel uw documentenmap in

Elk goed project begint met organisatie. Definieer uw documentdirectory waar u uw bestanden opslaat en waar uw afbeelding zich bevindt. Dit is hoe u dat doet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vergeet niet om te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u uw PDF wilt opslaan en waar uw afbeelding zich bevindt.

## Stap 2: Maak een nieuw PDF-document

Vervolgens gaan we een nieuw PDF-document maken waarin alle magie plaatsvindt:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Op dit punt heb je een leeg PDF-document gemaakt. Spannend, nietwaar?

## Stap 3: Een pagina toevoegen aan het document

Een PDF draait helemaal om pagina's. Laten we een nieuwe pagina aan ons document toevoegen met:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Nu heb je een canvas waarop je kunt beginnen met ontwerpen!

## Stap 4: Maak de koptekstsectie

Uw header bevat de afbeelding (zoals een logo) die u wilt weergeven. Maak de headersectie met de volgende code:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Nu hebt u een header die u kunt aanpassen!

## Stap 5: Voeg een afbeelding toe aan de header

Nu komen we bij het leuke gedeelte! Je moet de afbeelding toevoegen aan je header. Maak eerst een afbeeldingsobject:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Stel het bestandspad van uw afbeelding in:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Voeg ten slotte de afbeelding toe aan uw header:

```csharp
header.Paragraphs.Add(image1);
```

Gefeliciteerd! U hebt zojuist een afbeelding toegevoegd aan uw PDF-header.

## Stap 6: Maak de voettekstsectie

Laten we nu aan de footer werken. Vergelijkbaar met het headerproces, maak een footerobject:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Hier plaatst u uw paginanummer. 

## Stap 7: Voeg tekst toe aan de voettekst

Maak een tekstfragment dat het paginanummer bevat:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Voeg vervolgens dit tekstfragment toe aan de voettekst:

```csharp
footer.Paragraphs.Add(txt);
```

Zie je hoe makkelijk dat was? Je hebt je paginanummer dynamisch ingesteld!

## Stap 8: Sla het PDF-document op

De laatste stap in ons avontuur is het opslaan van het document. Gebruik deze opdracht om uw nieuw gemaakte PDF op te slaan:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

En zo is uw PDF klaar, gevuld met een header-afbeelding en paginanummers in de footer!

## Conclusie

En daar heb je het! Je hebt zojuist een PDF gemaakt met een afbeelding in de header en dynamische paginanummers in de footer met Aspose.PDF voor .NET. Het is ongelooflijk hoe een paar regels code kunnen resulteren in zo'n gepolijste output. Of het nu gaat om een bedrijfsrapport of een gepersonaliseerd document, het toevoegen van deze elementen verandert de toon en professionaliteit van je PDF.

## Veelgestelde vragen

### Kan ik Aspose.PDF op elk .NET-platform gebruiken?
Ja, Aspose.PDF voor .NET ondersteunt meerdere .NET-platformen, waaronder .NET Framework, .NET Core en meer.

### Is er een gratis proefversie beschikbaar voor Aspose.PDF?
 Absoluut! Je kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/).

### Welke afbeeldingsformaten worden ondersteund voor headers?
Aspose.PDF ondersteunt de meest voorkomende afbeeldingsformaten, zoals JPG, PNG en BMP voor kop- en voetteksten.

### Kan ik het paginanummerformaat aanpassen?
Ja, u kunt de voettekst en de opmaak eenvoudig aanpassen aan uw wensen.

### Is er technische ondersteuning beschikbaar?
 Ja, Aspose biedt toegewijde ondersteuning via hun forum. U kunt contact opnemen voor hulp[hier](https://forum.aspose.com/c/pdf/10).