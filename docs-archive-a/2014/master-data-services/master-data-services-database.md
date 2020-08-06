---
title: Base de datos de Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674168"
---
# <a name="master-data-services-database"></a><span data-ttu-id="cc95f-102">Base de datos de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="cc95f-102">Master Data Services Database</span></span>
  <span data-ttu-id="cc95f-103">La base de datos contiene toda la información para el sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc95f-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="cc95f-104">Es un punto central en una implementación de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc95f-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="cc95f-105">Las base de datos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="cc95f-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="cc95f-106">Almacena los valores, objetos de base de datos y los datos que requiere el sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc95f-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="cc95f-107">Contiene las tablas de ensayo que se van a utilizar para procesar los datos de los sistemas de origen.</span><span class="sxs-lookup"><span data-stu-id="cc95f-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="cc95f-108">Proporciona objetos de esquema y de base de datos para almacenar los datos maestros de los sistemas de origen.</span><span class="sxs-lookup"><span data-stu-id="cc95f-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="cc95f-109">Admite la funcionalidad de control de versiones, incluso la validación de reglas de negocios y notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cc95f-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="cc95f-110">Proporciona vistas para sistemas de suscripción que necesitan recuperar datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc95f-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc95f-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cc95f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="cc95f-112">Tabla de almacenamiento provisional de miembros hoja &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc95f-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="cc95f-113">Tabla de almacenamiento provisional de miembros consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc95f-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="cc95f-114">Tabla de almacenamiento provisional de relaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc95f-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="cc95f-115">Errores del proceso de almacenamiento provisional &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc95f-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc95f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc95f-116">See Also</span></span>  
 <span data-ttu-id="cc95f-117">[Crear una base de datos de Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="cc95f-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="cc95f-118">[&#40;de seguridad de objetos de base de datos Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cc95f-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="cc95f-119">Inicios de sesión, usuarios y roles en bases de datos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc95f-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
