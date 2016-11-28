---
title: "Виртуальные режим в элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater"
  - "DataRepeater, виртуальный режим"
  - "виртуальная привязка данных"
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Виртуальные режим в элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Если требуется отобразить большой объем табличных данных в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, можно улучшить производительность, установив свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> равным `True`, и явным образом управляя взаимодействием элемента управления с источником данных.  Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> предоставляет несколько событий, которые можно обрабатывать при взаимодействии с источником данных и при необходимости отображать с их помощью данные во время выполнения.  
  
## Как работает виртуальный режим  
 Наиболее распространенным сценарием для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> является привязка дочерних элементов управления шаблона <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> к источнику данных на этапе разработки и разрешение <xref:System.Windows.Forms.BindingSource> передавать данные в обе стороны при необходимости.  При использовании виртуального режима элемент управления не привязывается к источнику данных и данные передаются в источник данных и обратно для привязки к источнику данных во время выполнения.  
  
 Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> установлено равным `True`, можно создать пользовательский интерфейс, добавив элементы управления из меню **Панель элементов** вместо того, чтобы добавлять связанные элементы управления из окна **Источники данных**.  
  
 События происходят для каждого отдельного элемента управления и необходимо добавить код для обработки вывода данных.  Когда новый элемент <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> попадает в область просмотра, одновременно происходит событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> для каждого элемента управления, и необходимо предоставить значения для каждого элемента управления в обработчик событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>.  
  
 Если данные одного из элементов управления изменяются пользователем, вызывается событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> и пользователю необходимо подтвердить данные для записи их в источник данных.  
  
 Если пользователь добавил новый элемент, вызывается событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>.  Используйте этот обработчик событий для создания новой записи в источнике данных.  Чтобы предотвратить ненамеренное изменение, необходимо также проверить событие <xref:System.Windows.Forms.Control.KeyDown> для каждого элемента управления и вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>, если пользователь нажмет ESC.  
  
 В случае изменения источника данных можно обновить элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, вызвав методы <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetTemplateItem%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetTemplateItem%2A>.  Оба метода должны быть вызваны в нужном порядке.  
  
 Наконец, следует реализовать обработчики событий для события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>, происходящего при удалении элемента и по возможности для событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>, происходящих при любом удалении элемента пользователем при помощи кнопки DELETE.  
  
## Реализация виртуального режима  
 Следуйте поэтапно шагам, необходимым для реализации виртуального режима.  
  
#### Чтобы реализовать виртуальный режим  
  
1.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> из вкладки **Visual Basic PowerPacks** в **панели элементов** на форму или контейнерный элемент управления.  Установите для свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> значение `True`.  
  
2.  Перетащите элементы управления из **панели элементов** в область шаблона элементов \(верхняя область\) элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Для каждого в источнике данных, которое требуется отобразить, потребуется создать отдельный элемент управления.  
  
3.  Реализуйте обработчик события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>, чтобы предоставить значения для каждого элемента управления.  Это событие происходит при появлении нового элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в области просмотра.  Код будет выглядеть как в следующем примере, написанном для источника данных с именем `Employees`.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#1](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#1)]  
  
4.  Реализуйте обработчик для события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>, чтобы сохранить данные.  Это событие происходит при фиксировании пользователем изменений в элементах управления, дочерних элементу <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  Код будет выглядеть как в следующем примере, написанном для источника данных с именем `Employees`.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#2](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#2)]  
  
5.  Реализуйте обработчик для каждого события <xref:System.Windows.Forms.Control.KeyDown> дочернего элемента управления и проверки, не нажал ли пользователь ESC.  Вызовите метод <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> для предотвращения возникновения события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>.  Код будет аналогичен коду, который приведен в следующем примере.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#3](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#3)]  
  
6.  Реализуйте обработчик события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>.  Это событие происходит при добавлении пользователем нового элемента в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Код будет выглядеть как в следующем примере, написанном для источника данных с именем `Employees`.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#4](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#4)]  
  
7.  Реализуйте обработчик события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>.  Это событие происходит, если пользователь удаляет существующий элемент.  Код будет выглядеть как в следующем примере, написанном для источника данных с именем `Employees`.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#5](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#5)]  
  
8.  Для проверки на уровне элемента управления, можно реализовать обработчики для событий <xref:System.Windows.Forms.Control.Validating> дочерних элементов управления.  Код будет аналогичен коду, который приведен в следующем примере.  
  
     [!CODE [VbPowerPacksDataRepeaterVirtualMode#6](../CodeSnippet/VS_Snippets_VBCSharp/VbPowerPacksDataRepeaterVirtualMode#6)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)