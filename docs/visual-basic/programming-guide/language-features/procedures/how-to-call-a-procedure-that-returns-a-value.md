---
title: "Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic) | Microsoft Docs"
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
  - "вызовы процедур, возвращаемые значения"
  - "процедуры, вызов"
  - "процедуры, возвращаемое значение"
  - "код Visual Basic, процедуры"
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура `Function` возвращает значение вызывающему коду.  Для ее вызова следует указать ее имя и аргументы справа от оператора присваивания или в составе выражения.  
  
### Чтобы вызвать процедуру Function с помощью выражения  
  
1.  Используйте имя процедуры `Function` так же, как и переменную.  Можно использовать вызов процедуры `Function` везде, где можно использовать переменную или константу в выражении.  
  
2.  Запишите имя процедуры с заключенным в скобки списком аргументов.  Если не указано никаких аргументов, скобки можно опустить.  Тем не менее использование круглых скобок облегчает чтение кода.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь, что аргументы указаны в том же порядке, как в процедуре `Function` определены соответствующие параметры.  
  
     Кроме того можно указывать один или несколько аргументов по имени.  Дополнительные сведения см. в разделе [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
4.  Значение, возвращаемое процедурой, входит в выражение так же, как входило бы значение переменной или константы.  
  
### Чтобы вызвать процедуру Function в операторе присваивания  
  
1.  Используйте имя процедуры `Function` после знака равенства \(`=`\) в операторе присваивания.  
  
2.  Запишите имя процедуры с заключенным в скобки списком аргументов.  Если не указано никаких аргументов, скобки можно опустить.  Тем не менее использование круглых скобок облегчает чтение кода.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь, что аргументы вводятся в том же порядке, в каком `Function` определяет соответствующие им параметры, если только не используется их передача по имени.  
  
4.  Значение, возвращаемое процедурой, хранится в переменной или свойстве в левой части оператора присваивания.  
  
## Пример  
 В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> для получения значения переменной среды операционной системы.  Первая строка вызывает `Environ` в выражении, а вторая строка вызывает его в операторе присваивания.  `Environ` принимает имя переменной в качестве единственного аргумента.  Значение переменной возвращается в вызывающий код.  
  
 [!CODE [VbVbcnProcedures#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#7)]  
  
## См. также  
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Практическое руководство. Создание процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство. Возврат значения из процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)