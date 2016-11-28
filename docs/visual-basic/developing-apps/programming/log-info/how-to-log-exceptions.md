---
title: "Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic | Microsoft Docs"
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
  - "исключения, ведение журналов"
  - "исключения, отслеживание"
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации об исключениях, возникающих в приложении.  В этих примерах показано, как использовать метод `My.Application.Log.WriteException` для регистрации в журнале явно перехватываемых и необработанных исключений.  
  
 Для записи в журнал данных трассировки используйте метод `My.Application.Log.WriteEntry`.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.  
  
### Регистрация обработанного исключения в журнале  
  
1.  Создайте метод, который будет генерировать информацию об исключении.  
  
     [!CODE [VbVbalrMyApplicationLog#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#9)]  
  
2.  Используйте блок `Try...Catch` для перехвата исключения.  
  
     [!CODE [VbVbalrMyApplicationLog#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#6)]  
  
3.  Поместите код, который может сгенерировать исключение, в блок `Try`.  
  
     Удалите комментарий строки `Dim` и `MsgBox`, чтобы возникло исключение <xref:System.NullReferenceException>.  
  
     [!CODE [VbVbalrMyApplicationLog#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#7)]  
  
4.  В блоке `Catch` используйте метод `My.Application.Log.WriteException` для записи информации об исключении.  
  
     [!CODE [VbVbalrMyApplicationLog#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#8)]  
  
     В следующем примере показан полный код для регистрации в журнале обработанного исключения.  
  
     [!CODE [VbVbalrMyApplicationLog#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#10)]  
  
### Регистрация необработанного исключения в журнале  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  
  
2.  Перейдите на вкладку **Приложение**.  
  
3.  Нажмите кнопку **Просмотреть события приложения**, чтобы открыть редактор кода.  
  
     Откроется файл ApplicationEvents.vb.  
  
4.  Откройте в редакторе кода файл ApplicationEvents.vb.  В меню **Общие** выберите **События MyApplication**.  
  
5.  В меню **Объявления** выберите **UnhandledException**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> до запуска главного приложения.  
  
6.  Добавьте метод `My.Application.Log.WriteException` к обработчику событий `UnhandledException`.  
  
     [!CODE [VbVbalrMyApplicationLog#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#4)]  
  
     В следующем примере показан полный код для регистрации в журнале необработанного исключения.  
  
     [!CODE [VbVbalrMyApplicationLog#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog#5)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Пошаговое руководство. Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)