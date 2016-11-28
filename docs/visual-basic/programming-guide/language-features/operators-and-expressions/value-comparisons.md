---
title: "Сравнение значений (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы сравнения, сравнение выражений"
  - "выражения [Visual Basic], сравнение"
  - "числовые выражения"
  - "операторы [Visual Basic], сравнение"
  - "переменные [Visual Basic], сравнение значений"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Сравнение значений (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Операторы сравнения используются для создания выражений, которые сравнивают значения числовых переменных.  Эти выражения возвращают значение `Boolean`, указывающее какое из значений имеет результат сравнения \(true или false\).  Примеры таких выражений приведены ниже.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Результатом вычисления первого выражения является значение `True`, поскольку 45 больше 26.  Результатом вычисления второго выражения является значение `False`, поскольку 26 не больше 45.  
  
 Таким же способом можно сравнивать числовые выражения.  Сравниваемые выражения могут быть сложными, например:  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Данное сложное выражение содержит литералы, переменные и вызовы функций.  Сначала вычисляются обе части оператора сравнения, а затем полученные значения сравниваются с помощью этого оператора `>=` .  Если значение выражения в левой части больше или равно значению выражения в правой, то все выражение принимает значение `True`; в противном случае — значение `False`.  
  
 Выражения, сравнивающие значения, часто используются в операторах `If...Then`, например:  
  
 [!CODE [VbVbalrOperators#84](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#84)]  
  
 Знак `=` является оператором сравнения, а также оператором назначения.  При использовании в качестве оператора сравнения он вычисляет, равно ли значение слева значению справа, например:  
  
 [!CODE [VbVbalrOperators#85](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#85)]  
  
 Можно также использовать выражения сравнения везде, где необходимо использовать значение `Boolean`, например в операторе `If`, `While`, `Loop` или `ElseIf`, либо при назначении или передаче значения переменной `Boolean`.  В следующем примере значение, возвращенное выражением сравнения, назначается переменной `Boolean`.  
  
 [!CODE [VbVbalrOperators#86](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#86)]  
  
## См. также  
 [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)