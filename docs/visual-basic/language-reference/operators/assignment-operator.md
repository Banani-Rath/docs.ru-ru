---
title: "Оператор = (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Assign"
  - "vb.="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "= - операторы присваивания [Visual Basic]"
  - "= - оператор [Visual Basic]"
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор = (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для присвоения значения переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty = value  
```  
  
## Части  
 `variableorproperty`  
 Любые переменная или свойство с возможностью записи.  
  
 `value`  
 Любые литерал, константа или выражение.  
  
## Заметки  
 Элемент с левой стороны от знака равенства \(`=`\) может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  Оператор `=` присваивает значение, стоящее справа от него, переменной или свойству, расположенному слева.  
  
> [!NOTE]
>  Оператор `=` также используется в качестве оператора сравнения.  Дополнительные сведения см. в разделе [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## Перегрузка  
 Оператор `=` может быть перегружен только как оператор отношения, а не как оператор присваивания.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере демонстрируется оператор присваивания.  Значение в правой части присваивается переменной слева.  
  
 [!CODE [VbVbalrOperators#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#9)]  
  
## См. также  
 [Оператор &\=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Оператор \*\=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [Оператор \+\=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [Оператор \-\=](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Оператор \/\=](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [Оператор \\\=](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Оператор ^\=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)