---
title: Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 5df3a201eaae4ddcf2e5d5aac3de6e0d5013947c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353404"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
В следующем примере <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> используется для анимации положения <xref:System.Windows.Media.Media3D.PerspectiveCamera> в трехмерной сцене. Кроме того <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для направления указывает камеры в трехмерной сцене. Эти анимации используйте несколько ключевых кадров, которые создают серию эффектов анимации:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания скачкообразные «переходы» между значениями (без интерполяции).  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для, создают переменный переход между значениями в зависимости от <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> свойство. В приведенном ниже примере анимация начинается медленно, но к концу временного сегмента, экспоненциально ускоряется.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>См. также
- [Анимация положения и направления камеры в трехмерной сцене](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [Обзор трехмерной графики](3-d-graphics-overview.md)
