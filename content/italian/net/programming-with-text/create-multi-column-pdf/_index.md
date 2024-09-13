---
title: Crea PDF multicolonna
linktitle: Crea PDF multicolonna
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare un PDF multicolonna utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-text/create-multi-column-pdf/
---
Questo tutorial ti guiderà attraverso il processo di creazione di un PDF multicolonna usando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi creare un PDF multicolonna, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: creare una nuova istanza del documento
 Crea un'istanza di un nuovo`Document` oggetto aggiungendo la seguente riga di codice:

```csharp
Document doc = new Document();
```

## Passaggio 5: impostare i margini della pagina
 Specificare le informazioni sul margine sinistro e destro del file PDF utilizzando`PageInfo.Margin` proprietà del`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Passaggio 6: aggiungere una pagina al documento
 Aggiungere una nuova pagina al documento utilizzando`Add` metodo del`Pages` raccolta. Nel codice fornito, la nuova pagina è assegnata alla variabile`page`.

```csharp
Page page = doc.Pages.Add();
```

## Passaggio 7: creare un oggetto grafico e aggiungere una linea
 Crea un nuovo`Graph` oggetto con dimensioni specifiche e aggiungi una linea ad esso. Quindi, aggiungi il`Graph` opporsi al`Paragraphs` raccolta della pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Passaggio 8: aggiungere il testo dell'intestazione con formattazione HTML
 Crea un`HtmlFragment` oggetto e imposta il suo contenuto sul testo HTML desiderato. Quindi, aggiungi il frammento al`Paragraphs` raccolta della pagina.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Passaggio 9: creare un FloatingBox con più colonne
 Crea un`FloatingBox` oggetto e imposta il numero di colonne e la spaziatura delle colonne. Quindi, aggiungi frammenti di testo e una riga al`Paragraphs` raccolta di`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Passaggio 10: Salvare il documento PDF
 Salvare il documento PDF utilizzando`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir);
```

### Esempio di codice sorgente per creare PDF multicolonna utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Specificare le informazioni sul margine sinistro per il file PDF
doc.PageInfo.Margin.Left = 40;
// Specificare le informazioni sul margine destro per il file PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Aggiungere la riga alla raccolta di paragrafi dell'oggetto sezione
page.Paragraphs.Add(graph1);
// Specificare le coordinate per la linea
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Crea variabili stringa con testo contenente tag html
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Crea paragrafi di testo contenenti testo HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Aggiungere quattro colonne nella sezione
box.ColumnInfo.ColumnCount = 2;
// Imposta la spaziatura tra le colonne
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Crea un oggetto grafico per disegnare una linea
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Specificare le coordinate per la linea
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//Aggiungere la riga alla raccolta di paragrafi dell'oggetto sezione
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Salva file PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusione
Hai creato con successo un PDF multicolonna usando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo di questo tutorial?

Questo tutorial è incentrato sulla guida attraverso il processo di creazione di un PDF multicolonna utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali namespace dovrei importare per questo tutorial?

A: Nel file di codice in cui vuoi creare un PDF multicolonna, importa i seguenti namespace all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Nel codice, trova la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come posso creare una nuova istanza di Documento?

 A: Nel passaggio 4, creerai un nuovo`Document` oggetto utilizzando il codice fornito.

#### D: Come si impostano i margini della pagina?

 A: Nel passaggio 5, utilizzerai il`PageInfo.Margin` proprietà del`Document` per specificare le informazioni sui margini sinistro e destro del file PDF.

#### D: Come posso aggiungere una pagina al documento?

 A: Nel passaggio 6, aggiungerai una nuova pagina al documento utilizzando`Add` metodo del`Pages` collezione.

#### D: Come posso creare un oggetto Graph e aggiungere una linea?

 A: Nel passaggio 7, creerai un nuovo`Graph` oggetto, aggiungi una linea ad esso, quindi aggiungi il`Graph` opporsi al`Paragraphs` raccolta della pagina.

#### D: Come posso aggiungere un testo di intestazione con formattazione HTML?

A: Nel passaggio 8, creerai un`HtmlFragment` oggetto e imposta il suo contenuto sul testo HTML desiderato, quindi aggiungi il frammento al`Paragraphs` raccolta della pagina.

#### D: Come posso creare un FloatingBox con più colonne?

 A: Nel passaggio 9, creerai un`FloatingBox` oggetto con più colonne e spaziatura tra le colonne, quindi aggiungere frammenti di testo e una riga al`Paragraphs` raccolta di`FloatingBox`.

#### D: Come posso salvare il documento PDF?

 A: Nel passaggio 10, salverai il documento PDF utilizzando`Save` metodo del`Document` oggetto.

#### D: Qual è la cosa più importante da imparare da questo tutorial?

R: Seguendo questo tutorial, hai imparato a creare un documento PDF multicolonna usando Aspose.PDF per .NET. Questo può essere utile per visualizzare il contenuto in un layout strutturato e organizzato.