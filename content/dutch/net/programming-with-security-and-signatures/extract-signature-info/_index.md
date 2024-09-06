---
title: Handtekeninginfo extraheren
linktitle: Handtekeninginfo extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Handtekeninginformatie extraheren met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-security-and-signatures/extract-signature-info/
---
Het proces van het extraheren van handtekeninginformatie uit een PDF-document kan in verschillende scenario's erg nuttig zijn. Of u nu de authenticiteit van een ondertekend document wilt valideren of het certificaat wilt analyseren dat voor de handtekening is gebruikt, de Aspose.PDF voor .NET-bibliotheek biedt een handige oplossing. In deze tutorial leiden we u stapsgewijs door het proces van het extraheren van handtekeninginformatie met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:

1. Basiskennis van de programmeertaal C#.
2. Aspose.PDF voor .NET-bibliotheek op uw systeem geïnstalleerd.
3. Een geldig PDF-document met één of meer handtekeningvelden.

Laten we nu eens dieper ingaan op de implementatiedetails.

## Stap 1: De vereiste bibliotheken importeren

 Om te beginnen moet u de benodigde bibliotheken importeren in uw C#-project. In dit geval moeten we de`Aspose.Pdf` En`System.IO` namespaces. Dit kan worden gedaan door de volgende code toe te voegen aan het begin van uw C#-bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 2: Het documentpad instellen

Vervolgens moet u het pad instellen naar het PDF-document waaruit u de handtekeninginformatie wilt extraheren. Vervangen`"YOUR DOCUMENTS DIRECTORY"` in het volgende codefragment met het daadwerkelijke pad naar uw document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Stap 3: Handtekeninginformatie extraheren

Laten we nu verdergaan met het hoofdgedeelte van de code, waar we de handtekeninginformatie uit het PDF-document halen. We itereren door elk veld in het formulier van het document en controleren of het een handtekeningveld is. Als er een handtekeningveld wordt gevonden, gaan we verder met het extraheren van het certificaat. Voeg het volgende codefragment toe:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Haal het certificaat eruit
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Stap 4: Het certificaat extraheren

In deze stap halen we het certificaat uit het handtekeningveld en slaan het op als een bestand. Het geëxtraheerde certificaat kan verder worden geanalyseerd of worden gebruikt voor validatiedoeleinden. Het onderstaande codefragment demonstreert het extractie- en opslagproces:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Stap 5

: Het certificaat opslaan

Ten slotte slaan we het geëxtraheerde certificaat op als een bestand. In dit voorbeeld wordt het certificaat opgeslagen met de naam "input.cer" in de opgegeven directory. U kunt de code aanpassen aan uw wensen. Hier is het codefragment voor het opslaan van het certificaat:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Dat is alles! U hebt met succes handtekeninginformatie geëxtraheerd met Aspose.PDF voor .NET. U kunt deze code gerust integreren in uw eigen applicaties of aanpassen aan uw behoeften.

### Voorbeeldbroncode voor Extract Signature Info met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze tutorial hebben we een stapsgewijze handleiding doorlopen over het extraheren van handtekeninginformatie uit een PDF-document met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het proces behandeld van het importeren van de vereiste bibliotheken, het instellen van het documentpad, het extraheren van handtekeninginformatie, het extraheren van het certificaat en het opslaan ervan in een bestand. Door deze stappen te volgen, kunt u eenvoudig handtekeningdetails ophalen en ermee werken zoals nodig.

### Veelgestelde vragen

#### V: Waarom moet ik handtekeninginformatie uit een PDF-document halen?

A: Het extraheren van handtekeninginformatie uit een PDF-document is handig om de authenticiteit van een ondertekend document te valideren en het certificaat te analyseren dat voor de handtekening is gebruikt. Dit proces helpt de integriteit van de ondertekende inhoud te waarborgen en kan essentieel zijn voor juridische en beveiligingsdoeleinden.

#### V: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars met PDF-documenten in .NET-applicaties kunnen werken. Het biedt een breed scala aan functies voor het maken, wijzigen en interactief gebruiken van PDF-bestanden op een programmatische manier.

#### V: Wat zijn de vereisten voor het extraheren van handtekeninginformatie met Aspose.PDF voor .NET?

A: Om handtekeninginformatie te extraheren, hebt u basiskennis van de programmeertaal C# nodig, moet u de Aspose.PDF voor .NET-bibliotheek op uw systeem hebben geïnstalleerd en moet u beschikken over een geldig PDF-document met een of meer handtekeningvelden.

#### V: Hoe importeer ik de vereiste bibliotheken voor het extractieproces?

A: U kunt de benodigde bibliotheken importeren door de`using` richtlijnen voor`Aspose.Pdf` En`System.IO` aan het begin van uw C#-bestand. Deze richtlijnen stellen u in staat de klassen en methoden te gebruiken die nodig zijn voor het extraheren van handtekeninginformatie.

#### V: Hoe geef ik aan in welk PDF-document de handtekeninginformatie moet worden geëxtraheerd?

 A: U kunt het pad naar het PDF-document instellen door`"YOUR DOCUMENTS DIRECTORY"` met het werkelijke pad naar uw document in het meegeleverde codefragment. Dit pad wordt gebruikt om het PDF-document te laden waaruit u handtekeninginformatie wilt extraheren.

#### V: Hoe wordt handtekeninginformatie uit een PDF-document gehaald?

A: Het extractieproces omvat het doorlopen van de formuliervelden van het PDF-document, controleren of elk veld een handtekeningveld is en zo ja, het extraheren van het bijbehorende certificaat. Het geëxtraheerde certificaat kan worden opgeslagen als een bestand voor verdere analyse of validatie.

#### V: Hoe wordt het certificaat uit een handtekeningveld geëxtraheerd?

A: Het certificaat wordt uit een handtekeningveld gehaald met behulp van de`ExtractCertificate()` methode voorzien door de`SignatureField` klasse in Aspose.PDF voor .NET. Deze methode retourneert een stream met de certificaatgegevens.

#### V: Hoe kan ik het uitgepakte certificaat als bestand opslaan?

 A: U kunt het geëxtraheerde certificaat opslaan als een bestand door de certificaatstroom te lezen en de inhoud ervan naar een bestand te schrijven met behulp van de`FileStream` klasse. De code in de tutorial demonstreert dit proces.

#### V: Kan ik dit geëxtraheerde certificaat gebruiken voor handtekeningvalidatie?

A: Ja, het geëxtraheerde certificaat kan worden gebruikt voor handtekeningvalidatie. U kunt de details van het certificaat analyseren en de authenticiteit ervan verifiëren om de integriteit van het ondertekende document te garanderen.

#### V: Hoe kan ik deze code integreren in mijn eigen applicaties?

A: U kunt de meegeleverde code integreren in uw eigen C#-applicaties door de stapsgewijze handleiding te volgen. Wijzig de paden en bestandsnamen indien nodig en neem de code op in uw bestaande projecten.

#### V: Zijn er nog andere functies in Aspose.PDF voor .NET die verband houden met handtekeningbeheer?

A: Ja, Aspose.PDF voor .NET biedt een reeks functies voor het werken met digitale handtekeningen, waaronder het ondertekenen van documenten, het verifiëren van handtekeningen en het toevoegen van tijdstempelinformatie. U kunt de officiële documentatie raadplegen voor meer details over deze functies.

#### V: Waar kan ik aanvullende bronnen vinden voor het gebruik van Aspose.PDF voor .NET?

 A: Voor meer informatie, tutorials en bronnen over het gebruik van Aspose.PDF voor .NET,[Aspose.PDF voor .NET](https://reference.aspose.com/pdf/net/).

#### V: Is het mogelijk om handtekeningen uit versleutelde PDF-documenten te halen?

A: De mogelijkheid om handtekeningen uit gecodeerde PDF-documenten te halen, kan afhankelijk zijn van de coderingsinstellingen en machtigingen van het document. Mogelijk moet u ervoor zorgen dat u de benodigde machtigingen hebt om toegang te krijgen tot en handtekeninginformatie te halen.

#### V: Kan ik meerdere handtekeningen uit één PDF-document halen?

A: Ja, u kunt de meegeleverde code aanpassen om door alle handtekeningvelden in het PDF-document te itereren en handtekeninginformatie uit elk veld te halen. Hiermee kunt u informatie over meerdere handtekeningen in het document halen.

#### V: Wat zijn enkele praktische use cases voor het extraheren van handtekeninginformatie?

A: Enkele praktische toepassingsgevallen voor het extraheren van handtekeninginformatie zijn het valideren van de authenticiteit van digitaal ondertekende documenten, het analyseren van certificaatgegevens voor nalevingsdoeleinden en het bijhouden van een register van handtekeningen en ondertekenaars voor auditdoeleinden.

#### V: Zijn er juridische overwegingen bij het extraheren van handtekeninginformatie?

A: Het extraheren van handtekeninginformatie kan juridische implicaties hebben, vooral bij het verwerken van juridisch bindende documenten. Zorg ervoor dat u voldoet aan de relevante regelgeving en wetten met betrekking tot elektronische handtekeningen en documentauthenticiteit in uw rechtsgebied.