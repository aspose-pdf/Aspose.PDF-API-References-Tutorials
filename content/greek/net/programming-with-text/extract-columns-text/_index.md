---
title: Εξαγωγή κειμένου στηλών σε αρχείο PDF
linktitle: Εξαγωγή κειμένου στηλών σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εξάγετε κείμενο στηλών σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 150
url: /el/net/programming-with-text/extract-columns-text/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία εξαγωγής κειμένου στηλών σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να εξαγάγετε κείμενο στηλών, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Ανοίξτε το έγγραφο PDF
 Ανοίξτε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document`κατασκευαστή και περνώντας τη διαδρομή προς το αρχείο εισόδου PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Βήμα 5: Προσαρμόστε το μέγεθος της γραμματοσειράς
Μειώστε το μέγεθος της γραμματοσειράς των τμημάτων κειμένου κατά 0,7 για να βελτιώσετε την αναγνωσιμότητα και να αναπαραστήσετε καλύτερα το κείμενο στηλών.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Βήμα 6: Εξαγωγή κειμένου από στήλες
 Αποθηκεύστε το τροποποιημένο έγγραφο PDF σε μια ροή μνήμης και φορτώστε το ξανά ως νέο έγγραφο. Στη συνέχεια, χρησιμοποιήστε το`TextAbsorber` κλάση για εξαγωγή κειμένου από τις στήλες.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Βήμα 7: Αποθηκεύστε το εξαγόμενο κείμενο
Αποθηκεύστε το εξαγόμενο κείμενο σε ένα αρχείο κειμένου στην καθορισμένη διαδρομή αρχείου εξόδου.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Δείγμα πηγαίου κώδικα για κείμενο εξαγωγής στηλών χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Πρέπει να μειωθεί το μέγεθος της γραμματοσειράς τουλάχιστον κατά 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## συμπέρασμα
Έχετε εξαγάγει με επιτυχία το κείμενο στηλών από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το εξαγόμενο κείμενο έχει αποθηκευτεί στο καθορισμένο αρχείο εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο προσφέρει έναν οδηγό βήμα προς βήμα για την εξαγωγή στηλών κειμένου από ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο συνοδευτικός πηγαίος κώδικας C# παρέχει μια πρακτική επίδειξη των απαιτούμενων διαδικασιών.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω;

Α: Στο αρχείο κώδικα όπου σκοπεύετε να εξαγάγετε στήλες κειμένου, συμπεριλάβετε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Εντοπίστε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` στον κωδικό και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να ανοίξω ένα υπάρχον έγγραφο PDF;

 Α: Στο Βήμα 4, θα ανοίξετε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document` κατασκευαστή και παρέχοντας τη διαδρομή προς το αρχείο εισόδου PDF.

#### Ε: Γιατί προσαρμόζεται το μέγεθος της γραμματοσειράς;

Α: Το βήμα 5 περιλαμβάνει τη μείωση του μεγέθους της γραμματοσειράς των θραυσμάτων κειμένου κατά 0,7. Αυτή η προσαρμογή βελτιώνει την αναγνωσιμότητα και αναπαριστά με μεγαλύτερη ακρίβεια το κείμενο στηλών.

#### Ε: Πώς μπορώ να εξαγάγω κείμενο από στήλες;

 Α: Το βήμα 6 αποτελείται από την αποθήκευση του τροποποιημένου εγγράφου PDF σε μια ροή μνήμης, την εκ νέου φόρτωσή του ως νέο έγγραφο και, στη συνέχεια, τη χρήση του`TextAbsorber` κλάση για εξαγωγή κειμένου από τις στήλες.

#### Ε: Ποιος είναι ο σκοπός της αποθήκευσης του εξαγόμενου κειμένου;

Α: Στο Βήμα 7, θα αποθηκεύσετε το εξαγόμενο κείμενο σε ένα αρχείο κειμένου στην καθορισμένη διαδρομή αρχείου εξόδου.

#### Ε: Γιατί να μειώσετε το μέγεθος της γραμματοσειράς πριν την εξαγωγή;

Α: Η μείωση του μεγέθους της γραμματοσειράς διασφαλίζει ότι το εξαγόμενο κείμενο ευθυγραμμίζεται σωστά μέσα στις στήλες, παρέχοντας μια πιο ακριβή αναπαράσταση της αρχικής διάταξης.

#### Ε: Ποιο είναι το βασικό στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, έχετε αποκτήσει τις γνώσεις και τις δεξιότητες που απαιτούνται για την εξαγωγή στηλών κειμένου από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το κείμενο που προκύπτει έχει αποθηκευτεί στο καθορισμένο αρχείο εξόδου.