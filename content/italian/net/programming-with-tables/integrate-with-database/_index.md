---
title: Integrazione con database in file PDF
linktitle: Integrazione con database in file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Incorpora dati da un database in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 120
url: /it/net/programming-with-tables/integrate-with-database/
---
In questo tutorial, impareremo come incorporare dati da un database in un file PDF usando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come importare dati di tabella da un database in un documento PDF. Cominciamo!

## Fase 1: Impostazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungi il riferimento alla libreria e importa i namespace necessari.

## Passaggio 2: creazione della tabella dati
Creiamo un'istanza di DataTable per rappresentare i dati che vogliamo incorporare nel documento PDF. In questo esempio, creiamo una DataTable con tre colonne: Employee_ID, Employee_Name e Gender. Aggiungiamo anche due righe alla DataTable con dati fittizi.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Fase 3: Creazione del documento PDF e della tabella
Creiamo un'istanza di Document e aggiungiamo una pagina a questo documento. Poi, creiamo un'istanza di Table per rappresentare la nostra tabella nel documento PDF. Definiamo le larghezze delle colonne della tabella e gli stili dei bordi.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Passaggio 4: importazione dei dati dalla DataTable alla tabella
Utilizziamo il metodo ImportDataTable per importare i dati dalla DataTable alla tabella del documento PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Passaggio 5: aggiunta della tabella al documento
Aggiungiamo la tabella alla raccolta dei paragrafi della pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Passaggio 6: Salvare il documento
Salviamo il documento PDF con i dati dal database incorporato.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Congratulazioni! Ora sai come incorporare i dati del database in un documento PDF utilizzando Aspose.PDF per .NET.

### Esempio di codice sorgente per Integrate With Database utilizzando Aspose.PDF per .NET

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Aggiungere 2 righe nell'oggetto DataTable a livello di programmazione
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Crea istanza del documento
Document doc = new Document();
doc.Pages.Add();
// Inizializza una nuova istanza della tabella
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Imposta la larghezza delle colonne della tabella
table.ColumnWidths = "40 100 100 100";
// Imposta il colore del bordo della tabella come LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Aggiungere l'oggetto tabella alla prima pagina del documento di input
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Salva il documento aggiornato contenente l'oggetto tabella
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusione
In questo tutorial, abbiamo imparato come incorporare dati da un database in un documento PDF usando Aspose.PDF per .NET. Puoi usare questa guida passo passo per importare i dati dal tuo database e visualizzarli in documenti PDF. Esplora ulteriormente la documentazione di Aspose.PDF per scoprire altre funzionalità e possibilità offerte da questa potente libreria.

### FAQ per l'integrazione con il database nel file PDF

#### D: Posso usare Aspose.PDF per .NET con diversi tipi di database come MySQL, SQL Server o Oracle?

R: Sì, puoi usare Aspose.PDF per .NET con diversi tipi di database come MySQL, SQL Server, Oracle e altri. Aspose.PDF per .NET fornisce funzionalità per leggere dati da varie fonti di dati, inclusi database, file XML e altro. Puoi recuperare dati dal tipo di database desiderato e popolarli in una DataTable o in qualsiasi altra struttura dati compatibile con Aspose.PDF per .NET.

#### D: Come posso personalizzare l'aspetto della tabella nel documento PDF?

R: Puoi personalizzare l'aspetto della tabella nel documento PDF utilizzando varie proprietà fornite dalla libreria Aspose.PDF per .NET. Ad esempio, puoi impostare diversi stili di bordo, colori di sfondo, stili di carattere e allineamento per la tabella e le sue celle. Fai riferimento alla documentazione di Aspose.PDF per .NET per maggiori dettagli sulla personalizzazione dell'aspetto della tabella.

#### D: È possibile aggiungere collegamenti ipertestuali o elementi interattivi ai dati importati dal database?

R: Sì, puoi aggiungere collegamenti ipertestuali o altri elementi interattivi ai dati importati dal database. Aspose.PDF per .NET supporta l'aggiunta di collegamenti ipertestuali, segnalibri e altri elementi interattivi al documento PDF. Puoi manipolare il contenuto in DataTable prima di importarlo nella tabella e includere collegamenti ipertestuali o altre funzionalità interattive.

#### D: Posso suddividere le pagine della tabella se supera un certo numero di righe?

A: Sì, puoi impaginare la tabella se supera un certo numero di righe. Per ottenere questo risultato, puoi usare il`IsInNewPage` proprietà dell'oggetto Row per indicare che una nuova pagina dovrebbe iniziare dopo una riga specifica. Puoi calcolare il numero di righe da visualizzare per pagina e impostare la`IsInNewPage` proprietà di conseguenza.

#### D: Come posso esportare il documento PDF con i dati del database incorporati in diversi formati di file come DOCX o XLSX?

R: Aspose.PDF per .NET consente di convertire documenti PDF in vari altri formati di file, tra cui DOCX (Microsoft Word) e XLSX (Microsoft Excel). È possibile utilizzare la libreria Aspose.PDF per .NET in combinazione con altre librerie Aspose come Aspose.Words e Aspose.Cells per ottenere questo risultato. Per prima cosa, salvare il documento PDF con i dati del database incorporati, quindi utilizzare la rispettiva libreria Aspose per convertirlo nel formato di file desiderato.