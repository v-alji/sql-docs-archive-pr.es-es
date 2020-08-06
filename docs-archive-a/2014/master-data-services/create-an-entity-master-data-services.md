---
title: Crear una entidad (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677183"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="cecae-102">Crear una entidad (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cecae-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="cecae-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una entidad para contener los miembros y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="cecae-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cecae-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cecae-104">Prerequisites</span></span>  
 <span data-ttu-id="cecae-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="cecae-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cecae-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="cecae-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="cecae-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="cecae-107">You must be a model administrator.</span></span> <span data-ttu-id="cecae-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cecae-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="cecae-109">Debe existir un modelo.</span><span class="sxs-lookup"><span data-stu-id="cecae-109">A model must exist.</span></span> <span data-ttu-id="cecae-110">Para obtener más información, consulte [Crear un modelo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cecae-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="cecae-111">Crear una entidad</span><span class="sxs-lookup"><span data-stu-id="cecae-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="cecae-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="cecae-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="cecae-113">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="cecae-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="cecae-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="cecae-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="cecae-115">Haga clic en **Agregar entidad**.</span><span class="sxs-lookup"><span data-stu-id="cecae-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="cecae-116">En el cuadro **nombre de entidad** , escriba el nombre de la entidad.</span><span class="sxs-lookup"><span data-stu-id="cecae-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="cecae-117">En el cuadro **nombre de las tablas de ensayo** , escriba un nombre para la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="cecae-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="cecae-118">El nombre del modelo debe formar parte del nombre de la tabla de almacenamiento provisional, por ejemplo *Nombremodelo_Nombreentidad*.</span><span class="sxs-lookup"><span data-stu-id="cecae-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="cecae-119">Esto hace que resulte más sencillo buscar tablas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cecae-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="cecae-120">Para obtener más información sobre las tablas de almacenamiento provisional, vea [importación de datos &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cecae-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="cecae-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cecae-121">Optional.</span></span> <span data-ttu-id="cecae-122">Active la casilla **Crear automáticamente valores Code** .</span><span class="sxs-lookup"><span data-stu-id="cecae-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="cecae-123">Para obtener más información, consulte [creación automática de código &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cecae-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="cecae-124">En la lista **Habilitar jerarquías explícitas y colecciones** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cecae-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="cecae-125">**No**.</span><span class="sxs-lookup"><span data-stu-id="cecae-125">**No**.</span></span> <span data-ttu-id="cecae-126">Seleccione esta opción si no necesita habilitar la entidad para las jerarquías explícitas y las colecciones.</span><span class="sxs-lookup"><span data-stu-id="cecae-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="cecae-127">Puede cambiar esta opción posteriormente, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="cecae-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="cecae-128">**Sí**.</span><span class="sxs-lookup"><span data-stu-id="cecae-128">**Yes**.</span></span> <span data-ttu-id="cecae-129">Seleccione esta opción si desea habilitar la entidad para las jerarquías explícitas y colecciones.</span><span class="sxs-lookup"><span data-stu-id="cecae-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="cecae-130">En el cuadro **nombre de jerarquía explícita** , escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="cecae-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="cecae-131">Opcionalmente, seleccione **jerarquía obligatoria (todos los miembros hoja se incluyen** para convertir la jerarquía explícita en una jerarquía obligatoria.</span><span class="sxs-lookup"><span data-stu-id="cecae-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="cecae-132">Haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="cecae-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cecae-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cecae-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="cecae-134">Crear un atributo de texto &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cecae-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="cecae-135">Crear un atributo basado en dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cecae-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="cecae-136">Crear un atributo de archivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cecae-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cecae-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cecae-137">See Also</span></span>  
 <span data-ttu-id="cecae-138">[Entidades &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cecae-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="cecae-139">[Jerarquías explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cecae-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="cecae-140">[Cambiar el nombre de una entidad &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cecae-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="cecae-141">Eliminar una entidad &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cecae-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
