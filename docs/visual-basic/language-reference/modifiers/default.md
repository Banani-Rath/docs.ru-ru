---
title: "Default (Visual Basic) | Microsoft Docs"
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
  - "vb.Default"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Default -ключевое слово [Visual Basic]"
  - "свойства по умолчанию"
  - "свойства по умолчанию, в Visual Basic"
  - "по умолчанию, свойства"
  - "свойства [Visual Basic], по умолчанию"
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Default (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет свойство как свойство по умолчанию класса, структуры или интерфейса.  
  
## Заметки  
 Класс, структура или интерфейс могут назначить не более одного из свойств как *свойства по умолчанию*, при условии, что свойство принимает хотя бы один параметр.  Если код ссылается на класс или структуру без указания члена, Visual Basic разрешает ссылку, как ссылку на свойство по умолчанию.  
  
 Свойства по умолчанию могут привести к небольшому сокращению размера исходного кода, но могут сделать код более сложным для восприятия.  Если вызывающий код не знаком с классом или структурой, то когда он ссылается на имя класса или структуры он не может быть уверен в том, обращается ли эта ссылка к классу или структуре или к свойству по умолчанию.  Это может привести к ошибкам компилятора или к логическим ошибкам во время выполнения.  
  
 Можно частично уменьшить вероятность ошибок, связанных со свойством по умолчанию, используя тип проверки компилятором [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`.  
  
 Если планируется использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию, и если да, то какое у него имя.  
  
 Из\-за этих недостатков не следует определять свойства по умолчанию.  Также следует учитывать удобочитаемость кода, которая повышается при постоянной ссылке на все свойства явным образом, даже на свойства по умолчанию.  
  
 Модификатор `Default` можно использовать в следующем контексте.  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## См. также  
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)