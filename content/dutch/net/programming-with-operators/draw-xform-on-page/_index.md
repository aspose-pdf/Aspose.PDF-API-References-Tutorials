---
title: Teken XForm op pagina
linktitle: Teken XForm op pagina
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het tekenen van een XForm-formulier op een PDF-pagina met Aspose.PDF voor .NET. Voeg het formulier toe en positioneer het op de pagina.
type: docs
weight: 10
url: /nl/net/programming-with-operators/draw-xform-on-page/
---
In deze tutorial geven we u een stapsgewijze handleiding over hoe u een XForm op een pagina tekent met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt maken, bewerken en converteren. Met behulp van de operatoren die Aspose.PDF biedt, kunt u een XForm-formulier toevoegen en positioneren op een bestaande PDF-pagina.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:

1. Visual Studio geïnstalleerd met .NET Framework.
2. De Aspose.PDF-bibliotheek voor .NET.

## Stap 1: Projectinstelling

Om te beginnen, maak een nieuw project in Visual Studio en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. U kunt de bibliotheek downloaden van de officiële Aspose-website en deze op uw machine installeren.

## Stap 2: Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de naamruimten die nodig zijn om toegang te krijgen tot de klassen en methoden die door Aspose.PDF worden aangeboden:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Stap 3: Bestandspaden instellen

Definieer de bestandspaden voor de achtergrondafbeelding, het invoer-PDF-bestand en het uitvoer-PDF-bestand:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Zorg ervoor dat u de daadwerkelijke bestandspaden op uw computer opgeeft.

## Stap 4: Het invoer-PDF-bestand laden

Gebruik de volgende code om het invoer-PDF-bestand te laden:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// De volgende code maakt gebruik van de GSave/GRestore-operatoren
// De code gebruikt de operator ContatenateMatrix om de XForm te positioneren
// De code gebruikt de Do-operator om het XForm op de pagina te tekenen
// GSave/GRestore-operatoren verpakken bestaande inhoud
//dit wordt gedaan om de initiële grafische status aan het einde van de bestaande inhoud te verkrijgen
// anders kunnen er ongewenste transformaties achterblijven aan het einde van de keten van bestaande operatoren
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Voeg GSave-operator toe om de grafische status correct te resetten na nieuwe opdrachten
pageContents. Add(new GSave());

// Maak de XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Stel de breedte en hoogte van de afbeelding in
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Laad de afbeelding in een stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Voeg de afbeelding toe aan de XForm-bronafbeeldingenverzameling
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Gebruik van de Do-operator: deze operator tekent de afbeelding
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Plaats de XForm op de coördinaten x=100 en y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Teken de XForm met de Do-operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Plaats de XForm op de coördinaten x=100 en y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Teken de XForm met de Do-operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Herstel de grafische status met GRestore na GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Zorg ervoor dat u de werkelijke bestandspaden opgeeft en pas indien nodig het paginanummer en de XForm-posities aan.

### Voorbeeldbroncode voor Draw XForm On Page met behulp van Aspose.PDF voor .NET
 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Het voorbeeld toont aan
	// Gebruik van GSave/GRestore-operatoren
	// Gebruik van de operator ContatenateMatrix om xForm te positioneren
	//Gebruik operator om xForm op de pagina te tekenen
	// Bestaande inhoud inpakken met GSave/GRestore-operatorenpaar
	// dit is om de initiële grafische status van de bestaande inhoud te verkrijgen
	// anders zouden er aan het einde van de bestaande operatorketen ongewenste transformaties kunnen overblijven
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Voeg een operator toe om de grafische status op de juiste manier te wissen na nieuwe opdrachten
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm maken
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definieer de breedte en hoogte van de afbeelding
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Afbeelding in stream laden
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Afbeelding toevoegen aan de afbeeldingencollectie van de XForm-bronnen
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Gebruik van de Do-operator: deze operator tekent een afbeelding
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Plaats het formulier op de x=100 y=500 coördinaten
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Vorm tekenen met Do-operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Plaats het formulier op de x=100 y=300 coördinaten
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Vorm tekenen met Do-operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Herstel de grafische status met GRestore na de GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusie

In deze tutorial hebt u geleerd hoe u een XForm-formulier op een PDF-pagina tekent met Aspose.PDF voor .NET. Door de beschreven stappen te volgen, kunt u een XForm-formulier toevoegen en positioneren op een bestaande pagina, waardoor u meer flexibiliteit krijgt in uw PDF-documenten.

### FAQ's voor het tekenen van XForm op pagina

#### V: Wat is een XForm in Aspose.PDF?

A: Een XForm is een herbruikbaar grafisch object in een PDF-document. Hiermee kunt u complexe grafieken, afbeeldingen of tekst definiëren en tekenen die meerdere keren op verschillende pagina's kunnen worden hergebruikt.

#### V: Hoe importeer ik de benodigde naamruimten voor Aspose.PDF?

 A: Gebruik in uw C#-codebestand de`using` richtlijn om de vereiste naamruimten te importeren voor toegang tot de klassen en methoden die door Aspose worden geleverd.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### V: Wat is het doel van de operators GSave en GRestore?

 A: De`GSave` En`GRestore` operatoren in Aspose.PDF worden gebruikt om de grafische status op te slaan en te herstellen. Ze helpen ervoor te zorgen dat transformaties en instellingen die op één sectie van de content worden toegepast, geen invloed hebben op daaropvolgende secties.

#### V: Hoe definieer ik een XForm met behulp van Aspose.PDF?

 A: Om een XForm te maken, gebruikt u de`XForm.CreateNewForm` methode en voeg het toe aan de`Resources.Forms` verzameling van een specifieke pagina. U kunt vervolgens inhoud toevoegen aan de XForm's`Contents` eigendom.

#### V: Hoe kan ik een afbeelding tekenen in een XForm?

A: Laad de afbeelding in een stream en voeg deze toe aan de`Resources.Images` verzameling van de XForm. Gebruik de`Do` operator binnen de XForm`Contents` om de afbeelding te tekenen.

#### V: Hoe positioneer ik een XForm op een PDF-pagina?

 A: Om een XForm op een pagina te plaatsen, gebruikt u de`ConcatenateMatrix` operator binnen de pagina`Contents`Pas de matrixparameters aan om de vertaling (positie) en schaal van het XForm te specificeren.

#### V: Kan ik meerdere XForms op dezelfde pagina tekenen?

 A: Ja, u kunt meerdere XForms op dezelfde pagina tekenen door de`ConcatenateMatrix` parameters om elke XForm op verschillende coördinaten te positioneren.

#### V: Kan ik de inhoud van een XForm wijzigen nadat deze is gemaakt?

 A: Ja, u kunt de inhoud van een XForm wijzigen nadat u deze hebt gemaakt door er extra operatoren aan toe te voegen.`Contents` eigendom.

#### V: Wat gebeurt er als ik de operators GSave en GRestore weglaat?

A: Het weglaten van de GSave- en GRestore-operators kan leiden tot ongewenste transformaties of instellingen die worden toegepast op latere content. Het gebruik ervan helpt een schone grafische staat te behouden.

#### V: Kan ik XForms hergebruiken op verschillende pagina's van het PDF-document?

 A: Ja, u kunt XForms op meerdere pagina's hergebruiken door hetzelfde XForm toe te voegen aan de`Resources.Forms` verzameling van verschillende pagina's.

#### V: Is er een limiet aan het aantal XForms dat ik kan maken?

A: Hoewel er geen strikte limiet is aan het aantal XForms dat u kunt maken, moet u er rekening mee houden dat te veel XForms de prestaties en het geheugengebruik kunnen beïnvloeden. Gebruik ze verstandig.

#### V: Kan ik een XForm roteren of andere transformaties toepassen?

 A: Ja, u kunt de`ConcatenateMatrix` operator om transformaties zoals rotatie, schaling en translatie toe te passen op een XForm.
