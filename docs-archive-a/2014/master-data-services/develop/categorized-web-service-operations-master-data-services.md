---
title: Operaciones de servicio web clasificadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675491"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="24fbb-102">Operaciones de servicio web clasificadas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="24fbb-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="24fbb-103">El servicio web de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] contiene un conjunto completo de operaciones que le permiten escribir código para controlar todas las características que proporciona [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] a través de su interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="24fbb-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="24fbb-104">Las operaciones del servicio web se definen mediante la interfaz <xref:Microsoft.MasterDataServices.IService> y se implementan como métodos en la clase <xref:Microsoft.MasterDataServices.ServiceClient>.</span><span class="sxs-lookup"><span data-stu-id="24fbb-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="24fbb-105">En este tema se agrupan las operaciones del servicio web en categorías conceptuales para ayudarle a entender cómo se usa la API del servicio web.</span><span class="sxs-lookup"><span data-stu-id="24fbb-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="24fbb-106">Operaciones de modelo</span><span class="sxs-lookup"><span data-stu-id="24fbb-106">Model Operations</span></span>  
 <span data-ttu-id="24fbb-107">Estas operaciones se utilizan para crear, actualizar y eliminar modelos, así como para usar todo el contenido del modelo, como entidades, jerarquías y versiones.</span><span class="sxs-lookup"><span data-stu-id="24fbb-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="24fbb-108">Para obtener más información, consulte [Modelos &#40;Master Data Services&#41;](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="24fbb-109">Operaciones de entidad</span><span class="sxs-lookup"><span data-stu-id="24fbb-109">Entity Operations</span></span>  
 <span data-ttu-id="24fbb-110">Estas operaciones se utilizan para crear, actualizar y eliminar los miembros de una sola entidad.</span><span class="sxs-lookup"><span data-stu-id="24fbb-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="24fbb-111">Para más información, vea [Entidades &#40;Master Data Services&#41;](../entities-master-data-services.md) y [Miembros &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="24fbb-112">Operaciones de miembro</span><span class="sxs-lookup"><span data-stu-id="24fbb-112">Member Operations</span></span>  
 <span data-ttu-id="24fbb-113">Estas operaciones se utilizan para obtener, actualizar y eliminar miembros.</span><span class="sxs-lookup"><span data-stu-id="24fbb-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="24fbb-114">El conjunto de miembros con los que se trabaja puede contener miembros de varias entidades.</span><span class="sxs-lookup"><span data-stu-id="24fbb-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="24fbb-115">Para obtener más información, consulte [Miembros &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="24fbb-116">Operaciones de atributo y jerarquía</span><span class="sxs-lookup"><span data-stu-id="24fbb-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="24fbb-117">Estas operaciones se utilizan para obtener información de atributos y jerarquías.</span><span class="sxs-lookup"><span data-stu-id="24fbb-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="24fbb-118">Los atributos y las jerarquías se pueden modificar también mediante las operaciones de modelo, como <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="24fbb-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="24fbb-119">Para más información, vea [Atributos &#40;Master Data Services&#41;](../attributes-master-data-services.md) y [Jerarquías &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="24fbb-120">Operaciones de regla de negocio</span><span class="sxs-lookup"><span data-stu-id="24fbb-120">Business Rule Operations</span></span>  
 <span data-ttu-id="24fbb-121">Estas operaciones se utilizan para crear, actualizar, eliminar y publicar reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="24fbb-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="24fbb-122">Para más información, vea [Reglas de negocios &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="24fbb-123">Operaciones de anotación</span><span class="sxs-lookup"><span data-stu-id="24fbb-123">Annotation Operations</span></span>  
 <span data-ttu-id="24fbb-124">Estas operaciones se utilizan para crear, actualizar y eliminar anotaciones.</span><span class="sxs-lookup"><span data-stu-id="24fbb-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="24fbb-125">Para más información, vea [Anotaciones &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="24fbb-126">Operaciones de transacción</span><span class="sxs-lookup"><span data-stu-id="24fbb-126">Transaction Operations</span></span>  
 <span data-ttu-id="24fbb-127">Estas operaciones se utilizan para obtener y revertir transacciones.</span><span class="sxs-lookup"><span data-stu-id="24fbb-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="24fbb-128">Para obtener más información, consulte [Transacciones &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="24fbb-129">Operaciones de versión y validación</span><span class="sxs-lookup"><span data-stu-id="24fbb-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="24fbb-130">Estas operaciones se utilizan para copiar y validar versiones.</span><span class="sxs-lookup"><span data-stu-id="24fbb-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="24fbb-131">Para más información, vea [Versiones &#40;Master Data Services&#41;](../versions-master-data-services.md) y [Validación &#40;Master Data Services&#41;](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="24fbb-132">Operaciones de calidad de los datos</span><span class="sxs-lookup"><span data-stu-id="24fbb-132">Data Quality Operations</span></span>  
 <span data-ttu-id="24fbb-133">Estas operaciones se utilizan para realizar tareas de calidad de los datos y examinar sus resultados.</span><span class="sxs-lookup"><span data-stu-id="24fbb-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="24fbb-134">Operaciones de importación de datos</span><span class="sxs-lookup"><span data-stu-id="24fbb-134">Data Import Operations</span></span>  
 <span data-ttu-id="24fbb-135">Estas operaciones se utilizan para importar datos en una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24fbb-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="24fbb-136">Para más información, vea [Importación de datos &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="24fbb-137">Las operaciones siguientes se utilizan para importar datos mediante el proceso de almacenamiento temporal incluido en [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24fbb-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="24fbb-138">Estas operaciones solo se deben utilizar para permitir el uso de bases de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="24fbb-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="24fbb-139">Para nuevas implementaciones, utilice las operaciones anteriormente indicadas.</span><span class="sxs-lookup"><span data-stu-id="24fbb-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="24fbb-140">Operaciones de exportación de datos</span><span class="sxs-lookup"><span data-stu-id="24fbb-140">Data Export Operations</span></span>  
 <span data-ttu-id="24fbb-141">Estas operaciones se utilizan para exportar datos a través del uso de vistas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="24fbb-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="24fbb-142">Para obtener más información, vea [exportar datos &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="24fbb-143">Operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="24fbb-143">Security Operations</span></span>  
 <span data-ttu-id="24fbb-144">Estas operaciones se utilizan para modificar la configuración de seguridad que controla el acceso a la base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24fbb-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="24fbb-145">Para obtener más información, consulte [Seguridad &#40;Master Data Services&#41;](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24fbb-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="24fbb-146">Operaciones del sistema</span><span class="sxs-lookup"><span data-stu-id="24fbb-146">System Operations</span></span>  
 <span data-ttu-id="24fbb-147">Estas operaciones se utilizan para obtener y actualizar la configuración del sistema y las preferencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="24fbb-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
