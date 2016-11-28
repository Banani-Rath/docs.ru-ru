---
title: "Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic) | Microsoft Docs"
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
  - "процедуры, определение"
  - "процедуры, возвращаемое значение"
  - "код Visual Basic, процедуры"
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура `Function` используется для возвращения значения в вызывающий код.  
  
### Создание процедуры, возвращающей значение  
  
1.  Вне любых других процедур используйте оператор `Function`, за которым следует оператор `End Function`.  
  
2.  В инструкции `Function` введите зарезервированное слово `Function` с именем процедуры и затем список параметров в круглых скобках.  
  
3.  Введите круглые скобки, используя предложение `As` для указания типа данных возвращаемого значения.  
  
4.  Поместите операторы кода процедуры между оператором `Function` и `End Function`.  
  
5.  Оператор `Return` используется для возврата значения в вызывающий код.  
  
     Приведенная ниже процедура `Function` вычисляет длину самой длинной стороны прямоугольного треугольника \(гипотенузы\) по значениям двух других сторон.  
  
     [!CODE [VbVbcnProcedures#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#1)]  
  
     В следующем примере показан типичный вызов `hypotenuse`.  
  
     [!CODE [VbVbcnProcedures#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#6)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Практическое руководство. Возврат значения из процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)