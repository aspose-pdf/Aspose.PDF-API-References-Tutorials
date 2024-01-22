---
title: lnk Annotatielijndikte
linktitle: lnk Annotatielijndikte
second_title: Aspose.PDF voor .NET API-referentie
description: Dit artikel biedt een stapsgewijze handleiding voor het instellen van de lijnbreedte van de lnk-annotatie met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF is een krachtige en veelgebruikte tool voor het werken met PDF-bestanden in .NET-toepassingen. Het biedt een verscheidenheid aan functies voor het maken, bewerken en manipuleren van PDF-bestanden, inclusief de mogelijkheid om annotaties aan pagina's toe te voegen. In deze tutorial leggen we uit hoe je de lijndikte van een linkannotatie instelt met Aspose.PDF voor .NET.

Zodra u aan deze vereisten voldoet, maakt u een nieuw consoletoepassingsproject in Visual Studio. Voeg vervolgens een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek door met de rechtermuisknop op het project in de Solution Explorer te klikken, 'NuGet-pakketten beheren' te selecteren en naar 'Aspose.PDF' te zoeken in NuGet Package Manager.

Volg deze stappen om een link-annotatie aan een PDF-document toe te voegen:

##  Stap 1: Maak een nieuwe`Document` object.
```csharp
Document doc = new Document();
```
## Stap 2: Voeg een nieuwe pagina toe aan het document.
```csharp
doc.Pages.Add();
```
##  Stap 3: Maak een lijst van`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Stap 4: Maak een nieuwe`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Stap 5: Maak een nieuwe`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Stap 6: Voeg het gebaar toe aan de lijst met inktgebaren.
```csharp
inkList.Add(gesture);
```
##  Stap 7: Maak een nieuwe`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Stap 8: Stel het onderwerp en de titel van de annotatie in.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Stap 9: Stel de kleur van de annotatie in.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Stap 10: Maak een nieuwe`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Stap 11: Voeg de annotatie toe aan de pagina.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Stap 12: Sla het document op in een bestand.
```csharp
// Sla het uitvoerbestand op
doc.Save(dataDir);


```
### In het voorbeeld wordt de annotatielijndikte gekoppeld aan Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Sla het uitvoerbestand op
doc.Save(dataDir);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de lijndikte van een linkannotatie in een PDF-document kunt instellen met Aspose.PDF voor .NET. Aspose.PDF voor .NET biedt een breed scala aan tools en functies voor het werken met PDF-documenten, inclusief de mogelijkheid om linkannotaties te maken en aan te passen. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig interactieve links aan hun PDF-documenten toevoegen, waardoor de gebruikerservaring en interactiviteit van hun applicaties worden verbeterd. Aspose.PDF voor .NET is een veelzijdige bibliotheek waarmee .NET-ontwikkelaars efficiënt en effectief met PDF-bestanden kunnen werken.

### Veelgestelde vragen

#### Vraag: Wat is een linkannotatie in een PDF-document?

A: Een linkannotatie in een PDF-document is een interactief element waarmee u hyperlinks of acties kunt maken die de gebruiker naar een andere locatie binnen hetzelfde document, een externe website of een ander PDF-document leiden.

#### Vraag: Hoe kan ik de lijndikte van een linkannotatie instellen met Aspose.PDF voor .NET?

A: Om de lijnbreedte van een linkannotatie in te stellen met Aspose.PDF voor .NET, kunt u een`InkAnnotation` object en geef de eigenschap lijnbreedte op.

#### Vraag: Welke eigenschappen kunnen worden aangepast voor een linkannotatie in Aspose.PDF voor .NET?

A: U kunt verschillende eigenschappen van een linkannotatie in Aspose.PDF voor .NET aanpassen, zoals de locatie, grootte, kleur, randeigenschappen (breedte, stijl, streepjespatroon en effect), onderwerp, titel en zichtbaarheid.

#### Vraag: Kan ik een linkannotatie maken die meerdere inktbewegingen bevat?

 A: Ja, u kunt een linkannotatie maken die meerdere inktgebaren bevat door er meerdere toe te voegen`Point` arrays naar de`InkAnnotation` voorwerp.

#### Vraag: Hoe kan ik een linkannotatie toevoegen aan een specifieke pagina van het PDF-document?

 A: Om een linkannotatie aan een specifieke pagina van het PDF-document toe te voegen, moet u het paginanummer opgeven bij het maken van de link.`InkAnnotation` voorwerp. Bijvoorbeeld,`new InkAnnotation(doc.Pages[1], ...)` voegt de linkannotatie toe aan de eerste pagina.