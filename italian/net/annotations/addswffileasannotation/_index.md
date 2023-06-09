---
title: Aggiungi file Swf come annotazione
linktitle: Aggiungi file Swf come annotazione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come aggiungere file SWF come annotazioni in Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 30
url: /it/net/annotations/addswffileasannotation/
---
Se sei uno sviluppatore .NET che desidera aggiungere un file multimediale SWF come annotazione al tuo documento PDF utilizzando Aspose.PDF per .NET, questa guida passo-passo è per te. In questo articolo spiegheremo come aggiungere file SWF come annotazioni nei documenti PDF utilizzando il linguaggio di programmazione C#. 

Segui i passaggi seguenti per aggiungere un file SWF come annotazione nel documento PDF utilizzando Aspose.PDF per .NET:

## Passaggio 1: impostare il percorso della directory

Innanzitutto, dobbiamo impostare il percorso della directory in cui sono archiviati il file PDF e il file SWF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso della tua cartella dei documenti.

## Passaggio 2: caricare il documento PDF

Successivamente, dobbiamo caricare il documento PDF utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Questo codice caricherà il file "AddSwfFileAsAnnotation.pdf" dalla directory del documento.

## Passaggio 3: ottenere la pagina per aggiungere l'annotazione

Ora, dobbiamo ottenere il riferimento della pagina a cui vogliamo aggiungere l'annotazione. In questo tutorial, aggiungeremo l'annotazione alla prima pagina del documento.

```csharp
Page page = doc.Pages[1];
```

## Passaggio 4: creare un oggetto ScreenAnnotation

 Ora possiamo creare un file`ScreenAnnotation` oggetto con il file SWF come argomento.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 IL`ScreenAnnotation` costruttore prende tre argomenti:

- `page`: la pagina a cui verrà aggiunta l'annotazione.
- `rectangle`: il rettangolo in cui verrà visualizzato il file SWF sulla pagina.
- `dataDir + "input.swf"`: il percorso del file SWF.

## Passaggio 5: aggiungere l'annotazione alla pagina

Ora possiamo aggiungere l'annotazione alla raccolta di annotazioni della pagina.

```csharp
page.Annotations.Add(annotation);
```

## Passaggio 6: salvare il documento PDF aggiornato

Infine, dobbiamo salvare il documento PDF aggiornato con l'annotazione utilizzando il seguente codice:

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Questo codice salverà il documento PDF aggiornato con l'annotazione come "AddSwfFileAsAnnotation_out.pdf" nella directory del documento.

### Codice sorgente di esempio per l'aggiunta di file SWF come annotazione utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

// Ottenere il riferimento della pagina a cui è necessario aggiungere l'annotazione
Page page = doc.Pages[1];

// Crea un oggetto ScreenAnnotation con un file multimediale .swf come argomento
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

// Aggiungi l'annotazione alla raccolta di annotazioni della pagina
page.Annotations.Add(annotation);

dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
// Salva il documento PDF aggiornato con l'annotazione
doc.Save(dataDir);
```        
