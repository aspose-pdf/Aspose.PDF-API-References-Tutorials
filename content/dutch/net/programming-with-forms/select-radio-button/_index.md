---
title: Selecteer keuzerondje in PDF-document
linktitle: Selecteer keuzerondje in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een keuzerondje in een PDF-document selecteert met Aspose.PDF voor .NET.
type: docs
weight: 250
url: /nl/net/programming-with-forms/select-radio-button/
---
Hier vindt u een gedetailleerde tutorial over hoe u een keuzerondje selecteert met Aspose.PDF voor .NET. Volg deze stappen:

##  Stap 1: Begin met het definiëren van de map van uw documenten door het pad op te geven in het`dataDir` variable.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Stap 2: Open het PDF-document met behulp van de`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Stap 3: Haal het keuzerondjeveld op uit het documentformulier.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Stap 4: Geef de index op van het keuzerondje dat u uit de groep wilt selecteren.

```csharp
radioField. Selected = 2;
```

## Stap 5: Stel het uitvoerpad voor het bewerkte PDF-bestand in.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Stap 6: Sla het gewijzigde PDF-bestand op.

```csharp
pdfDocument.Save(dataDir);
```

## Stap 7: Geef een bevestigingsbericht en de locatie van het opgeslagen bestand weer.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Voorbeeldbroncode voor Select Radio Button met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Document openen
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Neem een veld
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Geef de index op van het keuzerondje uit de groep
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Sla het PDF-bestand op
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een keuzerondje kunt selecteren met Aspose.PDF voor .NET. Door de hierboven beschreven stappen te volgen, kunt u keuzerondjes in uw PDF-documenten manipuleren en wijzigen met Aspose.PDF voor .NET.


### Veelgestelde vragen

#### Vraag: Kan ik meerdere keuzerondjes in een groep selecteren met Aspose.PDF voor .NET?

A: Nee, keuzerondjes in een groep zijn zo ontworpen dat ze elkaar uitsluiten. U kunt binnen een groep slechts één keuzerondje tegelijk selecteren. Als u er één selecteert, wordt automatisch elk eerder geselecteerd keuzerondje in dezelfde groep gedeselecteerd.

#### Vraag: Hoe haal ik het geselecteerde keuzerondje op in een groep met behulp van Aspose.PDF voor .NET?

 A: Om het geselecteerde keuzerondje in een groep op te halen, kunt u de`Selected` eigendom van de`RadioButtonField` klas. Het retourneert de index van het geselecteerde keuzerondje binnen de groep.

#### Vraag: Kan ik de weergave van het geselecteerde keuzerondje in het PDF-document aanpassen?

A: Ja, u kunt het uiterlijk van het geselecteerde keuzerondje aanpassen met Aspose.PDF voor .NET. U kunt de kleur, grootte, randstijl en andere visuele kenmerken aanpassen aan uw gewenste uiterlijk.

#### Vraag: Is het mogelijk om programmatisch nieuwe keuzerondjesgroepen te maken met Aspose.PDF voor .NET?

A: Ja, u kunt programmatisch nieuwe keuzerondjesgroepen maken met Aspose.PDF voor .NET. U kunt nieuwe keuzerondjes aan het documentformulier toevoegen en voor elk keuzerondje dezelfde groepsnaam opgeven om een nieuwe groep te maken.

#### Vraag: Ondersteunt Aspose.PDF voor .NET het werken met interactieve PDF-formulieren?

A: Ja, Aspose.PDF voor .NET ondersteunt volledig het werken met interactieve PDF-formulieren, inclusief keuzerondjes, tekstvelden, selectievakjes en andere formulierelementen. Met behulp van de bibliotheek kunt u eenvoudig interactieve PDF-formulieren lezen, wijzigen en maken.