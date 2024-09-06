---
title: Στοιχείο τραπεζιού στυλ
linktitle: Στοιχείο τραπεζιού στυλ
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να μορφοποιείτε το στοιχείο πίνακα με το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα για την προσαρμογή στυλ και ιδιοτήτων.
type: docs
weight: 170
url: /el/net/programming-with-tagged-pdf/style-table-element/
---
Σε αυτό το λεπτομερές σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα στον παρεχόμενο πηγαίο κώδικα C# για να μορφοποιήσετε το στοιχείο του πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθήστε τις παρακάτω οδηγίες για να κατανοήσετε πώς να προσαρμόσετε τα στυλ και τις ιδιότητες του στοιχείου πίνακα.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε διαμορφώσει το περιβάλλον ανάπτυξης ώστε να χρησιμοποιεί το Aspose.PDF για .NET. Αυτό περιλαμβάνει την εγκατάσταση της βιβλιοθήκης Aspose.PDF και τη διαμόρφωση του έργου σας για αναφορά σε αυτό.

## Βήμα 2: Δημιουργία εγγράφου

Σε αυτό το βήμα, θα δημιουργήσουμε ένα νέο αντικείμενο εγγράφου Aspose.PDF.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Δημιουργία εγγράφου
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Δημιουργήσαμε ένα νέο έγγραφο και ορίσαμε τον τίτλο και τη γλώσσα του εγγράφου.

## Βήμα 3: Απόκτηση του στοιχείου δομής ρίζας

Σε αυτό το βήμα θα λάβουμε το στοιχείο δομής ρίζας για το έγγραφό μας.

```csharp
//Αποκτήστε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
```

Πήραμε το στοιχείο δομής ρίζας που θα χρησιμεύσει ως δοχείο για το στοιχείο του πίνακα.

## Βήμα 4: Δημιουργία του στοιχείου δομής πίνακα

Τώρα ας δημιουργήσουμε ένα νέο στοιχείο δομής πίνακα για το έγγραφό μας.

```csharp
// Δημιουργήστε το στοιχείο δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Δημιουργήσαμε ένα νέο στοιχείο δομής πίνακα και το προσθέσαμε στο στοιχείο δομής ρίζας.

## Βήμα 5: Προσαρμογή στυλ και ιδιοτήτων στοιχείων πίνακα

Σε αυτό το βήμα, θα προσαρμόσουμε τα στυλ και τις ιδιότητες του στοιχείου πίνακα.

```csharp
// Προσαρμόστε τα στυλ και τις ιδιότητες του στοιχείου πίνακα
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Προσαρμόστε το στυλ των επαναλαμβανόμενων γραμμών
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Χρησιμοποιήσαμε διάφορες ιδιότητες για να προσαρμόσουμε το στοιχείο του πίνακα, όπως χρώμα φόντου, περιγράμματα, στοίχιση, προεπιλεγμένο στυλ κελιού, περιθώρια, πλάτος στήλης κ.λπ.

## Βήμα 6: Προσθέστε κεφαλίδες πίνακα, σώμα και υποσέλιδο

Τώρα ας προσθέσουμε τις κεφαλίδες του πίνακα, το σώμα και το υποσέλιδο στο στοιχείο του πίνακα.
```csharp
// Προσθήκη κεφαλίδων πίνακα
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Αριθμός σειρών και στηλών στον πίνακα
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Δημιουργήστε τη γραμμή κεφαλίδας πίνακα
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Προσθέστε τις σειρές του σώματος του πίνακα
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Προσθέστε τη γραμμή βάσης του πίνακα
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Προσθέσαμε τις κεφαλίδες, τις γραμμές σώματος και τη γραμμή υποσέλιδου στον πίνακα χρησιμοποιώντας τα αντίστοιχα στοιχεία.

## Βήμα 7: Αποθήκευση του εγγράφου PDF με ετικέτα

Τώρα που δημιουργήσαμε το έγγραφό μας με το στοιχείο του πίνακα με στυλ, θα το αποθηκεύσουμε ως έγγραφο PDF με ετικέτα.

```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "StyleTableElement.pdf");
```

Αποθηκεύσαμε το έγγραφο PDF με ετικέτα στον καθορισμένο κατάλογο.

## Βήμα 8: Επικύρωση συμμόρφωσης PDF/UA

Στη συνέχεια, θα επικυρώσουμε τη συμμόρφωση PDF/UA του εγγράφου μας.

```csharp
// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Ανεβάσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA δημιουργώντας μια αναφορά XML.

### Δείγμα πηγαίου κώδικα για το στοιχείο Style Table χρησιμοποιώντας το Aspose.PDF για .NET 

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Λήψη στοιχείου δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;

// Δημιουργία στοιχείου δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Αποθήκευση εγγράφου Pdf με ετικέτα
document.Save(dataDir + "StyleTableElement.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να μορφοποιούμε το στοιχείο πίνακα με Aspose.PDF για .NET. Προσαρμόσαμε τα στυλ και τις ιδιότητες του στοιχείου πίνακα, προσθέσαμε κεφαλίδες, σειρές σώματος και ένα υποσέλιδο, αποθηκεύσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου σχετικά με τη μορφοποίηση του στοιχείου πίνακα χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ο στόχος αυτού του σεμιναρίου είναι να σας καθοδηγήσει στη διαδικασία μορφοποίησης του στοιχείου πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Παρέχει οδηγίες βήμα προς βήμα και παραδείγματα πηγαίου κώδικα C# για να σας βοηθήσει να προσαρμόσετε τα στυλ και τις ιδιότητες του στοιχείου πίνακα.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης ώστε να χρησιμοποιείτε το Aspose.PDF για .NET. Αυτό περιλαμβάνει την εγκατάσταση της βιβλιοθήκης Aspose.PDF και τη διαμόρφωση του έργου σας για αναφορά σε αυτό.

#### Ε: Πώς μπορώ να δημιουργήσω ένα νέο έγγραφο PDF και να ορίσω τον τίτλο και τη γλώσσα του χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Για να δημιουργήσετε ένα νέο έγγραφο PDF, πρέπει να δημιουργήσετε ένα`Document` αντικείμενο από τη βιβλιοθήκη Aspose.PDF. Ο πηγαίος κώδικας C# που παρέχεται στο σεμινάριο δείχνει πώς να δημιουργήσετε ένα έγγραφο και να ορίσετε τις ιδιότητες του τίτλου και της γλώσσας του.

#### Ε: Ποια είναι η σημασία του στοιχείου ριζικής δομής σε ένα έγγραφο PDF;

Α: Το στοιχείο δομής ρίζας λειτουργεί ως κοντέινερ για άλλα στοιχεία δομής, βοηθώντας στην οργάνωση και την κατηγοριοποίηση του περιεχομένου του εγγράφου PDF. Διαδραματίζει κρίσιμο ρόλο στη δημιουργία της λογικής δομής του εγγράφου.

#### Ε: Πώς μπορώ να δημιουργήσω και να προσαρμόσω ένα στοιχείο δομής πίνακα χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Μπορείτε να δημιουργήσετε ένα στοιχείο δομής πίνακα χρησιμοποιώντας το`CreateTableElement()` μέθοδος. Ο πηγαίος κώδικας του σεμιναρίου παρέχει παραδείγματα προσαρμογής διαφόρων ιδιοτήτων του στοιχείου πίνακα, όπως χρώμα φόντου, περιγράμματα, στοίχιση, πλάτος στήλης και άλλα.

#### Ε: Μπορώ να προσαρμόσω τα στυλ και τις ιδιότητες των κελιών πίνακα εντός του στοιχείου πίνακα;

Α: Ναι, το σεμινάριο καλύπτει τον τρόπο προσαρμογής των στυλ και των ιδιοτήτων ολόκληρου του στοιχείου πίνακα, συμπεριλαμβανομένων των κεφαλίδων, των γραμμών σώματος και του υποσέλιδου. Ωστόσο, δεν ασχολείται συγκεκριμένα με την προσαρμογή μεμονωμένων κελιών πίνακα.

#### Ε: Πώς μπορώ να προσθέσω κεφαλίδες, γραμμές σώματος και υποσέλιδο στο στοιχείο του πίνακα;

Α: Το σεμινάριο εξηγεί πώς μπορείτε να δημιουργήσετε και να προσθέσετε κεφαλίδες, γραμμές σώματος και ένα υποσέλιδο στο στοιχείο του πίνακα χρησιμοποιώντας τις κατάλληλες μεθόδους που παρέχονται από το Aspose.PDF για .NET.

#### Ε: Τι είναι η συμμόρφωση PDF/UA και πώς μπορώ να την επικυρώσω για το έγγραφο PDF με ετικέτα;

 Α: Η συμμόρφωση με PDF/UA διασφαλίζει ότι το έγγραφο PDF συμμορφώνεται με τα πρότυπα προσβασιμότητας, καθιστώντας το πιο προσιτό σε χρήστες με ειδικές ανάγκες. Το σεμινάριο δείχνει πώς να επικυρώσετε τη συμμόρφωση PDF/UA χρησιμοποιώντας το`Validate()` μέθοδο και να δημιουργήσετε μια αναφορά συμμόρφωσης XML.

#### Ε: Πώς μπορώ να ενσωματώσω αυτές τις έννοιες στις δικές μου εφαρμογές .NET;

Α: Μπορείτε να χρησιμοποιήσετε τα παρεχόμενα παραδείγματα πηγαίου κώδικα C# ως οδηγό για την εφαρμογή μορφοποίησης στοιχείων πίνακα στις δικές σας εφαρμογές .NET. Τροποποιήστε και προσαρμόστε τον κώδικα ώστε να ταιριάζει στις απαιτήσεις σας και ενσωματώστε τον στα έργα σας.

#### Ε: Υπάρχουν προτεινόμενες βέλτιστες πρακτικές για τη μορφοποίηση στοιχείων πίνακα σε έγγραφα PDF;

Α: Κατά τη μορφοποίηση στοιχείων πίνακα (πίνακες), λάβετε υπόψη την αναγνωσιμότητα και την προσβασιμότητα του περιεχομένου. Χρησιμοποιήστε σαφείς και ευανάγνωστες γραμματοσειρές, κατάλληλα χρώματα και διατηρήστε μια σταθερή διάταξη. Επικυρώστε τη συμμόρφωση PDF/UA για να διασφαλίσετε ότι πληρούνται τα πρότυπα προσβασιμότητας.

#### Ε: Ποιες άλλες δυνατότητες του Aspose.PDF για .NET μπορώ να εξερευνήσω για προσαρμογή εγγράφων PDF;

Α: Το Aspose.PDF για .NET προσφέρει μια σειρά από δυνατότητες για προσαρμογή εγγράφων PDF, όπως χειρισμό κειμένου, εισαγωγή εικόνας, διαχείριση πεδίου φόρμας, ψηφιακές υπογραφές, σχολιασμούς και άλλα. Συμβουλευτείτε την επίσημη τεκμηρίωση και τους πόρους για να εξερευνήσετε πρόσθετες λειτουργίες.