---
title: Voeg tekst met schaduwkleuren toe aan het PDF-bestand
linktitle: Voeg tekst met schaduwkleuren toe aan het PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst met schaduwkleuren aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-text/add-text-with-shading-colors/
---
Deze tutorial begeleidt u bij het toevoegen van tekst met schaduwkleuren aan een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waaraan u tekst met schaduwkleuren wilt toevoegen, voegt u de volgende gebruiksinstructie bovenaan het bestand toe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Laad het PDF-document
 Laad het bestaande PDF-document met behulp van de`Document` constructor en geef het pad naar het documentbestand op.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code komt hier...
}
```

## Stap 5: Zoek de tekst die u wilt wijzigen
 Gebruik`TextFragmentAbsorber` om de gewenste tekst in het document te vinden. In de opgegeven code wordt gezocht naar de tekst "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Stap 6: Stel de schaduwkleur voor de tekst in
 Maak een nieuwe`Color` object met een patroonkleurruimte en specificeer de verloopkleuren. Wijs deze kleur toe aan de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Stap 7: Aanvullende tekstopmaak toepassen (optioneel)
 U kunt extra opmaak op het tekstfragment toepassen, zoals onderstrepen, door de eigenschappen van het`TextState` voorwerp.

```csharp
textFragment.TextState.Underline = true;
```

## Stap 8: Sla het gewijzigde PDF-document op
 Sla het gewijzigde PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Voorbeeldbroncode voor het toevoegen van tekst met arceringskleuren met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Creëer een nieuwe kleur met patroonkleurruimte
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusie
U hebt met succes tekst met schaduwkleuren aan uw PDF-document toegevoegd met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

### Veelgestelde vragen

#### Vraag: Wat is de belangrijkste focus van deze tutorial?

A: Deze tutorial leidt u door het proces van het toevoegen van tekst met schaduwkleuren aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen om dit te bereiken.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: In het codebestand waaraan u tekst met schaduwkleuren wilt toevoegen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe laad ik een bestaand PDF-document?

 A: In stap 4 laadt u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het documentbestand opgeven:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code komt hier...
}
```

#### Vraag: Hoe vind en wijzig ik specifieke tekst in het PDF-document?

 A: In stap 5 gebruikt u de`TextFragmentAbsorber`om de gewenste tekst in het document te vinden. Vervolgens kunt u de eigenschappen ervan wijzigen:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### Vraag: Hoe kan ik schaduwkleuren voor de tekst instellen?

 A: In stap 6 maakt u een nieuw`Color` object met een patroonkleurruimte en specificeer de verloopkleuren. Wijs deze kleur toe aan de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### Vraag: Kan ik aanvullende tekstopmaak toepassen op de gewijzigde tekst?

 A: Ja, in stap 7 kunt u aanvullende tekstopmaak toepassen, zoals onderstrepen, door de eigenschappen van de tekst te wijzigen.`TextState` voorwerp:

```csharp
textFragment.TextState.Underline = true;
```

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document?

 A: In stap 8 slaat u het gewijzigde PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u uw PDF-document kunt verbeteren door tekst met schaduwkleuren toe te voegen met behulp van Aspose.PDF voor .NET. Dit kan met name handig zijn voor het markeren en benadrukken van specifieke tekstinhoud in uw PDF-bestanden.