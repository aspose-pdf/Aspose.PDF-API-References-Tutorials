---
title: Ottieni filigrana da file PDF
linktitle: Ottieni filigrana da file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come estrarre filigrane da file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-stamps-and-watermarks/get-watermark/
---
In questo tutorial, ti guideremo passo dopo passo su come ottenere una filigrana da un file PDF utilizzando Aspose.PDF per .NET. Ti mostreremo come utilizzare il codice sorgente C# fornito per scorrere gli artefatti di una pagina specifica e ottenere il tipo di filigrana, il testo e la posizione.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di avere quanto segue:

- Un ambiente di sviluppo .NET installato.
- La libreria Aspose.PDF per .NET scaricata e referenziata nel tuo progetto.

## Passaggio 2: caricamento del documento PDF

Il primo passaggio consiste nel caricare il documento PDF esistente nel progetto. Ecco come:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Apri il documento PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Assicurati di sostituire "YOUR DOCUMENTI DIRECTORY" con il percorso effettivo della directory in cui si trova il tuo documento PDF.

## Passaggio 3: ottenere la filigrana

Ora che hai caricato il documento PDF, puoi scorrere gli artefatti specifici della pagina per ottenere le informazioni sulla filigrana. Ecco come:

```csharp
// Sfoglia gli artefatti e ottieni il sottotipo, il testo e la posizione della filigrana
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Il codice precedente scorre tutti gli artefatti sulla prima pagina del documento PDF e visualizza il sottotipo, il testo e il rettangolo (posizione) di ogni filigrana incontrata.

### Esempio di codice sorgente per Ottieni filigrana utilizzando Aspose.PDF per .NET 
```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri documento
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Scorri e ottieni il tipo di vasca, il testo e la posizione dell'artefatto
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusione

Congratulazioni! Hai imparato come ottenere informazioni sulla filigrana da un documento PDF utilizzando Aspose.PDF per .NET. Ora puoi usare questa conoscenza per analizzare ed elaborare filigrane nei tuoi documenti PDF.

### Domande frequenti per ottenere la filigrana dal file PDF

#### D: Cos'è una filigrana in un documento PDF e perché dovrei estrarne le informazioni?

R: Una filigrana in un documento PDF è un'immagine o un testo riconoscibile che viene sovrapposto al contenuto del documento, spesso per indicarne lo stato, la proprietà o la natura riservata. L'estrazione delle informazioni sulla filigrana può essere utile per analizzare l'autenticità del documento, identificare l'origine del documento o elaborare i documenti in base alla presenza della filigrana.

#### D: In che modo il codice sorgente C# fornito aiuta nell'estrazione delle informazioni sulla filigrana da un file PDF?

 R: Il codice fornito mostra come caricare un documento PDF esistente, scorrere gli artefatti di una pagina specifica ed estrarre informazioni sulle filigrane. Lo fa accedendo al file`Subtype`, `Text` , E`Rectangle` proprietà di ciascun artefatto.

####  D: Che cosa significa`Subtype` property of an artifact represent?

 R: Il`Subtype` proprietà di un artefatto rappresenta il tipo dell'artefatto. Per le filigrane, indica che l'artefatto è una filigrana.

#### D: In che modo il codice determina la posizione (rettangolo) della filigrana sulla pagina?

 R: Il codice usa il`Rectangle` proprietà del manufatto per determinare la posizione della filigrana. IL`Rectangle` La proprietà rappresenta il rettangolo di delimitazione dell'artefatto nella pagina.

#### D: Posso modificare il codice per estrarre ulteriori informazioni sulla filigrana, come il suo aspetto o il colore?

R: Sì, puoi modificare il codice per accedere ad altre proprietà dell'artefatto, come l'aspetto o il colore, se tali informazioni sono disponibili e pertinenti al tuo caso d'uso.

#### D: Posso estrarre informazioni sulla filigrana da più pagine di un documento PDF utilizzando questo codice?

R: Sì, puoi modificare il codice per scorrere gli artefatti su più pagine modificando l'indice della pagina nel ciclo per accedere agli artefatti da pagine diverse.

#### D: Cosa succede se non ci sono filigrane sulla pagina specificata?

R: Se non sono presenti filigrane nella pagina specificata, il ciclo non verrà eseguito e non verranno visualizzate informazioni sulla filigrana.

#### D: Come posso utilizzare le informazioni sulla filigrana estratte per un'ulteriore elaborazione?

R: Le informazioni sulla filigrana estratte possono essere utilizzate per vari scopi, come la registrazione, l'analisi, il reporting o l'automazione di azioni specifiche basate sulla presenza o sulle proprietà delle filigrane.

#### D: Posso modificare questo codice per estrarre informazioni su altri tipi di artefatti in un documento PDF?

R: Sì, puoi modificare il codice per estrarre informazioni su altri tipi di artefatti accedendo alle loro proprietà utilizzando un approccio simile.

#### D: Come posso accedere a filigrane che non sono artefatti ma fanno parte del contenuto PDF?

R: Le filigrane che non sono artefatti possono far parte del contenuto PDF stesso, come immagini o testo. Per estrarre informazioni su questi tipi di filigrane, potrebbe essere necessario analizzare il contenuto del PDF e identificare gli elementi specifici che rappresentano le filigrane.