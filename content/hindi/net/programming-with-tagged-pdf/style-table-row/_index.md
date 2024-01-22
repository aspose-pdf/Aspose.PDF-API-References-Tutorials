---
title: शैली तालिका पंक्ति
linktitle: शैली तालिका पंक्ति
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: पंक्तियों को स्टाइल और फ़ॉर्मेट करने के लिए चरण-दर-चरण मार्गदर्शिका के लिए Aspose.PDF के साथ तालिका पंक्तियों को अनुकूलित करना सीखें।
type: docs
weight: 180
url: /hi/net/programming-with-tagged-pdf/style-table-row/
---
इस विस्तृत ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्ति को प्रारूपित करने के लिए चरण दर चरण दिए गए C# स्रोत कोड के बारे में बताएंगे। तालिका पंक्ति शैलियों और गुणों को अनुकूलित करने का तरीका समझने के लिए नीचे दिए गए निर्देशों का पालन करें।

## चरण 1: वातावरण स्थापित करना

शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपने विकास परिवेश को कॉन्फ़िगर कर लिया है। इसमें Aspose.PDF लाइब्रेरी स्थापित करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

## चरण 2: एक दस्तावेज़ बनाना

इस चरण में, हम एक नया दस्तावेज़ ऑब्जेक्ट Aspose.PDF बनाएंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

हमने एक नया दस्तावेज़ बनाया है और दस्तावेज़ का शीर्षक और भाषा निर्धारित की है।

## चरण 3: मूल संरचना तत्व प्राप्त करना

इस चरण में हम अपने दस्तावेज़ के लिए मूल संरचना तत्व प्राप्त करेंगे।

```csharp
//मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
```

हमें मूल संरचना तत्व मिला जो सरणी तत्व के लिए एक कंटेनर के रूप में काम करेगा।

## चरण 4: सरणी संरचना तत्व बनाना

आइए अब अपने दस्तावेज़ के लिए एक नया तालिका संरचना तत्व बनाएं।

```csharp
// सरणी संरचना तत्व बनाएं
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

हमने एक नया ऐरे स्ट्रक्चर एलिमेंट बनाया है और इसे रूट स्ट्रक्चर एलिमेंट में जोड़ा है।

## चरण 5: तालिका पंक्ति शैलियों और गुणों को अनुकूलित करें

इस चरण में, हम तालिका पंक्ति शैलियों और गुणों को अनुकूलित करेंगे।

```csharp
// तालिका पंक्ति शैलियों और गुणों को अनुकूलित करें
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// टेबल हेडर पंक्ति बनाएं
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// तालिका के मुख्य भाग की पंक्तियों को अनुकूलित करें
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// तालिका की पादलेख पंक्ति बनाएँ
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

हमने तालिका पंक्ति के विभिन्न पहलुओं को अनुकूलित किया है, जैसे पृष्ठभूमि रंग, सीमाएँ, पंक्ति की ऊँचाई, पृष्ठांकन, डिफ़ॉल्ट सेल शैली, और बहुत कुछ।

## चरण 6: टैग किए गए पीडीएफ दस्तावेज़ को सहेजना

अब जब हमने अपना दस्तावेज़ स्टाइल तालिका पंक्ति के साथ बना लिया है, तो हम इसे टैग किए गए पीडीएफ दस्तावेज़ के रूप में सहेजेंगे।
```csharp
// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableRow.pdf");
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजा है।

## चरण 7: पीडीएफ/यूए अनुपालन सत्यापन

इसके बाद, हम अपने दस्तावेज़ की पीडीएफ/यूए अनुरूपता को सत्यापित करेंगे।

```csharp
// पीडीएफ/यूए अनुपालन जांच
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को अपलोड किया और एक एक्सएमएल रिपोर्ट तैयार करके इसके पीडीएफ/यूए अनुपालन को मान्य किया।


### .NET के लिए Aspose.PDF का उपयोग करके स्टाइल टेबल पंक्ति के लिए नमूना स्रोत कोड 
```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// जड़ संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// तालिका संरचना तत्व बनाएं
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// टैग किए गए पीडीएफ दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableRow.pdf");

// पीडीएफ/यूए अनुपालन की जाँच करना
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF के साथ तालिका पंक्ति को कैसे प्रारूपित किया जाए। हमने तालिका पंक्ति शैलियों और गुणों को अनुकूलित किया, शीर्षलेख, मुख्य पंक्तियाँ और पाद लेख जोड़े, टैग किए गए पीडीएफ दस्तावेज़ को सहेजा, और इसके पीडीएफ/यूए अनुपालन को सत्यापित किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्तियों को फ़ॉर्मेट करने पर इस ट्यूटोरियल का उद्देश्य क्या है?

उ: इस ट्यूटोरियल का उद्देश्य .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ दस्तावेज़ में तालिका पंक्तियों को स्वरूपित करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। यह तालिका पंक्ति शैलियों और गुणों को अनुकूलित करने में आपकी सहायता के लिए चरण-दर-चरण निर्देश और C# स्रोत कोड उदाहरण प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए आवश्यक शर्तें क्या हैं?

उ: शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपना विकास वातावरण स्थापित कर लिया है। इसमें Aspose.PDF लाइब्रेरी को स्थापित करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक नया PDF दस्तावेज़ कैसे बना सकता हूँ और उसका शीर्षक और भाषा कैसे सेट कर सकता हूँ?

 उ: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, आपको एक बनाना होगा`Document` Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। ट्यूटोरियल में प्रदान किया गया C# स्रोत कोड दर्शाता है कि दस्तावेज़ कैसे बनाएं और उसका शीर्षक और भाषा गुण कैसे सेट करें।

#### प्रश्न: पीडीएफ दस्तावेज़ में मूल संरचना तत्व का क्या महत्व है?

ए: मूल संरचना तत्व अन्य संरचना तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जो पीडीएफ दस्तावेज़ की सामग्री को व्यवस्थित और वर्गीकृत करने में मदद करता है। यह दस्तावेज़ की तार्किक संरचना स्थापित करने में महत्वपूर्ण भूमिका निभाता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके तालिका पंक्तियों को प्रारूपित करने के लिए तालिका संरचना तत्व कैसे बना और अनुकूलित कर सकता हूं?

उ: ट्यूटोरियल बताता है कि तालिका संरचना तत्व कैसे बनाएं और तालिका पंक्तियों को प्रारूपित करने के लिए उसके गुणों को कैसे अनुकूलित करें। इसमें पृष्ठभूमि रंग, सीमाएँ, पंक्ति ऊँचाई, पृष्ठांकन, डिफ़ॉल्ट सेल शैली और बहुत कुछ जैसे पहलू शामिल हैं।

#### प्रश्न: क्या मैं तालिका पंक्ति के भीतर अलग-अलग सेल की शैलियों और गुणों को अनुकूलित कर सकता हूँ?

उ: हाँ, आप तालिका पंक्ति के भीतर अलग-अलग कक्षों की शैलियों और गुणों को अनुकूलित कर सकते हैं। ट्यूटोरियल दर्शाता है कि स्वरूपित तालिका पंक्ति के भीतर तालिका कक्षों के लिए पृष्ठभूमि रंग, सीमाएँ, पाठ रंग, पैडिंग और अधिक जैसे गुणों को कैसे सेट किया जाए।

#### प्रश्न: मैं स्वरूपित तालिका पंक्ति में शीर्षलेख, मुख्य पंक्तियाँ और पादलेख कैसे जोड़ सकता हूँ?

उ: ट्यूटोरियल तालिका संरचना तत्व में हेडर, बॉडी पंक्तियाँ और पाद लेख बनाने और जोड़ने के उदाहरण प्रदान करता है। ट्यूटोरियल में वर्णित गुणों का उपयोग करके इन तत्वों को और अधिक अनुकूलित किया जा सकता है।

#### प्रश्न: पीडीएफ/यूए अनुपालन क्या है, और मैं इसे अपने टैग किए गए पीडीएफ दस्तावेज़ के लिए कैसे मान्य कर सकता हूं?

 उत्तर: पीडीएफ/यूए अनुपालन यह सुनिश्चित करता है कि पीडीएफ दस्तावेज़ पहुंच मानकों के अनुरूप है, जिससे यह विकलांग उपयोगकर्ताओं के लिए अधिक सुलभ हो जाता है। ट्यूटोरियल दर्शाता है कि इसका उपयोग करके पीडीएफ/यूए अनुरूपता को कैसे मान्य किया जाए`Validate()` विधि और एक XML अनुपालन रिपोर्ट तैयार करें।

#### प्रश्न: मैं इन अवधारणाओं को अपने .NET अनुप्रयोगों में कैसे शामिल कर सकता हूं?

उ: आप अपने स्वयं के .NET अनुप्रयोगों में तालिका पंक्ति स्वरूपण को लागू करने के लिए एक गाइड के रूप में दिए गए C# स्रोत कोड उदाहरणों का उपयोग कर सकते हैं। अपनी आवश्यकताओं से मेल खाने के लिए कोड को संशोधित और अनुकूलित करें और इसे अपनी परियोजनाओं में एकीकृत करें।

#### प्रश्न: क्या पीडीएफ दस्तावेजों में तालिका पंक्तियों को प्रारूपित करने के लिए कोई अनुशंसित सर्वोत्तम अभ्यास हैं?

उ: तालिका पंक्तियों को स्वरूपित करते समय, सामग्री की पठनीयता और पहुंच पर विचार करें। सुनिश्चित करें कि रंगों में पर्याप्त कंट्रास्ट हो, स्पष्ट और सुपाठ्य फ़ॉन्ट का उपयोग करें और एक सुसंगत लेआउट बनाए रखें। सुगम्यता मानकों को पूरा करना सुनिश्चित करने के लिए पीडीएफ/यूए अनुपालन को मान्य करें।

#### प्रश्न: पीडीएफ दस्तावेज़ अनुकूलन के लिए मैं .NET के लिए Aspose.PDF की अन्य कौन सी विशेषताओं का पता लगा सकता हूँ?

उ: .NET के लिए Aspose.PDF पीडीएफ दस्तावेज़ अनुकूलन के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें टेक्स्ट हेरफेर, छवि प्रविष्टि, फॉर्म फ़ील्ड प्रबंधन, डिजिटल हस्ताक्षर, एनोटेशन और बहुत कुछ शामिल है। अतिरिक्त कार्यक्षमताओं का पता लगाने के लिए आधिकारिक दस्तावेज़ीकरण और संसाधनों से परामर्श लें।