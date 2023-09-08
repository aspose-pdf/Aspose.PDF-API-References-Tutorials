---
title: Da PDF a XPS
linktitle: Da PDF a XPS
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per convertire PDF in XPS utilizzando Aspose.PDF per .NET.
type: docs
weight: 220
url: /it/net/document-conversion/pdf-to-xps/
---
In questo tutorial ti guideremo attraverso il processo di conversione di un file PDF in formato XPS (XML Paper Specifica) utilizzando Aspose.PDF per .NET. Il formato XPS è un formato di file basato su XML utilizzato per rappresentare elettronicamente i documenti. Seguendo i passaggi seguenti, sarai in grado di convertire un file PDF in formato XPS.

## Prerequisiti
Prima di iniziare, assicurati di soddisfare i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Libreria Aspose.PDF per .NET installata sul tuo sistema.
- Un ambiente di sviluppo come Visual Studio.

## Passaggio 1: caricamento del documento PDF
In questo passaggio caricheremo il file PDF di origine utilizzando Aspose.PDF per .NET. Segui il codice qui sotto:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con la directory effettiva in cui si trova il file PDF.

## Passaggio 2: istanziare le opzioni di salvataggio XPS
Dopo aver caricato il file PDF, creeremo un'istanza delle opzioni di salvataggio XPS. Utilizza il seguente codice:

```csharp
// Istanziare le opzioni di salvataggio XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Passaggio 3: salvataggio del file XPS risultante
Ora salveremo il file PDF convertito in formato XPS. Utilizza il seguente codice:

```csharp
// Salva il documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Il codice sopra salva il file PDF convertito in formato XPS con il nome file`"PDFToXPS_out.xps"`.


### Codice sorgente di esempio per PDF in XPS utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica il documento PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Istanziare le opzioni di salvataggio XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Salva il documento XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusione
In questo tutorial, abbiamo trattato il processo passo passo di conversione di un file PDF in formato XPS utilizzando Aspose.PDF per .NET. Seguendo le istruzioni sopra descritte, ora dovresti essere in grado di convertire un file PDF in formato XPS. Questa funzione è utile quando desideri visualizzare o stampare documenti PDF in formato XPS.

### Domande frequenti

#### D: Il formato XPS è adatto alla compatibilità multipiattaforma?

R: Il formato XPS, essendo un formato file basato su XML, è indipendente dalla piattaforma e può essere visualizzato su vari sistemi operativi e dispositivi. I file XPS sono supportati sulle piattaforme Windows per impostazione predefinita e alcune applicazioni e visualizzatori di terze parti potrebbero essere disponibili per altre piattaforme.

#### D: Aspose.PDF per .NET può gestire file PDF complessi con più pagine e immagini durante la conversione XPS?

R: Sì, Aspose.PDF per .NET può gestire file PDF complessi con più pagine e immagini durante la conversione XPS. Conserva accuratamente il layout, le immagini e il contenuto testuale del PDF durante la conversione in formato XPS.

#### D: È possibile specificare impostazioni o opzioni aggiuntive durante il processo di conversione XPS?

 R: Sì, Aspose.PDF per .NET fornisce varie opzioni e impostazioni che possono essere personalizzate durante il processo di conversione XPS. Puoi controllare la compressione dell'immagine, l'incorporamento dei caratteri e altre impostazioni utilizzando il file`XpsSaveOptions` classe.

#### D: I PDF protetti da password possono essere convertiti in formato XPS utilizzando Aspose.PDF per .NET?

 R: Sì, Aspose.PDF per .NET supporta la conversione di PDF protetti da password in formato XPS. Quando si carica un PDF protetto da password, è possibile fornire la password utilizzando il file`Document` costruttore della classe o impostando il file`Password` proprietà prima di caricare il PDF.