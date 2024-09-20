---
title: Στοιχείο τραπεζιού στυλ
linktitle: Στοιχείο τραπεζιού στυλ
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε και να διαμορφώνετε ένα στοιχείο πίνακα στο Aspose.PDF για .NET με οδηγίες βήμα προς βήμα, προσαρμοσμένο στυλ και συμμόρφωση με PDF/UA.
type: docs
weight: 170
url: /el/net/programming-with-tagged-pdf/style-table-element/
---
## Εισαγωγή

Σε αυτό το άρθρο, θα εξετάσουμε τον τρόπο δημιουργίας και στυλ ενός στοιχείου πίνακα χρησιμοποιώντας το Aspose.PDF για .NET. Θα μάθετε πώς να δομείτε έναν πίνακα, να εφαρμόζετε προσαρμοσμένα στυλ και να επικυρώνετε τη συμμόρφωση PDF/UA του εγγράφου σας. Μέχρι το τέλος αυτού του σεμιναρίου, θα μπορείτε να δημιουργείτε πίνακες με επαγγελματική εμφάνιση στα PDF σας με ευκολία!

## Προαπαιτούμενα

Πριν μεταβείτε στο σεμινάριο, θα πρέπει να βεβαιωθείτε ότι έχετε τα εξής:

1. Visual Studio ή παρόμοιο IDE εγκατεστημένο στον υπολογιστή σας.
2. .NET Framework ή .NET Core SDK για την εκτέλεση της εφαρμογής.
3.  Το Aspose.PDF για τη βιβλιοθήκη .NET λήφθηκε και αναφέρεται στο έργο σας. Μπορείτε να πάρετε την πιο πρόσφατη έκδοση από[εδώ](https://releases.aspose.com/pdf/net/).
4.  Μια έγκυρη άδεια Aspose ή α[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για να ξεκλειδώσετε την πλήρη λειτουργικότητα της βιβλιοθήκης.

## Εισαγωγή πακέτων

Για να ξεκινήσετε, εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Αυτοί οι χώροι ονομάτων καλύπτουν βασικές λειτουργίες PDF, περιεχόμενο με ετικέτα, πίνακες και μορφοποίηση κειμένου.

Τώρα ας αναλύσουμε τη διαδικασία δημιουργίας και διαμόρφωσης ενός πίνακα στο Aspose.PDF. Θα εξετάσουμε κάθε ενότητα λεπτομερώς, ώστε να μπορείτε να την ακολουθήσετε.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο PDF και ρυθμίστε περιεχόμενο με ετικέτα

Σε αυτό το πρώτο βήμα, θα δημιουργήσουμε ένα κενό έγγραφο PDF και θα ρυθμίσουμε το περιεχόμενό του με ετικέτα.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε ένα νέο έγγραφο PDF
Document document = new Document();

// Ρύθμιση περιεχομένου με ετικέτα
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Ξεκινάμε δημιουργώντας ένα νέο`Document` αντικείμενο, που αντιπροσωπεύει το PDF μας. Ο`TaggedContent`Το αντικείμενο χρησιμοποιείται για τη διαχείριση της δομής του εγγράφου, διασφαλίζοντας τη συμμόρφωση με τα πρότυπα προσβασιμότητας. Ορίσαμε τον τίτλο και τη γλώσσα του εγγράφου για σωστή προσθήκη ετικετών.

## Βήμα 2: Ορίστε το στοιχείο ρίζας

Στη συνέχεια, θα δημιουργήσουμε το στοιχείο δομής ρίζας, το οποίο λειτουργεί ως κοντέινερ για όλο το περιεχόμενο στο PDF μας.

```csharp
// Λάβετε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
```

 Ο`RootElement` χρησιμεύει ως το βασικό δοχείο για όλα τα δομημένα στοιχεία, συμπεριλαμβανομένου του τραπεζιού μας. Βοηθά στη διατήρηση της δομικής ιεραρχίας του εγγράφου, η οποία είναι σημαντική τόσο για την οργάνωση όσο και για την προσβασιμότητα.

## Βήμα 3: Δημιουργήστε και δώστε στυλ στο στοιχείο του πίνακα

 Τώρα που έχει ρυθμιστεί το ριζικό στοιχείο, θα δημιουργήσουμε ένα`TableElement` και εφαρμόστε στυλ όπως χρώμα φόντου, περιγράμματα και στοίχιση.

```csharp
// Δημιουργία στοιχείου δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Δώστε στυλ στο τραπέζι
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Δημιουργούμε α`TableElement` , που ορίζει τη δομή του πίνακα μας. Ο`BackgroundColor`, `Border` , και`Alignment` Οι ιδιότητες μας επιτρέπουν να προσαρμόσουμε την εμφάνιση του πίνακα. Ο`Broken` Η ιδιότητα διασφαλίζει ότι εάν ο πίνακας σπάσει στις σελίδες, θα σπάσει κατακόρυφα.

## Βήμα 4: Ορισμός διαστάσεων πίνακα και στυλ κελιών

Σε αυτό το βήμα, θα ορίσουμε τον αριθμό των στηλών, την πλήρωση κελιών και άλλες σημαντικές ιδιότητες πίνακα.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Καθορίζουμε τα πλάτη των στηλών για να διασφαλίσουμε ότι κάθε στήλη στον πίνακα έχει ομοιόμορφη απόσταση. Ο`DefaultCellBorder`, `DefaultCellPadding` , και`DefaultCellTextState` ορίστε τα προεπιλεγμένα στυλ για τα κελιά, συμπεριλαμβανομένων των περιγραμμάτων, της συμπλήρωσης, του χρώματος κειμένου και του μεγέθους της γραμματοσειράς.

## Βήμα 5: Προσθέστε επαναλαμβανόμενες σειρές και προσαρμοσμένα στυλ

Μπορούμε επίσης να ορίσουμε στυλ για την επανάληψη σειρών και άλλων συγκεκριμένων στοιχείων πίνακα όπως κεφαλίδες και υποσέλιδα.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 Ο`RepeatingRowsCount` διασφαλίζει ότι οι τρεις πρώτες σειρές επαναλαμβάνονται εάν ο πίνακας εκτείνεται σε πολλές σελίδες. Ρυθμίσαμε το`RepeatingRowsStyle` για να εφαρμόσετε ένα προσαρμοσμένο χρώμα φόντου σε αυτές τις σειρές.

## Βήμα 6: Προσθέστε στοιχεία κεφαλής, σώματος και ποδιού τραπεζιού

Τώρα, ας δημιουργήσουμε τις ενότητες κεφαλίδας, σώματος και υποσέλιδου πίνακα και ας τις συμπληρώσουμε με περιεχόμενο.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Δημιουργία σειράς κεφαλίδας
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Συμπληρώστε το σώμα του τραπεζιού
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Το τραπέζι χωρίζεται σε τρία μέρη: το κεφάλι, το σώμα και το πόδι. Πρώτα δημιουργούμε τη γραμμή κεφαλίδας χρησιμοποιώντας`TableTHElement`και προσθέστε επικεφαλίδες στηλών. Στη συνέχεια, συμπληρώνουμε το σώμα του τραπεζιού με`TableTDElement`, γεμίζοντας κάθε κελί με μια ετικέτα που περιλαμβάνει τη θέση του.

## Βήμα 7: Αποθηκεύστε το έγγραφο

Τέλος, αποθηκεύουμε το έγγραφο PDF στον καθορισμένο κατάλογο.

```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "StyleTableElement.pdf");
```

Αυτό το βήμα ολοκληρώνει τη διαδικασία δημιουργίας εγγράφου αποθηκεύοντας το αρχείο PDF με τον πίνακα με στυλ.

## Βήμα 8: Επικύρωση συμμόρφωσης PDF/UA

Μετά την αποθήκευση του εγγράφου, είναι απαραίτητο να διασφαλίσετε ότι συμμορφώνεται με τα πρότυπα PDF/UA (Universal Accessibility).

```csharp
// Ελέγξτε τη συμμόρφωση PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Εδώ, φορτώνουμε ξανά το έγγραφο και το επικυρώνουμε σύμφωνα με τα πρότυπα PDF/UA. Η συμμόρφωση διασφαλίζει ότι το PDF σας πληροί τις απαιτήσεις προσβασιμότητας, καθιστώντας το κατάλληλο για ένα ευρύ φάσμα χρηστών.

## Σύναψη

Με το Aspose.PDF για .NET, η δημιουργία και η διαμόρφωση πινάκων στα έγγραφά σας PDF είναι απλή και διαισθητική. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να δημιουργήσετε πίνακες με προσαρμοσμένα στυλ και να διασφαλίσετε ότι τα PDF σας πληρούν τα πρότυπα προσβασιμότητας. Είτε δημιουργείτε αναφορές είτε δημιουργείτε δομημένα έγγραφα, οι πίνακες είναι ένα ισχυρό εργαλείο για την ξεκάθαρη παρουσίαση των δεδομένων.

## Συχνές ερωτήσεις

### Μπορώ να προσθέσω εικόνες μέσα στα κελιά του πίνακα;
 Ναι, μπορείτε να εισαγάγετε εικόνες σε κελιά πίνακα χρησιμοποιώντας το`Image` στοιχείο.

### Πώς μπορώ να προσαρμόσω δυναμικά τα πλάτη των στηλών;
 Μπορείτε να ρυθμίσετε το`ColumnAdjustment` ιδιοκτησία σε`AutoFitToWindow` για να προσαρμόσετε αυτόματα τα πλάτη των στηλών με βάση το περιεχόμενο.

### Είναι υποχρεωτική η συμμόρφωση με PDF/UA για όλα τα έγγραφα;
Αν και δεν είναι υποχρεωτικό, συνιστάται για έγγραφα που απαιτούν υψηλά πρότυπα προσβασιμότητας.

### Μπορώ να εφαρμόσω διαφορετικά στυλ σε συγκεκριμένες σειρές;
 Ναι, μπορείτε να προσαρμόσετε μεμονωμένες σειρές ή κελιά προσαρμόζοντάς τις`TextState` ή`BackgroundColor`.

### Ποιο είναι το όφελος από τη χρήση περιεχομένου με ετικέτα;
Το περιεχόμενο με ετικέτα βελτιώνει την προσβασιμότητα των εγγράφων και συμβάλλει στη διασφάλιση της συμμόρφωσης με πρότυπα όπως το PDF/UA.