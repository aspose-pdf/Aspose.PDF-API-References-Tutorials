---
title: Imposta i metadati XMP
linktitle: Imposta i metadati XMP
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come impostare XMPMetadata nei file PDF utilizzando Aspose.PDF per .NET. Segui questa guida passo dopo passo.
type: docs
weight: 330
url: /it/net/programming-with-document/setxmpmetadata/
---
In questo articolo, forniremo una guida dettagliata su come utilizzare Aspose.PDF per .NET per impostare i metadati XMP in un file PDF. Forniremo un codice sorgente di esempio completo alla fine dell'articolo.

## Passaggio 1: impostare il percorso della directory dei documenti

Prima di iniziare, dobbiamo impostare il percorso della directory in cui si trova il nostro documento PDF. Memorizzeremo questo percorso in una variabile chiamata "dataDir".

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assicurati di sostituire`YOUR DOCUMENT DIRECTORY` con il percorso effettivo del file PDF.

## Passaggio 2: apri il file PDF

Il primo passaggio consiste nell'aprire il file PDF per il quale desideri impostare i metadati XMP. Per fare ciò, dovrai creare un nuovo file`Document` oggetto e passare il percorso al file PDF.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Passaggio 3: impostare le proprietà dei metadati XMP

Ora che hai aperto il tuo file PDF, puoi iniziare a impostare le proprietà dei metadati XMP. Le proprietà che imposti dipenderanno dalle tue esigenze specifiche, ma qui ci sono alcune proprietà comuni che potresti voler impostare:

- `xmp:CreateDate`: la data di creazione del file PDF.
- `xmp:Nickname`: un soprannome o un alias per il file PDF.
- `xmp:CustomProperty`: una proprietà personalizzata con un valore specificato.

 Per impostare queste proprietà, puoi utilizzare il file`Metadata` proprietà del`Document` oggetto. Ecco un esempio:

```csharp
// Imposta proprietà
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

In questo tutorial, stiamo impostando la data di creazione sulla data e l'ora correnti, il soprannome su "Nickname" e una proprietà personalizzata su "Valore personalizzato". Puoi sostituire questi valori con i tuoi.

## Passaggio 4: salvare il file PDF

 Dopo aver impostato le proprietà dei metadati XMP, devi salvare il file PDF. Per fare questo, puoi usare il`Save` metodo del`Document` oggetto e passare il percorso in cui si desidera salvare il file PDF aggiornato.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//Salva documento
pdfDocument.Save(dataDir);
```

### Esempio di codice sorgente per Set XMPMetadata utilizzando Aspose.PDF per .NET

Ecco il codice sorgente di esempio completo per l'impostazione di XMPMetadata utilizzando Aspose.PDF per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Apri documento
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	// Imposta proprietà
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//Salva documento
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
