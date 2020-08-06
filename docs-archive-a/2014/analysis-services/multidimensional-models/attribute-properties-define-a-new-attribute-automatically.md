---
title: Definir un nuevo atributo automáticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- automatic attribute creation
- attributes [Analysis Services], creating
ms.assetid: 208a050a-5e2f-470c-b645-8d835e123db7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 40f9ae1f00dd0a6520c6d1b06111864fba02e8f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750346"
---
# <a name="define-a-new-attribute-automatically"></a><span data-ttu-id="00167-102">Definir un nuevo atributo automáticamente</span><span class="sxs-lookup"><span data-stu-id="00167-102">Define a New Attribute Automatically</span></span>
  <span data-ttu-id="00167-103">Puede crear un atributo nuevo en una dimensión con la edición de tipo arrastrar y colocar del Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="00167-103">You can create a new attribute in a dimension by using drag-and-drop editing in the Dimension Designer.</span></span>  
  
### <a name="to-create-a-new-attribute-automatically"></a><span data-ttu-id="00167-104">Para crear un nuevo atributo automáticamente</span><span class="sxs-lookup"><span data-stu-id="00167-104">To create a new attribute automatically</span></span>  
  
1.  <span data-ttu-id="00167-105">En el Diseñador de dimensiones, abra la dimensión en la que desea crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="00167-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="00167-106">En la pestaña **Estructura de dimensión** , en el panel **Vista del origen de datos** , seleccione la columna dentro de la tabla a la que desee enlazar el atributo y arrástrela al panel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="00167-106">On the **Dimension Structure** tab, in the **Data Source View** pane, in the table to which you want to bind the attribute, select the column, and then drag the column to the **Attributes** pane.</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="00167-107">crea el nuevo atributo con el mismo nombre que la columna con la que está enlazado.</span><span class="sxs-lookup"><span data-stu-id="00167-107">creates the new attribute that has the same name as the column to which it is bound.</span></span> <span data-ttu-id="00167-108">Si hay varios atributos que utilizan la misma columna, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] anexará un número al nombre de atributo.</span><span class="sxs-lookup"><span data-stu-id="00167-108">If there are multiple attributes that use the same column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] appends a number to the attribute name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00167-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00167-109">See Also</span></span>  
 <span data-ttu-id="00167-110">[Dimensiones en modelos multidimensionales](dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="00167-110">[Dimensions in Multidimensional Models](dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="00167-111">Referencia de las propiedades de los atributos de dimensión</span><span class="sxs-lookup"><span data-stu-id="00167-111">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
