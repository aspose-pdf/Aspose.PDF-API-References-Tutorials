---
title: Informazioni sull'immagine
linktitle: Informazioni sull'immagine
second_title: Aspose.PDF per riferimento API .NET
description: Estrarre le informazioni sull'immagine in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-images/image-information/
---

Questa guida ti guiderà passo dopo passo su come estrarre informazioni sulle immagini in un file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e procedi nel seguente modo:

## Passaggio 1: definire la directory dei documenti

 Assicurati di impostare la directory dei documenti corretta. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il file PDF di origine

 In questo passaggio, caricheremo il file PDF di origine utilizzando l'estensione`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Passaggio 3: imposta la risoluzione predefinita

In questo passaggio, imposteremo la risoluzione predefinita per le immagini. Nell'esempio, la risoluzione predefinita è impostata su 72.

```csharp
int defaultResolution = 72;
```

## Passaggio 4: inizializza oggetti e contatori

In questo passaggio, inizializzeremo gli oggetti e i contatori necessari per recuperare le informazioni sull'immagine.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Passaggio 5: scorrere gli operatori sulla prima pagina del documento

In questa fase, esamineremo gli operatori sulla prima pagina del documento per identificare le operazioni relative alle immagini.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Passaggio 6: gestire gli operatori ed estrarre le informazioni sull'immagine

In questa fase, gestiremo i diversi tipi di operatori ed estrarremo le informazioni sulle immagini.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Gestisci le operazioni GSave e GRestore per le trasformazioni
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Gestire l'operazione ConcatenateMatrix per le trasformazioni
else if (opCtm != null)
{
     // Applicare la matrice di trasformazione
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Gestire l'operazione Do per le immagini
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Recupera l'immagine
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Recupera le dimensioni dell'immagine
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calcolare la risoluzione in base alle informazioni di cui sopra
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Visualizza informazioni sull'immagine
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Esempio di codice sorgente per le informazioni sull'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il file PDF di origine
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definire la risoluzione predefinita per l'immagine
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definisci l'oggetto dell'elenco di array che conterrà i nomi delle immagini
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Inserisci un oggetto da impilare
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Ottieni tutti gli operatori sulla prima pagina del documento
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilizza gli operatori GSave/GRestore per ripristinare le trasformazioni impostate in precedenza
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Crea un'istanza dell'oggetto ConcatenateMatrix in quanto definisce la matrice di trasformazione corrente.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Create Do operatore che disegna oggetti dalle risorse. Disegna oggetti Form e oggetti Immagine
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Salva lo stato precedente e sposta lo stato corrente in cima allo stack
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Elimina lo stato attuale e ripristina quello precedente
		graphicsState.Pop();
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
		// Moltiplica la matrice corrente per la matrice di stato
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Nel caso in cui si tratti di un operatore di disegno di immagini
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Crea un oggetto XImage per contenere le immagini della prima pagina pdf
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Ottieni le dimensioni dell'immagine
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Ottieni informazioni su altezza e larghezza dell'immagine
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Risoluzione del calcolo basata sulle informazioni di cui sopra
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Visualizza le informazioni sulle dimensioni e sulla risoluzione di ciascuna immagine
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai imparato come estrarre le informazioni sull'immagine in un file PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare queste informazioni per varie attività di elaborazione delle immagini nelle applicazioni.