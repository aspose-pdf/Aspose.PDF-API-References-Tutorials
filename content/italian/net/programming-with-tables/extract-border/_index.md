---
title: Estrai bordo nel file PDF
linktitle: Estrai bordo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre il bordo nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-tables/extract-border/
---
In questo tutorial impareremo come estrarre il bordo nel file PDF utilizzando Aspose.PDF per .NET. Spiegheremo passo dopo passo il codice sorgente in C#. Alla fine di questo tutorial saprai come estrarre il bordo da un documento PDF e salvarlo come immagine. Iniziamo!

## Passaggio 1: configurazione dell'ambiente
Innanzitutto, assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa gli spazi dei nomi necessari.

## Passaggio 2: caricamento del documento PDF
In questo passaggio, carichiamo il documento PDF dal file specificato.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con la directory effettiva in cui si trova il tuo file PDF.

## Passaggio 3: estrazione dei bordi
Estrarremo il bordo dal documento PDF eseguendo un'iterazione sulle operazioni contenute nel documento.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Elaborare tutte le operazioni sui contenuti
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Verificare il tipo di operazione
         // ...
         // Aggiungi codice per elaborare ogni operazione
     }
}
```

 Creiamo un`graphicsState` stack per memorizzare gli stati grafici, un'immagine bitmap per catturare il bordo estratto, a`GraphicsPath` oggetto per memorizzare percorsi di disegno e altre variabili per tenere traccia dello stato e dei colori.

## Passaggio 4: elaborazione delle transazioni
In questa fase, elaboriamo ogni operazione del documento per estrarre il confine.

```csharp
// Verificare il tipo di operazione
if (opSaveState != null)
{
     // Salva lo stato precedente e sposta lo stato corrente in cima allo stack
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Elimina lo stato corrente e ripristina lo stato precedente
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Recupera la matrice di trasformazione corrente
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Moltiplica la matrice corrente per la matrice degli stati
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Aggiorna l'ultimo punto del disegno
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Elabora il disegno di una linea
     // ...
     // Aggiungi codice per gestire il disegno di una linea
}
// ...
// Aggiungi altro se blocca per altre operazioni
```

Controlliamo il tipo di operazione utilizzando le condizioni ed eseguiamo il codice appropriato per ciascuna operazione.

## Passaggio 5: backup dell'immagine
Infine, salviamo l'immagine bitmap contenente il bordo estratto in un file specificato.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Assicurati di specificare la directory e il nome file corretti per salvare l'immagine di output.

### Codice sorgente di esempio per Extract Border utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Il valore predefinito della matrice ctm è 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Il sistema di coordinate del disegno è in alto a sinistra, mentre il sistema di coordinate pdf è in basso a sinistra, quindi dobbiamo applicare la matrice di inversione
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Elabora tutti i comandi dei contenuti
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Salva lo stato precedente e sposta lo stato corrente in cima allo stack
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Elimina lo stato attuale e ripristina quello precedente
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// Moltiplicare la matrice corrente per la matrice degli stati
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come estrarre il bordo da un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questa guida passo passo per estrarre il bordo da altri documenti PDF.

### Domande frequenti sull'estrazione del bordo nel file PDF

#### D: Qual è lo scopo di estrarre il bordo da un file PDF?

R: Estrarre il bordo da un file PDF può essere utile per vari scopi. Permette di isolare e analizzare gli elementi strutturali del documento, come tabelle, diagrammi o elementi grafici. È possibile utilizzare il bordo estratto per identificare il layout, le dimensioni e il posizionamento del contenuto all'interno del documento PDF.

#### D: Posso estrarre il bordo da pagine o aree specifiche del documento PDF?

R: Sì, puoi modificare il codice sorgente C# fornito per estrarre il bordo da pagine o aree specifiche all'interno del documento PDF. Manipolando il`doc.Pages` raccolta e specificando criteri personalizzati, è possibile scegliere di estrarre il bordo da particolari pagine o aree di interesse.

#### D: Come posso personalizzare il formato e la qualità dell'immagine di output?

 R: Nel codice C# fornito, il bordo estratto viene salvato come immagine PNG. Se desideri modificare il formato dell'immagine di output, puoi modificare il file`ImageFormat.Png` parametro nel`bitmap.Save` metodo ad altri formati immagine supportati, come JPEG, BMP o GIF. Inoltre, puoi regolare la qualità dell'immagine o le impostazioni di compressione in base alle tue esigenze.

#### D: Quali altre operazioni posso eseguire sul confine estratto?

R: Una volta estratto il bordo come immagine, è possibile elaborarlo ulteriormente utilizzando librerie o algoritmi di elaborazione delle immagini. È possibile analizzare l'immagine, applicare filtri immagine, rilevare modelli o eseguire l'OCR (riconoscimento ottico dei caratteri) per estrarre testo dall'immagine, se necessario.

#### D: Esistono limitazioni o considerazioni durante l'estrazione dei bordi da documenti PDF complessi?

R: Il processo di estrazione può variare a seconda della complessità del documento PDF. PDF complessi con più livelli, trasparenza o grafica avanzata potrebbero richiedere ulteriori elaborazioni o regolazioni per estrarre con precisione il bordo. È essenziale testare a fondo il processo di estrazione su vari documenti PDF per garantire risultati affidabili.