---
title: "Тип необязательного значения для необязательного параметра &lt;имяПараметра&gt; несовместим с CLS | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC40042"
  - "vbc40042"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40042"
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Тип необязательного значения для необязательного параметра &lt;имяПараметра&gt; несовместим с CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Процедура помечена как `<CLSCompliant(True)>`, но объявляет параметр [Optional](../../../visual-basic/language-reference/modifiers/optional.md) со значением по умолчанию несовместимого типа.  
  
 Для совместимости процедуры с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) она должна использовать только CLS–совместимые типы.  Это относится к типам параметров, возвращаемому типу и типам всех ее локальных переменных.  Это также относится к значениям по умолчанию для необязательных параметров.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру `isCompliant` атрибута присваивается значение `True` или `False`, чтобы указать совместимость или несовместимость соответственно.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, то он считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40042  
  
### Чтобы исправить эту ошибку  
  
-   Если необязательный параметр должен иметь значение по умолчанию этого конкретного типа, удалите атрибут <xref:System.CLSCompliantAttribute>.  Процедура не может быть CLS–совместимой.  
  
-   Если процедура должна быть CLS\-совместимой, измените тип этого значения по умолчанию на ближайший CLS\-совместимый тип.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если производится взаимодействие с объектами автоматизации или COM–объектами, то имейте в виду, что некоторые типы имеют ширину данных, отличающуюся от ширины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] .  Например, в других средах тип `int` часто является 16\-разрядным.  Если из таких компонентов принимается 16\-разрядное целое число, следует объявить его в качестве `Short` вместо `Integer` в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## См. также  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)