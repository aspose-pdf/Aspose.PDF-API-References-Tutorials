---
title: Rechten behouden
linktitle: Rechten behouden
second_title: Aspose.PDF voor .NET API-referentie
description: Behoud formulierrechten in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-forms/preserve-rights/
---
In deze tutorial laten we u zien hoe u formulierrechten in een PDF-document kunt behouden met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het document

 Open het bron-PDF-document met behulp van een`FileStream` met lees- en schrijfrechten:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Stap 3: Formuliervelden bewerken

Ga door alle formuliervelden in het document en breng de nodige wijzigingen aan. In dit voorbeeld wijzigen we de waarde van een formulierveld met "A1" in de naam:

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

 Vergeet niet om de`FileStream` object als je klaar bent:

```csharp
fs. Close();
```

### Voorbeeldbroncode voor Preserve Rights met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lees het bron-PDF-bestand met FileAccess van Read and Write.
// We hebben ReadWrite-machtiging nodig omdat na wijziging,
// We moeten de bijgewerkte inhoud in hetzelfde document/bestand opslaan.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instantieer Document-instantie
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Waarden uit alle velden ophalen
foreach (Field formField in pdfDocument.Form)
{
	// Als de volledige naam van het veld A1 bevat, voer dan de bewerking uit
	if (formField.FullName.Contains("A1"))
	{
		// Formulierveld omzetten als tekstvak
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

In deze tutorial hebben we geleerd hoe u de rechten van een formulier in een PDF-document kunt behouden met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig toegang krijgen tot formuliervelden en specifieke wijzigingen aanbrengen terwijl u de toegangs- en schrijfmachtigingen behoudt.


### Veelgestelde vragen

#### V: Kan ik de rechten van specifieke formuliervelden behouden zonder dat dit gevolgen heeft voor andere velden in het PDF-document?

 A: Ja, door gebruik te maken van de`FullName` eigenschap van de formuliervelden kunt u specifieke formuliervelden selecteren die u wilt behouden, terwijl u andere velden ongemoeid laat.

#### V: Kan ik de rechten van een formulier behouden in een met een wachtwoord beveiligd PDF-document?

A: Ja, met Aspose.PDF voor .NET kunt u de rechten van een formulier behouden, zelfs in PDF-documenten die met een wachtwoord zijn beveiligd, zolang u het juiste wachtwoord opgeeft om het bestand te openen en te wijzigen.

#### V: Wat gebeurt er als ik probeer formuliervelden te wijzigen zonder de juiste toegangsrechten?

A: Als u formuliervelden probeert te wijzigen zonder de juiste toegangsrechten, worden de wijzigingen niet opgeslagen in het PDF-document en ontvangt u mogelijk een uitzondering of een foutmelding.

#### V: Is Aspose.PDF voor .NET compatibel met alle versies van .NET Framework?

A: Ja, Aspose.PDF voor .NET is compatibel met alle versies van .NET Framework, inclusief .NET Core en .NET Standard.

#### V: Kan ik formulierrechten in een PDF-document programmatisch behouden in andere programmeertalen dan C#?

A: Ja, Aspose.PDF voor .NET ondersteunt verschillende programmeertalen, zoals VB.NET en ASP.NET, naast C#.