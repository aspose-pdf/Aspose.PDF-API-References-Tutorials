---
title: Tavolo angolare arrotondato
linktitle: Tavolo angolare arrotondato
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un tavolo ad angolo arrotondato in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-tables/rounded-corner-table/
---

In questo tutorial, ti guideremo passo dopo passo per creare una tabella con angoli arrotondati in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: creazione della tabella
Innanzitutto, creeremo la tabella utilizzando il seguente codice:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Passaggio 2: impostazione dello stile degli angoli arrotondati
Successivamente, configureremo lo stile degli angoli arrotondati per la tabella:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Passaggio 3: configurazione del bordo della tabella
Per dare alla tabella un bordo ad angolo arrotondato, dobbiamo creare un oggetto BorderInfo e configurarlo con gli opportuni parametri:

```csharp
//Crea un oggetto GraphInfo per impostare il colore del bordo
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Imposta il raggio del bordo arrotondato su 15
bInfo.RoundedBorderRadius = 15;

// Applica le informazioni sul bordo alla tabella
tab1.Border = bInfo;
```

### Esempio di codice sorgente per Rounded Corner Table utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Imposta il bordo su un bordo più arrotondato dove il raggio del giro è 15
bInfo.RoundedBorderRadius = 15;
// Impostare lo stile Angolo del tavolo come Rotondo.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Imposta le informazioni sul bordo della tabella
tab1.Border = bInfo;
```

## Conclusione
Congratulazioni! Ora hai imparato come creare una tabella con angoli arrotondati in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida passo-passo ti ha mostrato come impostare lo stile degli angoli arrotondati e il bordo del tavolo. Ora puoi applicare questa conoscenza ai tuoi progetti.