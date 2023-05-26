---
title: lnk Larghezza della linea di annotazione
linktitle: lnk Larghezza della linea di annotazione
second_title: Aspose.PDF per riferimento API .NET
description: Questo articolo fornisce una guida dettagliata per l'impostazione della larghezza della linea dell'annotazione lnk utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF è uno strumento potente e ampiamente utilizzato per lavorare con i file PDF nelle applicazioni .NET. Fornisce una varietà di funzionalità per la creazione, la modifica e la manipolazione di file PDF, inclusa la possibilità di aggiungere annotazioni alle pagine. In questo tutorial, spiegheremo come impostare la larghezza della linea di un'annotazione di collegamento utilizzando Aspose.PDF per .NET.

Dopo aver ottenuto questi prerequisiti, creare un nuovo progetto di applicazione console in Visual Studio. Aggiungere quindi un riferimento alla libreria Aspose.PDF per .NET facendo clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, selezionando "Gestisci pacchetti NuGet" e cercando "Aspose.PDF" in Gestione pacchetti NuGet.

Per aggiungere un'annotazione lnk a un documento PDF, attenersi alla seguente procedura:

##  Crea un nuovo`Document` object.
```csharp
Document doc = new Document();
```
## Aggiungi una nuova pagina al documento.
```csharp
doc.Pages.Add();
```
##  Crea un elenco di`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Crea un nuovo`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Crea un nuovo`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Aggiungi il gesto all'elenco dei gesti input penna.
```csharp
inkList.Add(gesture);
```
##  Crea un nuovo`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Impostare l'oggetto e il titolo dell'annotazione.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Imposta il colore dell'annotazione.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Crea un nuovo`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Aggiungi l'annotazione alla pagina.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Salva il documento in un file.
```c// Save output file
doc.Save(dataDir);


```
### L'esempio mostra lnk Annotation Line Width con Aspose.PDF per .NET

```csharp


// Il percorso della directory dei documenti.
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
// Salva il file di output
doc.Save(dataDir);


```
