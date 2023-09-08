---
title: Estrazione dell'immagine
linktitle: Estrazione dell'immagine
second_title: Aspose.PDF per riferimento all'API .NET
description: Estrai facilmente immagini da documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 70
url: /it/net/programming-with-security-and-signatures/extracting-image/
---
Estrarre immagini da un documento PDF può essere utile in molti casi. Con Aspose.PDF per .NET, puoi estrarre facilmente le immagini utilizzando il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio è necessario specificare il percorso della cartella contenente il file PDF da cui si desidera estrarre l'immagine. Sostituire`"YOUR DOCUMENTS DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Passaggio 3: estrai l'immagine dal documento PDF

Ora estrarremo l'immagine dal documento PDF utilizzando il seguente codice:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

In questo esempio, eseguiamo il looping di ciascun campo del modulo nel documento PDF. Se viene trovato un campo firma, estraiamo l'immagine associata e la salviamo in un file JPEG.

### Codice sorgente di esempio per l'estrazione dell'immagine utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per estrarre immagini da un documento PDF utilizzando Aspose.PDF per .NET. Puoi integrare questo codice nei tuoi progetti per estrarre immagini e utilizzarle secondo necessità.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sull'estrazione avanzata delle immagini e sulle funzionalità di manipolazione dei documenti PDF.


### Domande frequenti

#### D: Aspose.PDF per .NET è adatto ai principianti?

R: Sebbene sia utile una certa familiarità con la programmazione C#, il nostro tutorial è progettato per essere adatto ai principianti e guidarti attraverso ogni passaggio.

#### D: Posso estrarre più immagini contemporaneamente?

R: Assolutamente! Implementando i loop e adattando il codice fornito, puoi estrarre più immagini da un singolo documento PDF.

#### D: Aspose.PDF per .NET è l'unica soluzione per l'estrazione delle immagini?

R: Sebbene siano disponibili altri strumenti, Aspose.PDF per .NET è rinomato per la sua efficienza e funzionalità complete.

#### D: Posso utilizzare le immagini estratte per scopi commerciali?

R: Sì, una volta estratte, le immagini sono tue e puoi utilizzarle secondo necessità, anche per progetti commerciali.

#### D: Dove posso trovare più risorse sulla manipolazione dei PDF con Aspose.PDF?

R: Visita la nostra documentazione ufficiale per una vasta gamma di risorse e approfondimenti sulla manipolazione avanzata dei PDF con Aspose.PDF per .NET.