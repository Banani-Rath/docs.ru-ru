---
title: "Практическое руководство. Запись значения в свойство (Visual Basic) | Microsoft Docs"
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
  - "свойства [Visual Basic], значения"
  - "значения свойств"
  - "значения, свойства"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, свойства"
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запись значения в свойство (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Записывайте значения в свойство, помещая имя свойства слева от оператора присваивания.  
  
 Процедура `Set` свойства сохраняет значение, но не нужно явно вызывать ее по имени.  Свойство можно использовать точно так же, как используются переменные.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] осуществляет вызовы процедур свойств.  
  
### Для установки значения свойства  
  
1.  Записывайте имя свойства слева от оператора присваивания.  
  
     В следующем примере устанавливается значение свойства [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` полдень, неявно делая вызов процедуры `Set`.  
  
     [!CODE [VbVbcnProcedures#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#11)]  
  
2.  Если свойство принимает аргументы, за именем свойства должен в скобках указываться список аргументов.  Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь что аргументы предоставляются в том же порядке, в котором свойство определяет соответствующие параметры.  
  
4.  Значение, созданное в правой части оператора присваивания, сохранится в свойстве.  
  
## См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Создание свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство. Вызов процедуры свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)