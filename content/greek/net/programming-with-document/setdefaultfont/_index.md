---
title: Ορισμός προεπιλεγμένης γραμματοσειράς σε αρχείο PDF
linktitle: Ορισμός προεπιλεγμένης γραμματοσειράς σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να ορίζετε την προεπιλεγμένη γραμματοσειρά σε ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET με αυτόν τον οδηγό βήμα προς βήμα.
type: docs
weight: 280
url: /el/net/programming-with-document/setdefaultfont/
---
Εάν εργάζεστε με έγγραφα PDF σε .NET, ενδέχεται να αντιμετωπίσετε προβλήματα όπου η γραμματοσειρά που χρησιμοποιείται στο PDF δεν είναι διαθέσιμη στο σύστημα όπου προβάλλεται ή εκτυπώνεται. Αυτό μπορεί να έχει ως αποτέλεσμα το κείμενο να εμφανίζεται λανθασμένα ή καθόλου. Το Aspose.PDF για .NET παρέχει μια λύση σε αυτό το πρόβλημα, επιτρέποντάς σας να ορίσετε μια προεπιλεγμένη γραμματοσειρά για το έγγραφο. Σε αυτό το παράδειγμα, πώς να ορίσετε την προεπιλεγμένη γραμματοσειρά χρησιμοποιώντας το Aspose.PDF για .NET.

## Βήμα 1: Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων

πρέπει να ορίσουμε τη διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφο PDF μας. Θα αποθηκεύσουμε αυτή τη διαδρομή σε μια μεταβλητή που ονομάζεται "dataDir".

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το έγγραφο PDF

 Θα ξεκινήσουμε με τη φόρτωση ενός υπάρχοντος εγγράφου PDF που λείπουν γραμματοσειρές. Σε αυτό το παράδειγμα, θα υποθέσουμε ότι το έγγραφο PDF βρίσκεται στον κατάλογο που καθορίζεται από το`dataDir` μεταβλητός.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // ο κωδικός πηγαίνει εδώ
}
```

## Βήμα 3: Ορίστε την προεπιλεγμένη γραμματοσειρά

 Στη συνέχεια, θα ορίσουμε την προεπιλεγμένη γραμματοσειρά για το έγγραφο PDF χρησιμοποιώντας το`PdfSaveOptions` τάξη. Σε αυτό το παράδειγμα, θα ορίσουμε την προεπιλεγμένη γραμματοσειρά σε "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Βήμα 4: Αποθηκεύστε το ενημερωμένο έγγραφο

Τέλος, θα αποθηκεύσουμε το ενημερωμένο έγγραφο σε νέο αρχείο. Σε αυτό το παράδειγμα, θα αποθηκεύσουμε το ενημερωμένο έγγραφο σε ένα αρχείο με το όνομα "output_out.pdf" στον ίδιο κατάλογο με το αρχείο εισόδου.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Παράδειγμα πηγαίου κώδικα για ορισμός προεπιλεγμένης γραμματοσειράς χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Φορτώστε ένα υπάρχον έγγραφο PDF με γραμματοσειρά που λείπει
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Καθορίστε το προεπιλεγμένο όνομα γραμματοσειράς
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## συμπέρασμα

Ο ορισμός μιας προεπιλεγμένης γραμματοσειράς σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET είναι ένας απλός και αποτελεσματικός τρόπος για να διασφαλίσετε ότι το κείμενο εμφανίζεται σωστά, ακόμα κι αν οι αρχικές γραμματοσειρές δεν είναι διαθέσιμες. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#, οι προγραμματιστές μπορούν εύκολα να ορίσουν την προεπιλεγμένη γραμματοσειρά και να δημιουργήσουν PDF που προσφέρουν μια συνεπή και αξιόπιστη εμπειρία προβολής σε διαφορετικά περιβάλλοντα. Αυτή η δυνατότητα είναι ιδιαίτερα χρήσιμη σε σενάρια όπου τα PDF θα προβάλλονται ή θα εκτυπώνονται σε διάφορα συστήματα που ενδέχεται να έχουν εγκατεστημένα διαφορετικά σύνολα γραμματοσειρών.

### Συχνές ερωτήσεις για τον ορισμό της προεπιλεγμένης γραμματοσειράς σε αρχείο PDF

#### Ε: Γιατί είναι σημαντικός ο ορισμός μιας προεπιλεγμένης γραμματοσειράς σε έγγραφα PDF;

Α: Ο ορισμός μιας προεπιλεγμένης γραμματοσειράς σε έγγραφα PDF είναι σημαντικός επειδή διασφαλίζει ότι το κείμενο θα εμφανίζεται σωστά ακόμα κι αν οι αρχικές γραμματοσειρές δεν είναι διαθέσιμες στο σύστημα όπου προβάλλεται ή εκτυπώνεται το PDF. Βοηθά στην αποφυγή προβλημάτων όπως το κείμενο που λείπει ή είναι αλλοιωμένο, διασφαλίζοντας μια συνεπή και αξιόπιστη εμπειρία προβολής.

#### Ε: Μπορώ να επιλέξω οποιαδήποτε γραμματοσειρά ως προεπιλεγμένη γραμματοσειρά χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Ναι, μπορείτε να επιλέξετε οποιαδήποτε γραμματοσειρά είναι διαθέσιμη στο σύστημα ως προεπιλεγμένη γραμματοσειρά χρησιμοποιώντας το Aspose.PDF για .NET. Απλώς καθορίστε το όνομα της γραμματοσειράς στο`DefaultFontName` ιδιοκτησία του`PdfSaveOptions` τάξη.

#### Ε: Τι συμβαίνει εάν η καθορισμένη προεπιλεγμένη γραμματοσειρά δεν είναι διαθέσιμη στο σύστημα;

Α: Εάν η καθορισμένη προεπιλεγμένη γραμματοσειρά δεν είναι διαθέσιμη στο σύστημα, το πρόγραμμα προβολής PDF θα χρησιμοποιήσει μια εναλλακτική γραμματοσειρά για να εμφανίσει το κείμενο. Συνιστάται να επιλέξετε μια ευρέως διαθέσιμη γραμματοσειρά όπως Arial ή Times New Roman για να διασφαλίσετε τη συμβατότητα μεταξύ διαφορετικών συστημάτων.