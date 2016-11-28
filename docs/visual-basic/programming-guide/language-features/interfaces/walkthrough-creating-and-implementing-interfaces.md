---
title: "Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic) | Microsoft Docs"
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
  - "реализация интерфейсов, пошаговое руководство"
  - "интерфейсы, создание"
  - "интерфейсы, проверка"
  - "интерфейсы, пошаговые руководства"
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Интерфейсы описывают характеристики свойств, методов и событий, но содержат сведения о реализации до структур и классов.  
  
 Это пошаговое руководство демонстрирует процедуры объявления и реализации интерфейса.  
  
> [!NOTE]
>  В этом пошаговом руководстве не предоставляет сведения о том, как создать пользовательский интерфейс.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Определение интерфейса  
  
1.  Откройте новый проект приложения Windows в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
2.  Добавьте в проект новый модуль, выбрав команду **Добавить модуль** в меню **Проект**.  
  
3.  Назовите новый модуль `Module1.vb` и нажмите кнопку **Добавить**.  Отобразится код нового модуля.  
  
4.  Определите интерфейс с именем `TestInterface` внутри `Module1` путем ввода `Interface TestInterface` между инструкциями `Module` и `End Module` и нажмите клавишу ENTER.  **Редактор кода** определит зарезервированное слово `Interface` и добавит инструкцию `End Interface` для формирования блока кода.  
  
5.  Определите для интерфейса свойство, метод и событие, расположив между операторами `Interface` и `End Interface` следующий код:  
  
     [!CODE [VbVbalrOOP#98](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#98)]  
  
## Реализация  
 Можно заметить, что синтаксис, используемый для объявления членов интерфейса, отличается от синтаксиса объявления членов класса.  Это отличие отражает тот факт, что интерфейсы не содержат кода реализации.  
  
#### Чтобы реализовать интерфейс  
  
1.  Добавьте класс с именем `ImplementationClass`, добавив следующую инструкцию в `Module1` после инструкции `End Interface`, но до инструкции `End Module` и нажмите клавишу ENTER:  
  
     [!CODE [VbVbalrOOP#99](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#99)]  
  
     В интегрированной среде разработки при нажатии клавиши ENTER **Редактор кода** подставит соответствующий оператор `End Class`.  
  
2.  Добавьте в класс `ImplementationClass` следующий оператор `Implements`, который определяет реализуемый классом интерфейс:  
  
     [!CODE [VbVbalrOOP#100](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#100)]  
  
     Указанный отдельно от других элементов в начале класса или структуры оператор `Implements` показывает, что класс или структура реализуют интерфейс.  
  
     При работе в среде разработки **Редактор кода** реализует члены класса, необходимые `TestInterface`, при нажатии клавиши ENTER; можно пропустить следующий шаг.  
  
3.  Если вы работаете не в интегрированной среде разработки, то необходимо реализовать все члены интерфейса `MyInterface`.  В процедуру события `ImplementationClass` добавьте следующий код для реализации `Event1`, `Method1` и `Prop1`:  
  
     [!CODE [VbVbalrOOP#101](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#101)]  
  
     Инструкция `Implements` указывает имена интерфейсов и членов реализуемых интерфейсов.  
  
4.  Завершите определение `Prop1` путем добавления закрытых полей класса, в которых хранится значение свойства:  
  
     [!CODE [VbVbalrOOP#102](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#102)]  
  
     Возвратите значение `pval` из метода Get доступа к свойства.  
  
     [!CODE [VbVbalrOOP#103](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#103)]  
  
     Установите значение `pval` в методе Set свойства.  
  
     [!CODE [VbVbalrOOP#104](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#104)]  
  
5.  Завершите определение `Method1`, добавив следующий код.  
  
     [!CODE [VbVbalrOOP#105](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#105)]  
  
#### Чтобы проверить реализацию интерфейса  
  
1.  Щелкните правой клавишей мыши форму запуска проекта в **обозревателе решений** и выберите команду **Показать код**.  Редактор покажет класс формы запуска.  По умолчанию форма запуска называется `Form1`.  
  
2.  Добавьте следующее поле `testInstance` в класс `Form1`:  
  
     [!CODE [VbVbalrOOP#120](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#120)]  
  
     При объявлении `testInstance` как `WithEvents`, класс `Form1` может обрабатывать его события.  
  
3.  Добавьте следующий обработчик событий к классу `Form1` для обработки событий, созданных `testInstance`:  
  
     [!CODE [VbVbalrOOP#106](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#106)]  
  
4.  Добавьте в класс `Form1` подпрограмму с именем `Test`, чтобы протестировать класс реализации:  
  
     [!CODE [VbVbalrOOP#107](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#107)]  
  
     Процедура `Test` создает экземпляр класса, который реализует `MyInterface`, и присваивает этот экземпляр полю `testInstance`, задает свойство и запускает метод через интерфейс.  
  
5.  Добавьте код для вызова процедуры `Test` из процедуры `Form1 Load` при запуске формы:  
  
     [!CODE [VbVbalrOOP#108](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#108)]  
  
6.  Нажав клавишу F5, запустите процедуру `Test`.  Появится сообщение "Prop1 was set to 9" \(значение свойства Prop1 установлено равным 9\).  После нажатия кнопки появится сообщение "The X parameter for Method1 is 5" \(параметр Х метода Method1 равен 5\).  Нажмите OK и появится сообщение "The event handler caught the event" \(событие перехвачено обработчиком\).  
  
## См. также  
 [Оператор Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Интерфейсы](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Оператор Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md)