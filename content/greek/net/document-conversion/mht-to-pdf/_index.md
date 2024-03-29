---
title: MHT σε PDF
linktitle: MHT σε PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη μετατροπή MHT σε PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 70
url: /el/net/document-conversion/mht-to-pdf/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία μετατροπής ενός αρχείου MHT σε PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το MHT (MIME HTML) είναι μια μορφή που χρησιμοποιείται για την αποθήκευση μιας πλήρους ιστοσελίδας, συμπεριλαμβανομένων εικόνων και σχετικού περιεχομένου. Ακολουθώντας τα παρακάτω βήματα, θα μπορείτε να μετατρέψετε αρχεία MHT σε μορφή PDF.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι πληροίτε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις της γλώσσας προγραμματισμού C#.
- Η βιβλιοθήκη Aspose.PDF για .NET είναι εγκατεστημένη στο σύστημά σας.
- Ένα περιβάλλον ανάπτυξης όπως το Visual Studio.

## Βήμα 1: Φόρτωση αρχείου MHT
Σε αυτό το βήμα θα φορτώσουμε το αρχείο MHT χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθήστε τον παρακάτω κώδικα:

```csharp
// Διαδρομή στον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Φορτώστε το έγγραφο
Document document = new Document(dataDir + "test.mht", options);
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENTS DIRECTORY"` με τον πραγματικό κατάλογο όπου βρίσκεται το αρχείο MHT.

## Βήμα 2: Μετατροπή MHT σε PDF
Αφού φορτώσουμε το αρχείο MHT, μπορούμε να προχωρήσουμε στη μετατροπή σε PDF. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
// Αποθηκεύστε την έξοδο ως έγγραφο PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Ο παραπάνω κώδικας μετατρέπει το αρχείο MHT σε μορφή PDF και το αποθηκεύει ως όνομα αρχείου`"MHTToPDF_out.pdf"`.

### Παράδειγμα πηγαίου κώδικα για MHT σε PDF χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Φόρτωση εγγράφου
Document document = new Document(dataDir  + "test.mht", options);
// Αποθηκεύστε την έξοδο ως έγγραφο PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία βήμα προς βήμα μετατροπής ενός αρχείου MHT σε PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τις οδηγίες που περιγράφονται παραπάνω, θα πρέπει τώρα να μπορείτε να μετατρέψετε αρχεία MHT σε μορφή PDF. Αυτή η δυνατότητα μπορεί να είναι χρήσιμη όταν χρειάζεται να μετατρέψετε ολόκληρες ιστοσελίδες σε έγγραφα PDF.

### Συχνές ερωτήσεις

#### Ε: Υποστηρίζει το Aspose.PDF για .NET τη μετατροπή αρχείων MHT με ενσωματωμένες εικόνες σε PDF;

Α: Ναι, το Aspose.PDF για .NET υποστηρίζει τη μετατροπή αρχείων MHT με ενσωματωμένες εικόνες σε PDF. Η βιβλιοθήκη μπορεί να χειριστεί το πλήρες περιεχόμενο της ιστοσελίδας, συμπεριλαμβανομένων εικόνων και σχετικών πόρων, και να το μετατρέψει σε έγγραφο PDF.

#### Ε: Μπορώ να προσαρμόσω την έξοδο PDF κατά τη διαδικασία μετατροπής MHT σε PDF;

Α: Ναι, το Aspose.PDF για .NET παρέχει διάφορες επιλογές για την προσαρμογή της εξόδου PDF κατά τη διαδικασία μετατροπής MHT σε PDF. Μπορείτε να ορίσετε ιδιότητες όπως το μέγεθος σελίδας, τον προσανατολισμό, τα περιθώρια και άλλα για να ελέγξετε την εμφάνιση του εγγράφου PDF που προκύπτει.

#### Ε: Το Aspose.PDF για .NET διατηρεί υπερσυνδέσμους και μορφοποίηση από το αρχικό αρχείο MHT στην έξοδο PDF;

Α: Ναι, το Aspose.PDF για .NET διατηρεί υπερσυνδέσμους και μορφοποίηση από το αρχικό αρχείο MHT στην έξοδο PDF. Η βιβλιοθήκη διασφαλίζει ότι το PDF που έχει μετατραπεί διατηρεί την ίδια διάταξη και περιεχόμενο με το αρχείο προέλευσης MHT.

#### Ε: Μπορώ να μετατρέψω πολλά αρχεία MHT σε ξεχωριστά έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ναι, μπορείτε να μετατρέψετε πολλά αρχεία MHT σε ξεχωριστά έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Απλώς φορτώστε κάθε αρχείο MHT και αποθηκεύστε το ως ξεχωριστό έγγραφο PDF με ένα μοναδικό όνομα αρχείου.