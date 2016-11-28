---
title: "Практическое руководство. Передача файла в Visual Basic | Microsoft Docs"
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
  - "файлы, отправка"
  - "My.Computer.Network.UploadFile - метод"
  - "сети, отправка файлов"
  - "UploadFile - метод"
  - "отправка файлов"
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Передача файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Для загрузки файла и хранения его в удаленном расположении можно использовать метод <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>.  Если параметр `ShowUI` имеет значение `True`, то отображается диалоговое окно, показывающее ход загрузки и позволяющее пользователю отменить операцию.  
  
### Передача файла  
  
-   Для передачи файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI \(универсального кода ресурса\). В этом примере файл `Order.txt` передается на веб\-узел `http://www.cohowinery.com/uploads.aspx`.  
  
     [!CODE [VbResourceTasks#6](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#6)]  
  
### Передача файла с отображением хода выполнения операции  
  
-   Для передачи файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI.  В этом примере файл `Order.txt` передается на веб\-узел `http://www.cohowinery.com/uploads.aspx` без указания имени пользователя или пароля, при этом отображается ход передачи. Время ожидания равно 500 миллисекундам.  
  
     [!CODE [VbResourceTasks#7](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#7)]  
  
### Передача файла с указанием имени пользователя и пароля  
  
-   Для загрузки файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI, а также имя пользователя и пароль.  В этом примере файл `Order.txt` передается на веб\-узел `http://www.cohowinery.com/uploads.aspx` с указанием имени пользователя `anonymous` и пустого пароля.  
  
     [!CODE [VbResourceTasks#8](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#8)]  
  
## Отказоустойчивость  
 Исключение может возникнуть при следующих условиях:  
  
-   Путь локального файла не является допустимым \(<xref:System.ArgumentException>\).  
  
-   Проверка подлинности не пройдена \(<xref:System.Security.SecurityException>\).  
  
-   Истекло время ожидания подключения \(<xref:System.TimeoutException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>   
 [Практическое руководство. Загрузка файла](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)   
 [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)