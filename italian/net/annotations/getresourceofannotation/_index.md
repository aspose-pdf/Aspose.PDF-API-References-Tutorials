---
title: Ottieni risorsa di annotazione
linktitle: Ottieni risorsa di annotazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come recuperare la risorsa di un'annotazione utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 90
url: /it/net/annotations/getresourceofannotation/
---

L'esempio mostra come ottenere risorse di annotazione con Aspose.PDF per .NET. Per ottenere la risorsa di un'annotazione utilizzando Aspose.PDF per .NET, attenersi alla seguente procedura:

## Imposta il percorso della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Apri il documento PDF che contiene l'annotazione di cui desideri ottenere la risorsa.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Crea un'annotazione.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Aggiungere l'annotazione a una pagina del documento.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Salva il documento.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Apri il documento modificato.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Ottenere l'azione dell'annotazione.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Ottenere la resa dell'azione.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Prendi la clip multimediale.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Ottieni la specifica del file.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Leggi i dati dei media.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Stampa il nome della resa e l'operazione di resa.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Seguendo questi passaggi, puoi facilmente ottenere la risorsa di un'annotazione in un documento PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Ottieni risorsa di annotazione utilizzando Aspose.PDF per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Apri documento
	Document doc = new Document(dataDir + "AddAnnotation.pdf");
	//Crea annotazione
	ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
	doc.Pages[1].Annotations.Add(sa);
	// Salva documento
	doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
	// Apri documento
	Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
	//Ottenere l'azione dell'annotazione
	RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
	//Ottieni la consegna dell'azione di consegna
	Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
	// Clip multimediale
	MediaClip clip = (rendition as MediaRendition).MediaClip;
	FileSpecification data = (clip as MediaClipData).Data;
	MemoryStream ms = new MemoryStream();
	byte[] buffer = new byte[1024];
	int read = 0;
	//I dati dei supporti sono accessibili in FileSpecification.Contents
	Stream source = data.Contents;
	while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
	{
	ms.Write(buffer, 0, read);
	}
	Console.WriteLine(rendition.Name);
	Console.WriteLine(action.RenditionOperation);

```