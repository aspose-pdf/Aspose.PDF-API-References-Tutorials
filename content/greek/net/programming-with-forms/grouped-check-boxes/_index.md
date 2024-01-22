---
title: Ομαδοποιημένα πλαίσια ελέγχου σε έγγραφο PDF
linktitle: Ομαδοποιημένα πλαίσια ελέγχου σε έγγραφο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Δημιουργήστε εύκολα ομαδοποιημένα πλαίσια ελέγχου σε έγγραφο PDF με το Aspose.PDF για .NET.
type: docs
weight: 170
url: /el/net/programming-with-forms/grouped-check-boxes/
---
Σε αυτό το σεμινάριο, θα σας δείξουμε πώς να δημιουργείτε ομαδοποιημένα πλαίσια ελέγχου σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# βήμα προς βήμα για να σας καθοδηγήσουμε σε αυτήν τη διαδικασία.

## Βήμα 1: Προετοιμασία

Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες βιβλιοθήκες και έχετε ορίσει τη διαδρομή προς τον κατάλογο των εγγράφων σας:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα αντικείμενο εγγράφου

Δημιουργία αντικειμένου εγγράφου:

```csharp
Document pdfDocument = new Document();
```

## Βήμα 3: Προσθήκη σελίδας σε έγγραφο PDF

Προσθέστε μια σελίδα στο έγγραφο PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Βήμα 4: Δημιουργήστε ένα αντικείμενο πεδίου RadioButton

Δημιουργήστε ένα αντικείμενο RadioButtonField με όρισμα τον αριθμό σελίδας:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Βήμα 5: Προσθέστε επιλογές κουμπιού επιλογής

Προσθέστε επιλογές κουμπιών επιλογής χρησιμοποιώντας το αντικείμενο RadioButtonOptionField και καθορίστε τη θέση τους χρησιμοποιώντας το αντικείμενο Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Βήμα 6: Προσαρμόστε τις επιλογές των κουμπιών επιλογής

Προσαρμόστε τις επιλογές των κουμπιών επιλογής ορίζοντας το στυλ, το περίγραμμα και την εμφάνισή τους:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Βήμα 7: Προσθέστε τα κουμπιά επιλογής στη φόρμα

Προσθέστε τα κουμπιά επιλογής στο αντικείμενο της φόρμας εγγράφου:

```csharp
pdfDocument.Form.Add(radio);
```

## Βήμα 8: Αποθηκεύστε το έγγραφο

Αποθηκεύστε το έγγραφο PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Δείγμα πηγαίου κώδικα για ομαδοποιημένα πλαίσια ελέγχου χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
try
{
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Δημιουργία αντικειμένου εγγράφου
	Document pdfDocument = new Document();
	// Προσθήκη σελίδας σε αρχείο PDF
	Page page = pdfDocument.Pages.Add();
	// Εγκαταστήστε το αντικείμενο RadioButtonField με τον αριθμό σελίδας ως όρισμα
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Προσθέστε την πρώτη επιλογή κουμπιού επιλογής και καθορίστε επίσης την προέλευσή του χρησιμοποιώντας το αντικείμενο Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Προσθήκη κουμπιού επιλογής για να σχηματίσετε το αντικείμενο του αντικειμένου Document
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Αποθηκεύστε το έγγραφο PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε ομαδοποιημένα πλαίσια ελέγχου σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσθέσετε προσαρμοσμένες επιλογές κουμπιών επιλογής και να τις ομαδοποιήσετε στα έγγραφά σας PDF χρησιμοποιώντας το Aspose.PDF.

### Συχνές ερωτήσεις

#### Ε: Τι είναι τα ομαδοποιημένα πλαίσια ελέγχου σε ένα έγγραφο PDF;

Α: Τα ομαδοποιημένα πλαίσια ελέγχου σε ένα έγγραφο PDF αναφέρονται σε ένα σύνολο επιλογών κουμπιών επιλογής που είναι ομαδοποιημένες. Τα κουμπιά επιλογής επιτρέπουν στους χρήστες να επιλέξουν μόνο μία επιλογή από μια ομάδα αμοιβαία αποκλειστικών επιλογών. Όταν επιλέγεται ένα κουμπί επιλογής, τα άλλα στην ίδια ομάδα αποεπιλέγονται αυτόματα. Αυτή η συμπεριφορά ομαδοποίησης είναι χρήσιμη όταν θέλετε να παρουσιάσετε στους χρήστες πολλαπλές επιλογές αλλά να περιορίσετε την επιλογή τους σε μία μόνο επιλογή.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση ομαδοποιημένων πλαισίων ελέγχου στο Aspose.PDF για .NET;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση ομαδοποιημένων πλαισίων ελέγχου στο Aspose.PDF για .NET. Το API παρέχει διάφορες επιλογές για να ορίσετε το στυλ, το περίγραμμα και την εμφάνιση των επιλογών των κουμπιών επιλογής. Μπορείτε να ορίσετε τη θέση κάθε επιλογής, να επιλέξετε ανάμεσα σε διαφορετικά στυλ πλαισίου (π.χ. τετράγωνο, κύκλος, σταυρός) και να προσαρμόσετε τις ιδιότητες περιγράμματος για να επιτύχετε την επιθυμητή οπτική αναπαράσταση.

#### Ε: Πώς μπορώ να προσθέσω ομαδοποιημένα πλαίσια ελέγχου σε μια συγκεκριμένη σελίδα σε ένα έγγραφο PDF;

Α: Για να προσθέσετε ομαδοποιημένα πλαίσια ελέγχου σε μια συγκεκριμένη σελίδα σε ένα έγγραφο PDF, πρέπει να δημιουργήσετε ένα`RadioButtonField` αντικείμενο με τον επιθυμητό αριθμό σελίδας ως όρισμα. Στη συνέχεια, δημιουργήστε`RadioButtonOptionField` αντικείμενα που αντιπροσωπεύουν κάθε επιλογή κουμπιού επιλογής και καθορίστε τη θέση τους χρησιμοποιώντας το`Rectangle` αντικείμενο. Τέλος, προσθέστε αυτές τις επιλογές στο`RadioButtonField` και προσαρμόστε την εμφάνισή τους όπως απαιτείται πριν προσθέσετε το`RadioButtonField` στο έντυπο εγγράφου.

#### Ε: Μπορώ να προσθέσω πολλές ομάδες πλαισίων ελέγχου σε ένα έγγραφο PDF;

 Α: Ναι, μπορείτε να προσθέσετε πολλές ομάδες πλαισίων ελέγχου σε ένα μόνο έγγραφο PDF. Κάθε ομάδα πρέπει να έχει ένα μοναδικό`RadioButtonField` αντικείμενο, και το`RadioButtonOptionField` Τα αντικείμενα σε κάθε ομάδα πρέπει να μοιράζονται την ίδια σελίδα και μοναδικά ονόματα για τις επιλογές τους. Αυτό διασφαλίζει ότι τα κουμπιά επιλογής σε κάθε ομάδα λειτουργούν σωστά και ότι οι επιλογές είναι αμοιβαία αποκλειόμενες.

#### Ε: Υποστηρίζονται ομαδοποιημένα πλαίσια ελέγχου σε όλα τα προγράμματα προβολής PDF και τις εφαρμογές;

Α: Ναι, τα ομαδοποιημένα πλαίσια ελέγχου υποστηρίζονται σε όλα τα προγράμματα προβολής PDF και τις εφαρμογές που είναι συμβατά με τα πρότυπα. Η προδιαγραφή PDF ορίζει τα κουμπιά επιλογής και τη συμπεριφορά ομαδοποίησης τους, καθιστώντας τα παγκοσμίως αναγνωρισμένα στη μορφή PDF. Ωστόσο, είναι απαραίτητο να δοκιμάσετε τη λειτουργικότητα σε διαφορετικά προγράμματα προβολής PDF για να διασφαλίσετε τη συνεπή συμπεριφορά σε διάφορες πλατφόρμες.