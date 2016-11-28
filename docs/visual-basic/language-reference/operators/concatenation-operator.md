---
title: "Оператор &amp; (Visual Basic) | Microsoft Docs"
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
  - "vb.&"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& - оператор"
  - "оператор амперсанд (&)"
  - "And (&) - оператор"
  - "операторы объединения, синтаксис"
  - "строки [Visual Basic], сцепление"
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Оператор &amp; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Генерирует объединение строк двух выражений.  
  
## Синтаксис  
  
```  
  
result = expression1 & expression2  
```  
  
## Части  
 `result`  
 Обязательный.  Любая переменная `String` или `Object`.  
  
 `expression1`  
 Обязательный.  Любое выражение с типом данных, который может быть расширен до `String`.  
  
 `expression2`  
 Обязательный.  Любое выражение с типом данных, который может быть расширен до `String`.  
  
## Заметки  
 Если тип данных `expression1` или `expression2` не является `String`, но расширяется до `String`, он преобразуется в `String`.  Если один из типов данных не расширяется до `String`, компилятор генерирует ошибку.  
  
 Типом данных `result` является `String`.  Если одно или оба выражения равны [Nothing](../../../visual-basic/language-reference/nothing.md) или имеют значение <xref:System.DBNull.Value?displayProperty=fullName>, они интерпретируются как строка со значением "".  
  
> [!NOTE]
>  Оператор `&` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Знак амперсанда \(&\) также можно использовать для определения переменных, как относящихся к типу `Long`.  Дополнительные сведения см. в разделе [Символы типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Пример  
 В данном примере оператор `&` используется для принудительного объединения строк.  Результатом является строковое значение, представляющее объединение двух строковых операндов.  
  
 [!CODE [VbVbalrOperators#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#2)]  
  
## См. также  
 [Оператор &\=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы объединения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)