---
title: Configura le chiavi di licenza a consumo nel file PDF
linktitle: Configura le chiavi di licenza a consumo nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per impostare chiavi di licenza misurate in un file PDF con Aspose.PDF per .NET e beneficiare di funzionalità avanzate.
type: docs
weight: 10
url: /it/net/licensing-aspose-pdf/configure-metered-license/
---
In questo tutorial, ti guideremo passo dopo passo su come impostare chiavi di licenza misurate nel file PDF con Aspose.PDF per .NET. La licenza misurata ti consente di utilizzare le funzionalità avanzate di Aspose.PDF in base al consumo effettivo.

### Passaggio 1: configurazione delle chiavi di licenza

Nel codice sorgente fornito è necessario specificare le chiavi pubblica e privata della licenza a consumo. Sostituisci il "*****" con le tue chiavi. Queste chiavi ti verranno fornite quando acquisti una licenza misurata da Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Passaggio 2: caricamento del documento

 Caricare il documento PDF dal disco utilizzando il file`Document` classe di Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Passaggio 3: ottenere il conteggio delle pagine del documento

 Usa il`Count` proprietà del`Pages` collection per ottenere il numero totale di pagine del documento.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Codice sorgente di esempio per la configurazione della licenza a consumo utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// impostare chiavi pubbliche e private misurate
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
//Accedi alla proprietà setMeteredKey e passa le chiavi pubbliche e private come parametri
metered.SetMeteredKey("*****", "*****");
// Caricare il documento dal disco.
Document doc = new Document(dataDir + "input.pdf");
//Ottieni il conteggio delle pagine del documento
Console.WriteLine(doc.Pages.Count);

```

## Conclusione

In questo tutorial, abbiamo spiegato come impostare una licenza a consumo con Aspose.PDF per .NET. Utilizzando una licenza misurata, puoi beneficiare delle funzionalità avanzate di Aspose.PDF in base al tuo utilizzo effettivo. Assicurati di fornire chiavi di licenza valide per utilizzare Aspose.PDF con tutte le sue funzionalità.

### Domande frequenti per la configurazione delle chiavi di licenza a consumo nel file PDF

#### D: Cos'è una licenza misurata in Aspose.PDF?

R: Una licenza misurata in Aspose.PDF è un modello di licenza che ti consente di pagare in base al consumo effettivo di funzionalità anziché a una tariffa di licenza fissa. Ti consente di utilizzare funzionalità avanzate di Aspose.PDF pagando solo per ciò che utilizzi.

#### D: Perché dovrei utilizzare una licenza a consumo per Aspose.PDF?

R: L'utilizzo di una licenza a consumo offre risparmi sui costi e flessibilità. Paghi solo per le funzionalità che utilizzi, rendendolo adatto a progetti con esigenze diverse. Elimina la necessità di costi di licenza anticipati e consente di accedere a funzionalità PDF avanzate.

#### D: Come posso ottenere le chiavi di licenza a consumo?

A: Quando acquisti una licenza misurata da Aspose, riceverai una coppia di chiavi pubbliche e private. Queste chiavi verranno utilizzate per autenticare e abilitare le licenze a consumo per l'applicazione Aspose.PDF.

#### D: Come posso configurare le chiavi di licenza a consumo in Aspose.PDF per .NET?

 R: Per configurare le chiavi di licenza a consumo, utilizzare il file`SetMeteredKey` metodo del`Aspose.Pdf.Metered` classe. Sostituire`"PUBLIC_KEY"` E`"PRIVATE_KEY"` con le tue vere chiavi.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

#### D: Come carico un documento PDF utilizzando Aspose.PDF per .NET?

 R: Per caricare un documento PDF dal disco, utilizzare il file`Document` classe di Aspose.PDF e fornire il percorso del file.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

#### D: Come posso ottenere il conteggio totale delle pagine di un documento PDF?

 R: Per ottenere il conteggio totale delle pagine di un documento PDF, utilizzare il file`Count` proprietà del`Pages` collezione.

```csharp
int pageCount = doc.Pages.Count;
Console.WriteLine("Total pages: " + pageCount);
```

#### D: Posso utilizzare licenze a consumo per altri prodotti Aspose?

R: Sì, la licenza a consumo è disponibile per vari prodotti Aspose, consentendoti di pagare in base all'utilizzo per un'ampia gamma di funzionalità.

#### D: Una licenza a consumo è adatta a tutti i tipi di progetti?

R: La licenza misurata è adatta a progetti con utilizzo di funzionalità variabili. Potrebbe non essere conveniente per progetti con un utilizzo coerente e ad alte funzionalità.

#### D: Dove posso trovare ulteriori informazioni sulle licenze a consumo di Aspose.PDF?

 R: Per ulteriori informazioni su licenze a consumo, prezzi e vantaggi, visitare il sito[Licenze a consumo Aspose.PDF](https://purchase.aspose.com/pricing/pdf/net) pagina.

#### D: Come posso garantire la sicurezza delle mie chiavi di licenza a consumo?

R: Le chiavi di licenza controllate vengono utilizzate per l'autenticazione e sono informazioni riservate. Assicurati che siano mantenuti riservati e non condivisi pubblicamente.

#### D: Posso passare dalla licenza tradizionale a quella a consumo?

R: Sì, puoi passare dalla licenza tradizionale alla licenza a consumo per Aspose.PDF in base ai requisiti del tuo progetto.

#### D: Posso utilizzare una versione di prova prima di acquistare una licenza a consumo?

 R: Sì, puoi provare il[versione di prova gratuita](https://products.aspose.com/pdf/net) di Aspose.PDF per valutarne le caratteristiche e le funzionalità prima di acquistare una licenza a consumo.

#### D: Con quale frequenza devo configurare le chiavi di licenza a consumo?

R: È necessario configurare le chiavi di licenza a consumo solo una volta all'avvio dell'applicazione. Fornisce l'accesso alle funzionalità avanzate durante il runtime dell'applicazione.

#### D: Posso applicare licenze a consumo a un'applicazione esistente?

R: Sì, puoi integrare le licenze a consumo in un'applicazione Aspose.PDF esistente per trarne vantaggio.