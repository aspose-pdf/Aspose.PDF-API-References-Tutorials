---
title: Ορισμός πληροφοριών αρχείου σε αρχείο PDF
linktitle: Ορισμός πληροφοριών αρχείου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.PDF για .NET για να ορίσετε πληροφορίες αρχείου σε αρχείο PDF με αυτόν τον οδηγό βήμα προς βήμα.
type: docs
weight: 310
url: /el/net/programming-with-document/setfileinfo/
---
Εάν εργάζεστε σε ένα έργο που απαιτεί διαχείριση αρχείων PDF χρησιμοποιώντας το Aspose.PDF για .NET, μία από τις δυνατότητες που μπορεί να θέλετε να χρησιμοποιήσετε είναι η δυνατότητα ορισμού πληροφοριών αρχείου για ένα έγγραφο PDF. Οι πληροφορίες του αρχείου περιλαμβάνουν διάφορες λεπτομέρειες όπως ο συγγραφέας, η ημερομηνία δημιουργίας, οι λέξεις-κλειδιά, η ημερομηνία τροποποίησης, το θέμα και ο τίτλος. Αυτός ο οδηγός θα σας καθοδηγήσει στη διαδικασία ρύθμισης πληροφοριών αρχείου για ένα έγγραφο PDF χρησιμοποιώντας τον πηγαίο κώδικα C# με το Aspose.PDF για .NET.

## Οδηγός βήμα προς βήμα για τη ρύθμιση των πληροφοριών αρχείων χρησιμοποιώντας το Aspose.PDF για .NET

1. Δημιουργήστε ένα νέο έργο C# στο Visual Studio IDE.
2. Προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET στο έργο σας.
3. Δημιουργήστε ένα νέο αντικείμενο εγγράφου PDF παρέχοντας τη διαδρομή προς το αρχείο PDF για το οποίο θέλετε να τροποποιήσετε τις πληροφορίες του αρχείου.

## Βήμα 1: Ορίστε τη διαδρομή στον κατάλογο εγγράφων.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Ανοίξτε το έγγραφο PDF

```csharp
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Βήμα 3: Χρησιμοποιήστε το αντικείμενο DocumentInfo για πρόσβαση στις πληροφορίες αρχείου του εγγράφου PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Βήμα 4: Ορίστε τις επιθυμητές τιμές πληροφοριών αρχείου χρησιμοποιώντας τις ιδιότητες του αντικειμένου DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Βήμα 5: Αποθηκεύστε το ενημερωμένο έγγραφο PDF στην καθορισμένη θέση.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Βήμα 6: Βεβαιωθείτε ότι οι πληροφορίες του αρχείου έχουν ενημερωθεί με επιτυχία.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Έχετε ορίσει με επιτυχία πληροφορίες αρχείου για ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET.

### Παράδειγμα πηγαίου κώδικα για Ορισμός πληροφοριών αρχείου χρησιμοποιώντας Aspose.PDF για .NET


```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Προσδιορίστε τις πληροφορίες του εγγράφου
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Αποθήκευση εγγράφου εξόδου
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Σύναψη

Συμπερασματικά, το Aspose.PDF για .NET παρέχει έναν απλό και αποτελεσματικό τρόπο ρύθμισης πληροφοριών αρχείων για έγγραφα PDF. Ακολουθώντας τα προαναφερθέντα βήματα, μπορείτε εύκολα να ορίσετε τις επιθυμητές τιμές πληροφοριών αρχείου για τα έγγραφά σας PDF χρησιμοποιώντας τον πηγαίο κώδικα C#.

### Συχνές ερωτήσεις για πληροφορίες για το σύνολο των αρχείων σε αρχείο PDF

#### Ε: Μπορώ να ορίσω πρόσθετες ιδιότητες πληροφοριών αρχείου που δεν αναφέρονται στο παράδειγμα;

 Α: Ναι, μπορείτε να ορίσετε πρόσθετες ιδιότητες πληροφοριών αρχείου χρησιμοποιώντας το`DocumentInfo` αντικείμενο στο Aspose.PDF για .NET. Ο`DocumentInfo`Η class παρέχει διάφορες ιδιότητες που σας επιτρέπουν να ορίσετε πρόσθετες πληροφορίες, όπως τον παραγωγό, την έκδοση και τις προσαρμοσμένες ιδιότητες.

#### Ε: Είναι δυνατή η ανάκτηση των πληροφοριών του αρχείου από ένα υπάρχον έγγραφο PDF;

 Α: Ναι, μπορείτε να ανακτήσετε τις πληροφορίες αρχείου από ένα υπάρχον έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Για να το κάνετε αυτό, μπορείτε να χρησιμοποιήσετε το`DocumentInfo` Αντικείμενο πρόσβασης στις ιδιότητες πληροφοριών αρχείου και ανάγνωση των πληροφοριών που είναι αποθηκευμένες στο έγγραφο PDF.

#### Ε: Η ρύθμιση των πληροφοριών αρχείου τροποποιεί το αρχικό έγγραφο PDF;

Α: Όχι, η ρύθμιση των πληροφοριών αρχείου χρησιμοποιώντας το Aspose.PDF για .NET δεν τροποποιεί το αρχικό έγγραφο PDF. Αντίθετα, δημιουργεί ένα νέο έγγραφο PDF με τις ενημερωμένες πληροφορίες αρχείου. Το αρχικό έγγραφο PDF παραμένει αμετάβλητο.