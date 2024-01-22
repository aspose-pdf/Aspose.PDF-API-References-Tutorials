---
title: 양식 필드 이동
linktitle: 양식 필드 이동
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 양식 필드를 쉽게 이동할 수 있습니다.
type: docs
weight: 200
url: /ko/net/programming-with-forms/move-form-field/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 양식 필드를 이동하는 방법을 보여줍니다. 이 프로세스를 안내하기 위해 C# 소스 코드를 단계별로 설명하겠습니다.

## 1단계: 준비

필요한 라이브러리를 가져왔는지 확인하고 문서 디렉터리 경로를 설정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 넣기

기존 PDF 문서를 로드합니다.

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## 3단계: 양식 필드 가져오기

이동하려는 양식 필드를 가져옵니다.

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4단계: 필드 위치 변경

새 직사각형 영역을 정의하여 양식 필드의 위치를 변경합니다.

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## 5단계: 편집된 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 양식 필드 이동의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// 필드 가져오기
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// 필드 위치 수정
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// 수정된 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 양식 필드를 이동하는 방법을 배웠습니다. 다음 단계를 수행하면 특정 필드로 쉽게 이동하고 필요에 따라 위치를 변경할 수 있습니다.


### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 단일 PDF 문서 내에서 여러 양식 필드를 이동할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 단일 PDF 문서 내에서 여러 양식 필드를 이동할 수 있습니다. 재배치하려는 각 양식 필드에 대해 프로세스를 반복하기만 하면 됩니다.

#### Q: 양식 필드를 이동하면 관련 데이터나 기능에 영향을 미치나요?

A: 아니요. 양식 필드를 이동해도 관련 데이터나 기능에는 영향을 미치지 않습니다. 양식 필드는 새 위치로 이동된 후에도 모든 속성과 값을 유지합니다.

#### Q: 양식 필드의 새 위치에 대한 정확한 좌표를 어떻게 확인할 수 있나요?

 A: 다음을 사용하여 새 위치를 지정할 수 있습니다.`Aspose.Pdf.Rectangle` 클래스에서는 직사각형 영역의 왼쪽 상단 모서리의 X 및 Y 좌표와 오른쪽 하단 모서리의 X 및 Y 좌표를 정의합니다.

#### Q: Aspose.PDF for .NET은 Windows 및 Linux 환경 모두와 호환됩니까?

A: 예, .NET용 Aspose.PDF는 Windows 및 Linux 환경과 모두 호환되므로 개발자가 선호하는 운영 체제에서 작업할 수 있는 유연성을 제공합니다.