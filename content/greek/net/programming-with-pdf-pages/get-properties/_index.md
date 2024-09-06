---
title: Λάβετε Ιδιότητες PDF
linktitle: Λάβετε Ιδιότητες PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για να λάβετε ιδιότητες PDF, όπως διαστάσεις κουτιού και περιστροφή, χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 100
url: /el/net/programming-with-pdf-pages/get-properties/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα για να αποκτήσετε τις ιδιότητες ενός PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα C# και θα σας παρέχουμε έναν ολοκληρωμένο οδηγό που θα σας βοηθήσει να κατανοήσετε και να εφαρμόσετε αυτήν τη δυνατότητα στα δικά σας έργα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να αποκτήσετε πρόσβαση σε διάφορες ιδιότητες μιας σελίδας PDF, όπως πλαίσιο τέχνης, πλαίσιο περικοπής, πλαίσιο περικοπής κ.λπ., χρησιμοποιώντας το Aspose.PDF για .NET.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Βασική γνώση της γλώσσας προγραμματισμού C#
- Το Aspose.PDF για .NET είναι εγκατεστημένο στο περιβάλλον ανάπτυξης σας

## Βήμα 1: Ορισμός καταλόγου εγγράφων
Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο των εγγράφων σας. Αυτή είναι η θέση του αρχείου PDF του οποίου τις ιδιότητες θέλετε να αποκτήσετε. Αντικαταστήστε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με την κατάλληλη διαδρομή.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Ανοίξτε το έγγραφο PDF
 Στη συνέχεια, πρέπει να ανοίξετε το έγγραφο PDF χρησιμοποιώντας το`Document` κλάση του Aspose.PDF. Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς το αρχείο PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Βήμα 3: Πρόσβαση στη Συλλογή Σελίδων
 Τώρα μπορείτε να αποκτήσετε πρόσβαση στη συλλογή σελίδων του εγγράφου χρησιμοποιώντας το`Pages` ιδιοκτησία του`pdfDocument` αντικείμενο.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Βήμα 4: Μεταβείτε σε μια συγκεκριμένη σελίδα
Στη συνέχεια, μπορείτε να μεταβείτε σε μια συγκεκριμένη σελίδα χρησιμοποιώντας το ευρετήριο της σελίδας στη συλλογή. Στο παρακάτω παράδειγμα, έχουμε πρόσβαση στη δεύτερη σελίδα (ευρετήριο 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Βήμα 5: Λήψη ιδιοτήτων σελίδας
 Τώρα μπορείτε να λάβετε τις διαφορετικές ιδιότητες της σελίδας PDF, όπως πλαίσιο τέχνης, πλαίσιο περικοπής, πλαίσιο περικοπής κ.λπ., χρησιμοποιώντας τις αντίστοιχες ιδιότητες του`pdfPage` αντικείμενο.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Δείγμα πηγαίου κώδικα για Λήψη Ιδιοτήτων χρησιμοποιώντας Aspose.PDF για .NET 

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Λήψη συλλογής σελίδων
PageCollection pageCollection = pdfDocument.Pages;
// Λάβετε συγκεκριμένη σελίδα
Page pdfPage = pageCollection[1];
// Λάβετε ιδιότητες σελίδας
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Σύναψη
Συγχαρητήρια ! Έχετε αποκτήσει με επιτυχία τις ιδιότητες ενός PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μάθατε πώς να ανοίγετε ένα έγγραφο PDF, να πλοηγείστε σε μια συγκεκριμένη σελίδα και να λαμβάνετε διάφορες ιδιότητες σελίδας, όπως πλαίσια διαστάσεων και περιστροφή. Τώρα μπορείτε να χρησιμοποιήσετε αυτές τις πληροφορίες για να προσαρμόσετε τον χειρισμό των αρχείων PDF σας με βάση τις ιδιότητές τους.

Βεβαιωθείτε ότι έχετε ελέγξει την επίσημη τεκμηρίωση του Aspose.PDF για .NET για περισσότερες πληροφορίες σχετικά με τις προηγμένες λειτουργίες και τις δυνατότητες προσαρμογής.

### Συχνές ερωτήσεις

#### Ε: Πώς μπορώ να αποκτήσω τις ιδιότητες ενός PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Για να λάβετε τις ιδιότητες ενός PDF χρησιμοποιώντας το Aspose.PDF για .NET, μπορείτε να ακολουθήσετε τα εξής βήματα:

1. Ορίστε τον κατάλογο του εγγράφου καθορίζοντας τη διαδρομή προς το αρχείο PDF του οποίου οι ιδιότητες θέλετε να ανακτήσετε.
2.  Ανοίξτε το έγγραφο PDF χρησιμοποιώντας το`Document` κλάση του Aspose.PDF, παρέχοντας τη σωστή διαδρομή προς το αρχείο PDF.
3.  Αποκτήστε πρόσβαση στη συλλογή σελίδων του εγγράφου χρησιμοποιώντας το`Pages` ιδιοκτησία του`pdfDocument` αντικείμενο.
4. Μεταβείτε σε μια συγκεκριμένη σελίδα χρησιμοποιώντας το ευρετήριο της σελίδας στη συλλογή (η δημιουργία ευρετηρίου ξεκινά από το 1).
5.  Αποκτήστε τις διαφορετικές ιδιότητες της σελίδας PDF, όπως ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number και Rotation, χρησιμοποιώντας τις αντίστοιχες ιδιότητες του`pdfPage` αντικείμενο.

#### Ε: Ποιες είναι οι διαφορετικές ιδιότητες μιας σελίδας PDF που μπορώ να ανακτήσω χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Μπορείτε να ανακτήσετε διάφορες ιδιότητες μιας σελίδας PDF χρησιμοποιώντας το Aspose.PDF για .NET, όπως:

- ArtBox: Αντιπροσωπεύει τις διαστάσεις του γραφικού της σελίδας.
- BleedBox: Αντιπροσωπεύει τις διαστάσεις του bleed της σελίδας.
- CropBox: Αντιπροσωπεύει τις διαστάσεις του ορατού περιεχομένου της σελίδας μετά την περικοπή.
- MediaBox: Αντιπροσωπεύει τις διαστάσεις των φυσικών μέσων της σελίδας.
- TrimBox: Αντιπροσωπεύει τις διαστάσεις του περικομμένου περιεχομένου της σελίδας.
- Rect: Αντιπροσωπεύει τις διαστάσεις του πλαισίου οριοθέτησης της σελίδας.
- Αριθμός σελίδας: Αντιπροσωπεύει τον αριθμό σελίδας στο έγγραφο.
- Rotate: Αντιπροσωπεύει τη γωνία περιστροφής της σελίδας.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση σε μια συγκεκριμένη σελίδα στο έγγραφο PDF για να ανακτήσω τις ιδιότητές της;

 Α: Για να αποκτήσετε πρόσβαση σε μια συγκεκριμένη σελίδα στο έγγραφο PDF και να ανακτήσετε τις ιδιότητές της, μπορείτε να χρησιμοποιήσετε το`Pages` ιδιοκτησία του`pdfDocument` αντικείμενο για πρόσβαση στη συλλογή σελίδων του εγγράφου. Στη συνέχεια, μπορείτε να χρησιμοποιήσετε το ευρετήριο της σελίδας στη συλλογή για να μεταβείτε στην επιθυμητή σελίδα. Για παράδειγμα, για πρόσβαση στη δεύτερη σελίδα, μπορείτε να χρησιμοποιήσετε`pdfDocument.Pages[1]` (η ευρετηρίαση ξεκινά από το 1).

#### Ε: Μπορώ να εκτελέσω λειτουργίες στις ανακτημένες ιδιότητες, όπως τροποποίηση ή αλλαγή μεγέθους των πλαισίων σελίδας;

Α: Ναι, μόλις ανακτήσετε τις ιδιότητες μιας σελίδας PDF χρησιμοποιώντας το Aspose.PDF για .NET, μπορείτε να εκτελέσετε διάφορες λειτουργίες σε αυτές. Για παράδειγμα, μπορείτε να τροποποιήσετε τις διαστάσεις των πλαισίων σελίδας, να περιστρέψετε τη σελίδα ή να χρησιμοποιήσετε τις ανακτημένες πληροφορίες για προσαρμοσμένη επεξεργασία και χειρισμό του εγγράφου PDF.

#### Ε: Το Aspose.PDF για .NET υποστηρίζει την εξαγωγή ιδιοτήτων από κρυπτογραφημένα ή προστατευμένα με κωδικό πρόσβασης αρχεία PDF;

Α: Ναι, το Aspose.PDF για .NET υποστηρίζει την εξαγωγή ιδιοτήτων από κρυπτογραφημένα ή προστατευμένα με κωδικό πρόσβασης αρχεία PDF. Εφόσον παρέχετε τον σωστό κωδικό πρόσβασης για να ανοίξετε το έγγραφο PDF, μπορείτε να αποκτήσετε πρόσβαση και να ανακτήσετε τις ιδιότητές του χρησιμοποιώντας την ίδια προσέγγιση που παρουσιάζεται στο σεμινάριο.