---
title: Δημιουργία στοιχείου πίνακα
linktitle: Δημιουργία στοιχείου πίνακα
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη δημιουργία ενός στοιχείου πίνακα με το Aspose.PDF για .NET. Δημιουργήστε εύκολα δυναμικά PDF με πίνακες.
type: docs
weight: 80
url: /el/net/programming-with-tagged-pdf/create-table-element/
---
Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός στοιχείου πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Το Aspose.PDF είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να χειρίζεστε έγγραφα PDF μέσω προγραμματισμού. Η δημιουργία ενός στοιχείου πίνακα είναι μια κοινή απαίτηση κατά τη δημιουργία δυναμικών αρχείων PDF και το Aspose.PDF προσφέρει έναν εύκολο και αποτελεσματικό τρόπο για να το επιτύχετε αυτό.

Ας βουτήξουμε στον κώδικα και ας μάθουμε πώς να δημιουργήσουμε ένα στοιχείο πίνακα χρησιμοποιώντας το Aspose.PDF για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1. Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
2. Βασική γνώση της γλώσσας προγραμματισμού C#.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Για να ξεκινήσετε, ανοίξτε το περιβάλλον ανάπτυξης C# και δημιουργήστε ένα νέο έργο. Βεβαιωθείτε ότι έχετε προσθέσει μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET στο έργο σας.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου

 Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο έγγραφο PDF χρησιμοποιώντας το`Document` τάξη.

```csharp
// Δημιουργήστε το έγγραφο
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Εδώ ορίζουμε επίσης τον τίτλο και τη γλώσσα για το περιεχόμενο με ετικέτα.

## Βήμα 3: Δημιουργία του στοιχείου πίνακα

Στη συνέχεια, πρέπει να δημιουργήσουμε το στοιχείο πίνακα και να το προσθέσουμε στο έγγραφο. Ξεκινάμε παίρνοντας το στοιχείο δομής ρίζας και, στη συνέχεια, δημιουργούμε ένα νέο στοιχείο πίνακα χρησιμοποιώντας το`CreateTableElement` μέθοδος.

```csharp
// Λάβετε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "CreateTableElement.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Δείγμα πηγαίου κώδικα για τη δημιουργία στοιχείου πίνακα χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Λήψη στοιχείου δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Αποθήκευση εγγράφου Pdf με ετικέτα
document.Save(dataDir + "CreateTableElement.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Σύναψη

Έχετε μάθει πώς να δημιουργείτε ένα στοιχείο πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε τώρα να δημιουργήσετε έγγραφα PDF με δυναμικούς πίνακες χρησιμοποιώντας αυτήν τη μέθοδο. Μη διστάσετε να εξερευνήσετε περισσότερες δυνατότητες του Aspose.PDF για να ανακαλύψετε πλήρως τις δυνατότητές του.

### Συχνές ερωτήσεις

#### Ε: Τι είναι ένα στοιχείο πίνακα σε ένα έγγραφο PDF και γιατί θα χρειαστεί να δημιουργήσω ένα χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ένα στοιχείο πίνακα σε ένα έγγραφο PDF αντιπροσωπεύει μια δομημένη συλλογή δεδομένων, που χρησιμοποιείται συχνά για τη δημιουργία πινάκων ή πλεγμάτων. Ίσως χρειαστεί να δημιουργήσετε ένα στοιχείο πίνακα χρησιμοποιώντας το Aspose.PDF για .NET κατά τη δημιουργία δυναμικών PDF που απαιτούν παρουσίαση δομημένων δεδομένων, όπως πληροφορίες σε πίνακα ή πλέγματα.

#### Ε: Πώς το Aspose.PDF για .NET απλοποιεί τη διαδικασία δημιουργίας ενός στοιχείου πίνακα;

Α: Το Aspose.PDF για .NET παρέχει ένα ολοκληρωμένο σύνολο κλάσεων και μεθόδων που σας επιτρέπουν να δημιουργείτε, να προσαρμόζετε και να διαχειρίζεστε στοιχεία πίνακα (πίνακες) σε ένα έγγραφο PDF μέσω προγραμματισμού. Αυτό εξαλείφει την ανάγκη χειροκίνητου χειρισμού PDF και απλοποιεί τη δημιουργία δομημένων αναπαραστάσεων δεδομένων.

#### Ε: Ποια είναι τα βασικά βήματα που περιλαμβάνονται στη δημιουργία ενός στοιχείου πίνακα χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Τα βασικά βήματα περιλαμβάνουν τη ρύθμιση του περιβάλλοντος, τη δημιουργία του εγγράφου, τη λήψη του στοιχείου δομής ρίζας, τη δημιουργία ενός στοιχείου πίνακα, τον καθορισμό σειρών και κελιών μέσα στον πίνακα και τον καθορισμό μορφοποίησης και ιδιοτήτων για τα στοιχεία. Το παρεχόμενο παράδειγμα κώδικα δείχνει αυτά τα βήματα.

####  Ε: Τι ρόλο παίζει το`taggedContent` object play in creating an array element?

 Α: Το`taggedContent` αντικείμενο, που λαμβάνεται από το έγγραφο`TaggedContent`ιδιοκτησία, σας επιτρέπει να ορίσετε τη δομή του περιεχομένου με ετικέτα μέσα στο έγγραφο PDF. Αυτό περιλαμβάνει τη δημιουργία και την οργάνωση στοιχείων πίνακα και των θυγατρικών τους στοιχείων με ιεραρχικό τρόπο.

#### Ε: Πώς εξασφαλίζει ο κώδικας προσβασιμότητα και σημασιολογία του δημιουργημένου στοιχείου πίνακα;

 Α: Ο κώδικας ορίζει χαρακτηριστικά όπως`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , και`ColSpan` για τη βελτίωση της προσβασιμότητας και της σημασιολογίας του στοιχείου του πίνακα. Αυτά τα χαρακτηριστικά συμβάλλουν σε μια καλά δομημένη, ενημερωτική και οπτικά ελκυστική αναπαράσταση δεδομένων.

#### Ε: Ποια είναι η σημασία της συμμόρφωσης PDF/UA στο πλαίσιο της δημιουργίας στοιχείων πίνακα;

 Α: Η συμμόρφωση PDF/UA (Universal Accessibility) διασφαλίζει ότι τα έγγραφα PDF που δημιουργούνται είναι προσβάσιμα σε χρήστες με ειδικές ανάγκες και πληρούν ορισμένα πρότυπα προσβασιμότητας. Το παράδειγμα κώδικα ελέγχει τη συμμόρφωση PDF/UA χρησιμοποιώντας το`Validate` μέθοδος, που σας βοηθά να δημιουργήσετε έγγραφα που να είναι περιεκτικά και προσβάσιμα.

#### Ε: Μπορώ να προσαρμόσω περαιτέρω τη μορφοποίηση και την εμφάνιση των στοιχείων του πίνακα;

Α: Ναι, μπορείτε να προσαρμόσετε τη μορφοποίηση και την εμφάνιση των στοιχείων του πίνακα προσαρμόζοντας χαρακτηριστικά όπως το χρώμα φόντου, το στυλ περιγράμματος, το μέγεθος γραμματοσειράς και τη στοίχιση. Το Aspose.PDF για .NET παρέχει ένα ευρύ φάσμα ιδιοτήτων για την προσαρμογή της οπτικής παρουσίασης στις απαιτήσεις σας.

#### Ε: Πώς μπορώ να επεκτείνω αυτή τη γνώση για να δημιουργήσω πιο σύνθετες δομές πίνακα ή να ενσωματώσω στοιχεία πίνακα σε μεγαλύτερα έγγραφα PDF;

Α: Μπορείτε να επεκτείνετε αυτή τη γνώση εξερευνώντας πρόσθετες δυνατότητες του Aspose.PDF για .NET, όπως η συγχώνευση πολλαπλών στοιχείων πίνακα, η δημιουργία ένθετων πινάκων, η προσθήκη κεφαλίδων και υποσέλιδων και η ενσωμάτωση στοιχείων πίνακα σε μεγαλύτερες διατάξεις PDF. Η τεκμηρίωση και τα παραδείγματα της βιβλιοθήκης παρέχουν καθοδήγηση για αυτά τα προηγμένα σενάρια.

#### Ε: Είναι δυνατή η εισαγωγή δεδομένων από εξωτερικές πηγές, όπως βάσεις δεδομένων ή υπολογιστικά φύλλα, για τη συμπλήρωση των στοιχείων του πίνακα;

Α: Ναι, μπορείτε να εισάγετε δεδομένα από εξωτερικές πηγές για να συμπληρώσετε στοιχεία πίνακα. Μπορείτε να χρησιμοποιήσετε τεχνικές ανάκτησης και μετασχηματισμού δεδομένων στη C# για να ανακτήσετε δεδομένα από βάσεις δεδομένων, υπολογιστικά φύλλα ή άλλες πηγές και στη συνέχεια να συμπληρώσετε τα στοιχεία του πίνακα ανάλογα.

#### Ε: Πώς μπορώ να χρησιμοποιήσω τη γνώση που αποκτώ από αυτό το σεμινάριο για να βελτιώσω την ποιότητα και τη χρηστικότητα των εγγράφων PDF που δημιουργώ μέσω προγραμματισμού;

Α: Οι γνώσεις που αποκτήθηκαν από αυτό το σεμινάριο σάς επιτρέπουν να δημιουργήσετε δομημένα και οπτικά ελκυστικά στοιχεία πίνακα (πίνακες) σε έγγραφα PDF. Με την ενσωμάτωση αυτών των τεχνικών, μπορείτε να βελτιώσετε την αναγνωσιμότητα, την προσβασιμότητα και την εμπειρία χρήστη των PDF που δημιουργούνται δυναμικά, καθιστώντας τα πιο ενημερωτικά και φιλικά προς το χρήστη.