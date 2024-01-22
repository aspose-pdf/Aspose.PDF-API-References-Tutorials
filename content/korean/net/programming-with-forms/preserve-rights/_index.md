---
title: 권리 보존
linktitle: 권리 보존
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서의 양식 권한을 보존하세요.
type: docs
weight: 210
url: /ko/net/programming-with-forms/preserve-rights/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 양식 권한을 유지하는 방법을 보여줍니다. 이 프로세스를 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉터리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 열기

 다음을 사용하여 소스 PDF 문서를 엽니다.`FileStream` 읽기 및 쓰기 권한이 있는 경우:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 3단계: 양식 필드 편집

문서의 모든 양식 필드를 살펴보고 필요한 사항을 변경합니다. 이 예에서는 이름에 "A1"이 있는 양식 필드의 값을 변경합니다.

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## 4단계: 업데이트된 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
pdfDocument.Save();
```

##  5단계: 닫기`FileStream`

 닫는 것을 잊지 마세요`FileStream` 완료되면 이의를 제기하세요.

```csharp
fs. Close();
```

### .NET용 Aspose.PDF를 사용하여 권리 보존을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 읽기 및 쓰기의 FileAccess를 사용하여 원본 PDF 양식을 읽습니다.
// 수정 후에는 ReadWrite 권한이 필요합니다.
// 업데이트된 내용을 동일한 문서/파일에 저장해야 합니다.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// 문서 인스턴스 인스턴스화
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// 모든 필드에서 값 가져오기
foreach (Field formField in pdfDocument.Form)
{
	// 필드의 전체 이름에 A1이 포함되어 있으면 작업을 수행합니다.
	if (formField.FullName.Contains("A1"))
	{
		// 양식 필드를 TextBox로 전송
		TextBoxField textBoxField = formField as TextBoxField;
		// 필드 값 수정
		textBoxField.Value = "Testing";
	}
}
// 업데이트된 문서를 save FileStream에 저장합니다.
pdfDocument.Save();
// 파일 스트림 개체를 닫습니다.
fs.Close();
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 양식의 권한을 보존하는 방법을 배웠습니다. 다음 단계를 수행하면 양식 필드에 쉽게 액세스하고 액세스 및 쓰기 권한을 유지하면서 특정 변경을 수행할 수 있습니다.


### FAQ

#### 질문: PDF 문서의 다른 항목에 영향을 주지 않고 특정 양식 필드의 권리를 보존할 수 있습니까?

 A: 네,`FullName` 양식 필드의 속성을 사용하여 다른 양식 필드는 영향을 받지 않고 보존할 특정 양식 필드를 지정할 수 있습니다.

#### 질문: 비밀번호로 보호된 PDF 문서에 있는 양식의 권한을 보존할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 파일에 액세스하고 수정하기 위해 올바른 비밀번호를 제공하는 한 비밀번호로 보호된 PDF 문서에서도 양식의 권한을 보존할 수 있습니다.

#### Q: 적절한 접근 권한 없이 양식 필드를 수정하려고 하면 어떻게 됩니까?

A: 적절한 액세스 권한 없이 양식 필드를 수정하려고 하면 변경 사항이 PDF 문서에 저장되지 않으며 예외 또는 오류 메시지가 나타날 수 있습니다.

#### Q: Aspose.PDF for .NET은 모든 버전의 .NET Framework와 호환됩니까?

A: 예, .NET용 Aspose.PDF는 .NET Core 및 .NET Standard를 포함한 모든 버전의 .NET Framework와 호환됩니다.

#### Q: C# 이외의 다른 프로그래밍 언어에서 프로그래밍 방식으로 PDF 문서의 양식 권한을 보존할 수 있습니까?

A: 예, Aspose.PDF for .NET은 C# 외에도 VB.NET, ASP.NET 등 다양한 프로그래밍 언어를 지원합니다.