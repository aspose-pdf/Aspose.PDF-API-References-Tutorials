---
title: Διαγράψτε τις λέξεις
linktitle: Διαγράψτε τις λέξεις
second_title: Aspose.PDF για Αναφορά API .NET
description: Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα για τη χρήση του Aspose.PDF για τη δυνατότητα Strike Out Words του .NET, συμπεριλαμβανομένου οδηγού βήμα προς βήμα και επεξηγήσεων
type: docs
weight: 150
url: /el/net/annotations/strikeoutwords/
---
Το Aspose.PDF για .NET είναι μια βιβλιοθήκη χειρισμού και επεξεργασίας εγγράφων PDF που παρέχει διάφορες δυνατότητες για τη δημιουργία, τροποποίηση και μετατροπή αρχείων PDF. Μία από τις χρήσιμες δυνατότητες που παρέχει το Aspose.PDF είναι η δυνατότητα διαγραφής λέξεων ή φράσεων σε ένα έγγραφο PDF χρησιμοποιώντας τον πηγαίο κώδικα C#. Σε αυτό το άρθρο, θα παρέχουμε έναν οδηγό βήμα προς βήμα για τον τρόπο διαγραφής λέξεων χρησιμοποιώντας το Aspose.PDF για .NET.

## Βήμα 1: Φόρτωση του εγγράφου PDF
Το πρώτο βήμα είναι να φορτώσετε το έγγραφο PDF που θέλετε να τροποποιήσετε. Σε αυτό το σεμινάριο, θα φορτώσουμε ένα έγγραφο PDF με το όνομα "input.pdf" από το φάκελο "YOUR DOCUMENT DECTORY". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Βήμα 2: Αναζήτηση θραυσμάτων κειμένου
Για να διαγράψετε συγκεκριμένες λέξεις ή φράσεις στο έγγραφο PDF, πρέπει πρώτα να τις αναζητήσετε. Το Aspose.PDF παρέχει μια κλάση TextFragmentAbsorber που μπορεί να χρησιμοποιηθεί για την αναζήτηση ενός συγκεκριμένου τμήματος κειμένου στο έγγραφο PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Στον παραπάνω κώδικα, αναζητούμε το τμήμα κειμένου "Estoque" στο έγγραφο PDF. Μπορείτε να το τροποποιήσετε για να αναζητήσετε οποιαδήποτε άλλη λέξη ή φράση που θέλετε να διαγράψετε.

## Βήμα 3: Διαγραφή των θραυσμάτων κειμένου
Αφού βρείτε τα τμήματα κειμένου, το επόμενο βήμα είναι να τα διαγράψετε. Το Aspose.PDF παρέχει μια κλάση StrikeOutAnnotation που μπορεί να χρησιμοποιηθεί για τη δημιουργία ενός σχολιασμού διαγραφής για το τμήμα κειμένου. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Στον παραπάνω κώδικα, δημιουργούμε έναν σχολιασμό διαγραφής για κάθε τμήμα κειμένου που βρήκαμε. Επίσης, ορίζουμε την αδιαφάνεια, το περίγραμμα και το χρώμα του σχολιασμού διαγραφής.

## Βήμα 4: Αποθήκευση του τροποποιημένου εγγράφου PDF
Αφού διαγράψετε τα τμήματα κειμένου, αποθηκεύστε το τροποποιημένο έγγραφο.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Παράδειγμα πηγαίου κώδικα για Strike Out Words χρησιμοποιώντας Aspose.PDF για .NET


```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Άνοιγμα εγγράφου
Document document = new Document(dataDir + "input.pdf");

// Δημιουργήστε ένα στιγμιότυπο του TextFragment Absorber για αναζήτηση συγκεκριμένου τμήματος κειμένου
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Επαναλάβετε τις σελίδες του εγγράφου PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Λάβετε την πρώτη σελίδα του εγγράφου PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Δημιουργήστε μια συλλογή από απορροφημένο κείμενο
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Επαναλάβετε την παραπάνω συλλογή
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Λάβετε ορθογώνιες διαστάσεις του αντικειμένου TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instantiate instantation StrikeOut Annotation
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Ορίστε την αδιαφάνεια για τον σχολιασμό
	strikeOut.Opacity = .80f;
	// Ορίστε το περίγραμμα για παράδειγμα σχολιασμού
	strikeOut.Border = new Border(strikeOut);
	// Ορίστε το χρώμα του σχολιασμού
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Προσθήκη σχολιασμού στη συλλογή σχολιασμών του TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε το Aspose.PDF για .NET για να διαγράψουμε συγκεκριμένες λέξεις σε ένα έγγραφο PDF. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#, μπορείτε εύκολα να φορτώσετε ένα έγγραφο PDF, να αναζητήσετε συγκεκριμένα τμήματα κειμένου και να δημιουργήσετε σχολιασμούς για να επισημάνετε οπτικά και να διαγράψετε αυτές τις λέξεις. Το Aspose.PDF για .NET παρέχει έναν απλό και αποτελεσματικό τρόπο χειρισμού εγγράφων PDF μέσω προγραμματισμού, καθιστώντας το ένα πολύτιμο εργαλείο για προγραμματιστές που εργάζονται με αρχεία PDF σε εφαρμογές .NET.

### Συχνές ερωτήσεις

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να χειρίζονται έγγραφα PDF μέσω προγραμματισμού σε εφαρμογές .NET. Παρέχει ένα ευρύ φάσμα δυνατοτήτων για εργασία με αρχεία PDF, συμπεριλαμβανομένης της εξαγωγής κειμένου, του χειρισμού σχολιασμών, της συμπλήρωσης φόρμας και πολλά άλλα.

#### Ε: Μπορώ να χρησιμοποιήσω το Aspose.PDF για .NET για να διαγράψω συγκεκριμένες λέξεις σε ένα έγγραφο PDF;

Α: Ναι, το Aspose.PDF για .NET παρέχει λειτουργικότητα για την αναζήτηση συγκεκριμένων τμημάτων κειμένου σε ένα έγγραφο PDF και στη συνέχεια τη δημιουργία σχολιασμών διαγραφής για οπτική επισήμανση και διαγραφή αυτών των λέξεων.

#### Ε: Πώς μπορώ να καθορίσω το κείμενο που θέλω να διαγράψω στο έγγραφο PDF;

 Α: Για να καθορίσετε το κείμενο που θέλετε να διαγράψετε, μπορείτε να χρησιμοποιήσετε το`TextFragmentAbsorber` κλάση που παρέχεται από το Aspose.PDF για .NET. Σας επιτρέπει να αναζητήσετε ένα συγκεκριμένο τμήμα κειμένου στο έγγραφο PDF με βάση τα επιθυμητά κριτήρια.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του σχολιασμού διαγραφής;

Α: Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες του σχολιασμού διαγραφής, όπως η αδιαφάνεια, το στυλ περιγράμματος και το χρώμα. Αυτό σας επιτρέπει να προσαρμόσετε την εμφάνιση του σχολιασμού διαγραφής στις συγκεκριμένες απαιτήσεις σας.