---
title: Agregar un atributo a una dimensión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677250"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="3c8a0-102">Incorporación de un atributo a una dimensión</span><span class="sxs-lookup"><span data-stu-id="3c8a0-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="3c8a0-103">Puede Agregar un atributo a una dimensión de forma automática o manual en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c8a0-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3c8a0-104">Para crear un atributo automáticamente, en la pestaña **Estructura de dimensión** del Diseñador de dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], seleccione la columna que desea asignar a un atributo y, a continuación, arrastre dicha columna desde el panel **Vista del origen de datos** al panel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="3c8a0-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="3c8a0-105">De esta forma se crea un atributo que se asigna a la columna, y asigna el mismo nombre al atributo que el nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="3c8a0-106">Si un atributo que utiliza dicho nombre ya existe, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] agregará un sufijo de número ordinal que empiece por "1" para el primer nombre duplicado.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="3c8a0-107">Para crear un atributo manualmente, establezca el panel **Atributos** en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="3c8a0-108">En la columna Nombre de la última fila de la cuadrícula, haga clic en el **\<new attribute>** elemento.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="3c8a0-109">Escriba un nombre para el nuevo atributo.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-109">Type a name for the new attribute.</span></span> <span data-ttu-id="3c8a0-110">De esta forma se crea un atributo que no se relaciona con una columna y que tiene la configuración predeterminada para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="3c8a0-111">Puede establecer la correlación en la ventana **Propiedades** de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] configurando la propiedad **KeyColumns** para el nuevo atributo.</span><span class="sxs-lookup"><span data-stu-id="3c8a0-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="3c8a0-112">Para obtener más información, vea [Definir un nuevo atributo automáticamente](attribute-properties-define-a-new-attribute-automatically.md), [Definir un nuevo atributo manualmente](../define-a-new-attribute-manually.md), [Enlazar un atributo a una columna de nombre](attribute-properties-bind-an-attribute-to-a-name-column.md)y [Modificar la propiedad KeyColumns de un atributo](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="3c8a0-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8a0-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c8a0-113">See Also</span></span>  
 [<span data-ttu-id="3c8a0-114">Referencia de las propiedades de los atributos de dimensión</span><span class="sxs-lookup"><span data-stu-id="3c8a0-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
