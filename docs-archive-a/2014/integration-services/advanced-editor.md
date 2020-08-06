---
title: Editor avanzado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670528"
---
# <a name="advanced-editor"></a><span data-ttu-id="f63d6-102">Editor avanzado</span><span class="sxs-lookup"><span data-stu-id="f63d6-102">Advanced Editor</span></span>
  <span data-ttu-id="f63d6-103">Use el cuadro de diálogo **Editor avanzado** para configurar las propiedades del objeto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f63d6-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="f63d6-104">El **Editor avanzado** está disponible para la mayor parte de los objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tienen propiedades que pueden configurarse.</span><span class="sxs-lookup"><span data-stu-id="f63d6-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="f63d6-105">Es el único editor disponible para aquellos objetos que no muestran una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="f63d6-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f63d6-106">tienen propiedades que se pueden establecer en el nivel de componente, en el nivel de entrada y salida, y en el nivel de columna de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="f63d6-106">data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="f63d6-107">El **Editor avanzado** enumera todas las propiedades comunes y personalizadas del objeto seleccionado y las muestra, según corresponda, en un máximo de cuatro de las cinco pestañas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f63d6-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="f63d6-108">**Administradores de conexión** : use esta pestaña para establecer las propiedades de conexión.</span><span class="sxs-lookup"><span data-stu-id="f63d6-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="f63d6-109">**Propiedades de componente** : use esta pestaña para establecer propiedades en el nivel de componente.</span><span class="sxs-lookup"><span data-stu-id="f63d6-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="f63d6-110">**Asignaciones de columnas** : use esta pestaña para asignar columnas disponibles como columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="f63d6-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="f63d6-111">**Columnas de entrada** : use esta pestaña para seleccionar columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="f63d6-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="f63d6-112">**Propiedades de entrada y salida** : use esta pestaña para establecer propiedades de entrada y salida; para agregar y eliminar salidas, seleccione o quite columnas de las entradas y las salidas, y establezca propiedades de las entradas y las salidas.</span><span class="sxs-lookup"><span data-stu-id="f63d6-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="f63d6-113">Las propiedades que se muestran varían en función del componente.</span><span class="sxs-lookup"><span data-stu-id="f63d6-113">The properties displayed vary by component.</span></span> <span data-ttu-id="f63d6-114">Para obtener más información sobre las propiedades que pueden mostrarse en el **Editor avanzado**, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f63d6-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f63d6-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="f63d6-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="f63d6-116">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="f63d6-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="f63d6-117">Propiedades de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f63d6-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="f63d6-118">Para obtener más información acerca del componente específico que está editando, vea su descripción en la sección Elementos de flujo de datos de la documentación de Objetos y conceptos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f63d6-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="f63d6-119">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f63d6-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="f63d6-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f63d6-120">See Also</span></span>  
 [<span data-ttu-id="f63d6-121">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f63d6-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
