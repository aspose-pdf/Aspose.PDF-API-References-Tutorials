---
title: Προσθήκη και αναζήτηση κρυφού κειμένου σε αρχείο PDF
linktitle: Προσθήκη και αναζήτηση κρυφού κειμένου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για την προσθήκη και αναζήτηση κρυφού κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 20
url: /el/net/programming-with-text/add-and-search-hidden-text/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον τρόπο προσθήκης και αναζήτησης κρυφού κειμένου σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθήστε αυτά τα βήματα για να εκτελέσετε αυτή τη λειτουργία εύκολα.

## 1. Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Το Visual Studio ή οποιοδήποτε άλλο περιβάλλον ανάπτυξης έχει εγκατασταθεί και ρυθμιστεί.
- Βασική γνώση της γλώσσας προγραμματισμού C#.
- Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να το κατεβάσετε από την επίσημη ιστοσελίδα του Aspose.

## 2. Δημιουργία του εγγράφου PDF με κρυφό κείμενο

Για να ξεκινήσετε, χρησιμοποιήστε τον ακόλουθο κώδικα για να δημιουργήσετε ένα νέο έγγραφο PDF που περιέχει κρυφό κείμενο:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Δημιουργήστε ένα έγγραφο
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Ορισμός ιδιότητας κειμένου - αόρατο
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Φροντίστε να παρέχετε την επιθυμητή διαδρομή και όνομα αρχείου για το έγγραφο PDF.

## 3. Αναζητήστε κείμενο στο έγγραφο

Στη συνέχεια, θα αναζητήσουμε το κρυφό κείμενο στο έγγραφο PDF. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Κάνε κάτι με τα θραύσματα
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Αυτό θα πραγματοποιήσει αναζήτηση στο κρυφό κείμενο στη δεύτερη σελίδα του εγγράφου PDF και θα εμφανίσει τις σχετικές πληροφορίες.

### Δείγμα πηγαίου κώδικα για Προσθήκη και αναζήτηση κρυφού κειμένου χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Δημιουργία εγγράφου με κρυφό κείμενο
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Ορισμός ιδιότητας κειμένου - αόρατο
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Αναζήτηση κειμένου στο έγγραφο
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Κάντε κάτι με θραύσματα
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Σύναψη

Συγχαρητήρια ! Προσθέσατε και βρήκατε με επιτυχία κρυφό κείμενο σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Τώρα μπορείτε να εφαρμόσετε αυτήν τη μέθοδο στα δικά σας έργα για να χειριστείτε και να αναζητήσετε κρυφό κείμενο σε αρχεία PDF.

### Συχνές ερωτήσεις

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές να δημιουργούν, να χειρίζονται και να μετασχηματίζουν έγγραφα PDF μέσα σε εφαρμογές .NET.

#### Ε: Μπορεί το κρυφό κείμενο να χρησιμοποιηθεί για σκοπούς υδατογράφησης;

Α: Απολύτως! Το κρυφό κείμενο μπορεί να χρησιμεύσει ως αποτελεσματικό μέσο υδατογράφησης εγγράφων PDF, προσθέτοντας ένα επιπλέον επίπεδο ασφάλειας.

#### Ε: Είναι δυνατή η αποκάλυψη κρυφού κειμένου σε ένα έγγραφο PDF;

Α: Ναι, η διαδικασία αναζήτησης και αποκάλυψης κρυφού κειμένου σε ένα έγγραφο PDF μπορεί να επιτευχθεί χρησιμοποιώντας τις τεχνικές που περιγράφονται σε αυτό το σεμινάριο.

#### Ε: Ποιες άλλες λειτουργίες προσφέρει το Aspose.PDF για .NET;

Α: Πέρα από τη χειραγώγηση κρυφού κειμένου, το Aspose.PDF για .NET παρέχει μια ευρεία γκάμα δυνατοτήτων, όπως δημιουργία PDF, μετατροπή, κρυπτογράφηση και άλλα.