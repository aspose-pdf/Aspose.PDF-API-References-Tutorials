---
title: Obtenha coordenadas de campo do formulário PDF
linktitle: Obtenha coordenadas de campo do formulário PDF
second_title: Referência da API Aspose.PDF para .NET
description: Obtenha facilmente coordenadas de campo de formulário PDF em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 120
url: /pt/net/programming-with-forms/get-coordinates/
---
Neste tutorial, mostraremos como obter coordenadas de campo de formulário PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo nesse processo.

## Etapa 1: Preparação

Certifique-se de importar as bibliotecas necessárias e definir o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento de saída

Carregue o documento PDF de saída:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Etapa 3: encontre os campos adicionados

Encontre os campos de formulário adicionados (neste exemplo, estamos usando os campos "Item1", "Item2" e "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Etapa 4: exibir as posições dos subitens para cada campo

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

### Exemplo de código-fonte para obter coordenadas usando Aspose.PDF para .NET 
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
	// E mostre as posições dos subitens de cada um deles.
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

Neste tutorial, aprendemos como obter coordenadas de campo de formulário usando Aspose.PDF para .NET. Seguindo essas etapas, você pode recuperar facilmente as coordenadas dos subelementos dos campos do formulário em seus documentos PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso usar este método para obter coordenadas para qualquer tipo de campo de formulário no Aspose.PDF for .NET?

R: Sim, você pode usar este método para obter coordenadas para vários tipos de campos de formulário no Aspose.PDF for .NET. O código-fonte C# fornecido demonstra como obter coordenadas para campos RadioButton, mas você pode adaptar a mesma abordagem para outros tipos de campo de formulário, como TextBox, CheckBox, ListBox e muito mais.

#### P: Como posso modificar ou ajustar as coordenadas do campo do formulário?

R: As coordenadas dos campos do formulário são baseadas no sistema de coordenadas do documento PDF, onde a origem (0,0) está localizada no canto inferior esquerdo da página. Para modificar ou ajustar as coordenadas do campo do formulário, você pode atualizar o`Rect` propriedade do respectivo campo do formulário ou de seus subitens, como RadioButtonOptionField.

#### P: Posso obter as coordenadas dos campos de formulário adicionados programaticamente a um documento PDF?

R: Sim, você pode obter as coordenadas dos campos do formulário que foram adicionados programaticamente a um documento PDF. Aspose.PDF for .NET permite adicionar campos de formulário dinamicamente e, uma vez adicionados, você pode recuperar suas coordenadas usando a abordagem demonstrada neste tutorial.

#### P: Qual é o propósito de recuperar as coordenadas do campo do formulário?

R: A recuperação de coordenadas de campos de formulário pode ser útil quando você precisa realizar operações específicas relacionadas ao layout ou validações em campos de formulário em um documento PDF. Ele permite posicionar e alinhar com precisão os campos do formulário com base em suas coordenadas, garantindo que eles apareçam corretamente no documento e forneçam uma experiência de usuário perfeita.

#### P: As coordenadas do campo do formulário são expressas em pontos ou em outra unidade?

R: As coordenadas do campo do formulário no Aspose.PDF for .NET são expressas em pontos. Um ponto equivale a 1/72 polegada, tornando-o uma unidade de medida padrão no formato PDF.