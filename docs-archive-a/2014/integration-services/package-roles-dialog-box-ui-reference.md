---
title: Referencia de la interfaz de usuario del cuadro de diálogo roles de paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747131"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="944a5-102">Referencia de la interfaz de usuario del cuadro de diálogo Roles del paquete</span><span class="sxs-lookup"><span data-stu-id="944a5-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="944a5-103">Use el cuadro de diálogo **Roles de paquete** , disponible en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para especificar los roles de base de datos que tienen acceso de lectura al paquete y los roles de base de datos que tienen acceso de escritura al paquete.</span><span class="sxs-lookup"><span data-stu-id="944a5-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="944a5-104">Los roles de base de datos se aplican solo a paquetes almacenados en la base de datos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span><span class="sxs-lookup"><span data-stu-id="944a5-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="944a5-105">Para obtener más información sobre los roles de base de datos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y sus permisos, vea [Roles de Integration Services &#40;servicio SSIS&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="944a5-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="944a5-106">Los roles enumerados en el cuadro de diálogo son los roles de base de datos actuales de la base de datos del sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="944a5-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="944a5-107">Si no se seleccionan roles, se aplican los roles de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] predeterminados.</span><span class="sxs-lookup"><span data-stu-id="944a5-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="944a5-108">De manera predeterminada, el rol de lector incluye **db_ssisadmin**, **db_ssisoperator**y el usuario que creó el paquete.</span><span class="sxs-lookup"><span data-stu-id="944a5-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="944a5-109">Un usuario que sea miembro de uno de estos roles o que haya creado los paquetes puede enumerar, ver, exportar y ejecutar paquetes.</span><span class="sxs-lookup"><span data-stu-id="944a5-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="944a5-110">De manera predeterminada, el rol de escritor incluye **db_ssisadmin** y el usuario que creó el paquete.</span><span class="sxs-lookup"><span data-stu-id="944a5-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="944a5-111">Un usuario que sea miembro de este rol y el usuario que creó los paquetes pueden importar, eliminar y cambiar paquetes.</span><span class="sxs-lookup"><span data-stu-id="944a5-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="944a5-112">La columna **ownersid** de la tabla **sysssispackages** contiene el identificador de seguridad único del usuario que creó el paquete.</span><span class="sxs-lookup"><span data-stu-id="944a5-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="944a5-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="944a5-113">Options</span></span>  
 <span data-ttu-id="944a5-114">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="944a5-114">**Package Name**</span></span>  
 <span data-ttu-id="944a5-115">Especifique el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="944a5-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="944a5-116">**Rol de lector**</span><span class="sxs-lookup"><span data-stu-id="944a5-116">**Reader Role**</span></span>  
 <span data-ttu-id="944a5-117">Seleccione un rol de la lista.</span><span class="sxs-lookup"><span data-stu-id="944a5-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="944a5-118">**Rol de escritor**</span><span class="sxs-lookup"><span data-stu-id="944a5-118">**Writer Role**</span></span>  
 <span data-ttu-id="944a5-119">Seleccione un rol de la lista.</span><span class="sxs-lookup"><span data-stu-id="944a5-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944a5-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="944a5-120">See Also</span></span>  
 <span data-ttu-id="944a5-121">[Roles de nivel de base de datos](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="944a5-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="944a5-122">Información general sobre seguridad &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="944a5-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
