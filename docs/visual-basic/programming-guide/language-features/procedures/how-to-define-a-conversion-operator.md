---
title: "Практическое руководство. Определение оператора преобразования (Visual Basic) | Microsoft Docs"
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
  - "перегрузка операторов"
  - "операторы [Visual Basic], определение"
  - "операторы [Visual Basic], перегрузка"
  - "процедуры, определение"
  - "процедуры, оператор"
  - "возвращаемые значения, Процедуры операторов"
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Определение оператора преобразования (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Если определены класс или структура, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных \(например `Integer`, `Double` или `String`\).  
  
 Определите преобразование типа как процедуру [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) внутри класса или структуры.  Все процедуры преобразования должны быть `Public Shared`, и каждая из них должна указывать [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) или [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Определение оператора в классе или структуре называется также *перегрузкой* оператора.  
  
## Пример  
 В следующем примере определяются операторы преобразования между структурой `digit` и `Byte`.  
  
 [!CODE [VbVbcnProcedures#27](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#27)]  
  
 Можно проверить структуру `digit` с помощью следующего кода.  
  
 [!CODE [VbVbcnProcedures#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#28)]  
  
## См. также  
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Вызов процедуры оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Практическое руководство. Использование класса, в котором определяются операторы](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)