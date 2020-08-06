---
title: Enlazar un atributo a una columna de nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- name columns [Analysis Services]
- attributes [Analysis Services], binding
ms.assetid: 467f0cf3-8691-476d-a7fb-a5df4e374eaf
author: minewiskan
ms.author: owend
ms.openlocfilehash: e25c59d34744e7a067c2b3e83d248c4674772737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676709"
---
# <a name="bind-an-attribute-to-a-name-column"></a><span data-ttu-id="385df-102">Enlazar un atributo a una columna de nombre</span><span class="sxs-lookup"><span data-stu-id="385df-102">Bind an Attribute to a Name Column</span></span>
  <span data-ttu-id="385df-103">Este procedimiento describe cómo enlazar un atributo a una columna de nombre mediante el panel **Atributos** del Diseñador de dimensiones y el cuadro de diálogo **Enlace de objetos** .</span><span class="sxs-lookup"><span data-stu-id="385df-103">This procedure describes how to bind an attribute to a name column manually by using the **Attributes** pane in the Dimension Designer and by using the **Object Binding** dialog box.</span></span>  
  
### <a name="to-bind-an-attribute-to-a-name-column"></a><span data-ttu-id="385df-104">Para enlazar un atributo a una columna de nombre</span><span class="sxs-lookup"><span data-stu-id="385df-104">To bind an attribute to a name column</span></span>  
  
1.  <span data-ttu-id="385df-105">En el Diseñador de dimensiones, abra la dimensión en la que desea crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="385df-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="385df-106">En la pestaña **Estructura de dimensión** del panel **Atributos** , haga clic con el botón derecho en el atributo que quiera configurar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="385df-106">On the **Dimension Structure** tab, in the **Attributes** pane, right-click the attribute that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="385df-107">En la ventana **Propiedades** , busque la propiedad **NameColumn** y, después, seleccione **(nuevo)**.</span><span class="sxs-lookup"><span data-stu-id="385df-107">In the **Properties** window, locate the **NameColumn** property, and then select **(new)**.</span></span>  
  
4.  <span data-ttu-id="385df-108">En el cuadro de diálogo **Enlace de objetos** , para **Tipo de enlace**, seleccione **Enlace de columna**.</span><span class="sxs-lookup"><span data-stu-id="385df-108">In the **Object Binding** dialog box, for **Binding type**, select **Column binding**.</span></span>  
  
5.  <span data-ttu-id="385df-109">En la lista **Columna de origen** , seleccione la columna a la que se enlazará el atributo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="385df-109">In the **Source column** list, select the column to which the attribute will be bound, and then click **OK**.</span></span>  
  
  
