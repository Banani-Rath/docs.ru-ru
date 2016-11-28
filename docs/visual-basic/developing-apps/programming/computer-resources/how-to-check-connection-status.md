---
title: "Практическое руководство. Проверка состояния подключения в Visual Basic | Microsoft Docs"
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
  - "статус соединения"
  - "подключения, проверка статуса"
  - "IsAvailable - свойство, сведения о IsAvailable"
  - "веб-подключения"
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Проверка состояния подключения в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> позволяет определить наличие рабочей сети или подключения к Интернету на компьютере.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Проверка наличия рабочего подключения на компьютере  
  
-   Определите значение свойства `IsAvailable`: `True` или `False`.  Следующий код проверяет значение свойства и сообщает его.  
  
     [!CODE [VbResourceTasks#3](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#3)]  
  
     Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Связь и сеть**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>