---
title: Excluir campo de formulário em documento PDF
linktitle: Excluir campo de formulário em documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Remova facilmente campos de formulário indesejados em documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 50
url: /pt/net/programming-with-forms/delete-form-field/
---
Neste tutorial, mostraremos como excluir um campo de formulário usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo nesse processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Abra o documento

Abra o documento PDF existente:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## Etapa 3: excluir um campo específico

Exclua um campo de formulário específico usando seu nome:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## Etapa 4: salve o documento editado

Salve o documento PDF modificado:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemplo de código-fonte para Excluir campo de formulário usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// Exclua um campo específico por nome
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// Salvar documento modificado
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como excluir um campo de formulário usando Aspose.PDF for .NET. Seguindo essas etapas, você pode remover facilmente campos de formulário indesejados de seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso excluir vários campos de formulário de uma vez usando Aspose.PDF for .NET?

 R: Sim, você pode excluir vários campos de formulário de uma vez usando Aspose.PDF for .NET. Basta ligar para o`Delete` método para cada campo do formulário que você deseja remover.

#### P: Como posso verificar se existe um campo de formulário antes de tentar excluí-lo?

 R: Você pode verificar se existe um campo de formulário antes de tentar excluí-lo usando o botão`Contains` método do`Form` propriedade. Por exemplo:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### P: O que acontece se eu tentar excluir um campo de formulário que não existe no documento PDF?

 R: Se você tentar excluir um campo de formulário que não existe no documento PDF, o`Delete` método não lançará um erro ou exceção. Simplesmente não fará nada, pois não há campo para excluir.

#### P: Posso excluir campos de formulário de diferentes tipos, como campos de texto, caixas de seleção e botões de opção?

 R: Sim, você pode excluir campos de formulário de diferentes tipos, como campos de texto, caixas de seleção e botões de opção, usando o mesmo`Delete` método em Aspose.PDF para .NET. Basta passar o nome do campo que deseja excluir como parâmetro do método.

#### P: É possível desfazer a exclusão de um campo de formulário no documento PDF?

R: Não, depois que um campo de formulário é excluído usando Aspose.PDF for .NET, ele não pode ser desfeito programaticamente. Recomenda-se criar um backup do documento PDF antes de fazer qualquer alteração nele, para que você possa reverter para o documento original, se necessário.