---
title: Behoud rechten
linktitle: Behoud rechten
second_title: Aspose.PDF voor .NET API-referentie
description: Behoud formulierrechten in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-forms/preserve-rights/
---
In deze zelfstudie laten we u zien hoe u formulierrechten in een PDF-document kunt behouden met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het document

 Open het bron-PDF-document met behulp van a`FileStream` met lees- en schrijfrechten:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Stap 3: Formuliervelden bewerken

Doorloop alle formuliervelden in het document en breng de nodige wijzigingen aan. In dit voorbeeld wijzigen we de waarde van een formulierveld met 'A1' in de naam:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Stap 4: Sla het bijgewerkte document op

Sla het gewijzigde PDF-document op:

```csharp
pdfDocument.Save();
```

##  Stap 5: Sluit de`FileStream`

 Vergeet niet de`FileStream` bezwaar maken als u klaar bent:

```csharp
fs. Close();
```

### Voorbeeldbroncode voor Preserve Rights met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lees het bron-PDF-formulier met FileAccess of Lezen en schrijven.
// We hebben ReadWrite-toestemming nodig omdat na wijziging
// We moeten de bijgewerkte inhoud in hetzelfde document/bestand opslaan.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instantie van documentinstantie
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Haal waarden uit alle velden op
foreach (Field formField in pdfDocument.Form)
{
	// Als de volledige naam van het veld A1 bevat, voert u de bewerking uit
	if (formField.FullName.Contains("A1"))
	{
		// Formulierveld casten als TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Veldwaarde wijzigen
		textBoxField.Value = "Testing";
	}
}
// Sla het bijgewerkte document op in Save FileStream
pdfDocument.Save();
// Sluit het File Stream-object
fs.Close();
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de rechten van een formulier in een PDF-document kunt behouden met behulp van Aspose.PDF voor .NET. Door deze stappen te volgen, krijgt u eenvoudig toegang tot formuliervelden en kunt u specifieke wijzigingen aanbrengen, terwijl u de toegangs- en schrijfrechten behoudt.


### Veelgestelde vragen

#### Vraag: Kan ik de rechten van specifieke formuliervelden behouden zonder gevolgen voor anderen in het PDF-document?

 A: Ja, door gebruik te maken van de`FullName` eigenschap van de formuliervelden, kunt u specifieke formuliervelden targeten voor behoud, terwijl u andere velden onaangetast laat.

#### Vraag: Kan ik de rechten van een formulier in een met een wachtwoord beveiligd PDF-document behouden?

A: Ja, met Aspose.PDF voor .NET kunt u de rechten van een formulier behouden, zelfs in met een wachtwoord beveiligde PDF-documenten, zolang u het juiste wachtwoord opgeeft om het bestand te openen en te wijzigen.

#### Vraag: Wat gebeurt er als ik formuliervelden probeer te wijzigen zonder de juiste toegangsrechten?

A: Als u formuliervelden probeert te wijzigen zonder de juiste toegangsrechten, worden de wijzigingen niet opgeslagen in het PDF-document en ontvangt u mogelijk een uitzondering of een foutmelding.

#### Vraag: Is Aspose.PDF voor .NET compatibel met alle versies van .NET Framework?

A: Ja, Aspose.PDF voor .NET is compatibel met alle versies van .NET Framework, inclusief .NET Core en .NET Standard.

#### Vraag: Kan ik formulierrechten in een PDF-document programmatisch behouden in andere programmeertalen dan C#?

A: Ja, Aspose.PDF voor .NET ondersteunt naast C# ook verschillende programmeertalen, zoals VB.NET en ASP.NET.