---
title: Teken XForm op pagina
linktitle: Teken XForm op pagina
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het tekenen van een XForm-formulier op een PDF-pagina met Aspose.PDF voor .NET. Voeg het formulier toe en positioneer het op de pagina.
type: docs
weight: 10
url: /nl/net/programming-with-operators/draw-xform-on-page/
---
In deze zelfstudie geven we u stapsgewijze handleiding voor het tekenen van een XForm op een pagina met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u programmatisch PDF-documenten kunt maken, manipuleren en converteren. Met behulp van de operators van Aspose.PDF kunt u een XForm-formulier toevoegen en positioneren op een bestaande PDF-pagina.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio geïnstalleerd met .NET-framework.
2. De Aspose.PDF-bibliotheek voor .NET.

## Stap 1: Projectconfiguratie

Om aan de slag te gaan, maakt u een nieuw project in Visual Studio en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. U kunt de bibliotheek downloaden van de officiële website van Aspose en deze op uw computer installeren.

## Stap 2: Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de naamruimten die nodig zijn voor toegang tot de klassen en methoden van Aspose.PDF:

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
// De code gebruikt de ContatenateMatrix-operator om het XForm te positioneren
// De code gebruikt de Do-operator om het XForm op de pagina te tekenen
// GSave/GRestore-operatoren verpakken bestaande inhoud
// dit wordt gedaan om de initiële grafische staat aan het einde van de bestaande inhoud te krijgen
// anders kunnen er ongewenste transformaties achterblijven aan het einde van de keten van bestaande operators
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Voeg een GSave-operator toe om de grafische status correct te resetten na nieuwe opdrachten
pageContents. Add(new GSave());

// Maak het XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Stel de breedte en hoogte van de afbeelding in
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Laad de afbeelding in een stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Voeg de afbeelding toe aan de verzameling XForm-bronafbeeldingen
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Gebruik van de Do-operator: deze operator tekent de afbeelding
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Plaats het XForm op de coördinaten x=100 en y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Teken het XForm met de Do-operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Plaats de XForm op coördinaten x=100 en y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Teken het XForm met de Do-operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Herstel de grafische status met GRestore na GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Zorg ervoor dat u de daadwerkelijke bestandspaden opgeeft en pas het paginanummer en de XForm-posities indien nodig aan.

### Voorbeeldbroncode voor Draw XForm On Page met Aspose.PDF voor .NET
 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Het monster demonstreert
	// Gebruik van GSave/GRestore-operators
	// ContatenateMatrix-operatorgebruik om xForm te positioneren
	// Gebruik operatorgebruik om xForm op pagina te tekenen
	// Verpak bestaande inhoud met een paar GSave/GRestore-operators
	// dit is om de initiële grafische status van de bestaande inhoud te verkrijgen
	// Anders zouden er aan het eind van de bestaande keten van operators mogelijk ongewenste transformaties kunnen blijven plaatsvinden
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Voeg een operator voor het opslaan van de grafische status toe om de grafische status correct te wissen na nieuwe opdrachten
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Maak xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definieer de breedte en hoogte van de afbeelding
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Laad afbeelding in stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Voeg een afbeelding toe aan de afbeeldingenverzameling van de XForm-bronnen
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Met behulp van de Do-operator: deze operator tekent een afbeelding
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Plaats het formulier op de x=100 y=500 coördinaten
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Teken een formulier met de Do-operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Plaats het formulier op de x=100 y=300 coördinaten
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Teken een formulier met de Do-operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Herstel de grafische status met GRestore na de GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een XForm-formulier op een PDF-pagina kunt tekenen met Aspose.PDF voor .NET. Door de beschreven stappen te volgen, kunt u een XForm-formulier toevoegen en op een bestaande pagina plaatsen, waardoor uw PDF-documenten meer flexibiliteit krijgen.

### Veelgestelde vragen over draw XForm op pagina

#### Vraag: Wat is een XForm in Aspose.PDF?

A: Een XForm is een herbruikbaar grafisch object in een PDF-document. Hiermee kunt u complexe afbeeldingen, afbeeldingen of tekst definiëren en tekenen die meerdere keren op verschillende pagina's kunnen worden hergebruikt.

#### Vraag: Hoe importeer ik de benodigde naamruimten voor Aspose.PDF?

 A: Gebruik in uw C#-codebestand de`using` richtlijn om de vereiste naamruimten te importeren voor toegang tot de klassen en methoden die door Aspose.PDF worden geleverd:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Vraag: Wat is het doel van de GSave- en GRestore-operatoren?

 EEN: De`GSave` En`GRestore`Operators in Aspose.PDF worden gebruikt om de grafische status op te slaan en te herstellen. Ze helpen ervoor te zorgen dat transformaties en instellingen die op één sectie van de inhoud worden toegepast, geen invloed hebben op volgende secties.

#### Vraag: Hoe definieer ik een XForm met Aspose.PDF?

 A: Om een XForm te maken, gebruikt u de`XForm.CreateNewForm` methode en voeg deze toe aan de`Resources.Forms` verzameling van een specifieke pagina. Vervolgens kunt u inhoud toevoegen aan de XForm's`Contents` eigendom.

#### Vraag: Hoe kan ik een afbeelding tekenen binnen een XForm?

 A: Laad de afbeelding in een stream en voeg deze toe aan de`Resources.Images` verzameling van het XForm. Gebruik de`Do` operator binnen de XForm's`Contents` om de afbeelding te tekenen.

#### Vraag: Hoe plaats ik een XForm op een PDF-pagina?

 A: Om een XForm op een pagina te plaatsen, gebruikt u de`ConcatenateMatrix` operator binnen de pagina's`Contents`. Pas de matrixparameters aan om de vertaling (positie) en schaling van het XForm te specificeren.

#### Vraag: Kan ik meerdere XForms op dezelfde pagina tekenen?

 A: Ja, u kunt meerdere XForms op dezelfde pagina tekenen door de`ConcatenateMatrix`parameters om elke XForm op verschillende coördinaten te positioneren.

#### Vraag: Kan ik de inhoud van een XForm wijzigen nadat deze is gemaakt?

 A: Ja, u kunt de inhoud van een XForm wijzigen nadat deze is gemaakt door er extra operators aan toe te voegen`Contents` eigendom.

#### Vraag: Wat gebeurt er als ik de operatoren GSave en GRestore weglaat?

A: Het weglaten van de operatoren GSave en GRestore kan ertoe leiden dat ongewenste transformaties of instellingen worden toegepast op daaropvolgende inhoud. Door ze te gebruiken, blijft de grafische staat schoon.

#### Vraag: Kan ik XForms hergebruiken op verschillende pagina's van het PDF-document?

 A: Ja, u kunt XForms op meerdere pagina's hergebruiken door hetzelfde XForm toe te voegen aan de`Resources.Forms` verzameling van verschillende pagina's.

#### Vraag: Is er een limiet aan het aantal XForms dat ik kan maken?

A: Hoewel er geen strikte limiet is voor het aantal XForms dat u kunt maken, moet u er rekening mee houden dat te veel XForms de prestaties en het geheugengebruik kunnen beïnvloeden. Gebruik ze oordeelkundig.

#### Vraag: Kan ik een XForm roteren of andere transformaties toepassen?

 A: Ja, u kunt de`ConcatenateMatrix`operator om transformaties zoals rotatie, schaling en vertaling toe te passen op een XForm.
