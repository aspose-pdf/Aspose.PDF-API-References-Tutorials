---
title: Προσθήκη και αναζήτηση κρυφού κειμένου σε αρχείο PDF
linktitle: Προσθήκη και αναζήτηση κρυφού κειμένου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε να προσθέτετε και να αναζητάτε κρυφό κείμενο σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα με παραδείγματα κώδικα που περιλαμβάνονται.
type: docs
weight: 20
url: /el/net/programming-with-text/add-and-search-hidden-text/
---
## Εισαγωγή

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε βήμα προς βήμα για τον τρόπο προσθήκης και αναζήτησης κρυφού κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος που θέλετε να βελτιώσετε τις προγραμματιστικές σας δεξιότητες, αυτό το άρθρο θα σας παρέχει τις πληροφορίες που χρειάζεστε για να ενσωματώσετε τη λειτουργικότητα κρυφού κειμένου στις εφαρμογές σας.

## Προαπαιτούμενα

Πριν βουτήξετε στο τμήμα κωδικοποίησης, υπάρχουν μερικές προϋποθέσεις που πρέπει να προσέξετε:

### Λίστα ελέγχου απαιτήσεων
- Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio. Αυτό το σεμινάριο προϋποθέτει ότι χρησιμοποιείτε .NET Framework.
-  Aspose.PDF για .NET: Πρέπει να έχετε τη βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/pdf/net/).
- Βασικές γνώσεις C#: Η εξοικείωση με τον προγραμματισμό C# θα σας βοηθήσει να κατανοήσετε καλύτερα τα αποσπάσματα κώδικα.

## Εισαγωγή πακέτων

Για να ξεκινήσετε με τον κώδικά σας, πρέπει να βεβαιωθείτε ότι εισάγετε τους απαραίτητους χώρους ονομάτων Aspose.PDF. Δείτε πώς να το κάνετε:

### Ρύθμιση του έργου σας
1. Ανοίξτε το Visual Studio και δημιουργήστε ένα νέο έργο C# ή χρησιμοποιήστε ένα υπάρχον.
2.  Εγκαταστήστε το Aspose.PDF προσθέτοντας το πακέτο NuGet. Μπορείτε να το κάνετε αυτό μεταβαίνοντας στο NuGet Package Manager και αναζητώντας`Aspose.PDF`. 
3.  Εναλλακτικά, μπορείτε να κατεβάσετε απευθείας τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/pdf/net/) και προσθέστε το ως αναφορά στο έργο σας.

### Εισαγωγή απαιτούμενων χώρων ονομάτων
Στο επάνω μέρος του αρχείου C#, εισαγάγετε τους ακόλουθους χώρους ονομάτων:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Αυτό το βήμα είναι κρίσιμο, καθώς αυτοί οι χώροι ονομάτων περιέχουν τις κλάσεις και τις μεθόδους που είναι απαραίτητες για τον χειρισμό εγγράφων PDF.

## Δημιουργία εγγράφου PDF με κρυφό κείμενο

Τώρα που έχετε ρυθμίσει, ας προχωρήσουμε στα βήματα για να δημιουργήσουμε ένα έγγραφο PDF που περιέχει τόσο ορατό όσο και αόρατο κείμενο.

### Βήμα 1: Ορισμός Καταλόγου Εγγράφων
Αρχικά, θα θέλετε να ρυθμίσετε τη διαδρομή όπου θα αποθηκευτεί το PDF. Εδώ αρχίζει η μαγεία!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Αλλάξτε το στον κατάλογό σας
```

 Αυτή η γραμμή ορίζει πού θα αποθηκευτεί το PDF που δημιουργήσατε. Μην ξεχάσετε να αντικαταστήσετε`YOUR DOCUMENT DIRECTORY` με την πραγματική σου πορεία.

### Βήμα 2: Δημιουργήστε ένα έγγραφο PDF
Στη συνέχεια, ας δημιουργήσουμε ένα νέο έγγραφο PDF και ας προσθέσουμε σελίδες σε αυτό.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Εδώ, αρχικοποιούμε ένα νέο έγγραφο και προσθέτουμε μια σελίδα όπου θα τοποθετούμε τα κομμάτια του κειμένου μας.

### Βήμα 3: Προσθήκη ορατού και κρυφού κειμένου
Τώρα θα προσθέσουμε τόσο ορατό όσο και αόρατο κείμενο στο PDF μας.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Σε αυτό το απόσπασμα,`frag1` θα είναι ορατό, ενώ`frag2` θα οριστεί σε αόρατο στη συνέχεια.

### Βήμα 4: Ορίστε το κείμενο σε Αόρατο
 Για να φτιάξετε το κείμενο του`frag2` αόρατο, απλά το τροποποιείς`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Ορίζοντας αυτήν την ιδιότητα, οποιοδήποτε κείμενο σχετίζεται με`frag2` δεν θα αποδοθεί κατά την προβολή του PDF.

### Βήμα 5: Προσθέστε τμήματα κειμένου στη σελίδα
Τέλος, προσθέτουμε αυτά τα τμήματα κειμένου στη σελίδα και αποθηκεύουμε το PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Αυτό το μέρος του κώδικα προσθέτει κομμάτια κειμένου στη σελίδα. Μετά από αυτό, αποθηκεύουμε και απορρίπτουμε το έγγραφο σωστά.

## Αναζήτηση για κρυφό κείμενο στο PDF

Τώρα που δημιουργήσαμε το PDF μας τόσο με ορατό όσο και με κρυφό κείμενο, πώς αναζητούμε αυτό το κρυφό κείμενο; Ας το αναλύσουμε.

### Βήμα 1: Φορτώστε το έγγραφο PDF
Για να αναζητήσουμε κείμενο μέσα στο PDF, πρέπει πρώτα να φορτώσουμε το έγγραφο που μόλις δημιουργήσαμε.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Βήμα 2: Δημιουργήστε έναν απορροφητή τμημάτων κειμένου
 θα χρησιμοποιήσουμε`TextFragmentAbsorber` για να καταγράψετε όλα τα τμήματα κειμένου στο PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Εδώ, καθορίζουμε ότι θέλουμε να απορροφήσουμε όλα τα τμήματα κειμένου από την πρώτη σελίδα.

### Βήμα 3: Επανάληψη μέσω των τμημάτων
Τώρα, μπορούμε να επαναλάβουμε τα συλλεγμένα τμήματα κειμένου για να μάθουμε ποια είναι ορατά και ποια είναι κρυφά.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Αυτός ο βρόχος ελέγχει κάθε τμήμα κειμένου και εκτυπώνει το περιεχόμενό του μαζί με τη θέση και την κατάσταση ορατότητάς του. Αν`fragment.TextState.Invisible` έχει οριστεί σε true, σημαίνει ότι το κείμενο είναι κρυφό!

### Βήμα 4: Διάθεση του εγγράφου
Τέλος, θυμηθείτε να απορρίψετε ξανά το έγγραφο μόλις τελειώσετε.

```csharp
doc.Dispose();
```

## Σύναψη

Σε αυτό το σεμινάριο, ακολουθήσαμε τη συναρπαστική διαδικασία προσθήκης και αναζήτησης κρυφού κειμένου σε αρχεία PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μάθαμε πώς να δημιουργήσουμε ένα έγγραφο PDF με ορατό και κρυφό κείμενο, καθώς και πώς να αναζητούμε αυτό το κρυφό κείμενο μέσω προγραμματισμού. Αυτή η δυνατότητα μπορεί να είναι απίστευτα χρήσιμη σε διάφορες εφαρμογές, είτε χρειάζεται να αποθηκεύσετε εμπιστευτικές πληροφορίες είτε να παρέχετε μια μοναδική εμπειρία χρήστη στα έγγραφά σας.

Καθώς εξοικειώνεστε περισσότερο με το ASPose.PDF, οι δυνατότητες γίνονται ατελείωτες. Συνεχίστε να πειραματίζεστε και να πιέζετε τα όρια του τι μπορείτε να επιτύχετε με τα έγγραφα PDF σας!

## Συχνές ερωτήσεις

### Μπορεί το Aspose.PDF να χειριστεί κρυπτογραφημένα αρχεία PDF;  
Ναι, το Aspose.PDF υποστηρίζει κρυπτογράφηση και αποκρυπτογράφηση εγγράφων PDF. Μπορείτε εύκολα να ασφαλίσετε τα PDF σας με κωδικούς πρόσβασης.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.PDF;  
 Απολύτως! Μπορείτε να κατεβάσετε τη δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).

### Ποιες γλώσσες προγραμματισμού υποστηρίζει το Aspose.PDF;  
Το Aspose.PDF παρέχει υποστήριξη για πολλές γλώσσες, συμπεριλαμβανομένων των C#, Java και Python.

### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.PDF;  
 Μπορείτε να αποκτήσετε πρόσβαση στην τεκμηρίωση[εδώ](https://reference.aspose.com/pdf/net/).

### Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα;  
 Για υποστήριξη, μπορείτε να επισκεφτείτε τα φόρουμ του Aspose[εδώ](https://forum.aspose.com/c/pdf/10).