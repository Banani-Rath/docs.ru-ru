---
title: "Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic) | Microsoft Docs"
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
  - "My.Forms - объект, разработка приложений"
  - "My.WebServices - объект, разработка приложений"
  - "быстрая разработка приложений (RAD), My.Forms"
  - "быстрая разработка приложений (RAD), My.WebServices"
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объекты [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) предоставляют доступ к формам, источникам данных и веб\-службам, используемым в приложении.  Это делается путем предоставления коллекций *экземпляров по умолчанию* каждого из этих объектов.  
  
## Экземпляры по умолчанию  
 Экземпляр по умолчанию — это экземпляр класса, который предоставляется средой выполнения и не нуждается в объявлении и присвоении значения с помощью операторов `Dim` и `New`.  В следующем примере показано, как можно было бы объявить экземпляр класса <xref:System.Windows.Forms.Form> под названием `Form1` и присвоить ему значение, и как можно получить экземпляр по умолчанию этого класса <xref:System.Windows.Forms.Form> с помощью `My.Forms`.  
  
 [!CODE [VbVbcnMy#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMy#5)]  
  
 [!CODE [VbVbcnMy#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnMy#6)]  
  
 Объект `My.Forms` возвращает коллекцию экземпляров по умолчанию для каждого класса `Form`, которые есть в проекте.  Аналогичным образом, `My.WebServices` предоставляет экземпляр по умолчанию прокси\-класса для каждой веб\-службы, для которой была создана ссылка на приложение.  
  
## См. также  
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)   
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)