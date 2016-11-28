---
title: "Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic) | Microsoft Docs"
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
  - "пользовательские события"
  - "объявление событий, пользовательский"
  - "события [Visual Basic], пользовательский"
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В некоторых случаях важно, чтобы использование памяти приложением было низким.  Пользовательские события позволяют приложению использовать память только для событий, которые оно обрабатывает.  
  
 По умолчанию, когда класс объявляет событие, компилятор выделяет память под поле для хранения сведений события.  Если класс имеет много неиспользуемых событий, они занимают много памяти.  
  
 Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.  
  
## Пример  
 В этом примере класс использует один экземпляр класса <xref:System.ComponentModel.EventHandlerList>, хранящийся в поле `Events`, для хранения сведений о используемых событиях.  Класс <xref:System.ComponentModel.EventHandlerList> является оптимизированным списочным классом, созданным для хранения делегатов.  
  
 Все события класса используют поле `Events` для наблюдения за тем, какие методы являются обработчиками каждого события.  
  
 [!CODE [VbVbalrEvents#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEvents#22)]  
  
## См. также  
 <xref:System.ComponentModel.EventHandlerList>   
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)