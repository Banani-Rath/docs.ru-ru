---
title: "Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic) | Microsoft Docs"
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
  - "переменные [Visual Basic], извлечение значений"
  - "переменные [Visual Basic], строковые данные"
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Храните значения в переменной, помещая имя переменной слева от оператора присваивания.  
  
## Помещение данных в переменную  
  
#### Хранение значения в переменной  
  
-   Записывайте имя переменной слева от оператора присваивания.  
  
     В следующем примере задается значение переменной `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Значение, созданное в правой части оператора присваивания, хранится в переменной.  
  
## Получение данных из переменной  
 Извлеките значение переменной посредством включения имени переменной в выражение.  
  
#### Извлечение значения из переменной  
  
-   Используйте имя переменной в выражении.  Можно использовать переменную везде, где можно использовать константу или литерал, за исключением выражения, определяющего значения константы.  
  
     \-или\-  
  
-   Используйте имя переменной после знака равенства \(`=`\) в операторе присваивания.  
  
     В следующем примере показано, как читать значение переменной `startValue` и затем использовать значение переменной `counter` в выражении.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Значение переменной участвует в выражении так же, как и константа, и затем хранится в переменной или в свойстве в левой части оператора присваивания.  
  
## См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)