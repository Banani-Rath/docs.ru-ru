---
title: "Часть выражения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "лямбда-выражения [Visual Basic], часть выражения"
  - "Часть выражения [Visual Basic]"
  - "подпрограммы [Visual Basic], части выражений"
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Часть выражения (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет параметры и код, который определяет подпрограмму\-лямбда\-выражение.  
  
## Синтаксис  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`parameterlist`|Необязательный.  Список имен локальных переменных, представляющих параметры этой процедуры.  Круглые скобки должны присутствовать даже если список пуст.  Дополнительные сведения см. в разделе [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Обязательный.  Один оператор.|  
|`statements`|Обязательный.  Список операторов.|  
  
## Заметки  
 *Лямбда\-выражение* — это функция или подпрограмма без имени, выполняющая один и более операторов.  Можно использовать лямбда\-выражение везде, где можно использовать тип делегата, за исключением использования в качестве аргумента в `RemoveHandler`.  Дополнительные сведения о делегатах и использовании лямбда\-выражений с делегатами см. в разделах [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Синтаксис лямбда\-выражений  
 Синтаксис лямбда\-выражения похож на синтаксис стандартной подпрограммы.  Различия заключаются в следующем:  
  
-   Лямбда\-выражение не имеет имени.  
  
-   Лямбда\-выражения не могут включать модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Телом однострокового лямбда\-выражения должен быть оператор, а не выражение.  Тело может содержать вызов подпрограммы, но не вызов функции.  
  
-   В лямбда\-выражении все параметры должны иметь определенный типы данных или все параметры должны быть установлены.  
  
-   Необязательный и `ParamArray` параметры не допускаются в лямбда\-выражении.  
  
-   Универсальные параметры не разрешены в лямбда\-выражении.  
  
## Пример  
 Ниже приведен пример лямбда\-выражения, записывающего значение на консоль.  В примере показан синтаксис однострокового и многострокового лямбда\-выражения для подпрограммы.  Дополнительные примеры см. в разделе [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!CODE [VbVbalrLambdas#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrLambdas#15)]  
  
## См. также  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)