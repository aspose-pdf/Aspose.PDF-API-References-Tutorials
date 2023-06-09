---
title: CGM in PDF
linktitle: CGM in PDF
second_title: Aspose.PDF per riferimento API .NET
description: Converti facilmente i file CGM in PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 20
url: /it/net/document-conversion/cgm-to-pdf/
---

In questo tutorial, ti guideremo passo dopo passo per convertire CGM in PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e forniremo istruzioni dettagliate per aiutarti a seguirlo facilmente.

## introduzione

La conversione di un file CGM in PDF ti consente di condividere e visualizzare i tuoi disegni tecnici universalmente. Con Aspose.PDF per .NET, puoi eseguire facilmente questa conversione e ottenere file PDF di alta qualità.

## Configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo per lavorare con Aspose.PDF per .NET. Segui i passaggi seguenti:

1. Installa Visual Studio o un altro IDE compatibile con lo sviluppo C#.
2. Crea un nuovo progetto C#.
3. Installa il pacchetto Aspose.PDF per .NET tramite NuGet per aggiungere le dipendenze necessarie.

## Converti file CGM in PDF

Per convertire un file CGM in PDF, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un'istanza di un oggetto LoadOption utilizzando CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Crea un'istanza di un oggetto Document
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Salva il documento PDF risultante
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 Nel codice sopra, assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il file CGM da convertire. Questo codice carica il file CGM utilizzando l'estensione`CgmLoadOptions` class, quindi crea un documento PDF utilizzando il file`Document` oggetto. Infine, il documento PDF risultante viene salvato.

### Esempio di codice sorgente per CGM in PDF utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un'istanza dell'oggetto LoadOption utilizzando CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Crea un'istanza dell'oggetto Document
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Salva il documento PDF risultante
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Conclusione

Congratulazioni! Ora sai come convertire un file CGM in PDF usando Aspose.PDF per .NET. Abbiamo seguito ogni fase del processo, dall'inizializzazione delle opzioni di caricamento CGM al salvataggio del documento PDF risultante. Usa gli esempi di codice forniti per integrare questa funzionalità nei tuoi progetti. Sperimenta con Aspose.PDF per .NET e scopri le possibilità estese che offre per la manipolazione dei file PDF.
