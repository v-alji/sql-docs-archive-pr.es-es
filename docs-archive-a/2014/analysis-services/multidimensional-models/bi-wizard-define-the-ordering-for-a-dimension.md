---
title: Definir la ordenación de una dimensión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670658"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="4fe39-102">Definir la ordenación en una dimensión</span><span class="sxs-lookup"><span data-stu-id="4fe39-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="4fe39-103">Agregar la mejora de orden de los atributos a un cubo o una dimensión para especificar de qué manera se ordenan los miembros de un atributo.</span><span class="sxs-lookup"><span data-stu-id="4fe39-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="4fe39-104">Los miembros pueden ordenarse por el nombre o la clave del atributo, o bien por el nombre o la clave de otro atributo (en función de la relación de atributo).</span><span class="sxs-lookup"><span data-stu-id="4fe39-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="4fe39-105">De forma predeterminada, los miembros se ordenan por nombre.</span><span class="sxs-lookup"><span data-stu-id="4fe39-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="4fe39-106">Esta mejora cambia la configuración de las propiedades `OrderBy` y `OrderByAttributeID` de los atributos para una dimensión.</span><span class="sxs-lookup"><span data-stu-id="4fe39-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="4fe39-107">Para agregar el orden de atributos, se usa el Asistente de Business Intelligence y se selecciona la opción **Especificar el orden de los atributos** en la página **Elegir mejora** .</span><span class="sxs-lookup"><span data-stu-id="4fe39-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="4fe39-108">A continuación, este asistente le guía por los pasos para seleccionar una dimensión a la que desee aplicar el orden de los atributos y especificar cómo se deben ordenar los atributos para la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4fe39-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="4fe39-109">Seleccionar una dimensión</span><span class="sxs-lookup"><span data-stu-id="4fe39-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="4fe39-110">En la primera página **Especificar el orden de los atributos** del asistente, se especifica la dimensión a la que se desea aplicar el orden de los atributos.</span><span class="sxs-lookup"><span data-stu-id="4fe39-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="4fe39-111">La mejora de orden de los atributos agregada a esta dimensión seleccionada produce cambios en la dimensión.</span><span class="sxs-lookup"><span data-stu-id="4fe39-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="4fe39-112">Estos cambios son heredados por todos los cubos que incluyan la dimensión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4fe39-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="4fe39-113">Especificar el orden</span><span class="sxs-lookup"><span data-stu-id="4fe39-113">Specifying Ordering</span></span>  
 <span data-ttu-id="4fe39-114">En la segunda página **Especificar el orden de los atributos** del asistente, se especifica de qué manera se ordenan todos los atributos de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="4fe39-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="4fe39-115">En la columna **Atributo de orden** , se puede cambiar el atributo utilizado para aplicar el orden.</span><span class="sxs-lookup"><span data-stu-id="4fe39-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="4fe39-116">Si el atributo que desea usar para ordenar los miembros no se encuentra en la lista, desplácese hacia abajo en la lista y, a continuación, seleccione **\<New attribute...>** para abrir el cuadro de diálogo **seleccionar una columna** , donde puede seleccionar una columna de una tabla de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4fe39-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="4fe39-117">Al seleccionar una columna mediante el cuadro de diálogo **Seleccionar una columna** se crea un atributo adicional con el que se ordenan los miembros de un atributo.</span><span class="sxs-lookup"><span data-stu-id="4fe39-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="4fe39-118">En la columna **Criterios** , puede seleccionar si ordena los miembros del atributo por **Clave** o **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4fe39-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
