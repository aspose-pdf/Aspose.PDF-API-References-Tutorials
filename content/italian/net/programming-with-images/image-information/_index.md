---
title: Informazioni sull'immagine nel file PDF
linktitle: Informazioni sull'immagine nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Estrai le informazioni sull'immagine nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-images/image-information/
---
Questa guida ti guiderà passo passo come estrarre informazioni sulle immagini nel file PDF utilizzando Aspose.PDF per .NET. Assicurati di aver già configurato il tuo ambiente e segui i passaggi seguenti:

## Passaggio 1: definire la directory dei documenti

 Assicurati di impostare la directory dei documenti corretta. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso della directory in cui si trova il documento PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il file PDF di origine

 In questo passaggio, caricheremo il file PDF di origine utilizzando il file`Document` classe di Aspose.PDF. Usa il`Document` costruttore e passare il percorso al documento PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Passaggio 3: imposta la risoluzione predefinita

In questo passaggio, imposteremo la risoluzione predefinita per le immagini. Nell'esempio la risoluzione predefinita è impostata su 72.

```csharp
int defaultResolution = 72;
```

## Passaggio 4: inizializzare oggetti e contatori

In questo passaggio inizializzeremo gli oggetti e i contatori necessari per recuperare le informazioni sull'immagine.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Passaggio 5: scorrere gli operatori sulla prima pagina del documento

In questo passaggio, esamineremo gli operatori sulla prima pagina del documento per identificare le operazioni relative alle immagini.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Passaggio 6: gestire gli operatori ed estrarre le informazioni sull'immagine

In questo passaggio gestiremo le diverse tipologie di operatori ed estrarremo le informazioni sulle immagini.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Gestire le operazioni GSave e GRestore per le trasformazioni
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
         // Recuperare le dimensioni dell'immagine
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calcolare la risoluzione in base alle informazioni di cui sopra
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Visualizza le informazioni sull'immagine
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Codice sorgente di esempio per informazioni sull'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il file PDF di origine
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definire la risoluzione predefinita per l'immagine
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definire l'oggetto dell'elenco di array che conterrà i nomi delle immagini
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Inserisci un oggetto da impilare
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Ottieni tutti gli operatori sulla prima pagina del documento
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilizzare gli operatori GSave/GRestore per ripristinare le trasformazioni impostate in precedenza
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Crea un'istanza dell'oggetto ConcatenateMatrix poiché definisce la matrice di trasformazione corrente.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Crea operatore Do che disegna oggetti dalle risorse. Disegna oggetti Form e oggetti Immagine
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
		// Moltiplicare la matrice corrente per la matrice degli stati
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Nel caso in cui si tratti di un operatore di disegno di immagini
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Crea un oggetto XImage per contenere le immagini della prima pagina PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Ottieni le dimensioni dell'immagine
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Ottieni informazioni su altezza e larghezza dell'immagine
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Calcolare la risoluzione in base alle informazioni di cui sopra
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Visualizza le informazioni su dimensione e risoluzione di ciascuna immagine
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai imparato come estrarre le informazioni sull'immagine in un file PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare queste informazioni per varie attività di elaborazione delle immagini nelle proprie applicazioni.

### Domande frequenti sulle informazioni sulle immagini nel file PDF

#### D: Qual è lo scopo di estrarre informazioni sull'immagine da un documento PDF utilizzando Aspose.PDF per .NET?

R: L'estrazione delle informazioni sull'immagine da un documento PDF fornisce informazioni dettagliate su dimensioni, risoluzione e altri attributi delle immagini all'interno del documento. Queste informazioni possono essere utilizzate per attività di elaborazione, analisi o ottimizzazione delle immagini.

#### D: In che modo Aspose.PDF per .NET aiuta a estrarre informazioni sull'immagine da un documento PDF?

R: Aspose.PDF per .NET fornisce strumenti per accedere e analizzare il contenuto di un documento PDF, comprese le sue immagini. Il codice fornito dimostra come estrarre e visualizzare le informazioni sull'immagine utilizzando vari operatori.

#### D: Che tipo di informazioni sull'immagine possono essere estratte utilizzando questo metodo?

R: Questo metodo consente di estrarre e visualizzare informazioni quali dimensioni in scala, risoluzione e nomi di immagini per le immagini all'interno di un documento PDF.

#### D: In che modo il codice identifica ed elabora gli operatori relativi alle immagini all'interno di un documento PDF?

R: Il codice scorre attraverso gli operatori su una pagina specifica del documento PDF. Identifica ed elabora gli operatori relativi alle operazioni, trasformazioni e rendering delle immagini.

#### D: Qual è il significato della risoluzione predefinita e come viene utilizzata nel codice?

R: La risoluzione predefinita viene utilizzata come punto di riferimento per calcolare la risoluzione effettiva delle immagini. Il codice calcola la risoluzione di ciascuna immagine in base alle sue dimensioni e all'impostazione di risoluzione predefinita.

#### D: Come possono essere utilizzate le informazioni sull'immagine estratte negli scenari del mondo reale?

R: Le informazioni sull'immagine estratte possono essere utilizzate per attività quali la valutazione della qualità dell'immagine, l'ottimizzazione dell'immagine, la generazione di miniature delle immagini e la facilitazione dei processi decisionali relativi alle immagini.

#### D: Posso modificare il codice per estrarre attributi aggiuntivi relativi all'immagine?

R: Sì, puoi personalizzare il codice per estrarre attributi aggiuntivi delle immagini, come spazio colore, profondità pixel o tipo di immagine.

#### D: Il processo di estrazione delle informazioni sulle immagini richiede molto tempo o risorse?

R: Il processo di estrazione delle informazioni sulle immagini è efficiente e ottimizzato per le prestazioni, garantendo un impatto minimo sull'utilizzo delle risorse e sui tempi di elaborazione.

#### D: In che modo gli sviluppatori possono trarre vantaggio dall'identificazione e dall'estrazione di informazioni sulle immagini dai documenti PDF?

R: Gli sviluppatori possono ottenere informazioni approfondite sulle caratteristiche delle immagini all'interno dei documenti PDF, consentendo loro di prendere decisioni informate in merito alla manipolazione, elaborazione e ottimizzazione delle immagini.

#### D: È possibile utilizzare questo metodo per l'elaborazione batch di documenti PDF contenenti immagini?

R: Sì, questo metodo può essere esteso all'elaborazione batch eseguendo l'iterazione di più pagine o documenti, estraendo informazioni sull'immagine ed eseguendo attività relative all'immagine.