---
title: Ottieni filigrana dal file PDF
linktitle: Ottieni filigrana dal file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre le filigrane dai file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-stamps-and-watermarks/get-watermark/
---
In questo tutorial, ti guideremo passo dopo passo su come ottenere una filigrana da un file PDF usando Aspose.PDF per .NET. Ti mostreremo come usare il codice sorgente C# fornito per scorrere gli artefatti di una pagina specifica e ottenere il tipo, il testo e la posizione della filigrana.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET è stata scaricata e a cui si fa riferimento nel progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passo è caricare il documento PDF esistente nel tuo progetto. Ecco come:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Apri il documento PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Assicurati di sostituire "DIRECTORY DEI TUOI DOCUMENTI" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Fase 3: Ottenere la filigrana

Ora che hai caricato il documento PDF, puoi scorrere gli artefatti di pagina specifici per ottenere le informazioni sulla filigrana. Ecco come:

```csharp
// Esplora gli artefatti e ottieni il sottotipo, il testo e la posizione della filigrana
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Il codice sopra riportato scorre tutti gli artefatti presenti nella prima pagina del documento PDF e visualizza il sottotipo, il testo e il rettangolo (posizione) di ogni filigrana riscontrata.

### Esempio di codice sorgente per Get Watermark utilizzando Aspose.PDF per .NET 
```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Scorrere e ottenere il tipo di vasca, il testo e la posizione dell'artefatto
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusione

Congratulazioni! Hai imparato come ottenere informazioni sulla filigrana da un documento PDF usando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per analizzare ed elaborare le filigrane nei tuoi documenti PDF.

### FAQ per ottenere la filigrana da un file PDF

#### D: Cos'è una filigrana in un documento PDF e perché dovrei estrarne le informazioni?

R: Una filigrana in un documento PDF è un'immagine o un testo riconoscibile che viene sovrapposto al contenuto del documento, spesso per indicarne lo stato, la proprietà o la natura riservata. L'estrazione delle informazioni sulla filigrana può essere utile per analizzare l'autenticità del documento, identificare la fonte del documento o elaborare i documenti in base alla presenza della filigrana.

#### D: In che modo il codice sorgente C# fornito aiuta a estrarre le informazioni sulla filigrana da un file PDF?

 A: Il codice fornito dimostra come caricare un documento PDF esistente, scorrere gli artefatti di una pagina specifica ed estrarre informazioni sulle filigrane. Lo fa accedendo a`Subtype`, `Text` , E`Rectangle` proprietà di ciascun manufatto.

####  D: Cosa significa?`Subtype` property of an artifact represent?

 A: Il`Subtype` proprietà di un artefatto rappresenta il tipo di artefatto. Per le filigrane, indica che l'artefatto è una filigrana.

#### D: In che modo il codice determina la posizione (rettangolo) della filigrana sulla pagina?

 A: Il codice utilizza il`Rectangle` proprietà dell'artefatto per determinare la posizione della filigrana. Il`Rectangle` la proprietà rappresenta il rettangolo di delimitazione dell'artefatto sulla pagina.

#### D: Posso modificare il codice per estrarre informazioni aggiuntive sulla filigrana, come il suo aspetto o il suo colore?

R: Sì, puoi modificare il codice per accedere ad altre proprietà dell'artefatto, come l'aspetto o il colore, se tali informazioni sono disponibili e pertinenti al tuo caso d'uso.

#### D: Posso estrarre le informazioni della filigrana da più pagine di un documento PDF utilizzando questo codice?

R: Sì, puoi modificare il codice per scorrere gli artefatti su più pagine cambiando l'indice della pagina nel ciclo per accedere agli artefatti da pagine diverse.

#### D: Cosa succede se non ci sono filigrane nella pagina specificata?

R: Se nella pagina specificata non sono presenti filigrane, il ciclo non verrà eseguito e non verranno visualizzate informazioni sulla filigrana.

#### D: Come posso utilizzare le informazioni estratte dalla filigrana per ulteriori elaborazioni?

R: Le informazioni estratte dalla filigrana possono essere utilizzate per vari scopi, come la registrazione, l'analisi, la creazione di report o l'automazione di azioni specifiche in base alla presenza o alle proprietà delle filigrane.

#### D: Posso modificare questo codice per estrarre informazioni su altri tipi di artefatti in un documento PDF?

R: Sì, è possibile modificare il codice per estrarre informazioni su altri tipi di artefatti accedendo alle loro proprietà utilizzando un approccio simile.

#### D: Come posso accedere alle filigrane che non sono artefatti ma fanno parte del contenuto del PDF?

R: Le filigrane che non sono artefatti possono essere parte del contenuto PDF stesso, come immagini o testo. Per estrarre informazioni su questi tipi di filigrane, potrebbe essere necessario analizzare il contenuto PDF e identificare elementi specifici che rappresentano le filigrane.