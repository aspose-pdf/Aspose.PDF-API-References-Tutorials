---
title: Προσθήκη TOC σε αρχείο PDF
linktitle: Προσθήκη TOC σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς μπορείτε να προσθέσετε έναν πίνακα περιεχομένων σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Οδηγός βήμα προς βήμα με παράδειγμα πηγαίο κώδικα. Ενισχύστε την πλοήγηση στα έγγραφα!
type: docs
weight: 40
url: /el/net/programming-with-document/addtoc/
---
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χρησιμοποιήσετε τη δυνατότητα Προσθήκη TOC (Πίνακας Περιεχομένων) σε αρχείο PDF του Aspose.PDF για .NET για να προσθέσετε έναν πίνακα περιεχομένων σε έγγραφα PDF. Θα παρέχουμε έναν οδηγό βήμα προς βήμα και θα εξηγήσουμε τον πηγαίο κώδικα C# που απαιτείται για να επιτευχθεί αυτό. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να δημιουργήσετε ένα έγγραφο PDF με πίνακα περιεχομένων χρησιμοποιώντας το Aspose.PDF για .NET.


## Βήμα 1: Φορτώστε το υπάρχον αρχείο PDF

 Για να ξεκινήσουμε, πρέπει να φορτώσουμε ένα υπάρχον αρχείο PDF. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον ακόλουθο κώδικα με την πραγματική διαδρομή προς το αρχείο PDF σας:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Βήμα 2: Δημιουργήστε μια νέα σελίδα για τον πίνακα περιεχομένων

Θα δημιουργήσουμε μια νέα σελίδα για να διατηρήσουμε τον πίνακα περιεχομένων. Ο ακόλουθος κώδικας εισάγει μια νέα σελίδα στο ευρετήριο 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Βήμα 3: Ορίστε τις πληροφορίες του πίνακα περιεχομένων

Στη συνέχεια, πρέπει να ορίσουμε τις πληροφορίες του πίνακα περιεχομένων. Θα ορίσουμε τον τίτλο και άλλες ιδιότητες του πίνακα περιεχομένων. Προσθέστε τον ακόλουθο κώδικα:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Βήμα 4: Δημιουργήστε στοιχεία TOC

Τώρα, θα δημιουργήσουμε τα στοιχεία του πίνακα περιεχομένων. Σε αυτό το σεμινάριο, θα δημιουργήσουμε τέσσερα στοιχεία TOC που αντιστοιχούν σε διαφορετικές σελίδες. Τροποποιήστε τον παρακάτω κώδικα σύμφωνα με τις απαιτήσεις σας:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Βήμα 5: Αποθηκεύστε το ενημερωμένο έγγραφο

 Τέλος, πρέπει να αποθηκεύσουμε το τροποποιημένο έγγραφο με τον πίνακα περιεχομένων. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον παρακάτω κώδικα με την επιθυμητή διαδρομή αρχείου εξόδου:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Παράδειγμα πηγαίου κώδικα για την προσθήκη TOC σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Φορτώστε ένα υπάρχον αρχείο PDF
Document doc = new Document(dataDir + "AddTOC.pdf");

// Αποκτήστε πρόσβαση στην πρώτη σελίδα του αρχείου PDF
Page tocPage = doc.Pages.Insert(1);

// Δημιουργία αντικειμένου για την αναπαράσταση πληροφοριών TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Ορίστε τον τίτλο για το TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Δημιουργήστε αντικείμενα συμβολοσειράς που θα χρησιμοποιηθούν ως στοιχεία TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Δημιουργία αντικειμένου Επικεφαλίδας
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Καθορίστε τη σελίδα προορισμού για το αντικείμενο επικεφαλίδας
	heading2.DestinationPage = doc.Pages[i + 2];

	// Σελίδα προορισμού
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Συντεταγμένη προορισμού
	segment2.Text = titles[i];

	// Προσθήκη επικεφαλίδας στη σελίδα που περιέχει TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Αποθηκεύστε το ενημερωμένο έγγραφο
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να προσθέσετε έναν πίνακα περιεχομένων (TOC) σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#, μπορείτε εύκολα να δημιουργήσετε ένα έγγραφο PDF με πίνακα περιεχομένων. Το TOC ενισχύει τη χρηστικότητα του εγγράφου, επιτρέποντας στους χρήστες να πλοηγούνται σε συγκεκριμένες ενότητες ή σελίδες πιο αποτελεσματικά. Το Aspose.PDF για .NET παρέχει μια ισχυρή και φιλική προς το χρήστη λύση για εργασία με αρχεία PDF σε εφαρμογές .NET, επιτρέποντάς σας να δημιουργείτε εύκολα δυναμικά και διαδραστικά έγγραφα PDF.

### Συχνές ερωτήσεις για την προσθήκη TOC σε αρχείο PDF

#### Ε: Τι είναι το Aspose.PDF για .NET;

Α: Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται αποτελεσματικά με αρχεία PDF σε εφαρμογές .NET. Παρέχει ένα ευρύ φάσμα δυνατοτήτων για τη δημιουργία, τον χειρισμό και τη διαχείριση εγγράφων PDF μέσω προγραμματισμού.

#### Ε: Ποιος είναι ο σκοπός της προσθήκης πίνακα περιεχομένων (TOC) σε ένα έγγραφο PDF;

Α: Ο πίνακας περιεχομένων (TOC) παρέχει ένα βοήθημα πλοήγησης στους χρήστες, δίνοντάς τους τη δυνατότητα να μεταβούν γρήγορα σε συγκεκριμένες ενότητες ή σελίδες του εγγράφου PDF. Βελτιώνει τη χρηστικότητα και την εμπειρία χρήστη του εγγράφου.

#### Ε: Πώς μπορώ να προσθέσω έναν πίνακα περιεχομένων σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Για να προσθέσετε έναν πίνακα περιεχομένων σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET, πρέπει να δημιουργήσετε μια νέα σελίδα για να διατηρείτε το TOC, να ορίσετε τις πληροφορίες του πίνακα περιεχομένων και, στη συνέχεια, να δημιουργήσετε στοιχεία TOC που αντιστοιχούν σε συγκεκριμένες σελίδες ή ενότητες στο έγγραφο.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του πίνακα περιεχομένων;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του πίνακα περιεχομένων ορίζοντας διάφορες ιδιότητες των στοιχείων TOC, όπως μέγεθος γραμματοσειράς, στυλ γραμματοσειράς και στοίχιση. Το Aspose.PDF για .NET παρέχει ευελιξία στο σχεδιασμό του TOC ώστε να ταιριάζει με την επιθυμητή εμφάνιση και αίσθηση.

#### Ε: Είναι το Aspose.PDF για .NET κατάλληλο για την προσθήκη προηγμένων δυνατοτήτων σε έγγραφα PDF;

Α: Απολύτως, το Aspose.PDF για .NET είναι μια πλούσια σε χαρακτηριστικά βιβλιοθήκη που σας επιτρέπει να προσθέτετε προηγμένες λειτουργίες σε έγγραφα PDF, συμπεριλαμβανομένων διαδραστικών στοιχείων, πεδίων φορμών, ψηφιακών υπογραφών και πολλά άλλα.