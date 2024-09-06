---
title: Αναζήτηση και λήψη σελίδας κειμένου σε αρχείο PDF
linktitle: Αναζήτηση και λήψη σελίδας κειμένου σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να αναζητάτε και να λαμβάνετε κείμενο από μια συγκεκριμένη σελίδα σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 430
url: /el/net/programming-with-text/search-and-get-text-page/
---
Αυτό το σεμινάριο εξηγεί πώς να χρησιμοποιήσετε το Aspose.PDF για .NET για αναζήτηση και λήψη κειμένου από μια συγκεκριμένη σελίδα σε αρχείο PDF. Ο παρεχόμενος πηγαίος κώδικας C# δείχνει τη διαδικασία βήμα προς βήμα.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Φροντίστε να αντικαταστήσετε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 4: Αναζήτηση και εξαγωγή κειμένου από μια σελίδα

 Δημιουργία α`TextFragmentAbsorber`αντικείμενο για να βρείτε όλες τις παρουσίες της φράσης αναζήτησης εισόδου σε μια συγκεκριμένη σελίδα:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Αντικαθιστώ`"Figure"` με το πραγματικό κείμενο που θέλετε να αναζητήσετε.

## Βήμα 5: Αναζήτηση σε μια συγκεκριμένη σελίδα

Αποδεχτείτε τον απορροφητή για μια συγκεκριμένη σελίδα του εγγράφου:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Βήμα 6: λάβετε εξαγόμενα τμήματα κειμένου

Λάβετε τα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextFragments` ιδιοκτησία του`TextFragmentAbsorber` αντικείμενο:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Βήμα 7: Κάντε βρόχο μέσα από τα τμήματα και τα τμήματα κειμένου

Κάντε βρόχο μέσα από τα ληφθέντα τμήματα κειμένου και τα τμήματα τους και αποκτήστε πρόσβαση στις ιδιότητές τους:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Μπορείτε να τροποποιήσετε τον κώδικα εντός του βρόχου για να εκτελέσετε περαιτέρω ενέργειες σε κάθε τμήμα κειμένου.

### Δείγμα πηγαίου κώδικα για Αναζήτηση και λήψη κειμένου χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Άνοιγμα εγγράφου
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Δημιουργήστε αντικείμενο TextAbsorber για να βρείτε όλες τις εμφανίσεις της φράσης αναζήτησης
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Αποδεχτείτε τον απορροφητήρα για όλες τις σελίδες
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Λάβετε τα εξαγόμενα τμήματα κειμένου
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Περιηγηθείτε στα θραύσματα
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Σύναψη

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να αναζητάτε και να λαμβάνετε κείμενο από μια συγκεκριμένη σελίδα ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτό το σεμινάριο παρείχε έναν οδηγό βήμα προς βήμα, από τη φόρτωση του εγγράφου έως την πρόσβαση στα εξαγόμενα τμήματα κειμένου. Τώρα μπορείτε να ενσωματώσετε

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Αναζήτηση και λήψη σελίδας κειμένου";

Α: Το σεμινάριο "Αναζήτηση και λήψη σελίδας κειμένου" έχει σχεδιαστεί για να επεξηγεί τον τρόπο χρήσης της βιβλιοθήκης Aspose.PDF για .NET για αναζήτηση και ανάκτηση κειμένου από μια συγκεκριμένη σελίδα σε ένα αρχείο PDF. Το σεμινάριο παρέχει λεπτομερείς οδηγίες και δείγμα κώδικα C# για την επίδειξη της διαδικασίας.

#### Ε: Πώς βοηθά αυτό το σεμινάριο στην εξαγωγή κειμένου από μια συγκεκριμένη σελίδα σε ένα έγγραφο PDF;

Α: Αυτό το σεμινάριο σάς καθοδηγεί στη διαδικασία εξαγωγής κειμένου από μια συγκεκριμένη σελίδα ενός εγγράφου PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF. Περιγράφει τα απαραίτητα βήματα και παρέχει κώδικα C# για την αναζήτηση μιας καθορισμένης φράσης κειμένου στην επιλεγμένη σελίδα και την ανάκτηση συσχετισμένων τμημάτων κειμένου.

#### Ε: Ποιες είναι οι προϋποθέσεις για να ακολουθήσετε αυτό το σεμινάριο;

Α: Πριν ξεκινήσετε αυτό το σεμινάριο, θα πρέπει να έχετε μια βασική κατανόηση της γλώσσας προγραμματισμού C#. Επιπλέον, πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.PDF για .NET. Μπορείτε να το αποκτήσετε από τον ιστότοπο Aspose ή να χρησιμοποιήσετε το NuGet για να το ενσωματώσετε στο έργο σας.

#### Ε: Πώς μπορώ να ρυθμίσω το έργο μου για να ακολουθήσω αυτό το σεμινάριο;

Α: Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο προτιμώμενο περιβάλλον ολοκληρωμένης ανάπτυξης (IDE) και προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET. Αυτό θα σας επιτρέψει να χρησιμοποιήσετε τις δυνατότητες της βιβλιοθήκης στο έργο σας.

#### Ε: Μπορώ να αναζητήσω κείμενο σε μια συγκεκριμένη σελίδα του εγγράφου PDF;

Α: Ναι, αυτό το σεμινάριο δείχνει πώς να αναζητήσετε κείμενο σε μια συγκεκριμένη σελίδα ενός εγγράφου PDF. Περιλαμβάνει τη χρήση του`TextFragmentAbsorber` κλάση για να εντοπίσετε περιπτώσεις μιας συγκεκριμένης φράσης κειμένου στην επιλεγμένη σελίδα.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση στα εξαγόμενα τμήματα κειμένου από τη συγκεκριμένη σελίδα;

 Α: Αφού αναζητήσετε το κείμενο στην καθορισμένη σελίδα, μπορείτε να αποκτήσετε πρόσβαση στα εξαγόμενα τμήματα κειμένου χρησιμοποιώντας το`TextSegments` ιδιοκτησία του`TextFragment` αντικείμενο. Αυτή η ιδιοκτησία παρέχει πρόσβαση σε μια συλλογή από`TextSegment` αντικείμενα που περιέχουν το εξαγόμενο κείμενο και σχετικές πληροφορίες.

#### Ε: Ποιες πληροφορίες μπορώ να ανακτήσω από τα εξαγόμενα τμήματα κειμένου;

A: Μπορείτε να ανακτήσετε διάφορες λεπτομέρειες από τα εξαγόμενα τμήματα κειμένου, συμπεριλαμβανομένου του περιεχομένου κειμένου, της θέσης (συντεταγμένες X και Y), των πληροφοριών γραμματοσειράς (όνομα, μέγεθος, χρώμα, κ.λπ.) και άλλα. Το δείγμα κώδικα του σεμιναρίου δείχνει πώς να αποκτήσετε πρόσβαση και να εκτυπώσετε αυτές τις λεπτομέρειες για κάθε τμήμα κειμένου.

#### Ε: Μπορώ να εκτελέσω προσαρμοσμένες ενέργειες στα εξαγόμενα τμήματα κειμένου;

Α: Ασφαλώς. Αφού έχετε τα εξαγόμενα τμήματα κειμένου, μπορείτε να προσαρμόσετε τον κώδικα εντός του βρόχου για να εκτελέσετε πρόσθετες ενέργειες σε κάθε τμήμα. Αυτό θα μπορούσε να περιλαμβάνει την αποθήκευση του εξαγόμενου κειμένου, την ανάλυση μοτίβων κειμένου ή την εφαρμογή αλλαγών μορφοποίησης.