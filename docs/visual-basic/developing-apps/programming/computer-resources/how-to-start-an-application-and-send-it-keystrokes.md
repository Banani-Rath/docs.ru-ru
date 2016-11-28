---
title: "Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic) | Microsoft Docs"
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
  - "нажатия клавиш, отправка"
  - "процессы, запуск и отправка сведений о нажатии клавиш"
  - "SendKeys.SendWait - примеры"
  - "Shell - пример команды [Visual Basic]"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере используется функция `Shell` для запуска приложения "Калькулятор", а затем перемножается 2 числа путем отправки событий нажатия клавиш с помощью метода `My.Computer.Keyboard.SendKeys`.  
  
## Пример  
 [!CODE [VbVbalrMyComputer#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#25)]  
  
## Отказоустойчивость  
 Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.  
  
## Безопасность платформы .NET Framework  
 Вызов функции `Shell` требует полного доверия \(класс <xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>