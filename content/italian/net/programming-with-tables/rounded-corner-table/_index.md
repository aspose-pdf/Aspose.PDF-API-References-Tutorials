---
title: Tavolo angolare arrotondato in documento PDF
linktitle: Tavolo angolare arrotondato in documento PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come creare una tabella con angoli arrotondati in un documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-tables/rounded-corner-table/
---
In questo tutorial, ti guideremo passo dopo passo nella creazione di una tabella con angoli arrotondati in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Fase 1: Creazione della tabella
Per prima cosa creeremo la tabella utilizzando il seguente codice:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Fase 2: Impostazione dello stile degli angoli arrotondati
Ora configureremo lo stile degli angoli arrotondati per la tabella:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Passaggio 3: Impostazione del bordo della tabella
Per dare alla tabella un bordo con gli angoli arrotondati, dobbiamo creare un oggetto BorderInfo e configurarlo con i parametri appropriati:

```csharp
// Crea un oggetto GraphInfo per impostare il colore del bordo
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Imposta il raggio del bordo arrotondato su 15
bInfo.RoundedBorderRadius = 15;

// Applica le informazioni sul bordo alla tabella
tab1.Border = bInfo;
```

### Esempio di codice sorgente per la tabella degli angoli arrotondati utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Imposta il bordo su un bordo più arrotondato in cui il raggio di arrotondamento è 15
bInfo.RoundedBorderRadius = 15;
// Imposta lo stile degli angoli della tabella su Rotondo.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Imposta le informazioni sul bordo della tabella
tab1.Border = bInfo;
```

## Conclusione
Congratulazioni! Ora hai imparato come creare una tabella con angoli arrotondati in un documento PDF usando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come impostare lo stile degli angoli arrotondati e il bordo della tabella. Ora puoi applicare questa conoscenza ai tuoi progetti.

### Domande frequenti sul tavolo con angoli arrotondati in documento PDF

#### D: Posso personalizzare il raggio degli angoli arrotondati della tabella?

A: Sì, puoi personalizzare il raggio degli angoli arrotondati della tabella modificando il valore del`bInfo.RoundedBorderRadius` proprietà nel codice sorgente C# fornito. Imposta semplicemente il valore del raggio desiderato (in punti) per ottenere l'aspetto dell'angolo arrotondato desiderato.

#### D: Posso applicare angoli arrotondati a singole celle nella tabella?

R: No, lo stile degli angoli arrotondati viene applicato all'intera tabella nel suo complesso. Aspose.PDF per .NET al momento non fornisce supporto integrato per l'applicazione di angoli arrotondati a singole celle all'interno della tabella.

#### D: Posso cambiare il colore del bordo degli angoli arrotondati?

 A: Sì, puoi cambiare il colore del bordo degli angoli arrotondati modificando il valore del`graph.Color` proprietà nel codice sorgente C#. Basta fornire il colore desiderato, come`Aspose.Pdf.Color.Red` o qualsiasi altra rappresentazione valida del colore.

#### D: È possibile applicare stili di angoli diversi (ad esempio, quadrati e arrotondati) a tabelle diverse all'interno dello stesso documento PDF?

R: Sì, è possibile applicare diversi stili d'angolo a diverse tabelle all'interno dello stesso documento PDF. Puoi creare più tabelle e configurare i loro stili d'angolo individualmente in base alle tue esigenze.

#### D: Posso regolare lo spessore del bordo degli angoli arrotondati?

 A: Sì, puoi regolare lo spessore del bordo degli angoli arrotondati modificando il`BorderInfo` proprietà dell'oggetto nel codice sorgente C#. Ad esempio, puoi impostare`bInfo.Width` proprietà per regolare lo spessore del bordo.