---
title: Σχεδιάστε το XForm στη σελίδα
linktitle: Σχεδιάστε το XForm στη σελίδα
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη σχεδίαση μιας φόρμας XForm σε μια σελίδα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Προσθέστε και τοποθετήστε τη φόρμα στη σελίδα.
type: docs
weight: 10
url: /el/net/programming-with-operators/draw-xform-on-page/
---
Σε αυτό το σεμινάριο, θα σας παρέχουμε έναν οδηγό βήμα προς βήμα για το πώς να σχεδιάσετε ένα XForm σε μια σελίδα χρησιμοποιώντας το Aspose.PDF για .NET. Το Aspose.PDF είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να δημιουργείτε, να χειρίζεστε και να μετατρέπετε έγγραφα PDF μέσω προγραμματισμού. Χρησιμοποιώντας τους τελεστές που παρέχονται από το Aspose.PDF, μπορείτε να προσθέσετε και να τοποθετήσετε μια φόρμα XForm σε μια υπάρχουσα σελίδα PDF.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Το Visual Studio είναι εγκατεστημένο με πλαίσιο .NET.
2. Η βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο στο Visual Studio και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τον επίσημο ιστότοπο της Aspose και να την εγκαταστήσετε στον υπολογιστή σας.

## Βήμα 2: Εισαγάγετε τους απαραίτητους χώρους ονομάτων

Στο αρχείο κώδικα C#, εισαγάγετε τους χώρους ονομάτων που απαιτούνται για πρόσβαση στις κλάσεις και τις μεθόδους που παρέχονται από το Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Βήμα 3: Ορισμός διαδρομών αρχείων

Καθορίστε τις διαδρομές αρχείου για την εικόνα φόντου, το αρχείο PDF εισόδου και το αρχείο PDF εξόδου:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Βεβαιωθείτε ότι έχετε καθορίσει τις πραγματικές διαδρομές αρχείων στον υπολογιστή σας.

## Βήμα 4: Φόρτωση του αρχείου εισόδου PDF

Χρησιμοποιήστε τον ακόλουθο κώδικα για να φορτώσετε το αρχείο εισόδου PDF:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Ο παρακάτω κώδικας χρησιμοποιεί τους τελεστές GSave/GRestore
// Ο κώδικας χρησιμοποιεί τον τελεστή ContatenateMatrix για να τοποθετήσει το XForm
// Ο κώδικας χρησιμοποιεί τον τελεστή Do για να σχεδιάσει το XForm στη σελίδα
// Οι χειριστές GSave/GRestore αναδιπλώνουν το υπάρχον περιεχόμενο
//Αυτό γίνεται για να ληφθεί η αρχική κατάσταση γραφικών στο τέλος του υπάρχοντος περιεχομένου
// Διαφορετικά, ενδέχεται να μείνουν ανεπιθύμητοι μετασχηματισμοί στο τέλος της αλυσίδας των υπαρχόντων χειριστών
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Προσθέστε τελεστή GSave για να επαναφέρετε σωστά την κατάσταση γραφικών μετά από νέες εντολές
pageContents. Add(new GSave());

// Δημιουργήστε το XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Ορίστε το πλάτος και το ύψος της εικόνας
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Φορτώστε την εικόνα σε μια ροή
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Προσθέστε την εικόνα στη συλλογή εικόνων πόρων XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Χρήση του τελεστή Do: αυτός ο τελεστής σχεδιάζει την εικόνα
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Τοποθετήστε το XForm στις συντεταγμένες x=100 και y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Σχεδιάστε το XForm με τον τελεστή Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Τοποθετήστε το XForm στις συντεταγμένες x=100 και y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Σχεδιάστε το XForm με τον τελεστή Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Επαναφέρετε την κατάσταση γραφικών με το GRestore μετά το GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Φροντίστε να καθορίσετε τις πραγματικές διαδρομές αρχείου και να προσαρμόσετε τον αριθμό σελίδας και τις θέσεις XForm όπως απαιτείται.

### Δείγμα πηγαίου κώδικα για το Draw XForm On Page χρησιμοποιώντας Aspose.PDF για .NET
 
```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Το δείγμα δείχνει
	// Χρήση χειριστή GSave/GRestore
	// Χρήση τελεστή ContatenateMatrix στη θέση xForm
	//Χρησιμοποιήστε τον τελεστή για να σχεδιάσετε το xForm στη σελίδα
	// Τυλίξτε τα υπάρχοντα περιεχόμενα με το ζεύγος τελεστών GSave/GRestore
	// Αυτό γίνεται για να λάβετε την αρχική κατάσταση γραφικών στο και των υπαρχόντων περιεχομένων
	// Διαφορετικά, ενδέχεται να παραμείνουν ορισμένοι ανεπιθύμητοι μετασχηματισμοί στο τέλος της αλυσίδας των υπαρχόντων χειριστών
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Προσθέστε τον τελεστή κατάστασης αποθήκευσης γραφικών για να διαγράψετε σωστά την κατάσταση γραφικών μετά από νέες εντολές
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Δημιουργήστε το xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Ορίστε το πλάτος και το ύψος της εικόνας
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Φόρτωση εικόνας στη ροή
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Προσθήκη εικόνας στη συλλογή εικόνων των πόρων XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Χρήση τελεστή Do: αυτός ο τελεστής σχεδιάζει εικόνα
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Τοποθετήστε τη φόρμα στις συντεταγμένες x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Σχεδίαση φόρμας με τελεστή Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Τοποθετήστε τη φόρμα στις συντεταγμένες x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Σχεδίαση φόρμας με τελεστή Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Επαναφέρετε την κατάσταση γραφικών με το GRestore μετά το GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να σχεδιάζετε μια φόρμα XForm σε μια σελίδα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τα βήματα που περιγράφονται, θα μπορείτε να προσθέσετε και να τοποθετήσετε μια φόρμα XForm σε μια υπάρχουσα σελίδα, δίνοντας έτσι μεγαλύτερη ευελιξία στα έγγραφά σας PDF.

### Συχνές ερωτήσεις για την κλήρωση XForm στη σελίδα

#### Ε: Τι είναι ένα XForm στο Aspose.PDF;

Α: Ένα XForm είναι ένα επαναχρησιμοποιήσιμο γραφικό αντικείμενο σε ένα έγγραφο PDF. Σας επιτρέπει να ορίζετε και να σχεδιάζετε πολύπλοκα γραφικά, εικόνες ή κείμενο που μπορούν να επαναχρησιμοποιηθούν πολλές φορές σε διαφορετικές σελίδες.

#### Ε: Πώς μπορώ να εισάγω τους απαραίτητους χώρους ονομάτων για το Aspose.PDF;

 Α: Στο αρχείο κώδικα C#, χρησιμοποιήστε το`using` οδηγία για την εισαγωγή των απαιτούμενων χώρων ονομάτων για πρόσβαση στις κλάσεις και τις μεθόδους που παρέχονται από το Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Ε: Ποιος είναι ο σκοπός των χειριστών GSave και GRestore;

 Α: Το`GSave` και`GRestore` Οι τελεστές στο Aspose.PDF χρησιμοποιούνται για την αποθήκευση και την επαναφορά της κατάστασης των γραφικών. Βοηθούν να διασφαλιστεί ότι οι μετασχηματισμοί και οι ρυθμίσεις που εφαρμόζονται σε μία ενότητα του περιεχομένου δεν επηρεάζουν τις επόμενες ενότητες.

#### Ε: Πώς μπορώ να ορίσω ένα XForm χρησιμοποιώντας το Aspose.PDF;

 Α: Για να δημιουργήσετε ένα XForm, χρησιμοποιήστε το`XForm.CreateNewForm` μέθοδο και προσθέστε το στο`Resources.Forms` συλλογή μιας συγκεκριμένης σελίδας. Στη συνέχεια, μπορείτε να προσθέσετε περιεχόμενο στα XForm's`Contents` ιδιοκτησία.

#### Ε: Πώς μπορώ να σχεδιάσω μια εικόνα μέσα σε ένα XForm;

Α: Φορτώστε την εικόνα σε μια ροή και προσθέστε την σε`Resources.Images` συλλογή του XForm. Χρησιμοποιήστε το`Do` χειριστή εντός των XForm's`Contents` για να σχεδιάσετε την εικόνα.

#### Ε: Πώς τοποθετώ ένα XForm σε μια σελίδα PDF;

 Α: Για να τοποθετήσετε ένα XForm σε μια σελίδα, χρησιμοποιήστε το`ConcatenateMatrix` χειριστή εντός της σελίδας`Contents`. Προσαρμόστε τις παραμέτρους του πίνακα για να καθορίσετε τη μετάφραση (θέση) και την κλιμάκωση του XForm.

#### Ε: Μπορώ να σχεδιάσω πολλά XForms στην ίδια σελίδα;

 Α: Ναι, μπορείτε να σχεδιάσετε πολλά XForms στην ίδια σελίδα προσαρμόζοντας το`ConcatenateMatrix` παραμέτρους για να τοποθετήσετε κάθε XForm σε διαφορετικές συντεταγμένες.

#### Ε: Μπορώ να τροποποιήσω το περιεχόμενο ενός XForm μετά τη δημιουργία του;

 Α: Ναι, μπορείτε να τροποποιήσετε τα περιεχόμενα ενός XForm μετά τη δημιουργία προσθέτοντας επιπλέον τελεστές σε αυτό`Contents` ιδιοκτησία.

#### Ε: Τι συμβαίνει εάν παραλείψω τους τελεστές GSave και GRestore;

Α: Η παράλειψη των τελεστών GSave και GRestore μπορεί να οδηγήσει σε ανεπιθύμητους μετασχηματισμούς ή ρυθμίσεις που θα εφαρμοστούν σε επόμενο περιεχόμενο. Η χρήση τους βοηθά στη διατήρηση μιας καθαρής κατάστασης γραφικών.

#### Ε: Μπορώ να χρησιμοποιήσω ξανά το XForms σε διαφορετικές σελίδες του εγγράφου PDF;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε ξανά το XForm σε πολλές σελίδες προσθέτοντας το ίδιο XForm στο`Resources.Forms` συλλογή από διαφορετικές σελίδες.

#### Ε: Υπάρχει όριο στον αριθμό των XForms που μπορώ να δημιουργήσω;

Α: Αν και δεν υπάρχει αυστηρός περιορισμός στον αριθμό των XForms που μπορείτε να δημιουργήσετε, έχετε υπόψη σας ότι πάρα πολλά XForms ενδέχεται να επηρεάσουν την απόδοση και τη χρήση της μνήμης. Χρησιμοποιήστε τα με σύνεση.

#### Ε: Μπορώ να περιστρέψω ένα XForm ή να εφαρμόσω άλλους μετασχηματισμούς;

 Α: Ναι, μπορείτε να χρησιμοποιήσετε το`ConcatenateMatrix` τελεστή για να εφαρμόσει μετασχηματισμούς όπως περιστροφή, κλιμάκωση και μετάφραση σε ένα XForm.
