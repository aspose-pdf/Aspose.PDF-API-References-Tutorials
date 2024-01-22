---
title: Επιτραπέζιο κελί στυλ
linktitle: Επιτραπέζιο κελί στυλ
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε στυλ κελιών πίνακα με το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα για τη δημιουργία και την προσαρμογή πινάκων.
type: docs
weight: 160
url: /el/net/programming-with-tagged-pdf/style-table-cell/
---
Καλώς ήρθατε σε αυτό το λεπτομερές σεμινάριο σχετικά με τη μορφοποίηση κελιών πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Σε αυτόν τον οδηγό, θα εξηγήσουμε λεπτομερώς κάθε βήμα του παρεχόμενου πηγαίου κώδικα C# για να σας βοηθήσουμε να κατανοήσετε πώς να κάνετε στυλ κελιών πίνακα. Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.PDF για .NET και έχετε ρυθμίσει το περιβάλλον ανάπτυξης πριν ξεκινήσετε.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Δημιουργήσαμε ένα νέο έγγραφο και ορίσαμε τον τίτλο και τη γλώσσα του εγγράφου.

## Βήμα 3: Απόκτηση του στοιχείου δομής ρίζας

Σε αυτό το βήμα θα λάβουμε το στοιχείο δομής ρίζας για το έγγραφό μας.

```csharp
//Αποκτήστε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
```

Πήραμε το στοιχείο δομής ρίζας που θα χρησιμεύσει ως δοχείο για τα στοιχεία του πίνακα.

## Βήμα 4: Δημιουργία του στοιχείου δομής πίνακα

Τώρα ας δημιουργήσουμε ένα νέο στοιχείο δομής πίνακα για το έγγραφό μας.

```csharp
// Δημιουργήστε το στοιχείο δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Δημιουργήσαμε ένα νέο στοιχείο δομής πίνακα και το προσθέσαμε στο στοιχείο δομής ρίζας. Δημιουργήσαμε επίσης τα στοιχεία κεφαλίδας, σώματος και υποσέλιδου πίνακα.

## Βήμα 5: Προσθήκη κεφαλίδων πίνακα

Σε αυτό το βήμα θα προσθέσουμε τις κεφαλίδες του πίνακα στον πίνακά μας.

```csharp
// Αριθμός σειρών και στηλών στον πίνακα
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Δημιουργήστε τη γραμμή κεφαλίδας πίνακα
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Δημιουργήσαμε μια σειρά κεφαλίδας για τον πίνακά μας και προσθέσαμε κελιά κεφαλίδας με ιδιότητες μορφοποίησης όπως χρώμα φόντου, περιθώρια, περιθώρια και στοίχιση.

## Βήμα 6: Προσθήκη των σειρών του σώματος του πίνακα

Τώρα ας προσθέσουμε τις γραμμές του σώματος του πίνακα στον πίνακά μας.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

Προσθέσαμε γραμμές στο σώμα του πίνακα χρησιμοποιώντας βρόχους για επανάληψη σε κάθε κελί πίνακα. Ορίζουμε ιδιότητες μορφοποίησης για κάθε κελί, όπως χρώμα φόντου, περιγράμματα, περιθώρια, στοίχιση κειμένου κ.λπ.

## Βήμα 7: Προσθήκη του υποσέλιδου

Τέλος, θα προσθέσουμε το υποσέλιδο του πίνακα στον πίνακά μας.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Δημιουργήσαμε ένα υποσέλιδο για τον πίνακά μας και προσθέσαμε κελιά υποσέλιδου με κείμενο.



## Βήμα 8: Αποθήκευση του εγγράφου PDF με ετικέτα

Τώρα που δημιουργήσαμε το έγγραφό μας με τον πίνακα με στυλ, θα το αποθηκεύσουμε ως έγγραφο PDF με ετικέτα.

```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "StyleTableCell.pdf");
```

Αποθηκεύσαμε το έγγραφο PDF με ετικέτα στον καθορισμένο κατάλογο.

## Βήμα 9: Επικύρωση συμμόρφωσης PDF/UA

Στη συνέχεια, θα επικυρώσουμε τη συμμόρφωση PDF/UA του εγγράφου μας.

```csharp
// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Ανεβάσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA δημιουργώντας μια αναφορά XML.

### Δείγμα πηγαίου κώδικα για το κελί του πίνακα στυλ χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Λήψη στοιχείου δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;

// Δημιουργία στοιχείου δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Αποθήκευση εγγράφου Pdf με ετικέτα
document.Save(dataDir + "StyleTableCell.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργείτε στυλ κελιών πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Είδαμε πώς να δημιουργήσετε ένα έγγραφο, να προσθέσετε έναν πίνακα με κεφαλίδες, σειρές σώματος και ένα υποσέλιδο και να προσαρμόσετε τα στυλ κελιών. Τέλος, αποθηκεύσαμε το έγγραφο PDF με ετικέτα και επικυρώσαμε τη συμμόρφωσή του με PDF/UA. Τώρα μπορείτε να χρησιμοποιήσετε το Aspose.PDF για .NET για να δημιουργήσετε και να διαμορφώσετε πίνακες στις εφαρμογές σας .NET.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου για τη μορφοποίηση κελιών πίνακα χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Αυτό το σεμινάριο στοχεύει να παρέχει έναν ολοκληρωμένο οδηγό σχετικά με τον τρόπο δημιουργίας στυλ κελιών πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Καλύπτει οδηγίες βήμα προς βήμα και παραδείγματα πηγαίου κώδικα C# για να σας βοηθήσει να κατανοήσετε και να εφαρμόσετε τη μορφοποίηση κελιών πίνακα.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.PDF για .NET και ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξής σας. Αυτό περιλαμβάνει τη διαμόρφωση του έργου σας για αναφορά στη βιβλιοθήκη Aspose.PDF.

#### Ε: Πώς μπορώ να δημιουργήσω ένα νέο έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Για να δημιουργήσετε ένα νέο έγγραφο PDF, πρέπει να δημιουργήσετε ένα`Document` αντικείμενο από τη βιβλιοθήκη Aspose.PDF. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει πώς να δημιουργήσετε ένα έγγραφο και να ορίσετε τον τίτλο και τη γλώσσα του.

#### Ε: Ποια είναι η σημασία του στοιχείου ριζικής δομής σε ένα έγγραφο PDF;

Α: Το στοιχείο δομής ρίζας χρησιμεύει ως κοντέινερ για άλλα στοιχεία δομής, βοηθώντας στην οργάνωση και την κατηγοριοποίηση του περιεχομένου του εγγράφου PDF. Διαδραματίζει κρίσιμο ρόλο στη δημιουργία της λογικής δομής του εγγράφου.

#### Ε: Πώς μπορώ να δημιουργήσω ένα στοιχείο δομής πίνακα και να προσαρμόσω την εμφάνισή του χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Μπορείτε να δημιουργήσετε ένα στοιχείο δομής πίνακα χρησιμοποιώντας το`CreateTableElement()` μέθοδος. Ο παρεχόμενος πηγαίος κώδικας δείχνει πώς να προσαρμόσετε την εμφάνιση του πίνακα, συμπεριλαμβανομένης της κεφαλίδας, του σώματος και του υποσέλιδου, ορίζοντας ιδιότητες όπως το χρώμα φόντου, τα περιθώρια, τα περιθώρια και τη στοίχιση.

#### Ε: Μπορώ να προσθέσω πολλές σειρές και στήλες στο σώμα του πίνακα και να προσαρμόσω τη μορφοποίησή τους;

Α: Ναι, το σεμινάριο δείχνει πώς μπορείτε να προσθέσετε πολλές σειρές και στήλες στο σώμα του πίνακα χρησιμοποιώντας βρόχους. Παρέχει επίσης παραδείγματα προσαρμογής μορφοποίησης κελιών, όπως χρώμα φόντου, περιγράμματα, στοίχιση κειμένου, στυλ γραμματοσειράς και άλλα.

#### Ε: Ποιος είναι ο σκοπός της επικύρωσης της συμμόρφωσης PDF/UA και πώς μπορώ να εκτελέσω αυτήν την επικύρωση;

 Α: Η επικύρωση της συμμόρφωσης PDF/UA διασφαλίζει ότι το έγγραφο PDF συμμορφώνεται με τα πρότυπα προσβασιμότητας, καθιστώντας το πιο προσιτό σε χρήστες με ειδικές ανάγκες. Το σεμινάριο δείχνει πώς να επικυρώσετε τη συμμόρφωση PDF/UA χρησιμοποιώντας το`Validate()` μέθοδο και δημιουργήστε μια αναφορά XML.

#### Ε: Πώς μπορώ να εφαρμόσω αυτές τις έννοιες στις δικές μου εφαρμογές .NET;

Α: Μπορείτε να χρησιμοποιήσετε τα παρεχόμενα παραδείγματα πηγαίου κώδικα C# ως οδηγό για την εφαρμογή μορφοποίησης κελιών πίνακα στις δικές σας εφαρμογές .NET. Προσαρμόστε τον κώδικα όπως απαιτείται για να ταιριάζει στις απαιτήσεις σας και ενσωματώστε τον στα έργα σας.

#### Ε: Υπάρχουν προτεινόμενες βέλτιστες πρακτικές για τη διαμόρφωση κελιών πίνακα σε έγγραφα PDF;

Α: Κατά τη διαμόρφωση κελιών πίνακα, λάβετε υπόψη τις ανάγκες του κοινού σας, συμπεριλαμβανομένων των απαιτήσεων προσβασιμότητας. Χρησιμοποιήστε χρώματα σε αντίθεση, κατάλληλες γραμματοσειρές και καθαρή στοίχιση κελιών για να βελτιώσετε την αναγνωσιμότητα. Επιπλέον, επικυρώστε τη συμμόρφωση PDF/UA για να διασφαλίσετε ότι πληρούνται τα πρότυπα προσβασιμότητας.

#### Ε: Ποιες άλλες δυνατότητες του Aspose.PDF για .NET μπορώ να εξερευνήσω για χειρισμό εγγράφων PDF;

Α: Το Aspose.PDF για .NET προσφέρει ένα ευρύ φάσμα δυνατοτήτων για χειρισμό εγγράφων PDF, όπως εξαγωγή κειμένου, εισαγωγή εικόνας, διαχείριση πεδίου φόρμας, ψηφιακές υπογραφές και άλλα. Εξερευνήστε την επίσημη τεκμηρίωση και τους πόρους για να μάθετε για πρόσθετες λειτουργίες.
