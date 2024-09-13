---
title: पीडीएफ फाइल में डेटाबेस के साथ एकीकृत करें
linktitle: पीडीएफ फाइल में डेटाबेस के साथ एकीकृत करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके डेटाबेस से डेटा को PDF फ़ाइल में एम्बेड करें।
type: docs
weight: 120
url: /hi/net/programming-with-tables/integrate-with-database/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में डेटाबेस से डेटा कैसे एम्बेड करें। हम C# में सोर्स कोड को चरण दर चरण समझाएँगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि डेटाबेस से टेबल डेटा को PDF दस्तावेज़ में कैसे आयात किया जाता है। चलिए शुरू करते हैं!

## चरण 1: वातावरण की स्थापना
सुनिश्चित करें कि आपने .NET के लिए Aspose.PDF के साथ अपना C# डेवलपमेंट एनवायरनमेंट कॉन्फ़िगर किया है। लाइब्रेरी में संदर्भ जोड़ें और आवश्यक नेमस्पेस आयात करें।

## चरण 2: डेटाटेबल बनाना
हम PDF दस्तावेज़ में एम्बेड किए जाने वाले डेटा को दर्शाने के लिए DataTable का एक उदाहरण बनाते हैं। इस उदाहरण में, हम तीन कॉलम के साथ एक DataTable बनाते हैं: Employee_ID, Employee_Name, और Gender। हम डमी डेटा के साथ DataTable में दो पंक्तियाँ भी जोड़ते हैं।

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## चरण 3: पीडीएफ दस्तावेज़ और तालिका बनाना
हम डॉक्यूमेंट का एक इंस्टेंस बनाते हैं और इस डॉक्यूमेंट में एक पेज जोड़ते हैं। इसके बाद, हम PDF डॉक्यूमेंट में अपनी टेबल को दर्शाने के लिए टेबल इंस्टेंस बनाते हैं। हम टेबल कॉलम की चौड़ाई और बॉर्डर स्टाइल को परिभाषित करते हैं।

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## चरण 4: डेटाटेबल से तालिका में डेटा आयात करना
हम DataTable से डेटा को PDF दस्तावेज़ में तालिका में आयात करने के लिए ImportDataTable विधि का उपयोग करते हैं।

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## चरण 5: दस्तावेज़ में तालिका जोड़ना
हम दस्तावेज़ पृष्ठ के पैराग्राफ़ संग्रह में तालिका जोड़ते हैं।

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## चरण 6: दस्तावेज़ सहेजें
हम एम्बेडेड डेटाबेस से डेटा के साथ पीडीएफ दस्तावेज़ को सहेजते हैं।

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

बधाई हो! अब आप जानते हैं कि .NET के लिए Aspose.PDF का उपयोग करके डेटाबेस डेटा को PDF दस्तावेज़ में कैसे एम्बेड किया जाता है।

### .NET के लिए Aspose.PDF का उपयोग करके डेटाबेस के साथ एकीकृत करने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//DataTable ऑब्जेक्ट में प्रोग्रामेटिक रूप से 2 पंक्तियाँ जोड़ें
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// दस्तावेज़ उदाहरण बनाएँ
Document doc = new Document();
doc.Pages.Add();
// तालिका का एक नया उदाहरण आरंभ करता है
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// तालिका की स्तंभ चौड़ाई निर्धारित करें
table.ColumnWidths = "40 100 100 100";
// टेबल बॉर्डर का रंग हल्का ग्रे पर सेट करें
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// तालिका कक्षों के लिए बॉर्डर सेट करें
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// इनपुट दस्तावेज़ के प्रथम पृष्ठ पर तालिका ऑब्जेक्ट जोड़ें
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// तालिका ऑब्जेक्ट युक्त अद्यतन दस्तावेज़ सहेजें
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.PDF का उपयोग करके डेटाबेस से डेटा को PDF दस्तावेज़ में कैसे एम्बेड किया जाए। आप अपने स्वयं के डेटाबेस से डेटा आयात करने और उन्हें PDF दस्तावेज़ों में प्रदर्शित करने के लिए इस चरण-दर-चरण मार्गदर्शिका का उपयोग कर सकते हैं। इस शक्तिशाली लाइब्रेरी द्वारा प्रदान की जाने वाली अन्य सुविधाओं और संभावनाओं को जानने के लिए Aspose.PDF दस्तावेज़ को और अधिक देखें।

### पीडीएफ फाइल में डेटाबेस के साथ एकीकृत करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं MySQL, SQL Server, या Oracle जैसे विभिन्न डेटाबेस प्रकारों के साथ .NET के लिए Aspose.PDF का उपयोग कर सकता हूँ?

उत्तर: हाँ, आप MySQL, SQL Server, Oracle, और अन्य जैसे विभिन्न डेटाबेस प्रकारों के साथ .NET के लिए Aspose.PDF का उपयोग कर सकते हैं। .NET के लिए Aspose.PDF डेटाबेस, XML फ़ाइलें, और अधिक सहित विभिन्न डेटा स्रोतों से डेटा पढ़ने के लिए कार्यक्षमता प्रदान करता है। आप अपने इच्छित डेटाबेस प्रकार से डेटा प्राप्त कर सकते हैं और इसे DataTable या किसी अन्य डेटा संरचना में पॉप्युलेट कर सकते हैं जो .NET के लिए Aspose.PDF के साथ संगत है।

#### प्रश्न: मैं पीडीएफ दस्तावेज़ में तालिका के स्वरूप को कैसे अनुकूलित कर सकता हूं?

उत्तर: आप .NET लाइब्रेरी के लिए Aspose.PDF द्वारा प्रदान किए गए विभिन्न गुणों का उपयोग करके PDF दस्तावेज़ में तालिका की उपस्थिति को अनुकूलित कर सकते हैं। उदाहरण के लिए, आप तालिका और उसके कक्षों के लिए अलग-अलग बॉर्डर शैलियाँ, पृष्ठभूमि रंग, फ़ॉन्ट शैलियाँ और संरेखण सेट कर सकते हैं। तालिका की उपस्थिति को अनुकूलित करने के बारे में अधिक जानकारी के लिए .NET दस्तावेज़ के लिए Aspose.PDF देखें।

#### प्रश्न: क्या डेटाबेस से आयातित डेटा में हाइपरलिंक या इंटरैक्टिव तत्व जोड़ना संभव है?

उत्तर: हाँ, आप डेटाबेस से आयात किए गए डेटा में हाइपरलिंक या अन्य इंटरैक्टिव तत्व जोड़ सकते हैं। .NET के लिए Aspose.PDF PDF दस्तावेज़ में हाइपरलिंक, बुकमार्क और अन्य इंटरैक्टिव तत्व जोड़ने का समर्थन करता है। आप तालिका में आयात करने से पहले DataTable में सामग्री में हेरफेर कर सकते हैं और हाइपरलिंक या अन्य इंटरैक्टिव सुविधाएँ शामिल कर सकते हैं।

#### प्रश्न: यदि तालिका में पंक्तियों की संख्या एक निश्चित संख्या से अधिक हो तो क्या मैं तालिका को पृष्ठांकित कर सकता हूँ?

उत्तर: हां, यदि तालिका में पंक्तियों की संख्या एक निश्चित संख्या से अधिक है, तो आप उसे पृष्ठांकित कर सकते हैं। ऐसा करने के लिए, आप इसका उपयोग कर सकते हैं`IsInNewPage` पंक्ति ऑब्जेक्ट की प्रॉपर्टी यह इंगित करने के लिए कि एक नया पेज किसी विशिष्ट पंक्ति के बाद शुरू होना चाहिए। आप प्रति पृष्ठ प्रदर्शित करने के लिए पंक्तियों की संख्या की गणना कर सकते हैं और सेट कर सकते हैं`IsInNewPage` संपत्ति तदनुसार.

#### प्रश्न: मैं एम्बेडेड डेटाबेस डेटा वाले PDF दस्तावेज़ को DOCX या XLSX जैसे विभिन्न फ़ाइल स्वरूपों में कैसे निर्यात कर सकता हूँ?

उत्तर: .NET के लिए Aspose.PDF आपको PDF दस्तावेज़ों को DOCX (Microsoft Word) और XLSX (Microsoft Excel) सहित विभिन्न अन्य फ़ाइल स्वरूपों में बदलने की अनुमति देता है। आप इसे प्राप्त करने के लिए Aspose.Words और Aspose.Cells जैसी अन्य Aspose लाइब्रेरी के साथ संयोजन में .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग कर सकते हैं। सबसे पहले, एम्बेडेड डेटाबेस डेटा के साथ PDF दस्तावेज़ को सहेजें, और फिर इसे अपने इच्छित फ़ाइल स्वरूप में बदलने के लिए संबंधित Aspose लाइब्रेरी का उपयोग करें।