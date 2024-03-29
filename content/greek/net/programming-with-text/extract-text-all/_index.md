---
title: Εξαγωγή κειμένου σε όλο το αρχείο PDF
linktitle: Εξαγωγή αρχείου PDF AllIn κειμένου
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εξαγάγετε όλο το κείμενο σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 180
url: /el/net/programming-with-text/extract-text-all/
---
Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία εξαγωγής όλου του κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τα απαραίτητα βήματα.

## Απαιτήσεις
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Visual Studio ή οποιοσδήποτε άλλος μεταγλωττιστής C# είναι εγκατεστημένος στον υπολογιστή σας.
- Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από τον επίσημο ιστότοπο του Aspose ή να χρησιμοποιήσετε έναν διαχειριστή πακέτων όπως το NuGet για να το εγκαταστήσετε.

## Βήμα 1: Ρύθμιση του έργου
1. Δημιουργήστε ένα νέο έργο C# στο περιβάλλον ανάπτυξης που προτιμάτε.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαιτούμενους χώρους ονομάτων
Στο αρχείο κώδικα όπου θέλετε να εξαγάγετε κείμενο, προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στο επάνω μέρος του αρχείου:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Βήμα 3: Ορίστε τον κατάλογο εγγράφων
 Στον κώδικα, εντοπίστε τη γραμμή που λέει`string dataDir = "YOUR DOCUMENT DIRECTORY";` και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 4: Ανοίξτε το έγγραφο PDF
 Ανοίξτε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document`κατασκευαστή και περνώντας τη διαδρομή προς το αρχείο εισόδου PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Βήμα 5: Εξαγωγή όλου του κειμένου
 Δημιουργώ ένα`TextAbsorber`αντικείμενο για εξαγωγή κειμένου από το έγγραφο. Στη συνέχεια, αποδεχτείτε τον απορροφητήρα για όλες τις σελίδες.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Βήμα 6: Λάβετε το εξαγόμενο κείμενο
 Πρόσβαση στο εξαγόμενο κείμενο από το`TextAbsorber` αντικείμενο.

```csharp
string extractedText = textAbsorber.Text;
```

## Βήμα 7: Αποθηκεύστε το εξαγόμενο κείμενο
 Δημιουργώ ένα`TextWriter` και ανοίξτε το αρχείο στο οποίο θέλετε να αποθηκεύσετε το εξαγόμενο κείμενο. Γράψτε το εξαγόμενο κείμενο στο αρχείο και κλείστε τη ροή.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Δείγμα πηγαίου κώδικα για Εξαγωγή κειμένου όλων χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Δημιουργήστε αντικείμενο TextAbsorber για εξαγωγή κειμένου
TextAbsorber textAbsorber = new TextAbsorber();
// Αποδεχτείτε τον απορροφητήρα για όλες τις σελίδες
pdfDocument.Pages.Accept(textAbsorber);
// Λάβετε το εξαγόμενο κείμενο
string extractedText = textAbsorber.Text;
// Δημιουργήστε ένα πρόγραμμα εγγραφής και ανοίξτε το αρχείο
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Γράψτε μια γραμμή κειμένου στο αρχείο
tw.WriteLine(extractedText);
// Κλείστε τη ροή
tw.Close();
```

## συμπέρασμα
Έχετε εξαγάγει με επιτυχία όλο το κείμενο από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το εξαγόμενο κείμενο έχει αποθηκευτεί στο καθορισμένο αρχείο εξόδου.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός αυτού του σεμιναρίου;

Α: Αυτό το σεμινάριο χρησιμεύει ως οδηγός για να σας βοηθήσει να εξαγάγετε όλο το κείμενο από ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ο συνοδευτικός πηγαίος κώδικας C# παρέχει οδηγίες βήμα προς βήμα για την επίτευξη αυτής της εργασίας.

#### Ε: Ποιους χώρους ονομάτων πρέπει να εισάγω;

Α: Στο αρχείο κώδικα όπου σκοπεύετε να εξαγάγετε κείμενο, συμπεριλάβετε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Ε: Πώς καθορίζω τον κατάλογο εγγράφων;

 Α: Εντοπίστε τη γραμμή`string dataDir = "YOUR DOCUMENT DIRECTORY";` στον κωδικό και αντικαταστήστε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

#### Ε: Πώς μπορώ να ανοίξω ένα υπάρχον έγγραφο PDF;

 Α: Στο Βήμα 4, θα ανοίξετε ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το`Document` κατασκευαστή και παρέχοντας τη διαδρομή προς το αρχείο εισόδου PDF.

#### Ε: Πώς μπορώ να εξαγάγω όλο το κείμενο από το έγγραφο;

 Α: Το βήμα 5 περιλαμβάνει τη δημιουργία α`TextAbsorber` αντικείμενο για εξαγωγή κειμένου από το έγγραφο PDF. Στη συνέχεια, θα αποδεχτείτε τον απορροφητή για όλες τις σελίδες.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση στο εξαγόμενο κείμενο;

 Α: Το βήμα 6 σας καθοδηγεί στην πρόσβαση στο εξαγόμενο κείμενο από το`TextAbsorber` αντικείμενο.

#### Ε: Πώς μπορώ να αποθηκεύσω το εξαγόμενο κείμενο σε ένα αρχείο;

 Α: Στο Βήμα 7, θα δημιουργήσετε ένα`TextWriter`, ανοίξτε το αρχείο όπου θέλετε να αποθηκεύσετε το εξαγόμενο κείμενο, γράψτε το εξαγόμενο κείμενο στο αρχείο και, στη συνέχεια, κλείστε τη ροή.

#### Ε: Ποιο είναι το βασικό στοιχείο από αυτό το σεμινάριο;

Α: Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να εξάγετε όλο το κείμενο από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το εξαγόμενο κείμενο έχει αποθηκευτεί σε ένα καθορισμένο αρχείο εξόδου, επιτρέποντάς σας να αναλύετε και να χειρίζεστε το περιεχόμενο κειμένου του εγγράφου.