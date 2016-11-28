---
title: "Практическое руководство. Группирование значений связанных констант (Visual Basic) | Microsoft Docs"
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
  - "константы, группирование"
  - "перечисления [Visual Basic], константы"
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Практическое руководство. Группирование значений связанных констант (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Перечисление является лучшим способом группирования связанных констант.  Перечисления создаются в разделе объявлений класса или модуля с помощью оператора `Enum`.  Дополнительные сведения см. в разделе [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### Группирование связанных постоянных значений  
  
1.  Создайте объявление, включающее уровень доступа к коду, ключевое слово `Enum` и допустимое имя.  В данном примере создается перечисление типа `Private` — `temperatureValues`.  
  
     [!CODE [VbEnumsTask#21](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#21)]  
  
2.  Определите константы в перечислении.  В данном примере создается перечисление типа `Public` — `temperatureValues`, и ему присваиваются значения.  
  
     [!CODE [VbEnumsTask#1](../CodeSnippet/VS_Snippets_VBCSharp/VbEnumsTask#1)]  
  
## См. также  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)