---
title: Εξαγωγή περιγράμματος σε αρχείο PDF
linktitle: Εξαγωγή περιγράμματος σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να εξαγάγετε το περίγραμμα σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 80
url: /el/net/programming-with-tables/extract-border/
---
Σε αυτό το σεμινάριο, θα μάθουμε πώς να εξαγάγετε το περίγραμμα σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Θα εξηγήσουμε τον πηγαίο κώδικα σε C# βήμα προς βήμα. Στο τέλος αυτού του σεμιναρίου, θα ξέρετε πώς να εξαγάγετε το περίγραμμα από ένα έγγραφο PDF και να το αποθηκεύσετε ως εικόνα. Ας ξεκινήσουμε!

## Βήμα 1: Ρύθμιση περιβάλλοντος
Πρώτα, βεβαιωθείτε ότι έχετε ρυθμίσει το περιβάλλον ανάπτυξης C# με το Aspose.PDF για .NET. Προσθέστε την αναφορά στη βιβλιοθήκη και εισαγάγετε τους απαραίτητους χώρους ονομάτων.

## Βήμα 2: Φόρτωση του εγγράφου PDF
Σε αυτό το βήμα, φορτώνουμε το έγγραφο PDF από το καθορισμένο αρχείο.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Φροντίστε να αντικαταστήσετε τον "ΚΑΤΑΛΟΓΟ ΕΓΓΡΑΦΩΝ ΣΑΣ" με τον πραγματικό κατάλογο όπου βρίσκεται το αρχείο PDF σας.

## Βήμα 3: Εξαγωγή άκρων
Θα εξαγάγουμε το περίγραμμα από το έγγραφο PDF επαναλαμβάνοντας τις λειτουργίες που περιέχονται στο έγγραφο.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Επεξεργαστείτε όλες τις λειτουργίες περιεχομένου
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Ελέγξτε τον τύπο λειτουργίας
         // ...
         // Προσθέστε κώδικα για την επεξεργασία κάθε λειτουργίας
     }
}
```

 Δημιουργούμε α`graphicsState` στοίβα για αποθήκευση καταστάσεων γραφικών, μια εικόνα bitmap για την καταγραφή του εξαγόμενου περιγράμματος, α`GraphicsPath` αντικείμενο για αποθήκευση μονοπατιών σχεδίασης και άλλες μεταβλητές για παρακολούθηση κατάστασης και χρωμάτων.

## Βήμα 4: Επεξεργασία συναλλαγών
Σε αυτό το βήμα, επεξεργαζόμαστε κάθε λειτουργία του εγγράφου για να εξαγάγουμε το περίγραμμα.

```csharp
// Ελέγξτε τον τύπο λειτουργίας
if (opSaveState != null)
{
     // Αποθηκεύστε την προηγούμενη κατάσταση και σπρώξτε την τρέχουσα κατάσταση στην κορυφή της στοίβας
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Διαγράψτε την τρέχουσα κατάσταση και επαναφέρετε την προηγούμενη κατάσταση
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Ανακτήστε τον τρέχοντα πίνακα μετασχηματισμού
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Πολλαπλασιάστε τον τρέχοντα πίνακα με τον πίνακα καταστάσεων
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Ενημερώστε το τελευταίο σημείο σχεδίασης
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Επεξεργαστείτε το σχέδιο μιας γραμμής
     // ...
     // Προσθέστε κώδικα για να χειριστείτε το σχέδιο μιας γραμμής
}
// ...
// Προσθέστε άλλα αν μπλοκ για άλλες λειτουργίες
```

Ελέγχουμε τον τύπο της λειτουργίας χρησιμοποιώντας συνθήκες και εκτελούμε τον κατάλληλο κωδικό για κάθε λειτουργία.

## Βήμα 5: Δημιουργία αντιγράφων ασφαλείας εικόνας
Τέλος, αποθηκεύουμε την εικόνα bitmap που περιέχει το εξαγόμενο περίγραμμα σε ένα καθορισμένο αρχείο.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Βεβαιωθείτε ότι έχετε καθορίσει τον σωστό κατάλογο και όνομα αρχείου για να αποθηκεύσετε την εικόνα εξόδου.

### Παράδειγμα πηγαίου κώδικα για εξαγωγή περιγράμματος χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Η προεπιλεγμένη τιμή του πίνακα ctm είναι 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Σύστημα συντεταγμένων σχεδίασης βασίζεται πάνω αριστερά, ενώ το σύστημα συντεταγμένων pdf βασίζεται χαμηλά αριστερά, επομένως πρέπει να εφαρμόσουμε τον πίνακα αντιστροφής
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Επεξεργαστείτε όλες τις εντολές περιεχομένου
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Αποθηκεύστε την προηγούμενη κατάσταση και σπρώξτε την τρέχουσα κατάσταση στην κορυφή της στοίβας
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Πετάξτε την τρέχουσα κατάσταση και επαναφέρετε την προηγούμενη
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// Πολλαπλασιάστε τον τρέχοντα πίνακα με τον πίνακα καταστάσεων
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να εξαγάγουμε το περίγραμμα από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε αυτόν τον οδηγό βήμα προς βήμα για να εξαγάγετε περίγραμμα από άλλα έγγραφα PDF.

### Συχνές ερωτήσεις για εξαγωγή περιγράμματος σε αρχείο PDF

#### Ε: Ποιος είναι ο σκοπός της εξαγωγής του περιγράμματος από ένα αρχείο PDF;

Α: Η εξαγωγή του περιγράμματος από ένα αρχείο PDF μπορεί να είναι χρήσιμη για διάφορους σκοπούς. Σας επιτρέπει να απομονώνετε και να αναλύετε τα δομικά στοιχεία του εγγράφου, όπως πίνακες, διαγράμματα ή γραφικά στοιχεία. Μπορείτε να χρησιμοποιήσετε το εξαγόμενο περίγραμμα για να προσδιορίσετε τη διάταξη, τις διαστάσεις και τη θέση του περιεχομένου μέσα στο έγγραφο PDF.

#### Ε: Μπορώ να εξαγάγω το περίγραμμα από συγκεκριμένες σελίδες ή περιοχές εντός του εγγράφου PDF;

Α: Ναι, μπορείτε να τροποποιήσετε τον παρεχόμενο πηγαίο κώδικα C# για να εξαγάγετε το περίγραμμα από συγκεκριμένες σελίδες ή περιοχές εντός του εγγράφου PDF. Με το χειρισμό του`doc.Pages` συλλογή και καθορισμός προσαρμοσμένων κριτηρίων, μπορείτε να επιλέξετε να εξαγάγετε το περίγραμμα από συγκεκριμένες σελίδες ή περιοχές ενδιαφέροντος.

#### Ε: Πώς μπορώ να προσαρμόσω τη μορφή και την ποιότητα της εικόνας εξόδου;

 Α: Στον παρεχόμενο κώδικα C#, το εξαγόμενο περίγραμμα αποθηκεύεται ως εικόνα PNG. Εάν θέλετε να αλλάξετε τη μορφή εικόνας εξόδου, μπορείτε να τροποποιήσετε το`ImageFormat.Png` παράμετρος στο`bitmap.Save` μέθοδο σε άλλες υποστηριζόμενες μορφές εικόνας, όπως JPEG, BMP ή GIF. Επιπλέον, μπορείτε να προσαρμόσετε την ποιότητα της εικόνας ή τις ρυθμίσεις συμπίεσης με βάση τις απαιτήσεις σας.

#### Ε: Ποιες άλλες λειτουργίες μπορώ να εκτελέσω στο εξαγόμενο περίγραμμα;

Α: Αφού εξαγάγετε το περίγραμμα ως εικόνα, μπορείτε να το επεξεργαστείτε περαιτέρω χρησιμοποιώντας βιβλιοθήκες ή αλγόριθμους επεξεργασίας εικόνας. Μπορείτε να αναλύσετε την εικόνα, να εφαρμόσετε φίλτρα εικόνας, να εντοπίσετε μοτίβα ή να εκτελέσετε OCR (Optical Character Recognition) για να εξαγάγετε κείμενο από την εικόνα, εάν χρειάζεται.

#### Ε: Υπάρχουν περιορισμοί ή ζητήματα κατά την εξαγωγή περιγραμμάτων από πολύπλοκα έγγραφα PDF;

Α: Η διαδικασία εξαγωγής μπορεί να διαφέρει ανάλογα με την πολυπλοκότητα του εγγράφου PDF. Πολύπλοκα PDF με πολλαπλά επίπεδα, διαφάνεια ή προηγμένα γραφικά ενδέχεται να απαιτούν πρόσθετη επεξεργασία ή προσαρμογές για την ακριβή εξαγωγή του περιγράμματος. Είναι απαραίτητο να δοκιμάσετε διεξοδικά τη διαδικασία εξαγωγής σε διάφορα έγγραφα PDF για να διασφαλίσετε αξιόπιστα αποτελέσματα.