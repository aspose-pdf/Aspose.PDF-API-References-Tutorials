---
title: Σειρά πίνακα στυλ
linktitle: Σειρά πίνακα στυλ
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσαρμόζετε τις σειρές πίνακα με το Aspose.PDF για .NET οδηγός βήμα προς βήμα για το στυλ και τη μορφοποίηση σειρών.
type: docs
weight: 180
url: /el/net/programming-with-tagged-pdf/style-table-row/
---
Σε αυτό το λεπτομερές σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα στον παρεχόμενο πηγαίο κώδικα C# για να μορφοποιήσετε τη σειρά του πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθήστε τις παρακάτω οδηγίες για να κατανοήσετε πώς να προσαρμόσετε τα στυλ και τις ιδιότητες σειρών πίνακα.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Βήμα 5: Προσαρμόστε στυλ και ιδιότητες σειρών πίνακα

Σε αυτό το βήμα, θα προσαρμόσουμε τα στυλ και τις ιδιότητες σειρών πίνακα.

```csharp
// Προσαρμόστε στυλ και ιδιότητες σειρών πίνακα
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Προσαρμόστε τις σειρές του σώματος του πίνακα
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Δημιουργήστε τη γραμμή υποσέλιδου του πίνακα
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Έχουμε προσαρμόσει διάφορες πτυχές της σειράς του πίνακα, όπως το χρώμα φόντου, τα περιγράμματα, το ύψος της γραμμής, τη σελιδοποίηση, το προεπιλεγμένο στυλ κελιού και άλλα.

## Βήμα 6: Αποθήκευση του εγγράφου PDF με ετικέτα

Τώρα που δημιουργήσαμε το έγγραφό μας με τη γραμμή του πίνακα με στυλ, θα το αποθηκεύσουμε ως έγγραφο PDF με ετικέτα.
```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "StyleTableRow.pdf");
```

Αποθηκεύσαμε το έγγραφο PDF με ετικέτα στον καθορισμένο κατάλογο.

## Βήμα 7: Επικύρωση συμμόρφωσης PDF/UA

Στη συνέχεια, θα επικυρώσουμε τη συμμόρφωση PDF/UA του εγγράφου μας.

```csharp
// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Ανεβάσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA δημιουργώντας μια αναφορά XML.


### Δείγμα πηγαίου κώδικα για Γραμμή πίνακα στυλ χρησιμοποιώντας Aspose.PDF για .NET 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Λήψη στοιχείου δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;

// Δημιουργία στοιχείου δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να μορφοποιούμε τη γραμμή πίνακα με το Aspose.PDF για .NET. Προσαρμόσαμε τα στυλ και τις ιδιότητες των σειρών του πίνακα, προσθέσαμε τις κεφαλίδες, τις γραμμές σώματος και το υποσέλιδο, αποθηκεύσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου για τη μορφοποίηση σειρών πίνακα με χρήση Aspose.PDF για .NET;

Α: Ο σκοπός αυτού του σεμιναρίου είναι να σας καθοδηγήσει στη διαδικασία μορφοποίησης σειρών πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Παρέχει οδηγίες βήμα προς βήμα και παραδείγματα πηγαίου κώδικα C# για να σας βοηθήσει να προσαρμόσετε στυλ και ιδιότητες σειρών πίνακα.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης ώστε να χρησιμοποιείτε το Aspose.PDF για .NET. Αυτό περιλαμβάνει την εγκατάσταση της βιβλιοθήκης Aspose.PDF και τη διαμόρφωση του έργου σας για αναφορά σε αυτό.

#### Ε: Πώς μπορώ να δημιουργήσω ένα νέο έγγραφο PDF και να ορίσω τον τίτλο και τη γλώσσα του χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Για να δημιουργήσετε ένα νέο έγγραφο PDF, πρέπει να δημιουργήσετε ένα`Document` αντικείμενο από τη βιβλιοθήκη Aspose.PDF. Ο πηγαίος κώδικας C# που παρέχεται στο σεμινάριο δείχνει πώς να δημιουργήσετε ένα έγγραφο και να ορίσετε τις ιδιότητες του τίτλου και της γλώσσας του.

#### Ε: Ποια είναι η σημασία του στοιχείου ριζικής δομής σε ένα έγγραφο PDF;

Α: Το στοιχείο δομής ρίζας λειτουργεί ως κοντέινερ για άλλα στοιχεία δομής, βοηθώντας στην οργάνωση και την κατηγοριοποίηση του περιεχομένου του εγγράφου PDF. Διαδραματίζει κρίσιμο ρόλο στη δημιουργία της λογικής δομής του εγγράφου.

#### Ε: Πώς μπορώ να δημιουργήσω και να προσαρμόσω ένα στοιχείο δομής πίνακα για να μορφοποιήσω σειρές πίνακα χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Το σεμινάριο εξηγεί πώς να δημιουργήσετε ένα στοιχείο δομής πίνακα και να προσαρμόσετε τις ιδιότητές του για να μορφοποιήσετε σειρές πίνακα. Καλύπτει πτυχές όπως το χρώμα φόντου, τα περιγράμματα, το ύψος της γραμμής, τη σελιδοποίηση, το προεπιλεγμένο στυλ κελιού και άλλα.

#### Ε: Μπορώ να προσαρμόσω τα στυλ και τις ιδιότητες μεμονωμένων κελιών σε μια σειρά πίνακα;

Α: Ναι, μπορείτε να προσαρμόσετε τα στυλ και τις ιδιότητες μεμονωμένων κελιών σε μια σειρά πίνακα. Το σεμινάριο δείχνει πώς να ορίσετε ιδιότητες όπως χρώμα φόντου, περιγράμματα, χρώμα κειμένου, συμπλήρωση και άλλα για κελιά πίνακα εντός της μορφοποιημένης γραμμής πίνακα.

#### Ε: Πώς μπορώ να προσθέσω κεφαλίδες, γραμμές σώματος και υποσέλιδο στη μορφοποιημένη σειρά πίνακα;

Α: Το σεμινάριο παρέχει παραδείγματα δημιουργίας και προσθήκης κεφαλίδων, γραμμών σώματος και υποσέλιδου στο στοιχείο δομής πίνακα. Αυτά τα στοιχεία μπορούν να προσαρμοστούν περαιτέρω χρησιμοποιώντας τις ιδιότητες που περιγράφονται στο σεμινάριο.

#### Ε: Τι είναι η συμμόρφωση PDF/UA και πώς μπορώ να την επικυρώσω για το έγγραφο PDF με ετικέτα;

 Α: Η συμμόρφωση με PDF/UA διασφαλίζει ότι το έγγραφο PDF συμμορφώνεται με τα πρότυπα προσβασιμότητας, καθιστώντας το πιο προσιτό σε χρήστες με ειδικές ανάγκες. Το σεμινάριο δείχνει πώς να επικυρώσετε τη συμμόρφωση PDF/UA χρησιμοποιώντας το`Validate()` μέθοδο και να δημιουργήσετε μια αναφορά συμμόρφωσης XML.

#### Ε: Πώς μπορώ να ενσωματώσω αυτές τις έννοιες στις δικές μου εφαρμογές .NET;

Α: Μπορείτε να χρησιμοποιήσετε τα παρεχόμενα παραδείγματα πηγαίου κώδικα C# ως οδηγό για την εφαρμογή μορφοποίησης σειρών πίνακα στις δικές σας εφαρμογές .NET. Τροποποιήστε και προσαρμόστε τον κώδικα ώστε να ταιριάζει στις απαιτήσεις σας και ενσωματώστε τον στα έργα σας.

#### Ε: Υπάρχουν προτεινόμενες βέλτιστες πρακτικές για τη μορφοποίηση σειρών πίνακα σε έγγραφα PDF;

Α: Κατά τη μορφοποίηση σειρών πίνακα, λάβετε υπόψη την αναγνωσιμότητα και την προσβασιμότητα του περιεχομένου. Βεβαιωθείτε ότι τα χρώματα έχουν επαρκή αντίθεση, χρησιμοποιήστε σαφείς και ευανάγνωστες γραμματοσειρές και διατηρήστε μια συνεπή διάταξη. Επικυρώστε τη συμμόρφωση PDF/UA για να διασφαλίσετε ότι πληρούνται τα πρότυπα προσβασιμότητας.

#### Ε: Ποιες άλλες δυνατότητες του Aspose.PDF για .NET μπορώ να εξερευνήσω για προσαρμογή εγγράφων PDF;

Α: Το Aspose.PDF για .NET προσφέρει ένα ευρύ φάσμα δυνατοτήτων για προσαρμογή εγγράφων PDF, συμπεριλαμβανομένης της επεξεργασίας κειμένου, της εισαγωγής εικόνας, της διαχείρισης πεδίου φόρμας, των ψηφιακών υπογραφών, των σχολιασμών και πολλά άλλα. Συμβουλευτείτε την επίσημη τεκμηρίωση και τους πόρους για να εξερευνήσετε πρόσθετες λειτουργίες.