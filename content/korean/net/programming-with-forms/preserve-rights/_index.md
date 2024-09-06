---
title: 권리 보존
linktitle: 권리 보존
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 양식 권한을 보존하세요.
type: docs
weight: 210
url: /ko/net/programming-with-forms/preserve-rights/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 양식 권한을 보존하는 방법을 보여드리겠습니다. 이 과정을 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉토리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 열기

 다음을 사용하여 소스 PDF 문서를 엽니다.`FileStream` 읽기 및 쓰기 권한이 있음:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 3단계: 양식 필드 편집

문서의 모든 양식 필드를 살펴보고 필요한 변경을 합니다. 이 예에서는 이름에 "A1"이 있는 양식 필드의 값을 변경합니다.

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

 닫는 것을 잊지 마세요`FileStream` 완료되면 객체를 지정합니다.

```csharp
fs. Close();
```

### .NET용 Aspose.PDF를 사용하여 Preserve Rights를 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// FileAccess의 Read 및 Write로 소스 PDF 양식을 읽습니다.
// 수정 후에는 ReadWrite 권한이 필요합니다.
// 업데이트된 내용을 동일한 문서/파일에 저장해야 합니다.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// 문서 인스턴스화
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// 모든 필드에서 값 가져오기
foreach (Field formField in pdfDocument.Form)
{
	// 필드의 전체 이름에 A1이 포함되어 있는 경우 다음 작업을 수행합니다.
	if (formField.FullName.Contains("A1"))
	{
		// 텍스트 상자로 캐스트 폼 필드
		TextBoxField textBoxField = formField as TextBoxField;
		// 필드 값 수정
		textBoxField.Value = "Testing";
	}
}
// 업데이트된 문서를 save FileStream에 저장합니다.
pdfDocument.Save();
// 파일 스트림 객체를 닫습니다.
fs.Close();
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 양식의 권한을 보존하는 방법을 알아보았습니다. 이러한 단계를 따르면 양식 필드에 쉽게 액세스하고 액세스 및 쓰기 권한을 보존하면서 특정 변경을 할 수 있습니다.


### 자주 묻는 질문

#### 질문: PDF 문서의 다른 양식 필드에 영향을 주지 않고 특정 양식 필드의 권한만 보존할 수 있나요?

 A: 네, 다음을 사용하여`FullName` 양식 필드의 속성을 사용하면 다른 양식 필드에는 영향을 주지 않고 특정 양식 필드만 보존할 수 있습니다.

#### 질문: 암호로 보호된 PDF 문서에서 양식의 권리를 보존할 수 있나요?

답변: 네, Aspose.PDF for .NET을 사용하면 암호로 보호된 PDF 문서에서도 양식의 권한을 보존할 수 있습니다. 단, 파일에 액세스하고 수정하기 위한 올바른 암호를 제공해야 합니다.

#### 질문: 적절한 접근 권한 없이 양식 필드를 수정하려고 하면 어떻게 되나요?

답변: 적절한 접근 권한 없이 양식 필드를 수정하려고 하면 변경 사항이 PDF 문서에 저장되지 않으며, 예외나 오류 메시지가 나타날 수 있습니다.

#### 질문: Aspose.PDF for .NET은 모든 버전의 .NET Framework와 호환됩니까?

답변: 네, Aspose.PDF for .NET은 .NET Core 및 .NET Standard를 포함한 모든 버전의 .NET Framework와 호환됩니다.

#### 질문: C# 외의 다른 프로그래밍 언어로 PDF 문서의 양식 권한을 프로그래밍 방식으로 보존할 수 있습니까?

답변: 네, Aspose.PDF for .NET은 C# 외에도 VB.NET, ASP.NET 등 다양한 프로그래밍 언어를 지원합니다.