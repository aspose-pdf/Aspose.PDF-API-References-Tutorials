---
title: शैली तालिका तत्व
linktitle: शैली तालिका तत्व
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ टेबल एलिमेंट को फ़ॉर्मेट करना सीखें। स्टाइल और प्रॉपर्टी को कस्टमाइज़ करने के लिए चरण-दर-चरण गाइड।
type: docs
weight: 170
url: /hi/net/programming-with-tagged-pdf/style-table-element/
---
इस विस्तृत ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके सरणी तत्व को फ़ॉर्मेट करने के लिए दिए गए C# स्रोत कोड के माध्यम से चरण दर चरण मार्गदर्शन करेंगे। सरणी तत्व की शैलियों और गुणों को अनुकूलित करने का तरीका समझने के लिए नीचे दिए गए निर्देशों का पालन करें।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपने विकास परिवेश को कॉन्फ़िगर किया है। इसमें Aspose.PDF लाइब्रेरी को इंस्टॉल करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

## चरण 2: दस्तावेज़ बनाना

इस चरण में, हम एक नया दस्तावेज़ ऑब्जेक्ट Aspose.PDF बनाएंगे।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ निर्माण
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

हमने एक नया दस्तावेज़ बनाया है और दस्तावेज़ का शीर्षक और भाषा निर्धारित की है।

## चरण 3: मूल संरचना तत्व प्राप्त करना

इस चरण में हम अपने दस्तावेज़ के लिए मूल संरचना तत्व प्राप्त करेंगे।

```csharp
//मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;
```

हमें मूल संरचना तत्व मिल गया है जो सरणी तत्व के लिए कंटेनर के रूप में काम करेगा।

## चरण 4: सरणी संरचना तत्व बनाना

अब आइए अपने दस्तावेज़ के लिए एक नया तालिका संरचना तत्व बनाएं।

```csharp
// सरणी संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

हमने एक नया ऐरे संरचना तत्व बनाया है और इसे मूल संरचना तत्व में जोड़ दिया है।

## चरण 5: ऐरे तत्व शैलियों और गुणों को अनुकूलित करना

इस चरण में, हम सरणी तत्व की शैलियों और गुणों को अनुकूलित करेंगे।

```csharp
// सरणी तत्व की शैलियों और गुणों को अनुकूलित करें
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// दोहराई गई पंक्तियों की शैली को अनुकूलित करें
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

हमने तालिका तत्व को अनुकूलित करने के लिए विभिन्न गुणों का उपयोग किया, जैसे पृष्ठभूमि रंग, बॉर्डर, संरेखण, डिफ़ॉल्ट सेल शैली, मार्जिन, कॉलम चौड़ाई, आदि।

## चरण 6: तालिका शीर्षलेख, मुख्य भाग और पादलेख जोड़ें

अब आइए टेबल तत्व में टेबल हेडर, बॉडी और फ़ूटर जोड़ें।
```csharp
// तालिका शीर्षलेख जोड़ें
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// तालिका में पंक्तियों और स्तंभों की संख्या
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// तालिका शीर्ष पंक्ति बनाएँ
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//तालिका मुख्य भाग की पंक्तियाँ जोड़ें
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// टेबल की फ़ुटिंग लाइन जोड़ें
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

हमने संबंधित तत्वों का उपयोग करके तालिका में शीर्षलेख, मुख्य पंक्तियाँ और पादलेख पंक्तियाँ जोड़ीं।

## चरण 7: टैग किए गए PDF दस्तावेज़ को सहेजना

अब जबकि हमने स्टाइल्ड टेबल तत्व के साथ अपना दस्तावेज़ बना लिया है, हम इसे टैग किए गए पीडीएफ दस्तावेज़ के रूप में सहेजेंगे।

```csharp
// टैग किए गए PDF दस्तावेज़ को सहेजें
document.Save(dataDir + "StyleTableElement.pdf");
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेज लिया।

## चरण 8: PDF/UA अनुपालन सत्यापन

इसके बाद, हम अपने दस्तावेज़ की PDF/UA अनुरूपता की पुष्टि करेंगे।

```csharp
// पीडीएफ/यूए अनुपालन जांच
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

हमने टैग किए गए पीडीएफ दस्तावेज़ को अपलोड किया और एक XML रिपोर्ट तैयार करके इसकी पीडीएफ/यूए अनुपालना की पुष्टि की।

### .NET के लिए Aspose.PDF का उपयोग करके स्टाइल टेबल तत्व के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// दस्तावेज़ बनाएँ
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// मूल संरचना तत्व प्राप्त करें
StructureElement rootElement = taggedContent.RootElement;

// तालिका संरचना तत्व बनाएँ
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
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

// टैग किए गए पीडीएफ दस्तावेज़ सहेजें
document.Save(dataDir + "StyleTableElement.pdf");

// PDF/UA अनुपालन की जाँच करना
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF के साथ ऐरे एलिमेंट को कैसे फ़ॉर्मेट किया जाए। हमने टेबल एलिमेंट की शैलियों और गुणों को अनुकूलित किया, हेडर, बॉडी रो और फ़ुटर जोड़े, टैग किए गए PDF दस्तावेज़ को सहेजा और इसके PDF/UA अनुपालन को मान्य किया।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF का उपयोग करके सरणी तत्व को फ़ॉर्मेट करने पर इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: इस ट्यूटोरियल का लक्ष्य आपको .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में ऐरे एलिमेंट को फ़ॉर्मेट करने की प्रक्रिया के माध्यम से मार्गदर्शन करना है। यह आपको ऐरे एलिमेंट की शैलियों और गुणों को अनुकूलित करने में मदद करने के लिए चरण-दर-चरण निर्देश और C# स्रोत कोड उदाहरण प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल का अनुसरण करने के लिए पूर्वापेक्षाएँ क्या हैं?

उत्तर: शुरू करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF का उपयोग करने के लिए अपना डेवलपमेंट वातावरण सेट अप कर लिया है। इसमें Aspose.PDF लाइब्रेरी को इंस्टॉल करना और इसे संदर्भित करने के लिए अपने प्रोजेक्ट को कॉन्फ़िगर करना शामिल है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक नया PDF दस्तावेज़ कैसे बना सकता हूं और उसका शीर्षक और भाषा कैसे सेट कर सकता हूं?

 उत्तर: एक नया पीडीएफ दस्तावेज़ बनाने के लिए, आपको एक बनाना होगा`Document` Aspose.PDF लाइब्रेरी से ऑब्जेक्ट। ट्यूटोरियल द्वारा प्रदान किया गया C# स्रोत कोड दर्शाता है कि दस्तावेज़ कैसे बनाया जाता है और उसका शीर्षक और भाषा गुण कैसे सेट किया जाता है।

#### प्रश्न: पीडीएफ दस्तावेज़ में मूल संरचना तत्व का क्या महत्व है?

उत्तर: मूल संरचना तत्व अन्य संरचना तत्वों के लिए एक कंटेनर के रूप में कार्य करता है, जो पीडीएफ दस्तावेज़ की सामग्री को व्यवस्थित और वर्गीकृत करने में मदद करता है। यह दस्तावेज़ की तार्किक संरचना स्थापित करने में महत्वपूर्ण भूमिका निभाता है।

#### प्रश्न: मैं .NET के लिए Aspose.PDF का उपयोग करके एक सरणी संरचना तत्व कैसे बनाऊं और अनुकूलित करूं?

 उत्तर: आप इसका उपयोग करके एक सरणी संरचना तत्व बना सकते हैं`CreateTableElement()` विधि। ट्यूटोरियल का स्रोत कोड तालिका तत्व के विभिन्न गुणों को अनुकूलित करने के उदाहरण प्रदान करता है, जैसे पृष्ठभूमि रंग, सीमाएं, संरेखण, स्तंभ चौड़ाई, और अधिक।

#### प्रश्न: क्या मैं सारणी तत्व के भीतर तालिका कक्षों की शैलियों और गुणों को अनुकूलित कर सकता हूँ?

उत्तर: हां, ट्यूटोरियल में बताया गया है कि हेडर, बॉडी रो और फ़ुटर सहित पूरे टेबल एलिमेंट की स्टाइल और प्रॉपर्टी को कैसे कस्टमाइज़ किया जाए। हालाँकि, यह विशेष रूप से अलग-अलग टेबल सेल को कस्टमाइज़ करने के बारे में नहीं बताता है।

#### प्रश्न: मैं तालिका तत्व में हेडर, बॉडी पंक्तियाँ और फ़ुटर कैसे जोड़ सकता हूँ?

उत्तर: ट्यूटोरियल बताता है कि .NET के लिए Aspose.PDF द्वारा प्रदान की गई उचित विधियों का उपयोग करके तालिका तत्व में हेडर, बॉडी रो और फ़ुटर कैसे बनाएं और जोड़ें।

#### प्रश्न: PDF/UA अनुपालन क्या है, और मैं अपने टैग किए गए PDF दस्तावेज़ के लिए इसे कैसे सत्यापित कर सकता हूं?

 उत्तर: PDF/UA अनुपालन सुनिश्चित करता है कि PDF दस्तावेज़ पहुँच मानकों के अनुरूप है, जिससे यह विकलांग उपयोगकर्ताओं के लिए अधिक सुलभ हो जाता है। ट्यूटोरियल दर्शाता है कि PDF/UA अनुरूपता को सत्यापित करने के लिए किस प्रकार का उपयोग किया जाता है`Validate()` विधि का उपयोग करें और एक XML अनुपालन रिपोर्ट तैयार करें।

#### प्रश्न: मैं इन अवधारणाओं को अपने .NET अनुप्रयोगों में कैसे शामिल कर सकता हूं?

उत्तर: आप अपने स्वयं के .NET अनुप्रयोगों में सरणी तत्व स्वरूपण को लागू करने के लिए दिए गए C# स्रोत कोड उदाहरणों का उपयोग एक गाइड के रूप में कर सकते हैं। अपनी आवश्यकताओं से मेल खाने के लिए कोड को संशोधित और अनुकूलित करें और इसे अपनी परियोजनाओं में एकीकृत करें।

#### प्रश्न: क्या पीडीएफ दस्तावेजों में सारणी तत्वों को प्रारूपित करने के लिए कोई अनुशंसित सर्वोत्तम अभ्यास हैं?

उत्तर: सारणी तत्वों (तालिकाओं) को फ़ॉर्मेट करते समय, सामग्री की पठनीयता और पहुँच-योग्यता पर विचार करें। स्पष्ट और सुपाठ्य फ़ॉन्ट, उपयुक्त रंगों का उपयोग करें और एक सुसंगत लेआउट बनाए रखें। पहुँच-योग्यता मानकों को पूरा करने के लिए PDF/UA अनुपालन को सत्यापित करें।

#### प्रश्न: PDF दस्तावेज़ अनुकूलन के लिए मैं .NET के लिए Aspose.PDF की अन्य कौन सी विशेषताएं खोज सकता हूं?

उत्तर: .NET के लिए Aspose.PDF पीडीएफ दस्तावेज़ अनुकूलन के लिए कई सुविधाएँ प्रदान करता है, जिसमें टेक्स्ट हेरफेर, छवि प्रविष्टि, फ़ॉर्म फ़ील्ड प्रबंधन, डिजिटल हस्ताक्षर, एनोटेशन और बहुत कुछ शामिल है। अतिरिक्त कार्यक्षमताओं का पता लगाने के लिए आधिकारिक दस्तावेज़ और संसाधनों से परामर्श करें।