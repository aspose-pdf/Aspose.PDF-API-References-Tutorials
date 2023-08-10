---
title: Configura chiavi di licenza misurate nel file PDF
linktitle: Configura chiavi di licenza misurate nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Guida passo-passo per impostare chiavi di licenza misurate in file PDF con Aspose.PDF per .NET e beneficiare di funzionalità avanzate.
type: docs
weight: 10
url: /it/net/licensing-aspose-pdf/configure-metered-license/
---
In questo tutorial, ti guideremo passo dopo passo su come impostare una chiave di licenza misurata in un file PDF con Aspose.PDF per .NET. La licenza misurata consente di utilizzare le funzionalità avanzate di Aspose.PDF in base al consumo effettivo.

### Passaggio 1: configurazione delle chiavi di licenza

Nel codice sorgente fornito, è necessario specificare le chiavi pubbliche e private della licenza a consumo. Sostituisci il "*****" valori con le tue chiavi. Queste chiavi ti verranno fornite quando acquisti una licenza misurata da Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### Passaggio 2: caricamento del documento

 Carica il documento PDF dal disco utilizzando il file`Document` classe di Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### Passaggio 3: ottieni il conteggio delle pagine del documento

 Usa il`Count` proprietà del`Pages` collection per ottenere il numero totale di pagine nel documento.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### Esempio di codice sorgente per configurare la licenza a consumo utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//impostare chiavi pubbliche e private misurate
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// Accedi alla proprietà setMeteredKey e passa chiavi pubbliche e private come parametri
metered.SetMeteredKey("*****", "*****");
// Carica il documento dal disco.
Document doc = new Document(dataDir + "input.pdf");
//Ottenere il conteggio delle pagine del documento
Console.WriteLine(doc.Pages.Count);

```

## Conclusione

In questo tutorial, abbiamo spiegato come impostare una licenza a consumo con Aspose.PDF per .NET. Utilizzando una licenza misurata, puoi beneficiare delle funzionalità avanzate di Aspose.PDF in base al tuo utilizzo effettivo. Assicurati di fornire chiavi di licenza valide per utilizzare Aspose.PDF con tutte le sue funzionalità.

### Domande frequenti per configurare le chiavi di licenza a consumo nel file PDF

#### D: Cos'è una licenza misurata in Aspose.PDF?

A: Una licenza misurata in Aspose.PDF è un modello di licenza che ti consente di pagare in base al consumo effettivo delle funzionalità piuttosto che a un canone di licenza fisso. Ti consente di utilizzare le funzionalità avanzate di Aspose.PDF pagando solo per ciò che usi.

#### D: Perché dovrei usare una licenza misurata per Aspose.PDF?

R: L'utilizzo di una licenza a consumo offre risparmio sui costi e flessibilità. Paghi solo per le funzionalità che utilizzi, rendendolo adatto a progetti con esigenze diverse. Elimina la necessità di costi di licenza anticipati e consente di accedere a funzionalità PDF avanzate.

#### D: Come si ottengono le chiavi di licenza a consumo?

R: Quando acquisti una licenza a consumo da Aspose, riceverai una coppia di chiavi pubbliche e private. Queste chiavi verranno utilizzate per autenticare e abilitare le licenze misurate per l'applicazione Aspose.PDF.

#### D: Come si configurano le chiavi di licenza a consumo in Aspose.PDF per .NET?

 R: Per configurare le chiavi di licenza a consumo, utilizzare il file`SetMeteredKey` metodo del`Aspose.Pdf.Metered` classe. Sostituire`"PUBLIC_KEY"` E`"PRIVATE_KEY"` con le tue chiavi reali.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

#### D: Come faccio a caricare un documento PDF utilizzando Aspose.PDF per .NET?

 R: Per caricare un documento PDF dal disco, utilizzare il file`Document` class di Aspose.PDF e fornire il percorso del file.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

#### D: Come posso ottenere il conteggio totale delle pagine di un documento PDF?

 R: Per ottenere il conteggio totale delle pagine di un documento PDF, utilizzare il file`Count` proprietà del`Pages` collezione.

```csharp
int pageCount = doc.Pages.Count;
Console.WriteLine("Total pages: " + pageCount);
```

#### D: Posso utilizzare le licenze misurate per altri prodotti Aspose?

R: Sì, le licenze misurate sono disponibili per vari prodotti Aspose, consentendoti di pagare in base al tuo utilizzo per un'ampia gamma di funzionalità.

#### D: Una licenza a consumo è adatta a tutti i tipi di progetti?

R: Le licenze misurate sono adatte a progetti con un utilizzo variabile delle funzionalità. Potrebbe non essere conveniente per i progetti con un utilizzo coerente e ad alta funzionalità.

#### D: Dove posso trovare ulteriori informazioni sulle licenze misurate Aspose.PDF?

 R: Per ulteriori informazioni su licenze a consumo, prezzi e vantaggi, visitare il[Aspose.PDF Licenze misurate](https://purchase.aspose.com/pricing/pdf/net) pagina.

#### D: Come posso garantire la sicurezza delle mie chiavi di licenza a consumo?

R: Le chiavi di licenza misurate vengono utilizzate per l'autenticazione e sono informazioni riservate. Assicurati che siano mantenuti riservati e non condivisi pubblicamente.

#### D: Posso passare dalla licenza tradizionale a quella a consumo?

R: Sì, puoi passare dalla licenza tradizionale alla licenza misurata per Aspose.PDF in base ai requisiti del tuo progetto.

#### D: Posso utilizzare una versione di prova prima di acquistare una licenza a consumo?

 A: Sì, puoi provare il[versione di prova gratuita](https://products.aspose.com/pdf/net) di Aspose.PDF per valutare le sue caratteristiche e funzionalità prima di acquistare una licenza misurata.

#### D: Con quale frequenza devo configurare le chiavi di licenza a consumo?

R: È necessario configurare le chiavi di licenza a consumo solo una volta all'avvio dell'applicazione. Fornisce l'accesso alle funzionalità avanzate durante il runtime dell'applicazione.

#### D: Posso applicare una licenza a consumo a un'applicazione esistente?

R: Sì, puoi integrare le licenze misurate in un'applicazione Aspose.PDF esistente per beneficiare dei suoi vantaggi.