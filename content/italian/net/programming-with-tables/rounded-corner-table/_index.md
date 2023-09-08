---
title: Tavolo ad angolo arrotondato nel documento PDF
linktitle: Tavolo ad angolo arrotondato nel documento PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come creare una tabella con angoli arrotondati nel documento PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 190
url: /it/net/programming-with-tables/rounded-corner-table/
---
In questo tutorial, ti guideremo passo dopo passo per creare una tabella con angoli arrotondati nel documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# fornito e ti mostreremo come implementarlo.

## Passaggio 1: creazione della tabella
Per prima cosa creeremo la tabella utilizzando il seguente codice:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Passaggio 2: impostazione dello stile con angoli arrotondati
Successivamente, configureremo lo stile degli angoli arrotondati per la tabella:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Passaggio 3: impostazione del bordo della tabella
Per dare alla tabella un bordo con angoli arrotondati dobbiamo creare un oggetto BorderInfo e configurarlo con gli appositi parametri:

```csharp
// Crea un oggetto GraphInfo per impostare il colore del bordo
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Imposta il raggio del bordo arrotondato su 15
bInfo.RoundedBorderRadius = 15;

// Applicare le informazioni sul bordo alla tabella
tab1.Border = bInfo;
```

### Codice sorgente di esempio per la tabella con angoli arrotondati utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crea un oggetto BorderInfo vuoto
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Imposta il bordo su un bordo più arrotondato in cui il raggio dell'arrotondamento è 15
bInfo.RoundedBorderRadius = 15;
// Imposta lo stile Angolo della tabella su Rotondo.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Imposta le informazioni sul bordo della tabella
tab1.Border = bInfo;
```

## Conclusione
Congratulazioni! Ora hai imparato come creare una tabella con angoli arrotondati in un documento PDF utilizzando Aspose.PDF per .NET. Questa guida passo passo ti ha mostrato come impostare lo stile degli angoli arrotondati e il bordo della tabella. Ora puoi applicare questa conoscenza ai tuoi progetti.

### Domande frequenti sul tavolo con angolo arrotondato nel documento PDF

#### D: Posso personalizzare il raggio degli angoli arrotondati del tavolo?

R: Sì, puoi personalizzare il raggio degli angoli arrotondati del tavolo modificando il valore di`bInfo.RoundedBorderRadius` proprietà nel codice sorgente C# fornito. È sufficiente impostare il valore del raggio desiderato (in punti) per ottenere l'aspetto degli angoli arrotondati desiderato.

#### D: Posso applicare angoli arrotondati alle singole celle della tabella?

R: No, lo stile degli angoli arrotondati viene applicato all'intera tabella nel suo insieme. Aspose.PDF per .NET attualmente non fornisce supporto integrato per l'applicazione di angoli arrotondati alle singole celle all'interno della tabella.

#### D: Posso cambiare il colore del bordo dell'angolo arrotondato?

 R: Sì, puoi cambiare il colore del bordo dell'angolo arrotondato modificando il valore di`graph.Color` proprietà nel codice sorgente C#. Basta fornire il colore desiderato, ad esempio`Aspose.Pdf.Color.Red` o qualsiasi altra rappresentazione di colore valida.

#### D: È possibile applicare stili di angoli diversi (ad esempio, quadrati e arrotondati) a tabelle diverse all'interno dello stesso documento PDF?

R: Sì, è possibile applicare stili di angoli diversi a tabelle diverse all'interno dello stesso documento PDF. Puoi creare più tavoli e configurare i loro stili d'angolo individualmente in base alle tue esigenze.

#### D: Posso regolare lo spessore del bordo dell'angolo arrotondato?

 R: Sì, puoi regolare lo spessore del bordo dell'angolo arrotondato modificando il file`BorderInfo` le proprietà dell'oggetto nel codice sorgente C#. Ad esempio, puoi impostare il file`bInfo.Width` proprietà per regolare lo spessore del bordo.