---
title: Use Latex Script 3
linktitle: Use Latex Script 3
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 570
url: /net/programming-with-text/use-latex-script-3/
---
### Sample source code for Use Latex Script 3 using Aspose.PDF for .NET 
```csharp
            var dataDir = "YOUR DOCUMENT DIRECTORY";
            var s = @"
            \usepackage{amsmath,amsthm}
            \begin{document}
            \begin{proof} The proof is a follows: 
            \begin{align}
            (x+y)^3&=(x+y)(x+y)^2
            (x+y)(x^2+2xy+y^2)\\
            &=x^3+3x^2y+3xy^3+x^3.\qedhere
            \end{align}
            \end{proof}
            \end{document}";
            var doc = new Document();
            var page = doc.Pages.Add();
            var latex = new LatexFragment(s);
            page.Paragraphs.Add(latex);
            doc.Save(dataDir + "Script_out.pdf");
```