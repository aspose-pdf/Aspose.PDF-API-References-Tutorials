---
title: Απόκρυψη αριθμών σελίδων στο TOC
linktitle: Απόκρυψη αριθμών σελίδων στο TOC
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να αποκρύπτετε αριθμούς σελίδων σε έναν πίνακα περιεχομένων χρησιμοποιώντας το Aspose.PDF για .NET με αυτόν τον αναλυτικό οδηγό.
type: docs
weight: 220
url: /el/net/programming-with-document/hidepagenumbersintoc/
---
Σε αυτό το άρθρο, θα συζητήσουμε την υλοποίηση της δυνατότητας Απόκρυψη αριθμών σελίδας σε TOC του Aspose.PDF για .NET χρησιμοποιώντας C#. Θα ξεκινήσουμε με μια σύντομη εισαγωγή στο Aspose.PDF για .NET και, στη συνέχεια, θα εξετάσουμε τον αναλυτικό οδηγό για την εφαρμογή αυτής της δυνατότητας. 

## Εισαγωγή στο Aspose.PDF για .NET

Το Aspose.PDF για .NET είναι ένα ισχυρό στοιχείο χειρισμού PDF που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να χειρίζονται αρχεία PDF μέσω προγραμματισμού. Παρέχει ένα ευρύ φάσμα δυνατοτήτων και λειτουργιών που διευκολύνουν την εργασία με έγγραφα PDF. Το Aspose.PDF για .NET υποστηρίζει λειτουργικά συστήματα 32-bit και 64-bit και μπορεί να χρησιμοποιηθεί με πλατφόρμες .NET Framework, .NET Core και Xamarin. 

## Τι είναι η δυνατότητα Απόκρυψη αριθμών σελίδας σε TOC;

Ο Πίνακας Περιεχομένων (TOC) είναι ένα ουσιαστικό μέρος ενός εγγράφου PDF που παρέχει στους χρήστες μια γρήγορη επισκόπηση του περιεχομένου. Μερικές φορές, οι χρήστες μπορεί να θέλουν να αποκρύψουν τους αριθμούς σελίδων στο TOC για να το κάνουν πιο φιλικό προς το χρήστη. Το Aspose.PDF για .NET παρέχει μια ενσωματωμένη δυνατότητα για την απόκρυψη αριθμών σελίδων στο TOC. Αυτή η δυνατότητα μπορεί να χρησιμοποιηθεί για τη δημιουργία πιο φιλικών προς το χρήστη εγγράφων PDF. 

## Προαπαιτούμενα

Για να ακολουθήσετε αυτό το σεμινάριο, θα χρειαστείτε τα εξής:

- Visual Studio 2010 ή μεταγενέστερη έκδοση
- Το Aspose.PDF για .NET είναι εγκατεστημένο στο σύστημά σας
- Βασικές γνώσεις γλώσσας προγραμματισμού C#

## Οδηγός βήμα προς βήμα για την εφαρμογή της δυνατότητας Απόκρυψη αριθμών σελίδας σε TOC

Ακολουθήστε τα παρακάτω βήματα για να εφαρμόσετε τη δυνατότητα Απόκρυψη αριθμών σελίδας σε TOC χρησιμοποιώντας το Aspose.PDF για .NET:

## Βήμα 1: Δημιουργήστε μια νέα εφαρμογή κονσόλας C# στο Visual Studio

Ανοίξτε το Visual Studio και δημιουργήστε μια νέα εφαρμογή κονσόλας C#.

## Βήμα 2: Προσθήκη αναφοράς στο Aspose.PDF για .NET

Κάντε δεξί κλικ στο φάκελο Αναφορές στο έργο σας και επιλέξτε Προσθήκη αναφοράς. Περιηγηθείτε στη θέση όπου το Aspose.PDF για .NET είναι εγκατεστημένο στο σύστημά σας και προσθέστε μια αναφορά σε αυτό.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο PDF

Δημιουργήστε ένα νέο έγγραφο PDF χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Βήμα 2: Δημιουργήστε μια σελίδα TOC

Δημιουργήστε μια νέα σελίδα για το TOC και προσθέστε την στο έγγραφο PDF χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Βήμα 3: Προσθήκη ενότητας λίστας στη συλλογή ενοτήτων του εγγράφου PDF

Προσθέστε την ενότητα λίστας στη συλλογή ενοτήτων του εγγράφου PDF χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
tocPage.TocInfo = tocInfo;
```

## Βήμα 4: Καθορίστε τη μορφή της λίστας τεσσάρων επιπέδων

Καθορίστε τη μορφή της λίστας τεσσάρων επιπέδων ορίζοντας τα αριστερά περιθώρια και τις ρυθμίσεις μορφής κειμένου κάθε επιπέδου χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Βήμα 5: Προσθέστε τέσσερις επικεφαλίδες στην ενότητα

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Παράδειγμα πηγαίου κώδικα για απόκρυψη αριθμών σελίδων σε TOC χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Προσθέστε την ενότητα λίστας στη συλλογή ενοτήτων του εγγράφου Pdf
tocPage.TocInfo = tocInfo;
//Καθορίστε τη μορφή της λίστας τεσσάρων επιπέδων ορίζοντας τα αριστερά περιθώρια και
//ρυθμίσεις μορφής κειμένου για κάθε επίπεδο

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Προσθέστε τέσσερις επικεφαλίδες στην ενότητα
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εργασίας με μεταδεδομένα XMP σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Τα μεταδεδομένα XMP παρέχουν πολύτιμες πληροφορίες σχετικά με το έγγραφο PDF, συμπεριλαμβανομένου του τίτλου, του συγγραφέα, της ημερομηνίας δημιουργίας και άλλων. Το Aspose.PDF για .NET επιτρέπει στους προγραμματιστές να έχουν πρόσβαση και να χειρίζονται αυτά τα μεταδεδομένα, παρέχοντας ένα ευέλικτο και ισχυρό API για εργασία με έγγραφα PDF.

### Συχνές ερωτήσεις

#### Ε: Τι είναι τα μεταδεδομένα XMP σε ένα έγγραφο PDF;

A: Τα μεταδεδομένα XMP (Extensible Metadata Platform) σε ένα έγγραφο PDF είναι μια τυπική μορφή για την αποθήκευση πληροφοριών μεταδεδομένων σχετικά με το έγγραφο. Περιλαμβάνει λεπτομέρειες όπως τίτλος εγγράφου, συγγραφέας, ημερομηνία δημιουργίας, λέξεις-κλειδιά και άλλα. Τα μεταδεδομένα XMP παρέχουν έναν δομημένο και τυποποιημένο τρόπο αποθήκευσης και κοινής χρήσης πληροφοριών σχετικά με το έγγραφο PDF.

#### Ε: Μπορώ να τροποποιήσω τα μεταδεδομένα XMP ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Ναι, μπορείτε να τροποποιήσετε τα μεταδεδομένα XMP ενός εγγράφου PDF μέσω προγραμματισμού χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να έχετε πρόσβαση στο`Info` ιδιοκτησία του`Document` αντικείμενο, το οποίο σας δίνει πρόσβαση στις ιδιότητες μεταδεδομένων XMP. Στη συνέχεια, μπορείτε να ενημερώσετε τις τιμές αυτών των ιδιοτήτων για να τροποποιήσετε τα μεταδεδομένα XMP του εγγράφου PDF.

#### Ε: Μπορώ να εξαγάγω προσαρμοσμένες ιδιότητες μεταδεδομένων XMP από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

 Α: Ναι, μπορείτε να εξαγάγετε προσαρμοσμένες ιδιότητες μεταδεδομένων XMP από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε το`Metadata` ιδιοκτησία του`Document`αντικείμενο, το οποίο παρέχει πρόσβαση σε όλες τις ιδιότητες μεταδεδομένων XMP του εγγράφου PDF. Στη συνέχεια, μπορείτε να εξαγάγετε προσαρμοσμένες ιδιότητες και να χρησιμοποιήσετε τις τιμές τους όπως απαιτείται.