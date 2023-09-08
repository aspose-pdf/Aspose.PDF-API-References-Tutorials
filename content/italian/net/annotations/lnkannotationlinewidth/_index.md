---
title: lnk Larghezza della linea di annotazione
linktitle: lnk Larghezza della linea di annotazione
second_title: Aspose.PDF per riferimento all'API .NET
description: Questo articolo fornisce una guida passo passo per impostare la larghezza della linea dell'annotazione lnk utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF è uno strumento potente e ampiamente utilizzato per lavorare con file PDF nelle applicazioni .NET. Fornisce una varietà di funzionalità per creare, modificare e manipolare file PDF, inclusa la possibilità di aggiungere annotazioni alle pagine. In questo tutorial, spiegheremo come impostare la larghezza della linea di un'annotazione di collegamento utilizzando Aspose.PDF per .NET.

Una volta ottenuti questi prerequisiti, creare un nuovo progetto di applicazione console in Visual Studio. Aggiungere quindi un riferimento alla libreria Aspose.PDF per .NET facendo clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, selezionando "Gestisci pacchetti NuGet" e cercando "Aspose.PDF" in Gestione pacchetti NuGet.

Per aggiungere un'annotazione di collegamento a un documento PDF, attenersi alla seguente procedura:

##  Passaggio 1: creane uno nuovo`Document` object.
```csharp
Document doc = new Document();
```
## Passaggio 2: aggiungi una nuova pagina al documento.
```csharp
doc.Pages.Add();
```
##  Passaggio 3: creare un elenco di`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Passaggio 4: creane uno nuovo`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Passaggio 5: creane uno nuovo`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Passaggio 6: aggiungi il gesto all'elenco dei gesti input penna.
```csharp
inkList.Add(gesture);
```
##  Passaggio 7: creane uno nuovo`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Passaggio 8: imposta l'oggetto e il titolo dell'annotazione.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Passaggio 9: imposta il colore dell'annotazione.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Passaggio 10: creane uno nuovo`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Passaggio 11: aggiungi l'annotazione alla pagina.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Passaggio 12: salva il documento in un file.
```csharp
// Salva il file di output
doc.Save(dataDir);


```
### L'esempio mostra la larghezza della linea di annotazione lnk con Aspose.PDF per .NET

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

## Conclusione

In questo tutorial, abbiamo imparato come impostare la larghezza della linea di un'annotazione di collegamento in un documento PDF utilizzando Aspose.PDF per .NET. Aspose.PDF per .NET fornisce un'ampia gamma di strumenti e funzionalità per lavorare con documenti PDF, inclusa la possibilità di creare e personalizzare annotazioni di collegamento. Seguendo la guida passo passo e utilizzando il codice sorgente C# fornito, gli sviluppatori possono aggiungere facilmente collegamenti interattivi ai propri documenti PDF, migliorando l'esperienza utente e l'interattività delle proprie applicazioni. Aspose.PDF per .NET è una libreria versatile che consente agli sviluppatori .NET di lavorare con file PDF in modo efficiente ed efficace.

### Domande frequenti

#### D: Cos'è un'annotazione di collegamento in un documento PDF?

R: Un'annotazione di collegamento in un documento PDF è un elemento interattivo che consente di creare collegamenti ipertestuali o azioni che indirizzano l'utente a un'altra posizione all'interno dello stesso documento, a un sito Web esterno o a un documento PDF diverso.

#### D: Come posso impostare la larghezza della linea di un'annotazione di collegamento utilizzando Aspose.PDF per .NET?

R: Per impostare la larghezza della linea di un'annotazione di collegamento utilizzando Aspose.PDF per .NET, è possibile creare un`InkAnnotation` oggetto e specificare la proprietà della larghezza della linea.

#### D: Quali proprietà possono essere personalizzate per un'annotazione di collegamento in Aspose.PDF per .NET?

R: È possibile personalizzare varie proprietà di un'annotazione di collegamento in Aspose.PDF per .NET, come posizione, dimensione, colore, proprietà del bordo (larghezza, stile, modello di trattino ed effetto), oggetto, titolo e visibilità.

#### D: Posso creare un'annotazione di collegamento che contenga più gesti input penna?

 R: Sì, puoi creare un'annotazione di collegamento che contiene più gesti input penna aggiungendone più`Point` array al`InkAnnotation` oggetto.

#### D: Come posso aggiungere un'annotazione di collegamento a una pagina specifica del documento PDF?

 R: Per aggiungere un'annotazione di collegamento a una pagina specifica del documento PDF, è necessario specificare il numero di pagina durante la creazione del file`InkAnnotation` oggetto. Per esempio,`new InkAnnotation(doc.Pages[1], ...)` aggiunge l'annotazione del collegamento alla prima pagina.