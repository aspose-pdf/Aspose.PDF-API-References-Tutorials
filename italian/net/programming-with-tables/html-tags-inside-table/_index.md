---
title: Tag HTML all'interno della tabella nel file PDF
linktitle: Tag HTML all'interno della tabella nel file PDF
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare i tag HTML all'interno di una tabella nel file PDF con Aspose.PDF per .NET.
type: docs
weight: 100
url: /it/net/programming-with-tables/html-tags-inside-table/
---
In questo tutorial impareremo come utilizzare i tag HTML all'interno di una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente in C# passo dopo passo. Alla fine di questo tutorial, saprai come inserire contenuto HTML in una tabella in un documento PDF. Iniziamo!

## Passaggio 1: configurazione dell'ambiente
Assicurati di aver configurato il tuo ambiente di sviluppo C# con Aspose.PDF per .NET. Aggiungere il riferimento alla libreria e importare gli spazi dei nomi necessari.

## Passaggio 2: creazione dei dati della tabella
Creiamo un DataTable contenente una colonna "data" di tipo String. Quindi aggiungiamo righe a questo DataTable utilizzando il contenuto HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Passaggio 3: creazione del documento e della tabella
Creiamo un nuovo documento PDF e aggiungiamo una pagina in questo documento. Successivamente, inizializziamo un'istanza della classe Table e impostiamo le proprietà della tabella.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Passaggio 4: importazione dei dati nella tabella
Importiamo i dati dal DataTable nella tabella utilizzando il metodo "ImportDataTable". Specifichiamo i parametri del metodo per indicare quale intervallo di righe e colonne del DataTable deve essere importato.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Passaggio 5: aggiunta della tabella al documento
Aggiungiamo la tabella alla pagina del documento.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Fase 6: salvare il documento
Salviamo il documento PDF con la tabella contenente il contenuto HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Codice sorgente di esempio per i tag HTML all'interno della tabella utilizzando Aspose.PDF per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inizializza una nuova istanza di Table
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Imposta la larghezza delle colonne della tabella
tableProvider.ColumnWidths = "400 50 ";
// Imposta il colore del bordo della tabella come LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Imposta il bordo per le celle della tabella
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare i tag HTML all'interno di una tabella in un documento PDF utilizzando Aspose.PDF per .NET. Puoi utilizzare questa guida dettagliata per inserire contenuto HTML nelle celle di una tabella in un documento PDF utilizzando C#.

### Domande frequenti per i tag HTML all'interno della tabella nel file PDF

#### D: Posso utilizzare altri tag e attributi HTML all'interno delle celle della tabella?

 R: Sì, puoi utilizzare vari tag e attributi HTML all'interno delle celle della tabella, ad esempio`<b>`, `<i>`, `<a>`e molti altri. Aspose.PDF per .NET supporta un'ampia gamma di elementi e stili HTML che è possibile utilizzare per formattare il contenuto all'interno delle celle della tabella.

#### D: Posso applicare stili CSS al contenuto HTML all'interno delle celle della tabella?

R: Sì, puoi applicare stili CSS al contenuto HTML all'interno delle celle della tabella. Aspose.PDF per .NET fornisce il supporto per gli stili CSS di base che possono essere applicati agli elementi HTML.

#### D: È possibile aggiungere immagini insieme al contenuto HTML all'interno delle celle della tabella?

 R: Sì, puoi aggiungere immagini insieme al contenuto HTML all'interno delle celle della tabella. Puoi usare l'HTML`<img>` tag per includere immagini da varie fonti, come file locali o URL.

#### D: Come posso specificare diverse larghezze di colonna per la tabella?

 R: Puoi specificare diverse larghezze di colonna per la tabella utilizzando il file`ColumnWidths` proprietà della tavola. La proprietà accetta una stringa contenente valori separati da spazi, dove ogni valore rappresenta la larghezza di una colonna in punti.

#### D: Posso utilizzare tabelle nidificate all'interno di una cella con contenuto HTML?

R: Sì, puoi utilizzare tabelle nidificate all'interno di una cella con contenuto HTML. È possibile creare istanze di tabelle separate e aggiungerle come parte del contenuto HTML all'interno di una cella per ottenere l'effetto di nidificazione.