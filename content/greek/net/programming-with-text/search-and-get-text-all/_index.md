---
title: Αναζήτηση και λήψη κειμένου σε όλα
linktitle: Αναζήτηση και λήψη κειμένου σε όλα
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να αναζητάτε και να λαμβάνετε κείμενο από όλες τις σελίδες ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 420
url: /el/net/programming-with-text/search-and-get-text-all/
---
Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.PDF για .NET για αναζήτηση και λήψη κειμένου από όλες τις σελίδες ενός εγγράφου PDF. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τη διαδικασία βήμα προς βήμα.

## Προαπαιτούμενα

Πριν συνεχίσετε με το σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:

- Βασικές γνώσεις γλώσσας προγραμματισμού C#.
- Εγκαταστάθηκε το Aspose.PDF για τη βιβλιοθήκη .NET. Μπορείτε να το αποκτήσετε από τον ιστότοπο Aspose ή να χρησιμοποιήσετε το NuGet για να το εγκαταστήσετε στο έργο σας.

## Βήμα 1: Ρύθμιση του έργου

Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο ενσωματωμένο περιβάλλον ανάπτυξης (IDE) που προτιμάτε και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET.

## Βήμα 2: Εισαγάγετε τους απαραίτητους χώρους ονομάτων

Προσθέστε τα ακόλουθα χρησιμοποιώντας οδηγίες στην αρχή του αρχείου C# για να εισαγάγετε τους απαιτούμενους χώρους ονομάτων:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Βήμα 3: Φορτώστε το έγγραφο PDF

 Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων PDF και φορτώστε το έγγραφο χρησιμοποιώντας το`Document` τάξη:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 4: Αναζήτηση και εξαγωγή κειμένου

 Δημιουργία α`TextFragmentAbsorber` αντικείμενο για να βρείτε όλες τις παρουσίες της φράσης αναζήτησης εισόδου:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Αντικαθιστώ`"text"` με το πραγματικό κείμενο που θέλετε να αναζητήσετε.

## Βήμα 5: Αναζήτηση σε όλες τις σελίδες

Αποδεχτείτε τον απορροφητή για όλες τις σελίδες του εγγράφου:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Βήμα 6: λάβετε εξαγόμενα τμήματα κειμένου

 Λάβετε τα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextFragments` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Βήμα 7: Κάντε βρόχο μέσα από τα τμήματα κειμένου

Κάντε βρόχο στα ληφθέντα τμήματα κειμένου και αποκτήστε πρόσβαση στις ιδιότητές τους:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Μπορείτε να τροποποιήσετε τον κώδικα εντός του βρόχου για να εκτελέσετε περαιτέρω ενέργειες σε κάθε τμήμα κειμένου.

### Δείγμα πηγαίου κώδικα για Search And Get Text All χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις εμφανίσεις της φράσης αναζήτησης
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Αποδεχτείτε τον απορροφητήρα για όλες τις σελίδες
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Λάβετε τα εξαγόμενα τμήματα κειμένου
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Περιηγηθείτε στα θραύσματα
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Σύναψη

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να αναζητάτε και να λαμβάνετε κείμενο από όλες τις σελίδες ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό το σεμινάριο παρείχε έναν οδηγό βήμα προς βήμα, από τη φόρτωση του εγγράφου έως την πρόσβαση στα εξαγόμενα τμήματα κειμένου. Τώρα μπορείτε να ενσωματώσετε αυτόν τον κώδικα στα δικά σας έργα C# για να αναλύσετε και να επεξεργαστείτε περιεχόμενο κειμένου σε αρχεία PDF.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Αναζήτηση και λήψη όλων των κειμένων";

Α: Το σεμινάριο "Αναζήτηση και λήψη όλων των κειμένων" δείχνει πώς μπορείτε να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για .NET για αναζήτηση και εξαγωγή κειμένου από όλες τις σελίδες ενός εγγράφου PDF. Το σεμινάριο παρέχει οδηγίες βήμα προς βήμα μαζί με δείγμα κώδικα C# για την εκτέλεση αναζήτησης και ανάκτησης κειμένου.

#### Ε: Πώς βοηθά αυτό το σεμινάριο στην εξαγωγή κειμένου από έγγραφα PDF;

Α: Αυτό το σεμινάριο σάς καθοδηγεί στη διαδικασία εξαγωγής κειμένου από όλες τις σελίδες ενός εγγράφου PDF. Χρησιμοποιεί τη βιβλιοθήκη Aspose.PDF για να εντοπίσει συγκεκριμένες φράσεις κειμένου και να ανακτήσει σχετικές πληροφορίες, όπως θέση, ιδιότητες γραμματοσειράς και χρώματα.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε αυτό το σεμινάριο, θα πρέπει να έχετε μια βασική κατανόηση της γλώσσας προγραμματισμού C#. Επιπλέον, πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να το αποκτήσετε από τον ιστότοπο Aspose ή να χρησιμοποιήσετε το NuGet για να το ενσωματώσετε στο έργο σας.

#### Ε: Πώς μπορώ να ρυθμίσω το έργο μου για να ακολουθήσω αυτό το σεμινάριο;

Α: Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο προτιμώμενο περιβάλλον ολοκληρωμένης ανάπτυξης (IDE) και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET. Αυτό θα σας επιτρέψει να αποκτήσετε πρόσβαση στη λειτουργικότητα της βιβλιοθήκης στο έργο σας.

#### Ε: Πώς μπορώ να αναζητήσω συγκεκριμένο κείμενο σε ένα έγγραφο PDF;

 Α: Μπορείτε να χρησιμοποιήσετε το`TextFragmentAbsorber`τάξη για να βρείτε περιπτώσεις μιας συγκεκριμένης φράσης αναζήτησης στο έγγραφο PDF. Δημιουργώντας μια παρουσία αυτής της κλάσης και προσδιορίζοντας το κείμενο-στόχο, μπορείτε να καταγράψετε όλες τις εμφανίσεις αυτού του κειμένου.

#### Ε: Μπορώ να αναζητήσω κείμενο σε όλες τις σελίδες του εγγράφου PDF;

 Α: Ναι, το σεμινάριο δείχνει πώς να αναζητήσετε κείμενο σε όλες τις σελίδες του εγγράφου PDF. Ο`pdfDocument.Pages.Accept(textFragmentAbsorber)` Η μέθοδος χρησιμοποιείται για την αποδοχή του απορροφητή για όλες τις σελίδες, επιτρέποντάς σας να αναζητήσετε το επιθυμητό κείμενο σε κάθε σελίδα.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση στα αποσπάσματα κειμένου που έχουν εξαχθεί;

 Α: Μετά την αναζήτηση του κειμένου, μπορείτε να αποκτήσετε πρόσβαση στα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextFragments` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο. Αυτή η ιδιοκτησία παρέχει πρόσβαση σε μια συλλογή από`TextFragment` αντικείμενα που περιέχουν το εξαγόμενο κείμενο και σχετικές πληροφορίες.

#### Ε: Ποιες πληροφορίες μπορώ να ανακτήσω από τα εξαγόμενα τμήματα κειμένου;

A: Μπορείτε να ανακτήσετε διάφορες λεπτομέρειες από τα εξαγόμενα τμήματα κειμένου, όπως το πραγματικό περιεχόμενο κειμένου, τη θέση (συντεταγμένες X και Y), πληροφορίες γραμματοσειράς (όνομα, μέγεθος, χρώμα, κ.λπ.) και άλλα. Το δείγμα κώδικα του σεμιναρίου δείχνει πώς να αποκτήσετε πρόσβαση και να εκτυπώσετε αυτές τις λεπτομέρειες.

#### Ε: Μπορώ να εκτελέσω περαιτέρω ενέργειες στα εξαγόμενα τμήματα κειμένου;

Α: Απολύτως. Αφού έχετε τα εξαγόμενα τμήματα κειμένου, μπορείτε να τροποποιήσετε τον κώδικα εντός του βρόχου για να εκτελέσετε προσαρμοσμένες ενέργειες σε κάθε τμήμα. Αυτό θα μπορούσε να περιλαμβάνει την αποθήκευση του εξαγόμενου κειμένου, την ανάλυση μοτίβων κειμένου ή την εφαρμογή αλλαγών μορφοποίησης.