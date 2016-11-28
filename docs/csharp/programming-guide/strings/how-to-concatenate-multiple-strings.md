---
title: "Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "сцепление строк [C#]"
  - "объединение строк [C#]"
  - "строки [C#], объединение"
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

*Объединение* — это процесс добавления одной строки к концу другой.  При объединении строковых литералов или строковых констант с помощью оператора `+` компилятор создает одну строку.  Объединение среды выполнения не происходит.  Однако строковые переменные могут быть объединены только во время выполнения.  В таком случае следует уяснить влияние различных подходов на производительность.  
  
## Пример  
 В следующем примере показано разделение длинного строкового литерала на маленькие строки для повышения удобочитаемости в исходном коде.  Во время компиляции эти части будут объединены в одну строку.  Производительность не снижается, независимо от количества используемых строк.  
  
 [!CODE [csProgGuideStrings#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStrings#30)]  
  
## Пример  
 Для объединения строковых переменных можно использовать операторы `+` или `+=` или методы <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.  Оператор `+` прост в использовании и позволяет сформировать наглядный код.  Даже при одновременном использовании нескольких операторов "\+" содержимое строки копируется только один раз.  Однако если повторить такую операцию несколько раз \(например, в цикле\), могут возникнуть проблемы с производительностью.  Например, рассмотрим следующий код:  
  
 [!CODE [csProgGuideStrings#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStrings#23)]  
  
> [!NOTE]
>  В операциях объединения строк компилятор С\# обрабатывает нулевую строку так же, как пустую строку, но не преобразовывает значение исходной нулевой строки.  
  
 Если не выполняется объединения большого количества строк \(например, в цикле\), то снижение производительности этого кода, вероятно, будет незначительным.  Это также относится к методам <xref:System.String.Concat%2A?displayProperty=fullName> и <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 Однако, если самым важным является производительность, то для объединения строк всегда следует использовать класс <xref:System.Text.StringBuilder>.  В следующем коде используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder> для объединения строк без "эффекта цепочки" оператора `+`.  
  
 [!CODE [csProgGuideStrings#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStrings#22)]  
  
## См. также  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)