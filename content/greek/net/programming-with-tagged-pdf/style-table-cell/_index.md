---
title: Επιτραπέζιο κελί στυλ
linktitle: Επιτραπέζιο κελί στυλ
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να δημιουργείτε στυλ κελιών πίνακα σε ένα PDF χρησιμοποιώντας το Aspose.PDF για .NET με αυτό το λεπτομερές σεμινάριο. Ακολουθήστε τις οδηγίες για να δημιουργήσετε και να μορφοποιήσετε όμορφους πίνακες PDF.
type: docs
weight: 160
url: /el/net/programming-with-tagged-pdf/style-table-cell/
---
## Εισαγωγή

Η δημιουργία πινάκων PDF με επαγγελματική εμφάνιση μπορεί να είναι δύσκολη, αλλά με το Aspose.PDF για .NET, είναι εκπληκτικά απλή! Είτε σχεδιάζετε κεφαλίδες, υποσέλιδα ή συγκεκριμένα κελιά πίνακα, αυτή η ισχυρή βιβλιοθήκη σάς παρέχει όλα τα εργαλεία που χρειάζεστε για να δημιουργήσετε όμορφα μορφοποιημένα έγγραφα PDF. Σε αυτό το σεμινάριο, θα μάθουμε πώς να δημιουργείτε στυλ κελιών πίνακα σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μην ανησυχείτε—θα αναλύσουμε τα πάντα σε βήματα που μπορείτε να ακολουθήσετε εύκολα.

## Προαπαιτούμενα

Πριν βουτήξετε στον κώδικα, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Aspose.PDF για .NET: Κάντε λήψη και εγκατάσταση της πιο πρόσφατης έκδοσης του Aspose.PDF από[εδώ](https://releases.aspose.com/pdf/net/).
2. IDE (όπως το Visual Studio): Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET.
3. Βασικές γνώσεις προγραμματισμού C#: Απαιτείται λίγη εξοικείωση με την C#.
4.  Άδεια χρήσης Aspose.PDF: Λάβετε μια προσωρινή ή πλήρη άδεια χρήσης για να ξεκλειδώσετε τις πλήρεις δυνατότητες της βιβλιοθήκης. Μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://purchase.aspose.com/temporary-license/).

## Εισαγωγή πακέτων

Πριν ξεκινήσετε, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων. Θα χρειαστείτε τα ακόλουθα στο έργο σας:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Τώρα που όλα έχουν ρυθμιστεί, ας μεταβούμε στον οδηγό βήμα προς βήμα!

Θα δημιουργήσουμε έναν πίνακα σε ένα έγγραφο PDF και θα δημιουργήσουμε στυλ στα κελιά του. Κάθε βήμα θα εξηγήσει τη διαδικασία λεπτομερώς.

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο PDF

 Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο έγγραφο PDF. Στο Aspose.PDF, μπορείτε να αρχικοποιήσετε ένα νέο`Document` αντικείμενο, το οποίο αντιπροσωπεύει το αρχείο PDF σας.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργήστε ένα νέο έγγραφο PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Εδώ, αρχικοποιούμε ένα έγγραφο PDF και ορίζουμε τον τίτλο και τη γλώσσα του. Αυτό δίνει στο έγγραφό σας μια σωστή δομή, η οποία είναι απαραίτητη για τη συμμόρφωση με PDF/UA.

## Βήμα 2: Ρυθμίστε τη δομή του πίνακα

Οι πίνακες σε αρχεία PDF ορίζονται μέσα στα στοιχεία δομής. Ας δημιουργήσουμε τον πίνακα και ας ορίσουμε τις γραμμές και τις στήλες του πίνακα.

```csharp
// Λάβετε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;

// Δημιουργήστε ένα στοιχείο δομής πίνακα
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Τώρα ορίσαμε την κεφαλή του πίνακα (`TableTHeadElement`), σώμα (`TableTBodyElement`), και πόδι (`TableTFootElement`) ενότητες. Μπορείτε να τα σκεφτείτε αυτά ως τον σκελετό του τραπεζιού σας.

## Βήμα 3: Δώστε στυλ στα κελιά κεφαλίδας

Το στυλ των κελιών της κεφαλίδας τα κάνει να ξεχωρίζουν. Εδώ, εφαρμόζουμε χρώματα φόντου, περιγράμματα και στοίχιση κειμένου.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Σε αυτό το βήμα, κάνουμε κύκλο σε κάθε κελί κεφαλίδας, δίνοντάς του ένα πράσινο-κίτρινο φόντο, ένα γκρι περίγραμμα και ένα κείμενο με στοίχιση δεξιά. Μπορείτε να προσαρμόσετε αυτές τις ιδιότητες ώστε να ταιριάζουν με το σχέδιο που επιθυμείτε.

## Βήμα 4: Συμπληρώστε και δώστε στυλ στο σώμα του πίνακα

Το σώμα του πίνακα περιέχει τα πραγματικά δεδομένα. Δείτε πώς μπορείτε να στυλ κάθε κελί με συγκεκριμένα περιθώρια, περιθώρια και ρυθμίσεις κειμένου.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Σε αυτό το βήμα, γεμίζουμε το σώμα του πίνακα με τέσσερις σειρές και διαμορφώνουμε κάθε κελί με κίτρινο φόντο και κεντραρισμένο, έντονο μπλε κείμενο. Χρησιμοποιούμε επίσης το`MarginInfo`κλάση για να ορίσετε το padding γύρω από το κείμενο.

## Βήμα 5: Δώστε στυλ στο υποσέλιδο

Για να δώσουμε στον πίνακα μια πλήρη δομή, προσθέτουμε και διαμορφώνουμε τα κελιά του υποσέλιδου, όπως ακριβώς κάναμε με την κεφαλίδα.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Το τμήμα του υποσέλιδου έχει παρόμοιο στυλ με την κεφαλίδα, διευκολύνοντας τους αναγνώστες να ακολουθήσουν τη δομή του πίνακα.

## Βήμα 6: Αποθηκεύστε και επικυρώστε το έγγραφο PDF

Τέλος, αποθηκεύουμε το έγγραφο PDF και ελέγχουμε αν είναι συμβατό με PDF/UA.

```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "StyleTableCell.pdf");

// Έλεγχος συμμόρφωσης PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Αποθηκεύουμε το PDF και χρησιμοποιούμε το`Validate` μέθοδος για να διασφαλιστεί ότι πληροί τα πρότυπα προσβασιμότητας (συμμόρφωση με PDF/UA).

## Σύναψη

Η διαμόρφωση πινάκων στυλ σε PDF χρησιμοποιώντας το Aspose.PDF για .NET είναι ταυτόχρονα ισχυρό και ευέλικτο. Με μερικές γραμμές κώδικα, μπορείτε να δημιουργήσετε προσαρμοσμένα σχέδια πινάκων που θα κάνουν τα έγγραφά σας PDF να ξεχωρίζουν. Από την προσαρμογή των περιγραμμάτων και του φόντου κελιών έως τη διασφάλιση της συμμόρφωσης με την προσβασιμότητα, το Aspose.PDF διευκολύνει τη δημιουργία εκλεπτυσμένων αρχείων PDF.

## Συχνές ερωτήσεις

### Μπορώ να εφαρμόσω διαφορετικά στυλ σε μεμονωμένα κελιά πίνακα;  
Ναι, μπορείτε να διαμορφώσετε μεμονωμένα κελιά προσαρμόζοντας το`TableTDElement` σκηνικά θέατρου.

### Πώς μπορώ να συγχωνεύσω κελιά πίνακα;  
 Μπορείτε να χρησιμοποιήσετε το`ColSpan` και`RowSpan` ιδιότητες για τη συγχώνευση κελιών σε έναν πίνακα.

### Είναι δυνατή η δημιουργία πίνακα συμβατό με PDF/UA;  
 Ναι, όπως αποδεικνύεται σε αυτόν τον οδηγό, μπορείτε να διασφαλίσετε τη συμμόρφωση PDF/UA επικυρώνοντας το έγγραφό σας χρησιμοποιώντας το`Validate` μέθοδος.

### Μπορώ να χρησιμοποιήσω διαφορετικές γραμματοσειρές στα κελιά του πίνακα;  
 Απολύτως! Μπορείτε να καθορίσετε διαφορετικές γραμματοσειρές χρησιμοποιώντας το`TextState` αντικείμενο για κάθε κελί.

### Πώς μπορώ να κατεβάσω το Aspose.PDF για .NET;  
 Μπορείτε να το κατεβάσετε από το[σελίδα εκδόσεων](https://releases.aspose.com/pdf/net/).