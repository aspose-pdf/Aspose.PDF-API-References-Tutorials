---
title: Obter coordenadas de campo de formulário PDF
linktitle: Obter coordenadas de campo de formulário PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Obtenha facilmente coordenadas de campos de formulários PDF em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-forms/get-coordinates/
---
Neste tutorial, mostraremos como obter coordenadas de campos de formulários PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Carregue o documento de saída

Carregue o documento PDF de saída:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Etapa 3: Encontre campos adicionados

Localize os campos de formulário adicionados (neste exemplo, estamos usando os campos "Item1", "Item2" e "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Etapa 4: Exibir posições de subitens para cada campo

Percorra as opções de cada campo e visualize as coordenadas de cada subitem:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Exemplo de código-fonte para Obter Coordenadas usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carregue o documento de saída
	Document doc1 = new Document( dataDir + "input.pdf");
	// Encontre campos adicionados
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// E mostrar as posições dos subitens para cada um deles.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusão

Neste tutorial, aprendemos como obter coordenadas de campos de formulário usando Aspose.PDF para .NET. Seguindo essas etapas, você pode recuperar facilmente as coordenadas dos subelementos dos seus campos de formulário em seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso usar esse método para obter coordenadas para qualquer tipo de campo de formulário no Aspose.PDF para .NET?

R: Sim, você pode usar esse método para obter coordenadas para vários tipos de campos de formulário no Aspose.PDF para .NET. O código-fonte C# fornecido demonstra como obter coordenadas para campos RadioButton, mas você pode adaptar a mesma abordagem para outros tipos de campos de formulário, como TextBox, CheckBox, ListBox e muito mais.

#### P: Como posso modificar ou ajustar as coordenadas do campo do formulário?

A: As coordenadas do campo de formulário são baseadas no sistema de coordenadas do documento PDF, onde a origem (0,0) está localizada no canto inferior esquerdo da página. Para modificar ou ajustar as coordenadas do campo de formulário, você pode atualizar o`Rect` propriedade do respectivo campo de formulário ou seus subitens, como RadioButtonOptionField.

#### P: Posso obter as coordenadas dos campos de formulário adicionados programaticamente a um documento PDF?

R: Sim, você pode obter as coordenadas de campos de formulário que foram adicionados programaticamente a um documento PDF. O Aspose.PDF for .NET permite que você adicione campos de formulário dinamicamente e, uma vez adicionados, você pode recuperar suas coordenadas usando a abordagem demonstrada neste tutorial.

#### P: Qual é o propósito de recuperar coordenadas de campos de formulário?

R: Recuperar coordenadas de campos de formulário pode ser útil quando você precisa executar operações específicas relacionadas ao layout ou validações em campos de formulário dentro de um documento PDF. Ele permite que você posicione e alinhe com precisão os campos de formulário com base em suas coordenadas, garantindo que eles apareçam corretamente no documento e forneçam uma experiência de usuário perfeita.

#### P: As coordenadas do campo do formulário são expressas em pontos ou outra unidade?

R: As coordenadas do campo de formulário no Aspose.PDF para .NET são expressas em pontos. Um ponto é equivalente a 1/72 polegada, tornando-se uma unidade de medida padrão no formato PDF.