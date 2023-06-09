---
title: Estrai il testo dall'annotazione del timbro
linktitle: Estrai il testo dall'annotazione del timbro
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre facilmente il testo da un'annotazione di timbro nei tuoi documenti PDF con Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
In questo tutorial, ti guideremo passo dopo passo su come estrarre il testo da un'annotazione di timbro in un documento PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per estrarre il testo da un'annotazione di timbro specifica su una determinata pagina del documento PDF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento
Document doc = new Document(dataDir + "test.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: estrarre il testo dall'annotazione del timbro

Ora che hai caricato il documento PDF, puoi estrarre il testo dall'annotazione specifica del timbro. Ecco come:

```csharp
// Recupera l'annotazione del buffer
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Crea un assorbitore di testo
TextAbsorber ta = new TextAbsorber();

// Visita l'aspetto dell'annotazione
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Visualizza il testo estratto
Console.WriteLine(ta.Text);
```

Il codice precedente recupera l'annotazione del timbro dalla pagina specificata del documento PDF e quindi utilizza un assorbitore di testo per estrarre il testo dall'aspetto dell'annotazione. Il testo estratto viene quindi visualizzato nell'output.

### Esempio di codice sorgente per estrarre il testo dall'annotazione del timbro utilizzando Aspose.PDF per .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Conclusione

Congratulazioni! Hai imparato come estrarre il testo da un'annotazione di timbro in un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi utilizzare questo metodo per estrarre il testo da altre annotazioni nei tuoi documenti PDF.
