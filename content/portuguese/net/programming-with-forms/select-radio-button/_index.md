---
title: Selecione o botão de opção no documento PDF
linktitle: Selecione o botão de opção no documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como selecionar um botão de opção em um documento PDF usando Aspose.PDF for .NET.
type: docs
weight: 250
url: /pt/net/programming-with-forms/select-radio-button/
---
Aqui está um tutorial detalhado sobre como selecionar um botão de opção usando Aspose.PDF for .NET. Siga esses passos:

##  Passo 1: Comece definindo o diretório dos seus documentos especificando o caminho no`dataDir` variable.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Passo 2: Abra o documento PDF usando o`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Etapa 3: Obtenha o campo do botão de opção no formulário do documento.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Etapa 4: Especifique o índice do botão de opção para selecionar no grupo.

```csharp
radioField. Selected = 2;
```

## Etapa 5: Defina o caminho de saída do arquivo PDF editado.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Etapa 6: Salve o arquivo PDF modificado.

```csharp
pdfDocument.Save(dataDir);
```

## Passo 7: Exiba uma mensagem de confirmação e a localização do arquivo salvo.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Exemplo de código-fonte para Select Radio Button usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Obtenha um campo
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Especifique o índice do botão de opção do grupo
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Salve o arquivo PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como selecionar um botão de opção usando Aspose.PDF for .NET. Seguindo as etapas descritas acima, você pode manipular e modificar botões de opção em seus documentos PDF usando Aspose.PDF for .NET.


### Perguntas frequentes

#### P: Posso selecionar vários botões de opção em um grupo usando Aspose.PDF for .NET?

R: Não, os botões de opção em um grupo são projetados para serem mutuamente exclusivos. Você só pode selecionar um botão de opção por vez dentro de um grupo, e selecionar um irá desmarcar automaticamente qualquer botão de opção selecionado anteriormente no mesmo grupo.

#### P: Como recupero o botão de opção selecionado em um grupo usando Aspose.PDF for .NET?

 R: Para recuperar o botão de opção selecionado em um grupo, você pode usar o`Selected` propriedade do`RadioButtonField` aula. Ele retornará o índice do botão de opção selecionado dentro do grupo.

#### P: Posso personalizar a aparência do botão de opção selecionado no documento PDF?

R: Sim, você pode personalizar a aparência do botão de opção selecionado usando Aspose.PDF for .NET. Você pode modificar sua cor, tamanho, estilo de borda e outros atributos visuais para corresponder à aparência desejada.

#### P: É possível criar novos grupos de botões de opção programaticamente usando Aspose.PDF for .NET?

R: Sim, você pode criar novos grupos de botões de opção programaticamente usando Aspose.PDF for .NET. Você pode adicionar novos botões de opção ao formulário do documento e especificar o mesmo nome de grupo para cada botão de opção para criar um novo grupo.

#### P: O Aspose.PDF for .NET oferece suporte ao trabalho com formulários PDF interativos?

R: Sim, o Aspose.PDF for .NET oferece suporte total ao trabalho com formulários PDF interativos, incluindo botões de opção, campos de texto, caixas de seleção e outros elementos de formulário. Você pode ler, modificar e criar facilmente formulários PDF interativos usando a biblioteca.