---
title: Extrair borda em arquivo PDF
linktitle: Extrair borda em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como extrair a borda de um arquivo PDF usando Aspose.PDF for .NET.
type: docs
weight: 80
url: /pt/net/programming-with-tables/extract-border/
---
Neste tutorial, aprenderemos como extrair a borda de um arquivo PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte em C# passo a passo. Ao final deste tutorial você saberá como extrair a borda de um documento PDF e salvá-la como imagem. Vamos começar!

## Passo 1: Configurando o ambiente
Primeiro, certifique-se de configurar seu ambiente de desenvolvimento C# com Aspose.PDF for .NET. Adicione a referência à biblioteca e importe os namespaces necessários.

## Passo 2: Carregando o Documento PDF
Nesta etapa, carregamos o documento PDF do arquivo especificado.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo diretório real onde seu arquivo PDF está localizado.

## Etapa 3: Extração de Borda
Extrairemos a borda do documento PDF iterando as operações contidas no documento.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Processar todas as operações de conteúdo
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Verifique o tipo de operação
         // ...
         // Adicione código para processar cada operação
     }
}
```

 Nós criamos um`graphicsState` pilha para armazenar estados gráficos, uma imagem bitmap para capturar a borda extraída, um`GraphicsPath` objeto para armazenar caminhos de desenho e outras variáveis para rastrear estado e cores.

## Etapa 4: Processamento de transações
Nesta etapa processamos cada operação do documento para extrair a borda.

```csharp
// Verifique o tipo de operação
if (opSaveState != null)
{
     // Salve o estado anterior e coloque o estado atual no topo da pilha
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Exclua o estado atual e restaure o estado anterior
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Recuperar a matriz de transformação atual
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Multiplique a matriz atual pela matriz de estado
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Atualize o último ponto de desenho
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Processar o desenho de uma linha
     // ...
     // Adicione código para desenhar uma linha
}
// ...
// Adicione blocos else if para outras operações
```

Verificamos o tipo de operação usando condições e executamos o código apropriado para cada operação.

## Etapa 5: imagem de backup
Finalmente, salvamos a imagem bitmap contendo a borda extraída em um arquivo especificado.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Certifique-se de especificar o diretório e o nome de arquivo corretos para salvar a imagem de saída.

### Exemplo de código-fonte para Extrair Borda usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// O valor padrão da matriz ctm é 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
// sistema de coordenadas System.Drawing é baseado no canto superior esquerdo, enquanto o sistema de coordenadas pdf é baseado no canto inferior esquerdo, então temos que aplicar a matriz de inversão
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Processe todos os comandos de conteúdo
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Salve o estado anterior e coloque o estado atual no topo da pilha
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Jogue fora o estado atual e restaure o anterior
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// Multiplique a matriz atual pela matriz de estado
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Conclusão
Neste tutorial, aprendemos como extrair a borda de um documento PDF usando Aspose.PDF for .NET. Você pode usar este guia passo a passo para extrair bordas de outros documentos PDF.

### Perguntas frequentes para extrair borda em arquivo PDF

#### P: Qual é o propósito de extrair a borda de um arquivo PDF?

R: Extrair a borda de um arquivo PDF pode ser útil para diversos fins. Permite isolar e analisar os elementos estruturais do documento, como tabelas, diagramas ou elementos gráficos. Você pode usar a borda extraída para identificar o layout, as dimensões e o posicionamento do conteúdo no documento PDF.

#### P: Posso extrair a borda de páginas ou áreas específicas do documento PDF?

R: Sim, você pode modificar o código-fonte C# fornecido para extrair a borda de páginas ou regiões específicas do documento PDF. Ao manipular o`doc.Pages` coleção e especificando critérios personalizados, você pode optar por extrair a borda de páginas ou áreas de interesse específicas.

#### P: Como posso personalizar o formato e a qualidade da imagem de saída?

 R: No código C# fornecido, a borda extraída é salva como uma imagem PNG. Se quiser alterar o formato da imagem de saída, você pode modificar o`ImageFormat.Png` parâmetro no`bitmap.Save` método para outros formatos de imagem suportados, como JPEG, BMP ou GIF. Além disso, você pode ajustar a qualidade da imagem ou as configurações de compactação com base em seus requisitos.

#### P: Que outras operações posso realizar na borda extraída?

R: Depois de extrair a borda como uma imagem, você poderá processá-la posteriormente usando bibliotecas ou algoritmos de processamento de imagem. Você pode analisar a imagem, aplicar filtros de imagem, detectar padrões ou realizar OCR (reconhecimento óptico de caracteres) para extrair texto da imagem, se necessário.

#### P: Há alguma limitação ou consideração ao extrair bordas de documentos PDF complexos?

R: O processo de extração pode variar dependendo da complexidade do documento PDF. PDFs complexos com múltiplas camadas, transparência ou gráficos avançados podem exigir processamento ou ajustes adicionais para extrair a borda com precisão. É essencial testar minuciosamente o processo de extração em vários documentos PDF para garantir resultados confiáveis.