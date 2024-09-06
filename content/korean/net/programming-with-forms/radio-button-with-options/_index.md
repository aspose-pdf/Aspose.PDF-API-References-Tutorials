---
title: 옵션이 있는 라디오 버튼
linktitle: 옵션이 있는 라디오 버튼
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에 옵션이 있는 라디오 버튼을 쉽게 추가할 수 있습니다.
type: docs
weight: 230
url: /ko/net/programming-with-forms/radio-button-with-options/
---

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 옵션이 있는 라디오 버튼을 추가하는 방법을 보여드리겠습니다. 이 과정을 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 개체 인스턴스화

새 PDF 문서를 만들려면 Document 객체를 인스턴스화하세요.

```csharp
Document doc = new Document();
```

## 3단계: 페이지 및 표 추가

문서에 페이지를 추가하고 라디오 버튼 옵션을 보관할 테이블을 만듭니다.

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## 4단계: RadioButtonField 객체 인스턴스화

라디오 버튼을 나타내기 위해 RadioButtonField 객체를 인스턴스화합니다.

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## 5단계: 라디오 버튼 옵션 추가

RadioButtonField 객체에 라디오 버튼 옵션을 추가합니다.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## 6단계: 라디오 버튼 옵션 사용자 정의

테두리, 텍스트 색상, 캡션 텍스트 등의 속성을 설정하여 라디오 버튼 옵션을 사용자 정의합니다.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// opt2 및 opt3에 대해 동일한 단계를 반복합니다.

```

## 7단계: 라디오 버튼 옵션을 테이블에 추가합니다.

라디오 버튼 옵션을 표에 추가하여 표시합니다.

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## 8단계: PDF 문서 저장

생성된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 옵션이 있는 라디오 버튼에 대한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// PDF 파일을 저장하세요
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에 옵션이 있는 라디오 버튼을 성공적으로 추가했습니다. 이제 이 방법을 사용하여 PDF 문서에서 대화형 양식을 만들 수 있습니다.