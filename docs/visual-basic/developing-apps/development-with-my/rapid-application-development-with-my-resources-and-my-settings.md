---
title: "Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic) | Microsoft Docs"
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
  - "My.Resources - объект, разработка приложений"
  - "My.Settings - объект, разработка приложений"
  - "быстрая разработка приложений (RAD), My.Resources"
  - "быстрая разработка приложений (RAD), My.Settings"
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объект `My.Resources` предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения.  
  
## Извлечение ресурсов  
 С помощью объекта `My.Resources` можно извлекать ряд ресурсов, таких как звуковые файлы, значки, изображения и строки.  Например, можно получить доступ к файлам ресурсов приложения, относящихся к определенному языку и региональным параметрам.  В следующем примере значку формы присваивается значок `Form1Icon`, хранящийся в файле ресурсов приложения.  
  
 [!CODE [VbVbcnMy#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMy#7)]  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы.  Он не обеспечивает доступа к файлам ресурсов, связанных с формами.  К ресурсам формы необходимо получать доступ из формы.  Дополнительные сведения см. в разделе [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Аналогично, объект `My.Settings` предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения приложения.  Дополнительные сведения см. в разделах [Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) и [Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## См. также  
 [Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)   
 [Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Доступ к параметрам приложения](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)