---
title: "Воспроизведение звуков (Visual Basic) | Microsoft Docs"
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
  - "My.Computer.Audio - объект, задачи"
  - "воспроизведение звуков"
  - "воспроизведение звуков, Visual Basic"
  - "звуковые циклы"
  - "звуки, фон"
  - "звуки, воспроизведение"
  - "системные звуки"
  - "системные звуки, воспроизведение"
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Воспроизведение звуков (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `My.Computer.Audio` предоставляет методы воспроизведения звука.  
  
## Воспроизведение звуков  
 Воспроизведение в фоновом режиме позволяет приложению выполнять другой код во время воспроизведения звука.  Метод `My.Computer.Audio.Play` позволяет воспроизводить в приложении только один фоновый звук в каждый момент времени. При воспроизведении нового звука в фоновом режиме в приложении воспроизведение предыдущего звука прекращается.  Можно также воспроизвести звуковой сигнал и дождаться его завершения, см. раздел.  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.  Если `AudioPlayMode.WaitToComplete` определен, `My.Computer.Audio.Play` ожидает полного завершения воспроизведения звука, прежде чем выполнение вызывающего кода продолжится.  При использовании этого примера необходимо убедиться, что имя файла звуковому wav, который относится к файлу на локальном компьютере  
  
 [!CODE [VbVbalrMyComputer#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#15)]  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.  При использовании этого примера необходимо убедиться, что ресурсы приложения включают звуковой wav\-файл с именем Водопадом.  
  
 [!CODE [VbVbalrMyComputer#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#16)]  
  
## Циклическое воспроизведение звуков  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме при `PlayMode.BackgroundLoop` указано.  При использовании этого примера необходимо убедиться, что имя файла звуковому wav, который относится к файлу на локальном компьютере.  
  
 [!CODE [VbVbalrMyComputer#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#11)]  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме при `PlayMode.BackgroundLoop` указано.  При использовании этого примера необходимо убедиться, что ресурсы приложения включают звуковой wav\-файл с именем Водопадом.  
  
 [!CODE [VbVbalrMyComputer#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#12)]  
  
 В предыдущем примере кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он расположен в разделе **Приложения Windows Forms \> Звук**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
 В общем случае при циклическом воспроизведении звука приложение должно будет остановить его в некоторый момент.  
  
## Остановка воспроизведения звуков в фоновом режиме  
 Используйте метод `My.Computer.Audio.Stop` для остановки текущего воспроизведения фонового или циклического звука в приложении.  
  
 В стандартной ситуации во время циклического воспроизведения звука приложение должно останавливать воспроизведение в некоторый момент.  
  
 В следующем примере останавливается, который воспроизводит звук в фоновом режиме.  
  
 [!CODE [VbVbalrMyComputer#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#18)]  
  
 В предыдущем примере кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он расположен в разделе **Приложения Windows Forms \> Звук**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## Воспроизведение системных звуков  
 Используйте метод `My.Computer.Audio.PlaySystemSound` для воспроизведения указанного системного звука.  
  
 Метод `My.Computer.Audio.PlaySystemSound` принимает в качестве параметра один из общих членов класса <xref:System.Media.SystemSound>.  Системный звук <xref:System.Media.SystemSounds.Asterisk%2A> обычно обозначает ошибку.  
  
 В следующем примере используется метод `My.Computer.Audio.PlaySystemSound` для воспроизведения системного звука.  
  
 [!CODE [VbVbalrMyComputer#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyComputer#17)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>