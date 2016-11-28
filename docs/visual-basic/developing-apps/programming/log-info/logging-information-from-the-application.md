---
title: "Запись сведений в журнал из приложения (Visual Basic) | Microsoft Docs"
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
  - "приложения [Visual Basic], запись сведений в журнал"
  - "примеры [Visual Basic], запись сведений приложения в журнал"
  - "Log - объект"
  - "ведение журналов"
  - "My.Application.Log - объект"
  - "My.Log - объект"
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Запись сведений в журнал из приложения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Этот раздел содержит сведения о том, как регистрировать в журнале информацию из приложения с помощью объектов `My.Application.Log` или `My.Log` и как расширить возможности ведения журнала в приложении.  
  
 Объект `Log` предоставляет методы для записи информации в прослушиватели журнала приложения, а свойство объекта `Log` `TraceSource` — подробные сведения о конфигурации.  Объект `Log` настраивается в файле конфигурации приложения.  
  
 Объект `My.Log` доступен только для приложений ASP.NET.  Для клиентских приложений следует использовать объект `My.Application.Log`.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## Задачи  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Запись информации о событиях в журналы приложения.|[Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Запись информации об исключениях в журналы приложения.|[Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Запись данных трассировки в журналы приложения во время запуска и завершения работы приложения.|[Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Настройка объекта `My.Application.Log` для записи информации в текстовый файл.|[Практическое руководство. Запись сведений о событиях в текстовый файл](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Настройка объекта `My.Application.Log` для записи информации в журнал событий.|[Практическое руководство. Запись в журнал событий приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Изменение места, в которое объект `My.Application.Log` записывает информацию.|[Пошаговое руководство. Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Выбор места, в которое объект `My.Application.Log` записывает информацию.|[Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Создание пользовательского прослушивателя журнала для `My.Application.Log`.|[Пошаговое руководство. Создание пользовательских прослушивателей журнала](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Фильтрация выходных данных журналов `My.Application.Log`.|[Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Устранение неполадок, связанных с прослушивателями журнала](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)