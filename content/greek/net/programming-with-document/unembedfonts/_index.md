---
title: Ενσωμάτωση γραμματοσειρών και βελτιστοποίηση αρχείων PDF
linktitle: Ενσωμάτωση γραμματοσειρών και βελτιστοποίηση αρχείων PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.PDF για .NET για λήψη Unembed Fonts και βελτιστοποίηση αρχείων PDF. Ένας οδηγός βήμα προς βήμα.
type: docs
weight: 370
url: /el/net/programming-with-document/unembedfonts/
---
Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που παρέχει ένα ευρύ φάσμα δυνατοτήτων για εργασία με έγγραφα PDF. Ένα από τα χαρακτηριστικά του είναι η λήψη μη ενσωματωμένων γραμματοσειρών από ένα έγγραφο PDF. Αυτό μπορεί να είναι χρήσιμο εάν χρειάζεται να εξαγάγετε γραμματοσειρές από ένα έγγραφο PDF και να τις χρησιμοποιήσετε σε άλλες εφαρμογές.

θα παρέχουμε έναν οδηγό βήμα προς βήμα για να εξηγήσουμε τον ακόλουθο πηγαίο κώδικα C# της δυνατότητας λήψης μη ενσωματωμένων γραμματοσειρών του Aspose.PDF για .NET.

## Βήμα 1: Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων

Πριν ξεκινήσουμε, πρέπει να ορίσουμε τη διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφο PDF μας. Θα αποθηκεύσουμε αυτή τη διαδρομή σε μια μεταβλητή που ονομάζεται "dataDir".

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Αντικαταστήστε το "YOUR DOCUMENT DECTORY" με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφό σας PDF.

## Βήμα 2: Ανοίξτε το έγγραφο PDF

 Το πρώτο βήμα είναι να φορτώσετε το έγγραφο PDF που θέλετε να το κάνετε, χρησιμοποιήστε το`Document` κλάση Aspose.PDF για .NET. Το ακόλουθο απόσπασμα κώδικα δείχνει πώς να φορτώσετε το έγγραφο PDF:

```csharp
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Βήμα 3: Ορίστε την επιλογή UnembedFonts

 Για να λάβετε μη ενσωματωμένες γραμματοσειρές από το έγγραφο PDF, πρέπει να ορίσετε το`UnembedFonts` επιλογή να`true` . Αυτή η επιλογή είναι διαθέσιμη στο`OptimizationOptions` τάξη. Το παρακάτω απόσπασμα κώδικα δείχνει πώς να ορίσετε το`UnembedFonts` επιλογή:

```csharp
// Ορίστε την επιλογή UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Βήμα 4: Βελτιστοποιήστε το έγγραφο PDF

 Μετά τη ρύθμιση του`UnembedFonts` επιλογή, μπορείτε να βελτιστοποιήσετε το έγγραφο PDF χρησιμοποιώντας το`OptimizeResources` μέθοδος του`Document` τάξη. Το ακόλουθο απόσπασμα κώδικα δείχνει πώς να βελτιστοποιήσετε το έγγραφο PDF:

```csharp
// Βελτιστοποιήστε το έγγραφο PDF χρησιμοποιώντας το OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Βήμα 5: Αποθηκεύστε το ενημερωμένο έγγραφο

 Μόλις βελτιστοποιηθεί το έγγραφο PDF, μπορείτε να αποθηκεύσετε το ενημερωμένο έγγραφο χρησιμοποιώντας το`Save` μέθοδος του`Document`τάξη. Το ακόλουθο απόσπασμα κώδικα δείχνει πώς να αποθηκεύσετε το ενημερωμένο έγγραφο:

```csharp
// Αποθήκευση ενημερωμένου εγγράφου
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Βήμα 6: Λάβετε το αρχικό και το μειωμένο μέγεθος αρχείου

 Τέλος, μπορείτε να λάβετε το αρχικό και το μειωμένο μέγεθος αρχείου του εγγράφου PDF χρησιμοποιώντας το`FileInfo` κλάση Συστήματος.ΙΟ. Το ακόλουθο απόσπασμα κώδικα δείχνει πώς να αποκτήσετε το αρχικό και το μειωμένο μέγεθος αρχείου:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Παράδειγμα πηγαίου κώδικα για λήψη γραμματοσειρών χωρίς ενσωμάτωση χρησιμοποιώντας Aspose.PDF για .NET

Ακολουθεί το πλήρες παράδειγμα πηγαίου κώδικα για τη λήψη μη ενσωματωμένων γραμματοσειρών από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET:

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ορίστε την επιλογή UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Βελτιστοποιήστε το έγγραφο PDF χρησιμοποιώντας το OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Αποθήκευση ενημερωμένου εγγράφου
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, δείξαμε πώς να χρησιμοποιείτε το Aspose.PDF για .NET για τη λήψη γραμματοσειρών χωρίς ενσωμάτωση από ένα έγγραφο PDF. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε εύκολα να εφαρμόσετε αυτήν τη δυνατότητα στις εφαρμογές σας C#. Η μη ενσωμάτωση γραμματοσειρών μπορεί να είναι επωφελής όταν χρειάζεται να εργαστείτε με τις εξαγόμενες γραμματοσειρές ξεχωριστά ή να εξασφαλίσετε συνεπή χρήση γραμματοσειρών σε διάφορες πλατφόρμες.

## Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός της απεγκατάστασης γραμματοσειρών από ένα έγγραφο PDF;

Α: Η μη ενσωμάτωση γραμματοσειρών από ένα έγγραφο PDF σάς επιτρέπει να εξαγάγετε τις ενσωματωμένες γραμματοσειρές και να τις χρησιμοποιήσετε σε άλλες εφαρμογές. Αυτό μπορεί να είναι χρήσιμο για τη διασφάλιση συνεπούς απόδοσης γραμματοσειράς και τη διατήρηση της οπτικής εμφάνισης του εγγράφου.

#### Ε: Πώς μπορώ να καθορίσω τη διαδρομή προς τον κατάλογο εγγράφων στον κώδικα C#;

 Α: Για να καθορίσετε τη διαδρομή προς τον κατάλογο εγγράφων, αντικαταστήστε το`"YOUR DOCUMENT DIRECTORY"` στον κώδικα με την πραγματική διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφο PDF σας.

####  Ε: Τι κάνει το`UnembedFonts` option do, and where is it set?

 Α: Το`UnembedFonts` επιλογή, διαθέσιμη στο`OptimizationOptions` class, ενεργοποιεί ή απενεργοποιεί την απεμπλοκή γραμματοσειρών από το έγγραφο PDF. Για να ορίσετε αυτήν την επιλογή σε`true`, χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Ε: Μπορώ να επαναφέρω τις αλλαγές που έγιναν κατά τη διαδικασία βελτιστοποίησης;

Α: Το Aspose.PDF για .NET δεν πραγματοποιεί μόνιμες αλλαγές στο αρχικό έγγραφο PDF κατά τη βελτιστοποίηση. Η διαδικασία βελτιστοποίησης εκτελείται σε ένα αντίγραφο του εγγράφου, αφήνοντας το πρωτότυπο ανέπαφο.

#### Ε: Πώς μπορώ να ελέγξω το αρχικό και το μειωμένο μέγεθος αρχείου μετά τη βελτιστοποίηση;

Α: Μπορείτε να χρησιμοποιήσετε το`FileInfo` τάξη του`System.IO` για να λάβετε το αρχικό και μειωμένο μέγεθος αρχείου. Ακολουθεί ένα παράδειγμα αποσπάσματος κώδικα για να επιτευχθεί αυτό:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```