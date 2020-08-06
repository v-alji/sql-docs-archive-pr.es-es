---
title: Importación de datos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663019"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="53875-102">Importación de datos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="53875-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="53875-103">Una vez que haya creado un modelo para los datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede empezar a agregar datos y a realizar cambios en los datos de la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53875-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="53875-104">Puede usar tablas de almacenamiento provisional de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , procedimientos almacenados y Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="53875-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="53875-105">También puede usar el [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] para agregar datos al repositorio de MDS (base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="53875-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="53875-106">Para obtener más información, vea [publicar datos &#40;Complemento MDS para Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="53875-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="53875-107">Al agregar y actualizar los datos, puede hacer lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="53875-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="53875-108">Cargar y actualizar miembros, así como actualizar valores de atributo</span><span class="sxs-lookup"><span data-stu-id="53875-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="53875-109">Desactivar o eliminar miembros</span><span class="sxs-lookup"><span data-stu-id="53875-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="53875-110">Mover miembros de jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="53875-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="53875-111">La adición y la actualización de datos incluyen las siguientes tareas principales.</span><span class="sxs-lookup"><span data-stu-id="53875-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="53875-112">Cargar datos en las tablas de almacenamiento provisional en la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53875-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="53875-113">Cargar datos de las tablas de almacenamiento provisional en las tablas adecuadas de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53875-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="53875-114">Puede usar los procedimientos almacenados de almacenamiento provisional o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para cargar los datos.</span><span class="sxs-lookup"><span data-stu-id="53875-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="53875-115">En [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], la compatibilidad con los procesos de almacenamiento provisional de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] está en desuso.</span><span class="sxs-lookup"><span data-stu-id="53875-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="53875-116">Desactivación y eliminación de miembros</span><span class="sxs-lookup"><span data-stu-id="53875-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="53875-117">La desactivación significa que el miembro se puede reactivar.</span><span class="sxs-lookup"><span data-stu-id="53875-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="53875-118">Si reactiva un miembro, se restauran sus atributos y su pertenencia a jerarquías y colecciones.</span><span class="sxs-lookup"><span data-stu-id="53875-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="53875-119">Todas las transacciones anteriores quedan intactas.</span><span class="sxs-lookup"><span data-stu-id="53875-119">All previous transactions are intact.</span></span> <span data-ttu-id="53875-120">Las transacciones desactivación son visibles para los administradores en el área funcional de **Administración de versiones** de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="53875-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="53875-121">Eliminar significa purgar el miembro del sistema permanentemente.</span><span class="sxs-lookup"><span data-stu-id="53875-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="53875-122">Todas las transacciones del miembro, todas las relaciones y todos los atributos se eliminan de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="53875-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="53875-123">No se puede utilizar el almacenamiento provisional para reactivar los miembros.</span><span class="sxs-lookup"><span data-stu-id="53875-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="53875-124">Se debe hacer manualmente en Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="53875-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="53875-125">Para obtener más información, consulte [Reactivar un miembro o una colección &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53875-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="53875-126">No se puede utilizar el almacenamiento provisional para eliminar o desactivar colecciones.</span><span class="sxs-lookup"><span data-stu-id="53875-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="53875-127">Para obtener más información sobre cómo desactivar colecciones de forma manual, consulte [Eliminar un miembro o una colección &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53875-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="53875-128">Movimiento de miembros de jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="53875-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="53875-129">Al mover la ubicación de los miembros de jerarquías explícitas de forma masiva, puede designar lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="53875-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="53875-130">Un miembro consolidado como elemento primario de un miembro consolidado.</span><span class="sxs-lookup"><span data-stu-id="53875-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="53875-131">Un miembro consolidado como elemento primario de un miembro hoja.</span><span class="sxs-lookup"><span data-stu-id="53875-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="53875-132">Un miembro hoja es un elemento relacionado de una hoja o de un miembro consolidado.</span><span class="sxs-lookup"><span data-stu-id="53875-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="53875-133">Un miembro consolidado es un elemento relacionado de una hoja o de un miembro consolidado.</span><span class="sxs-lookup"><span data-stu-id="53875-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="53875-134">Tablas y procedimientos almacenados de de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="53875-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="53875-135">La base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] incluye los siguientes tipos de tablas de almacenamiento provisional que puede rellenar con sus datos.</span><span class="sxs-lookup"><span data-stu-id="53875-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="53875-136">Tabla de almacenamiento provisional de miembros hoja &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="53875-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="53875-137">Tabla de almacenamiento provisional de miembros consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="53875-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="53875-138">Tabla de almacenamiento provisional de relaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="53875-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="53875-139">Para cada entidad del modelo, hay una tabla de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="53875-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="53875-140">El nombre de la tabla indica la entidad correspondiente y el tipo de entidad, como miembro hoja.</span><span class="sxs-lookup"><span data-stu-id="53875-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="53875-141">La siguiente imagen muestra las tablas de almacenamiento provisional de las entidades de moneda, cliente y producto.</span><span class="sxs-lookup"><span data-stu-id="53875-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="53875-142">![Tablas de almacenamiento provisional en la base de datos MDS](../../2014/master-data-services/media/mds-stagingtables.png "Tablas de almacenamiento provisional en la base de datos MDS")</span><span class="sxs-lookup"><span data-stu-id="53875-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="53875-143">El nombre de cada tabla se especifica cuando se crea una entidad y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="53875-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="53875-144">Si el nombre de la tabla de ensayo contiene _1 u otro número, otra tabla con ese nombre ya existía cuando se creó la entidad.</span><span class="sxs-lookup"><span data-stu-id="53875-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="53875-145">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] incluye los siguientes tipos de procedimientos almacenados de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="53875-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="53875-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="53875-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="53875-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="53875-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="53875-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="53875-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="53875-149">Para cada entidad del modelo, hay tres procedimientos almacenados que corresponden a las tablas de almacenamiento provisional de miembros hoja, miembros consolidados y relaciones.</span><span class="sxs-lookup"><span data-stu-id="53875-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="53875-150">La siguiente imagen muestra los procedimientos almacenados de almacenamiento provisional de las entidades de moneda, cliente y producto.</span><span class="sxs-lookup"><span data-stu-id="53875-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="53875-151">![Procedimientos almacenados de almacenamiento provisional en la base de datos MDS](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Procedimientos almacenados de almacenamiento provisional en la base de datos MDS")</span><span class="sxs-lookup"><span data-stu-id="53875-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="53875-152">Para obtener más información sobre los procedimientos almacenados, consulte [Procedimiento almacenado de almacenamiento provisional &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53875-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="53875-153">Registrar transacciones</span><span class="sxs-lookup"><span data-stu-id="53875-153">Logging Transactions</span></span>
 <span data-ttu-id="53875-154">Se pueden registrar todas las transacciones que se producen cuando se importan o actualizan datos o relaciones.</span><span class="sxs-lookup"><span data-stu-id="53875-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="53875-155">Una opción del procedimiento almacenado permite este registro.</span><span class="sxs-lookup"><span data-stu-id="53875-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="53875-156">Si inicia el proceso de almacenamiento provisional mediante [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no se realiza ningún registro.</span><span class="sxs-lookup"><span data-stu-id="53875-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="53875-157">En [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], el valor de **Registrar todas las transacciones de almacenamiento provisional** no se aplica a este método de almacenamiento provisional de datos.</span><span class="sxs-lookup"><span data-stu-id="53875-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="53875-158">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="53875-158">Related Content</span></span>

-   [<span data-ttu-id="53875-159">Validación &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="53875-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="53875-160">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="53875-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)


