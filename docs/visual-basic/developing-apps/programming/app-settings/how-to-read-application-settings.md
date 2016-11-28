---
title: "Практическое руководство. Чтение параметров приложения в Visual Basic | Microsoft Docs"
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
  - "параметры приложения, чтение"
  - "My.Settings - объект, чтение параметров приложений"
  - "чтение параметров приложений"
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Чтение параметров приложения в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Пользовательский параметр можно прочитать с помощью свойства объекта `My.Settings`.  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства.  Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра.  Параметр **Область** показывает, доступно ли свойство только для чтения; если область задана как **Приложение**, то свойство доступно только для чтения, а если область задана как **Пользователь**, то свойство доступно для чтения и записи.  Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## Пример  
 В этом пример показывается установка значения параметра `Nickname`.  
  
 [!CODE [VbVbalrMyResources#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyResources#14)]  
  
 Для работы примера необходимо, чтобы приложение имело свойство `Nickname` типа `String`.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)