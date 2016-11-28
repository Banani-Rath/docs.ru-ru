---
title: "Указано недопустимое имя для журнала событий | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Указано недопустимое имя для журнала событий
Для журнала событий было указано недопустимое имя. Обычно это является результатом недопустимых символов в имени, пустого имени файла или слишком длинного имени файла.  
  
### Исправление ошибки  
  
-   Если указанное имя содержит более восьми символов, убедитесь, что отсутствует конфликт с именами других журналов событий. При определении уникальности имени оцениваются только первые восемь символов.  
  
-   Если указывается путь, убедитесь, что он анализируется правильно.  
  
-   Проверьте имя на наличие недопустимых символов. Символы, которые нельзя использовать в имени файла: `<`, `>`, `:`, `"`, `/`, `\` и `|`.  
  
## См. также  
 [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)   
 [Практическое руководство. Переименование файла](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)   
 [How to: Create and Remove Custom Event Logs](http://msdn.microsoft.com/ru-ru/af9b7da0-80c7-46ac-b7f7-897063ddd503)