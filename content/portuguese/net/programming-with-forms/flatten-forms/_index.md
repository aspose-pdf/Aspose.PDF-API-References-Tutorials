---
title: Achatar formulários em documento PDF
linktitle: Achatar formulários em documento PDF
second_title: Referência da API Aspose.PDF para .NET
description: Achate facilmente formulários em documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /pt/net/programming-with-forms/flatten-forms/
---
Neste tutorial, mostraremos como nivelar formulários usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo neste processo.

## Etapa 1: Preparação

Primeiro, certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o formulário PDF de origem

Carregue o formulário PDF de origem:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Etapa 3: nivelar os formulários

Primeiro verifique se há algum campo de formulário no documento. Nesse caso, itere em cada campo e aplique nivelamento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Etapa 4: salve o documento atualizado

Salve o documento PDF atualizado:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Exemplo de código-fonte para Flatten Forms usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar formulário PDF de origem
Document doc = new Document(dataDir + "input.pdf");
// Achatar formulários
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Salve o documento atualizado
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusão

Neste tutorial, aprendemos como nivelar formulários usando Aspose.PDF para .NET. Seguindo essas etapas, você pode nivelar facilmente formulários em seus documentos PDF, tornando os campos não editáveis e mesclando anotações com o conteúdo do documento.

### Perguntas frequentes

#### P: O que significa "achatamento de formulários" no Aspose.PDF para .NET?

R: Achatar formulários no Aspose.PDF for .NET refere-se ao processo de tornar os campos de formulário em um documento PDF não editáveis e mesclar anotações (como campos de formulário, anotações e assinaturas digitais) com o conteúdo do documento. Depois que os formulários são nivelados, os usuários não podem modificar os campos do formulário e a aparência visual dos campos do formulário torna-se parte do conteúdo estático do documento PDF.

#### P: Posso reverter o processo de nivelamento e tornar os campos do formulário editáveis novamente?

R: Não, uma vez que os campos do formulário são nivelados, o processo é irreversível usando Aspose.PDF for .NET. O nivelamento mescla permanentemente a aparência dos campos do formulário com o conteúdo do PDF, e os elementos individuais dos campos do formulário não são mais acessíveis ou editáveis.

#### P: Quando devo nivelar formulários em um documento PDF?

R: O nivelamento de formulários é útil quando você deseja preservar a aparência visual dos campos de formulário e das anotações em um documento PDF, evitando que os usuários modifiquem os dados. Isso geralmente é feito quando você deseja compartilhar um documento PDF com dados de formulário pré-preenchidos ou anotações que não devem ser alteradas pelos destinatários.

#### P: O nivelamento de formulários afetará outras anotações, como assinaturas digitais?

R: Sim, nivelar formulários mesclará todas as anotações, incluindo assinaturas digitais, com o conteúdo do PDF. Depois que os formulários forem nivelados, quaisquer assinaturas digitais existentes se tornarão uma parte permanente do documento e os usuários não poderão modificá-las ou removê-las.

#### P: Posso nivelar seletivamente campos específicos do formulário e deixar outros editáveis?

R: Sim, você pode nivelar seletivamente campos de formulário específicos em um documento PDF e deixar outros editáveis. Em vez de usar o código para nivelar todos os campos do formulário, você pode optar por nivelar apenas os campos de formulário desejados com base em seus nomes ou outros critérios.