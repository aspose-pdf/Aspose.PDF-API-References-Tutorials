---
title: Tekst met schaduwkleuren toevoegen in PDF-bestand
linktitle: Tekst met schaduwkleuren toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst met schaduwkleuren toevoegt aan een PDF-bestand met behulp van Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-text/add-text-with-shading-colors/
---
Deze tutorial begeleidt u door het proces van het toevoegen van tekst met schaduwkleuren in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waar u tekst met arceringskleuren wilt toevoegen, voegt u de volgende richtlijn toe boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Stap 3: Stel de documentdirectory in
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
 Gebruik`TextFragmentAbsorber` om de gewenste tekst in het document te vinden. In de meegeleverde code wordt gezocht naar de tekst "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Stap 6: Stel de schaduwkleur voor de tekst in
 Maak een nieuwe`Color` object met een patroonkleurruimte en specificeer de gradiëntschaduwkleuren. Wijs deze kleur toe aan de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Stap 7: Extra tekstopmaak toepassen (optioneel)
 U kunt extra opmaak op het tekstfragment toepassen, zoals onderstrepen, door de eigenschappen van de tekst te wijzigen.`TextState` voorwerp.

```csharp
textFragment.TextState.Underline = true;
```

## Stap 8: Sla het gewijzigde PDF-document op
 Sla het gewijzigde PDF-document op met behulp van de`Save` methode van de`Document` voorwerp.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Voorbeeldbroncode voor Tekst met schaduwkleuren toevoegen met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Nieuwe kleur maken met patroonkleurruimte
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusie
U hebt succesvol tekst met schaduwkleuren toegevoegd aan uw PDF-document met behulp van Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad van het uitvoerbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich vooral?

A: Deze tutorial begeleidt u door het proces van het toevoegen van tekst met schaduwkleuren aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de benodigde stappen om dit te bereiken.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waar u tekst met arceringskleuren wilt toevoegen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe laad ik een bestaand PDF-document?

 A: In stap 4 laadt u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het documentbestand opgeven:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Code komt hier...
}
```

#### V: Hoe kan ik specifieke tekst in het PDF-document vinden en wijzigen?

 A: In stap 5 gebruikt u de`TextFragmentAbsorber`om de gewenste tekst in het document te vinden. Vervolgens kunt u de eigenschappen ervan wijzigen:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### V: Hoe kan ik schaduwkleuren voor de tekst instellen?

 A: In stap 6 maakt u een nieuwe`Color` object met een patroonkleurruimte en specificeer de gradiëntschaduwkleuren. Wijs deze kleur toe aan de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### V: Kan ik extra tekstopmaak toepassen op de gewijzigde tekst?

 A: Ja, in stap 7 kunt u extra tekstopmaak toepassen, zoals onderstrepen, door de eigenschappen van de tekst te wijzigen.`TextState` voorwerp:

```csharp
textFragment.TextState.Underline = true;
```

#### V: Hoe kan ik het gewijzigde PDF-document opslaan?

 A: In stap 8 slaat u het gewijzigde PDF-document op met behulp van de`Save` methode van de`Document` voorwerp:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u succesvol geleerd hoe u uw PDF-document kunt verbeteren door tekst toe te voegen met schaduwkleuren met behulp van Aspose.PDF voor .NET. Dit kan met name handig zijn voor het markeren en benadrukken van specifieke tekstinhoud in uw PDF-bestanden.