---
title: "Константы, определенные пользователем (Visual Basic) | Microsoft Docs"
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
  - "циклические ссылки между константами"
  - "Const - оператор [Visual Basic], пользовательские константы"
  - "константы, циклические ссылки"
  - "константы, определяемые пользователем"
  - "область действия, константы"
  - "пользовательские константы"
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Константы, определенные пользователем (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Константа по своей сути — имя со смысловой нагрузкой, которое используется вместо неизменного числа или строки.  Константы хранят значения, которые, как видно из самого названия, остаются при выполнении приложения постоянными.  Можно использовать константы, определенные с помощью используемых элементов управления или компонентов, или создать свои собственные.  Созданные пользователем константы называются *определяемыми пользователем*.  
  
 Константы объявляют при помощи оператора `Const`, руководствуясь теми же правилами, что и при создании имени переменной.  Если `Option Strict` имеет значение `On`, необходимо явно объявлять тип константы.  
  
## Использование оператора Const  
 Оператор `Const` представляет числовые и временные показатели:  
  
 [!CODE [VbEnumsTask#10](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#10)]  
  
 С его помощью также определяют константы типа `String`:  
  
 [!CODE [VbEnumsTask#13](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#13)]  
  
 Правая сторона тождества \(`=`\) зачастую является числом или буквенной строкой, но она может быть и выражением, которое дает в итоге строку или число \(хотя это выражение не может содержать вызов функции\).  Константы можно определять, даже с помощью уже определенных констант.  
  
 [!CODE [VbEnumsTask#15](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#15)]  
  
## Область действия определяемых пользователем констант  
 Область действия оператора `Const` соответствует области действия переменной, объявленной в том же расположении.  Можно задать область действия одним из следующих способов:  
  
-   Чтобы создать константу, которая существует в пределах процедуры, следует объявить ее в этой процедуре.  
  
-   Чтобы создать константу, доступную всем процедурам класса, но не коду за пределами модуля, следует объявить ее в разделе объявлений класса.  
  
-   Чтобы создать константу, доступную всем членам сборки, но не внешним клиентам сборки, следует объявить ее в разделе объявлений класса с использованием ключевого слова `Friend`.  
  
-   Чтобы создать константу, доступную в рамках всего приложения, следует объявить ее в разделе объявлений класса, используя ключевое слово `Public`.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### Профилактика циклических ссылок  
 Поскольку константы могут определяться другими константами, существует опасность случайного создания *цикла* или циклической ссылки между двумя или несколькими константами.  Цикл возникает в том случае, если две или несколько открытых констант определены друг через друга, как показано в следующем примере:  
  
 [!CODE [VbEnumsTask#16](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#16)]  
[!CODE [VbEnumsTask#17](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#17)]  
  
 При возникновении цикла [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выдает ошибку компилятора.  
  
## См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)