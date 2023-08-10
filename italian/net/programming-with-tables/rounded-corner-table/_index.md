---
title: Tavolo ad angolo arrotondato in documento PDF
linktitle: Tavolo ad angolo arrotondato in documento PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come creare un tavolo ad angolo arrotondato nel documento PDF utilizzando Aspose.PDF per .NET.
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

### Domande frequenti per tavolo ad angolo arrotondato nel documento PDF

#### D: Posso personalizzare il raggio degli angoli arrotondati del tavolo?

R: Sì, puoi personalizzare il raggio degli angoli arrotondati del tavolo modificando il valore di`bInfo.RoundedBorderRadius` proprietà nel codice sorgente C# fornito. Basta impostare il valore del raggio desiderato (in punti) per ottenere l'aspetto dell'angolo arrotondato desiderato.

#### D: Posso applicare angoli arrotondati a singole celle all'interno della tabella?

R: No, lo stile degli angoli arrotondati viene applicato all'intero tavolo nel suo insieme. Aspose.PDF per .NET attualmente non fornisce supporto integrato per l'applicazione di angoli arrotondati a singole celle all'interno della tabella.

#### D: Posso cambiare il colore del bordo dell'angolo arrotondato?

 R: Sì, puoi cambiare il colore del bordo dell'angolo arrotondato modificando il valore di`graph.Color` proprietà nel codice sorgente C#. Basta fornire il colore desiderato, ad esempio`Aspose.Pdf.Color.Red` o qualsiasi altra rappresentazione cromatica valida.

#### D: È possibile applicare diversi stili di angoli (ad es. quadrati e arrotondati) a tabelle diverse all'interno dello stesso documento PDF?

R: Sì, è possibile applicare diversi stili di angoli a diverse tabelle all'interno dello stesso documento PDF. Puoi creare più tavoli e configurare i loro stili d'angolo individualmente in base alle tue esigenze.

#### D: Posso regolare lo spessore del bordo dell'angolo arrotondato?

 R: Sì, puoi regolare lo spessore del bordo dell'angolo arrotondato modificando il file`BorderInfo` proprietà dell'oggetto nel codice sorgente C#. Ad esempio, puoi impostare il`bInfo.Width` proprietà per regolare lo spessore del bordo.