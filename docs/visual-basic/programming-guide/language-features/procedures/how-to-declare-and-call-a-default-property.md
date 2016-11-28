---
title: "Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic | Microsoft Docs"
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
  - "свойства по умолчанию"
  - "свойства по умолчанию, в Visual Basic"
  - "по умолчанию, свойства"
  - "процедуры, определение"
  - "свойства [Visual Basic], по умолчанию"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, свойства"
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*свойство по умолчанию* является свойством класса или структуры, к которому кода может получать доступ без его указания.  Если вызывающий код задает имя класса или структуры \(но не свойства\), а контекст разрешает доступ к свойству, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] разрешает доступ к свойству по умолчанию этого класса или структуры, если оно существует.  
  
 Класс или структура может иметь не более одного свойства по умолчанию.  Однако, можно перегружать свойство по умолчанию и иметь более одной его версии.  
  
 Дополнительные сведения см. в разделе [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### Для объявления свойства по умолчанию  
  
1.  объявите свойство обычным способом.  Не указывайте зарезервированные слова `Shared` и `Private`.  
  
2.  Вставьте ключевое слово `Default` в объявление.  
  
3.  Укажите хотя бы один параметр свойства.  Нельзя определить свойство по умолчанию, которое не принимает, по крайней мере, один аргумент.  
  
     [!CODE [VbVbcnProcedures#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#17)]  
  
### Для вызова свойства по умолчанию  
  
1.  Объявите переменную типа содержащего класса или структуры.  
  
     [!CODE [VbVbcnProcedures#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#16)]  
  
2.  Используйте имя переменной отдельно в выражении, которое обычно содержит имя свойства.  
  
     [!CODE [VbVbcnProcedures#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#21)]  
  
3.  Укажите после имени переменной список аргументов в круглых скобках.  Свойство по умолчанию должно принимать хотя бы один аргумент.  
  
     [!CODE [VbVbcnProcedures#20](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#20)]  
  
4.  Чтобы извлечь значение свойства по умолчанию используйте имя переменной со списком аргументов в выражении или после знака равенства \(`=`\) в инструкции присваивания.  
  
     [!CODE [VbVbcnProcedures#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#15)]  
  
5.  Чтобы задать значение свойства по умолчанию, используйте имя переменной со списком аргументов слева от оператора присваивания.  
  
     [!CODE [VbVbcnProcedures#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#14)]  
  
6.  Можно указать имя свойства по умолчанию вместе с именем переменной точно так же, как обычно при получении доступа к любому другому свойству.  
  
     [!CODE [VbVbcnProcedures#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#19)]  
  
## Пример  
 Пример объявления свойства по умолчанию в классе:  
  
 [!CODE [VbVbcnProcedures#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#12)]  
  
## Пример  
 В следующем примере показано, как вызвать свойство по умолчанию `myProperty` для класса `class1`.  Три оператора присваивания сохраняют значения в `myProperty`, и вызов <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> считывает значения.  
  
 [!CODE [VbVbcnProcedures#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnProcedures#13)]  
  
 Наиболее часто используется свойство по умолчанию <xref:Microsoft.VisualBasic.Collection.Item%2A> для различных классов коллекций.  
  
## Отказоустойчивость  
 Свойства по умолчанию могут привести к небольшому сокращению размера исходного кода, но могут сделать код более сложным для восприятия.  Если вызывающий код не знаком с классом или структурой, то когда он ссылается на имя класса или структуры он не может быть уверен в том, обращается ли эта ссылка к классу или структуре или к свойству по умолчанию.  Это может привести к ошибкам компилятора или к логическим ошибкам во время выполнения.  
  
 Можно частично уменьшить вероятность ошибок, связанных со свойством по умолчанию, используя тип проверки компилятором [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`.  
  
 Если планируется использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию, и если да, то какое у него имя.  
  
 Из\-за этих недостатков не следует определять свойства по умолчанию.  Также следует учитывать удобочитаемость кода, которая повышается при постоянной ссылке на все свойства явным образом, даже на свойства по умолчанию.  
  
## См. также  
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Создание свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство. Вызов процедуры свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Практическое руководство. Запись значения в свойство](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)