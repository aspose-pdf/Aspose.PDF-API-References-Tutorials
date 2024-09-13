---
title: Αντικαταστάσιμα σύμβολα στο υποσέλιδο κεφαλίδων
linktitle: Αντικαταστάσιμα σύμβολα στο υποσέλιδο κεφαλίδων
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να χρησιμοποιείτε αντικαταστάσιμα σύμβολα στην κεφαλίδα και το υποσέλιδο ενός εγγράφου PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 320
url: /el/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να χρησιμοποιήσετε αντικαταστάσιμα σύμβολα στην κεφαλίδα και το υποσέλιδο ενός εγγράφου PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Θα προχωρήσουμε στη διαδικασία βήμα προς βήμα δημιουργίας ενός PDF, ορίζοντας περιθώρια, προσθήκη κεφαλίδας και υποσέλιδου με αντικαταστάσιμα σύμβολα και αποθήκευση του PDF χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
- Βασική κατανόηση του προγραμματισμού C#.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων

 Πρώτα, πρέπει να ορίσετε τη διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε το αρχείο PDF που δημιουργήθηκε. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στο`dataDir` μεταβλητή με τη διαδρομή προς τον επιθυμητό κατάλογο.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Δημιουργήστε ένα έγγραφο και μια σελίδα PDF

 Στη συνέχεια, δημιουργούμε ένα νέο έγγραφο PDF και προσθέτουμε μια σελίδα σε αυτό χρησιμοποιώντας το`Document` τάξη και`Page` τάξη από τη βιβλιοθήκη Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Βήμα 3: Ορισμός περιθωρίων

 Ορίζουμε τα περιθώρια για τη σελίδα χρησιμοποιώντας το`MarginInfo` τάξη. Προσαρμόστε τις τιμές περιθωρίου σύμφωνα με τις απαιτήσεις σας.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Βήμα 4: Προσθήκη κεφαλίδας με αντικαταστάσιμα σύμβολα

 Δημιουργούμε α`HeaderFooter` αντικείμενο για τη σελίδα και προσθέστε ένα`TextFragment` με αντικαταστάσιμα σύμβολα σε αυτό.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Ορίστε τις ιδιότητες του κειμένου εάν θέλετε
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Προσθέστε περισσότερα TextFragments ή προσαρμόστε όπως απαιτείται
```

## Βήμα 5: Προσθήκη υποσέλιδου με αντικαταστάσιμα σύμβολα

 Ομοίως, δημιουργούμε ένα`HeaderFooter` αντικείμενο για το υποσέλιδο της σελίδας και προσθήκη`TextFragment` αντικείμενα με αντικαταστάσιμα σύμβολα σε αυτό.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Προσθέστε περισσότερα TextFragments ή προσαρμόστε όπως απαιτείται

hfFoot.Paragraphs.Add(tab2);
```

## Βήμα 6: Αποθηκεύστε το έγγραφο PDF

Τέλος, αποθηκεύουμε το έγγραφο PDF στο καθορισμένο αρχείο εξόδου.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Δείγμα πηγαίου κώδικα για αντικαταστάσιμα σύμβολα στο υποσέλιδο κεφαλίδων χρησιμοποιώντας Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Αντιστοιχίστε το στιγμιότυπο marginInfo στην ιδιότητα Margin του sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Δημιουργήστε μια παράγραφο κειμένου που θα αποθηκεύει το περιεχόμενο για να εμφανίζεται ως κεφαλίδα
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Δημιουργήστε ένα αντικείμενο HeaderFooter για την ενότητα
HeaderFooter hfFoot = new HeaderFooter();
// Ορίστε το αντικείμενο HeaderFooter σε μονό και ζυγό υποσέλιδο
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Προσθέστε μια παράγραφο κειμένου που περιέχει τον τρέχοντα αριθμό σελίδας του συνολικού αριθμού σελίδων
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Δημιουργήστε ένα αντικείμενο πίνακα
Table tab2 = new Table();
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
hfFoot.Paragraphs.Add(tab2);
// Σετ με τα πλάτη στηλών του πίνακα
tab2.ColumnWidths = "165 172 165";
//Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Ορίστε την κατακόρυφη στοίχιση του κειμένου ως στοίχιση στο κέντρο
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java είναι μια συλλογή κάθε στοιχείου Java που προσφέρεται από την Aspose. Μεταγλωττίζεται σε καθημερινή βάση #$NL" + "για να διασφαλιστεί ότι περιέχει τις πιο ενημερωμένες εκδόσεις κάθε των στοιχείων Java μας " + "Χρησιμοποιώντας το Aspose.Total για προγραμματιστές Java μπορούν να δημιουργήσουν ένα ευρύ φάσμα εφαρμογών #$NL #$NP" + "Το Aspose.Total για Java είναι μια συλλογή από κάθε στοιχείο Java. Προσφέρεται από την Aspose Μεταγλωττίζεται σε καθημερινή βάση #$NL για να διασφαλιστεί ότι περιέχει τις πιο ενημερωμένες εκδόσεις καθενός από τα στοιχεία Java " + "Χρησιμοποιώντας το Aspose.Total για προγραμματιστές Java γκάμα εφαρμογών #$NL #$NL #$NP" + "Aspose.Total για Java είναι μια συλλογή από κάθε στοιχείο Java που προσφέρεται από την Aspose. Μεταγλωττίζεται σε καθημερινή βάση για να διασφαλιστεί ότι περιέχει τα περισσότερα Οι ενημερωμένες εκδόσεις καθενός από τα στοιχεία Java " + "Χρησιμοποιώντας το Aspose.Total για προγραμματιστές Java μπορούν να δημιουργήσουν ένα ευρύ φάσμα εφαρμογών.
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Προσθέστε τον πίνακα στη συλλογή παραγράφων της επιθυμητής ενότητας
page.Paragraphs.Add(table);
// Ορίστε το προεπιλεγμένο περίγραμμα κελιού χρησιμοποιώντας το αντικείμενο BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Ορισμός περιγράμματος πίνακα χρησιμοποιώντας ένα άλλο προσαρμοσμένο αντικείμενο BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Δημιουργήστε σειρές στον πίνακα και μετά κελιά στις σειρές
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να χρησιμοποιείτε αντικαταστάσιμα σύμβολα στην κεφαλίδα και το υποσέλιδο ενός εγγράφου PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και εκτελώντας τον παρεχόμενο κώδικα C#, μπορείτε να δημιουργήσετε ένα PDF, να ορίσετε περιθώρια, να προσθέσετε κεφαλίδα και υποσέλιδο με αντικαταστάσιμα σύμβολα και να αποθηκεύσετε το PDF.

### Συχνές ερωτήσεις

#### Ε: Ποιος είναι ο σκοπός του σεμιναρίου "Replaceable Symbols In Header Footer";

Α: Το σεμινάριο "Replaceable Symbols In Header Footer" έχει σκοπό να σας καθοδηγήσει στη διαδικασία χρήσης της βιβλιοθήκης Aspose.PDF για .NET για την προσθήκη αντικαταστάσιμων συμβόλων στην κεφαλίδα και το υποσέλιδο ενός εγγράφου PDF. Τα αντικαταστάσιμα σύμβολα σάς επιτρέπουν να αντικαθιστάτε δυναμικά συγκεκριμένα σύμβολα κράτησης θέσης με πραγματικές τιμές κατά τη δημιουργία του PDF.

#### Ε: Τι είναι τα αντικαταστάσιμα σύμβολα στο πλαίσιο μιας κεφαλίδας και υποσέλιδου PDF;

Α: Τα αντικαταστάσιμα σύμβολα είναι σύμβολα κράτησης θέσης που μπορείτε να εισαγάγετε στην κεφαλίδα και το υποσέλιδο ενός εγγράφου PDF. Αυτά τα σύμβολα λειτουργούν ως δυναμικά σύμβολα κράτησης θέσης για τιμές που μπορούν να συμπληρωθούν κατά το χρόνο εκτέλεσης, όπως αριθμοί σελίδων, ημερομηνίες και προσαρμοσμένες πληροφορίες.

#### Ε: Γιατί θα ήθελα να χρησιμοποιήσω αντικαταστάσιμα σύμβολα σε μια κεφαλίδα και ένα υποσέλιδο PDF;

Α: Τα αντικαθιστώμενα σύμβολα στην κεφαλίδα και το υποσέλιδο είναι χρήσιμα όταν θέλετε να συμπεριλάβετε δυναμικές πληροφορίες στα έγγραφα PDF, όπως αριθμούς σελίδων, ημερομηνίες ή άλλα μεταβλητά δεδομένα που ενδέχεται να αλλάξουν κατά τη δημιουργία του εγγράφου.

#### Ε: Πώς μπορώ να ορίσω τα περιθώρια για τη σελίδα PDF;

 Α: Μπορείτε να ορίσετε τα περιθώρια για τη σελίδα PDF χρησιμοποιώντας το`MarginInfo` τάξη και αναθέτοντάς το στο`Margin` ιδιοκτησία του`PageInfo` της σελίδας. Προσαρμόστε τις τιμές περιθωρίου όπως απαιτείται.

#### Ε: Πώς μπορώ να προσθέσω σύμβολα με δυνατότητα αντικατάστασης στην κεφαλίδα και το υποσέλιδο;

 Α: Μπορείτε να προσθέσετε σύμβολα με δυνατότητα αντικατάστασης δημιουργώντας ένα`HeaderFooter` αντικείμενο για την κεφαλίδα και το υποσέλιδο της σελίδας. Στη συνέχεια, μπορείτε να προσθέσετε`TextFragment`αντικείμενα με το επιθυμητό κείμενο, συμπεριλαμβανομένων των αντικαταστάσιμων συμβόλων, στο`Paragraphs` συλλογή των`HeaderFooter` αντικείμενο.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση των αντικαταστάσιμων συμβόλων;

 Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των αντικαταστάσιμων συμβόλων τροποποιώντας τις ιδιότητες του`TextFragment` αντικείμενα που περιέχουν τα σύμβολα. Μπορείτε να ορίσετε ιδιότητες όπως γραμματοσειρά, μέγεθος γραμματοσειράς, χρώμα, στοίχιση και διάστιχο.

#### Ε: Τι είδους αντικαταστάσιμα σύμβολα μπορώ να χρησιμοποιήσω;

Α: Μπορείτε να χρησιμοποιήσετε μια ποικιλία αντικαταστάσιμων συμβόλων, όπως:

- `$p`: Αριθμός τρέχουσας σελίδας.
- `$P`: Συνολικός αριθμός σελίδων.
- `$d`: Τρέχουσα ημερομηνία.
- `$t`: Τρέχουσα ώρα.
- Προσαρμοσμένα σύμβολα κράτησης θέσης που ορίζετε.

#### Ε: Μπορώ να συμπεριλάβω άλλο κείμενο και μορφοποίηση γύρω από τα αντικαταστάσιμα σύμβολα;

 Α: Ναι, μπορείτε να συμπεριλάβετε άλλο κείμενο και μορφοποίηση γύρω από τα αντικαταστάσιμα σύμβολα στο`TextFragment` αντικείμενα. Αυτό σας επιτρέπει να δημιουργήσετε πιο σύνθετες κεφαλίδες και υποσέλιδα που ενσωματώνουν δυναμικό και στατικό περιεχόμενο.

#### Ε: Πώς μπορώ να αποθηκεύσω το έγγραφο PDF που δημιουργήθηκε;

 Α: Για να αποθηκεύσετε το έγγραφο PDF που δημιουργήθηκε, μπορείτε να χρησιμοποιήσετε το`Save` μέθοδος του`Document`τάξη. Δώστε την επιθυμητή διαδρομή αρχείου εξόδου και το όνομα ως όρισμα.

#### Ε: Απαιτείται έγκυρη άδεια Aspose για αυτό το σεμινάριο;

Α: Ναι, απαιτείται έγκυρη άδεια Aspose για την επιτυχή εκτέλεση του κώδικα σε αυτό το σεμινάριο. Μπορείτε να αποκτήσετε μια πλήρη άδεια ή μια προσωρινή άδεια 30 ημερών από τον ιστότοπο Aspose.