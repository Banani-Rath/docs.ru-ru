---
title: "Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic) | Microsoft Docs"
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
  - "String - тип данных, проверка"
  - "строки [Visual Basic], проверка"
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В следующем примере кода задается значение `Boolean`, показывающее, представляет ли строка допустимую дату или время.  
  
## Пример  
 [!CODE [VbVbcnRegEx#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnRegEx#2)]  
  
## Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` датой и временем, которые нужно проверить.  Можно заменить строку другой жестко\-запрограммированной строкой, с помощью переменной `String` или метода, возвращающего строку, например `InputBox`.  
  
## Отказоустойчивость  
 Этот метод используется для проверки строки перед попыткой преобразования переменной `String` в `DateTime`.  Проверив дату или время сначала, можно избежать возникновения исключений во время выполнения.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>   
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>   
 [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)