---
title: Crear un atributo basado en dominio (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662139"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="70b43-102">Crear un atributo basado en dominio (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="70b43-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="70b43-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], los administradores pueden crear un atributo basado en dominio si quieren restringir los valores de una columna a un conjunto específico de valores.</span><span class="sxs-lookup"><span data-stu-id="70b43-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="70b43-104">Los valores pueden estar ya en la hoja de cálculo o pueden proceder de una entidad existente.</span><span class="sxs-lookup"><span data-stu-id="70b43-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70b43-105"> Si los usuarios escriben un valor en la columna restringida, en lugar de seleccionarlo en la lista, los errores aparecen en la columna **$InputStatus$** al publicar.</span><span class="sxs-lookup"><span data-stu-id="70b43-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70b43-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="70b43-106">Prerequisites</span></span>  
 <span data-ttu-id="70b43-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="70b43-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="70b43-108">Debe disponer del permiso para tener acceso a las áreas funcionales del **Explorador** y de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="70b43-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="70b43-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="70b43-109">You must be a model administrator.</span></span> <span data-ttu-id="70b43-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70b43-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="70b43-111">El modelo y la entidad deben existir.</span><span class="sxs-lookup"><span data-stu-id="70b43-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="70b43-112">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="70b43-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="70b43-113">En Excel, cargue la entidad que contenga la columna (atributo) que vaya a restringir.</span><span class="sxs-lookup"><span data-stu-id="70b43-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="70b43-114">Para obtener más información, consulte [carga de datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70b43-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="70b43-115">Haga clic en cualquier celda en la columna que vaya a restringir.</span><span class="sxs-lookup"><span data-stu-id="70b43-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="70b43-116">En el grupo **Compilar modelo** , haga clic en **Propiedades de atributo**.</span><span class="sxs-lookup"><span data-stu-id="70b43-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="70b43-117">En el cuadro de diálogo **Propiedades de atributo** , en la lista **Tipo de atributo** , elija **Lista restringida (basada en dominio)**.</span><span class="sxs-lookup"><span data-stu-id="70b43-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="70b43-118">En la lista **Rellenar el atributo con valores de** :</span><span class="sxs-lookup"><span data-stu-id="70b43-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="70b43-119">Para usar valores de la hoja de cálculo, elija **la columna seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="70b43-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="70b43-120">Se creará una nueva entidad y una tabla de ensayo con los valores de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="70b43-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="70b43-121">Para usar valores de una entidad existente, elija el nombre de la entidad.</span><span class="sxs-lookup"><span data-stu-id="70b43-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="70b43-122">Si elige **la columna seleccionada** en el paso anterior, en el cuadro **Nuevo nombre de entidad** , escriba un nombre para la nueva entidad.</span><span class="sxs-lookup"><span data-stu-id="70b43-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="70b43-123">Puede ser el mismo que el nombre de la columna (atributo).</span><span class="sxs-lookup"><span data-stu-id="70b43-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="70b43-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="70b43-124">Click **OK**.</span></span> <span data-ttu-id="70b43-125">Cada celda de la columna tiene ahora una lista de valores para que los usuarios elijan.</span><span class="sxs-lookup"><span data-stu-id="70b43-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="70b43-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="70b43-126">Next Steps</span></span>  
  
-   <span data-ttu-id="70b43-127">Para agregar y eliminar los valores en la lista restringida, cargue la entidad en la que el atributo se basa.</span><span class="sxs-lookup"><span data-stu-id="70b43-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="70b43-128">Para obtener más información sobre la carga de entidades, vea [cargar datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70b43-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b43-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70b43-129">See Also</span></span>  
 <span data-ttu-id="70b43-130">[Atributos basados en dominio &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="70b43-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="70b43-131">[Cree una entidad &#40;Complemento MDS para Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="70b43-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="70b43-132">Generar un modelo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="70b43-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
