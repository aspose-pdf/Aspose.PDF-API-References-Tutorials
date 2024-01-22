---
title: Αναζήτηση κανονικής έκφρασης σε αρχείο PDF
linktitle: Αναζήτηση κανονικής έκφρασης σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να αναζητάτε και να ανακτάτε κείμενο χρησιμοποιώντας κανονικές εκφράσεις σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 440
url: /el/net/programming-with-text/search-regular-expression/
---
Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.PDF για .NET για αναζήτηση και ανάκτηση κειμένου που ταιριάζει με μια τυπική έκφραση σε αρχείο PDF. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τη διαδικασία βήμα προς βήμα.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 4: Αναζήτηση με κανονική έκφραση

 Δημιουργώ ένα`TextFragmentAbsorber` αντικείμενο και ορίστε το πρότυπο τυπικής έκφρασης για να βρείτε όλες τις φράσεις που ταιριάζουν με το μοτίβο:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Όπως το 1999-2000
```

 Αντικαθιστώ`"\\d{4}-\\d{4}"` με το επιθυμητό μοτίβο κανονικής έκφρασης.

## Βήμα 5: Ορίστε τις επιλογές αναζήτησης κειμένου

 Δημιουργώ ένα`TextSearchOptions` αντικείμενο και ρυθμίστε το στο`TextSearchOptions` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο για να ενεργοποιήσετε τη χρήση κανονικών εκφράσεων:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Βήμα 6: Αναζήτηση σε όλες τις σελίδες

Αποδεχτείτε τον απορροφητή για όλες τις σελίδες του εγγράφου:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Βήμα 7: Ανάκτηση αποσπασμάτων κειμένου που έχουν εξαχθεί

Λάβετε τα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextFragments` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Βήμα 8: Κάντε βρόχο μέσα από τα τμήματα κειμένου

Κάντε βρόχο στα ανακτημένα τμήματα κειμένου και αποκτήστε πρόσβαση στις ιδιότητές τους:

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

### Δείγμα πηγαίου κώδικα για Search Regular Expression χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις φράσεις που ταιριάζουν με την κανονική έκφραση
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Όπως το 1999-2000
// Ορίστε την επιλογή αναζήτησης κειμένου για να καθορίσετε τη χρήση κανονικών εκφράσεων
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να αναζητάτε και να ανακτάτε κείμενο που ταιριάζει με μια κανονική έκφραση σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό το σεμινάριο παρείχε έναν οδηγό βήμα προς βήμα, από τη φόρτωση του εγγράφου έως την πρόσβαση στα εξαγόμενα τμήματα κειμένου. Τώρα μπορείτε να ενσωματώσετε αυτόν τον κώδικα στα δικά σας έργα C# για να πραγματοποιήσετε σύνθετες αναζητήσεις κειμένου σε αρχεία PDF.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Αναζήτηση κανονικής έκφρασης σε αρχείο PDF";

Α: Το σεμινάριο "Αναζήτηση κανονικής έκφρασης σε αρχείο PDF" στοχεύει να δείξει πώς να χρησιμοποιείτε τη βιβλιοθήκη Aspose.PDF για .NET για αναζήτηση και εξαγωγή κειμένου που ταιριάζει με ένα καθορισμένο μοτίβο τυπικής έκφρασης σε ένα αρχείο PDF. Το σεμινάριο παρέχει ολοκληρωμένη καθοδήγηση και δείγμα κώδικα C# για την επίδειξη της διαδικασίας.

#### Ε: Πώς βοηθά αυτό το σεμινάριο στην αναζήτηση κειμένου χρησιμοποιώντας κανονικές εκφράσεις σε ένα έγγραφο PDF;

Α: Αυτό το σεμινάριο παρέχει μια βήμα προς βήμα προσέγγιση για τη χρήση της βιβλιοθήκης Aspose.PDF για τη διεξαγωγή αναζητήσεων κειμένου σε ένα έγγραφο PDF με βάση ένα πρότυπο τυπικής έκφρασης. Αναφέρει λεπτομερώς πώς να ρυθμίσετε το έργο, να φορτώσετε το έγγραφο PDF, να ορίσετε ένα τυπικό μοτίβο έκφρασης και να ανακτήσετε τα αντίστοιχα τμήματα κειμένου.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε αυτό το σεμινάριο, θα πρέπει να έχετε μια βασική κατανόηση της γλώσσας προγραμματισμού C#. Επιπλέον, πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να το αποκτήσετε από τον ιστότοπο Aspose ή να χρησιμοποιήσετε το NuGet για να το ενσωματώσετε στο έργο σας.

#### Ε: Πώς μπορώ να ρυθμίσω το έργο μου για να ακολουθήσω αυτό το σεμινάριο;

Α: Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο προτιμώμενο περιβάλλον ολοκληρωμένης ανάπτυξης (IDE) και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET. Αυτό θα σας επιτρέψει να αξιοποιήσετε τις δυνατότητες της βιβλιοθήκης στο πλαίσιο του έργου σας.

#### Ε: Μπορώ να χρησιμοποιήσω κανονικές εκφράσεις για να αναζητήσω κείμενο σε ένα έγγραφο PDF;

 Α: Ναι, αυτό το σεμινάριο δείχνει πώς να χρησιμοποιείτε κανονικές εκφράσεις για την αναζήτηση και την εξαγωγή κειμένου από ένα έγγραφο PDF. Περιλαμβάνει τη χρήση του`TextFragmentAbsorber` τάξη και προσδιορίζοντας ένα τυπικό μοτίβο έκφρασης για να βρείτε φράσεις που ταιριάζουν με το παρεχόμενο μοτίβο.

#### Ε: Πώς ορίζω το πρότυπο κανονικής έκφρασης για αναζήτηση κειμένου;

 Α: Για να ορίσετε ένα τυπικό μοτίβο έκφρασης για αναζήτηση κειμένου, δημιουργήστε ένα`TextFragmentAbsorber` αντικείμενο και ορίστε το μοτίβο του χρησιμοποιώντας το`Text` παράμετρος. Αντικαταστήστε το προεπιλεγμένο μοτίβο`"\\d{4}-\\d{4}"` στον κώδικα του σεμιναρίου με το επιθυμητό μοτίβο κανονικής έκφρασης.

#### Ε: Πώς μπορώ να ενεργοποιήσω τη χρήση τυπικών εκφράσεων για αναζήτηση κειμένου;

 Α: Η χρήση κανονικών εκφράσεων ενεργοποιείται δημιουργώντας a`TextSearchOptions` αντικείμενο και ορίζοντας την τιμή του σε`true` . Αντιστοιχίστε αυτό το αντικείμενο στο`TextSearchOptions` ιδιοκτησία του`TextFragmentAbsorber` παράδειγμα. Αυτό διασφαλίζει ότι το μοτίβο κανονικής έκφρασης εφαρμόζεται κατά την αναζήτηση κειμένου.

#### Ε: Μπορώ να ανακτήσω τμήματα κειμένου που ταιριάζουν με το πρότυπο τυπικής έκφρασης;

 Α: Απολύτως. Αφού εφαρμόσετε την αναζήτηση κανονικών εκφράσεων στο έγγραφο PDF, μπορείτε να ανακτήσετε τα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextFragments` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο. Αυτά τα τμήματα κειμένου περιέχουν τα τμήματα κειμένου που ταιριάζουν με το καθορισμένο πρότυπο τυπικής έκφρασης.

#### Ε: Τι μπορώ να έχω πρόσβαση από τα ανακτημένα τμήματα κειμένου;

A: Από τα ανακτημένα τμήματα κειμένου, μπορείτε να αποκτήσετε πρόσβαση σε διάφορες ιδιότητες, όπως το αντιστοιχισμένο περιεχόμενο κειμένου, τη θέση (συντεταγμένες X και Y), πληροφορίες γραμματοσειράς (όνομα, μέγεθος, χρώμα) και άλλα. Το δείγμα κώδικα εντός του βρόχου του σεμιναρίου δείχνει τον τρόπο πρόσβασης και εμφάνισης αυτών των ιδιοτήτων.

#### Ε: Πώς μπορώ να προσαρμόσω τις ενέργειες στα εξαγόμενα τμήματα κειμένου;

Α: Αφού έχετε τα εξαγόμενα τμήματα κειμένου, μπορείτε να προσαρμόσετε τον κώδικα εντός του βρόχου για να εκτελέσετε πρόσθετες ενέργειες σε κάθε τμήμα κειμένου. Αυτό μπορεί να περιλαμβάνει την αποθήκευση του εξαγόμενου κειμένου, την ανάλυση μοτίβων ή την εφαρμογή αλλαγών μορφοποίησης με βάση τις απαιτήσεις σας.