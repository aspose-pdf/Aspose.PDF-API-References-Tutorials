---
title: Formulierveld ophalen in tabvolgorde
linktitle: Formulierveld ophalen in tabvolgorde
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u formuliervelden in tabvolgorde kunt ophalen met Aspose.PDF voor .NET.
type: docs
weight: 240
url: /nl/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Wanneer u met PDF-documenten in C# werkt met Aspose.PDF voor .NET, kunt u een scenario tegenkomen waarin u formuliervelden in een specifieke tabvolgorde moet ophalen. Dit kan handig zijn wanneer u bewerkingen op formuliervelden wilt uitvoeren op basis van hun tabvolgorde. In deze tutorial laten we u stap voor stap zien hoe u formuliervelden in tabvolgorde kunt ophalen met Aspose.PDF voor .NET.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Visual Studio geïnstalleerd op uw systeem
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd

Laten we nu eens kijken naar de stappen om formuliervelden in tabvolgorde op te halen.

## Stap 1: De documentdirectory instellen

 Om te beginnen moet u de documentdirectory instellen waar uw PDF-document zich bevindt. U kunt dit doen door het pad naar de directory in de`dataDir` variabel.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het PDF-document laden

 In deze stap laden we het PDF-document met Aspose.PDF voor .NET.`Document` klasse biedt de mogelijkheid om PDF-documenten te laden en te bewerken.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Hier,`"Test2.pdf"`is de naam van het PDF-document dat u wilt laden. Zorg ervoor dat het document aanwezig is in de opgegeven documentdirectory.

## Stap 3: Formuliervelden ophalen in tabvolgorde

 Om formuliervelden in tabvolgorde op te halen, moeten we toegang krijgen tot de`FieldsInTabOrder` eigendom van de`Page` klasse. Deze eigenschap retourneert een lijst met formuliervelden, gesorteerd op hun tabvolgorde.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

In het bovenstaande codefragment halen we de formuliervelden op van de tweede pagina (`doc.Pages[1]` ) en door elk veld itereren om hun gedeeltelijke namen samen te voegen tot de`s` variabele. U kunt dit codefragment aanpassen op basis van uw specifieke vereisten.

## Stap 4: De tabvolgorde wijzigen

 Als u de tabvolgorde van formuliervelden wilt wijzigen, kunt u dit doen via de`TabOrder` eigenschap van elk veld en het toewijzen van een nieuwe tabvolgordewaarde. Hier is een voorbeeld:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

In het bovenstaande codefragment wijzen we nieuwe tabvolgordewaarden toe aan drie formuliervelden (`doc.Form[3]`, `doc.Form[1]` , En`doc.Form[2]`). Pas de veldindexen en tabvolgordewaarden aan volgens uw specifieke vereisten.

## Stap 5: Het gewijzigde document opslaan

 Nadat u de tabvolgorde van formuliervelden hebt gewijzigd, moet u het gewijzigde document opslaan. U kunt dit doen met behulp van de`Save` methode van de`Document` klas.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Hier,`"39522_out.pdf"` is de naam van het uitvoerbestand waar het gewijzigde document wordt opgeslagen. Geef de gewenste naam en locatie voor het uitvoerbestand op.

### Voorbeeldbroncode voor het ophalen van formuliervelden in tabvolgorde met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe u formuliervelden in tabvolgorde kunt ophalen met Aspose.PDF voor .NET. We hebben de stappen behandeld die nodig zijn om een PDF-document te laden, formuliervelden in tabvolgorde op te halen, de tabvolgorde te wijzigen en het gewijzigde document op te slaan. Door deze stappen te volgen, kunt u efficiënt met formuliervelden werken en hun tabvolgorde aanpassen aan uw vereisten.


### Veelgestelde vragen

#### V: Hoe kan ik de opgehaalde formuliervelden in mijn C#-code gebruiken voor verdere verwerking?

 A: U kunt de opgehaalde formuliervelden in uw C#-code gebruiken door toegang te krijgen tot hun eigenschappen, zoals`Value`, `Name`, `Rect`enz. Met deze eigenschappen kunt u de gegevens in het formulierveld lezen en indien nodig wijzigen.

#### V: Kan ik formuliervelden van alle pagina's van het PDF-document in tabvolgorde ophalen?

 A: Ja, u kunt formuliervelden van alle pagina's van het PDF-document ophalen door door elke pagina te itereren en de`FieldsInTabOrder` eigenschap zoals getoond in de tutorial. Dit geeft u formuliervelden gesorteerd op hun tabvolgorde op alle pagina's.

#### V: Is het mogelijk om alleen specifieke typen formuliervelden, zoals tekstvelden of selectievakjes, in tabbladvolgorde op te halen?

A: Ja, u kunt formuliervelden filteren op basis van hun typen, zoals tekstvelden of selectievakjes, nadat u ze in tabvolgorde hebt opgehaald. U kunt voorwaardelijke statements gebruiken om het type van elk formulierveld te controleren en ze dienovereenkomstig te verwerken.

#### V: Kan ik formuliervelden ophalen op basis van hun naam in plaats van de tabvolgorde?

 A: Ja, u kunt formuliervelden ophalen op basis van hun namen met behulp van de`doc.Form` verzameling en het specificeren van de veldnaam als een index. Bijvoorbeeld,`doc.Form["fieldName"]`haalt het formulierveld op met de opgegeven naam.

#### V: Ondersteunt Aspose.PDF voor .NET het werken met gecodeerde PDF-documenten?

A: Ja, Aspose.PDF voor .NET biedt ondersteuning voor het werken met gecodeerde PDF-documenten. U kunt gecodeerde PDF-bestanden laden en bewerken met behulp van de juiste wachtwoordparameters.