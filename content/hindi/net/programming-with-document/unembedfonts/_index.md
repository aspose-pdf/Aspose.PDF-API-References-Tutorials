---
title: फ़ॉन्ट्स को अनएम्बेड करें और पीडीएफ फाइलों को अनुकूलित करें
linktitle: फ़ॉन्ट्स को अनएम्बेड करें और पीडीएफ फाइलों को अनुकूलित करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि .NET के लिए Aspose.PDF का उपयोग कैसे करें, ताकि फ़ॉन्ट्स को अनएम्बेड किया जा सके और PDF फ़ाइलों को ऑप्टिमाइज़ किया जा सके। चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 370
url: /hi/net/programming-with-document/unembedfonts/
---
.NET के लिए Aspose.PDF एक शक्तिशाली लाइब्रेरी है जो PDF दस्तावेज़ों के साथ काम करने के लिए कई तरह की सुविधाएँ प्रदान करती है। इसकी एक विशेषता PDF दस्तावेज़ से अनएम्बेड फ़ॉन्ट प्राप्त करना है। यह तब उपयोगी हो सकता है जब आपको PDF दस्तावेज़ से फ़ॉन्ट निकालने और उन्हें अन्य अनुप्रयोगों में उपयोग करने की आवश्यकता हो।

हम .NET के लिए Aspose.PDF की अनएम्बेड फ़ॉन्ट सुविधा के निम्नलिखित C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## चरण 1: दस्तावेज़ निर्देशिका का पथ सेट करें

शुरू करने से पहले, हमें उस निर्देशिका का पथ सेट करना होगा जहाँ हमारा PDF दस्तावेज़ स्थित है। हम इस पथ को "dataDir" नामक एक चर में संग्रहीत करेंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के वास्तविक पथ से बदलें जहां आपका PDF दस्तावेज़ स्थित है।

## चरण 2: पीडीएफ दस्तावेज़ खोलें

 पहला कदम पीडीएफ दस्तावेज़ को लोड करना है जिसे आप ऐसा करना चाहते हैं, इसका उपयोग करें`Document` .NET के लिए Aspose.PDF का क्लास। निम्न कोड स्निपेट दिखाता है कि PDF दस्तावेज़ को कैसे लोड किया जाए:

```csharp
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## चरण 3: अनएम्बेडफॉन्ट्स विकल्प सेट करें

 पीडीएफ दस्तावेज़ से अनएम्बेड फ़ॉन्ट प्राप्त करने के लिए, आपको सेट करना होगा`UnembedFonts` विकल्प`true` . यह विकल्प उपलब्ध है`OptimizationOptions` क्लास. निम्न कोड स्निपेट दिखाता है कि कैसे सेट किया जाए`UnembedFonts` विकल्प:

```csharp
// अनएम्बेडफॉन्ट्स विकल्प सेट करें
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## चरण 4: PDF दस्तावेज़ को अनुकूलित करें

 सेटिंग के बाद`UnembedFonts` विकल्प का उपयोग करके, आप पीडीएफ दस्तावेज़ को अनुकूलित कर सकते हैं`OptimizeResources` की विधि`Document` निम्न कोड स्निपेट दिखाता है कि PDF दस्तावेज़ को कैसे अनुकूलित किया जाए:

```csharp
// OptimizationOptions का उपयोग करके PDF दस्तावेज़ को अनुकूलित करें
pdfDocument.OptimizeResources(optimizeOptions);
```

## चरण 5: अपडेट किए गए दस्तावेज़ को सहेजें

 एक बार जब पीडीएफ दस्तावेज़ अनुकूलित हो जाता है, तो आप अद्यतन दस्तावेज़ को उपयोग करके सहेज सकते हैं`Save` की विधि`Document`class. निम्नलिखित कोड स्निपेट दिखाता है कि अपडेट किए गए दस्तावेज़ को कैसे सहेजना है:

```csharp
// अद्यतन दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## चरण 6: मूल और कम फ़ाइल आकार प्राप्त करें

 अंत में, आप पीडीएफ दस्तावेज़ का मूल और कम फ़ाइल आकार प्राप्त कर सकते हैं`FileInfo` System.IO का वर्ग। निम्न कोड स्निपेट दिखाता है कि मूल और कम फ़ाइल आकार कैसे प्राप्त करें:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### .NET के लिए Aspose.PDF का उपयोग करके अनएम्बेड फ़ॉन्ट प्राप्त करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ से अनएम्बेड फ़ॉन्ट प्राप्त करने के लिए पूर्ण उदाहरण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// अनएम्बेडफॉन्ट्स विकल्प सेट करें
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// OptimizationOptions का उपयोग करके PDF दस्तावेज़ को अनुकूलित करें
pdfDocument.OptimizeResources(optimizeOptions);
// अद्यतन दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने दिखाया कि PDF दस्तावेज़ से अनएम्बेड फ़ॉन्ट प्राप्त करने के लिए .NET के लिए Aspose.PDF का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से अपने C# अनुप्रयोगों में इस सुविधा को लागू कर सकते हैं। जब आपको निकाले गए फ़ॉन्ट के साथ अलग से काम करने की आवश्यकता होती है या विभिन्न प्लेटफ़ॉर्म पर लगातार फ़ॉन्ट उपयोग सुनिश्चित करने की आवश्यकता होती है, तो अनएम्बेडिंग फ़ॉन्ट फायदेमंद हो सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ से फ़ॉन्ट्स को अनएम्बेड करने का उद्देश्य क्या है?

उत्तर: PDF दस्तावेज़ से फ़ॉन्ट को अनएम्बेड करने से आप एम्बेड किए गए फ़ॉन्ट को निकाल सकते हैं और उन्हें अन्य अनुप्रयोगों में उपयोग कर सकते हैं। यह सुसंगत फ़ॉन्ट रेंडरिंग सुनिश्चित करने और दस्तावेज़ के दृश्य स्वरूप को संरक्षित करने के लिए उपयोगी हो सकता है।

#### प्रश्न: मैं C# कोड में दस्तावेज़ निर्देशिका का पथ कैसे निर्दिष्ट करूँ?

 A: दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करने के लिए, प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` कोड में उस निर्देशिका का वास्तविक पथ लिखें जहां आपका पीडीएफ दस्तावेज़ स्थित है।

####  प्रश्न: इसका क्या मतलब है?`UnembedFonts` option do, and where is it set?

 उत्तर:`UnembedFonts` विकल्प, उपलब्ध है`OptimizationOptions` क्लास, पीडीएफ दस्तावेज़ से फ़ॉन्ट को अनइम्बेड करने को सक्षम या अक्षम करता है। इस विकल्प को सेट करने के लिए`true`, निम्नलिखित कोड का उपयोग करें:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### प्रश्न: क्या मैं अनुकूलन प्रक्रिया के दौरान किए गए परिवर्तनों को पूर्ववत कर सकता हूँ?

उत्तर: .NET के लिए Aspose.PDF अनुकूलन के दौरान मूल PDF दस्तावेज़ में स्थायी परिवर्तन नहीं करता है। अनुकूलन प्रक्रिया दस्तावेज़ की एक प्रति पर की जाती है, जिससे मूल दस्तावेज़ बरकरार रहता है।

#### प्रश्न: मैं अनुकूलन के बाद मूल और कम किए गए फ़ाइल आकार की जांच कैसे कर सकता हूं?

 उत्तर: आप इसका उपयोग कर सकते हैं`FileInfo` की श्रेणी`System.IO` मूल और कम फ़ाइल आकार प्राप्त करने के लिए। इसे प्राप्त करने के लिए यहां एक उदाहरण कोड स्निपेट दिया गया है:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```