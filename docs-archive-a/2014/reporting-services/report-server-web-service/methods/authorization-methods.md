---
title: Métodos de autorización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747979"
---
# <a name="authorization-methods"></a><span data-ttu-id="f7a40-102">Métodos de autorización</span><span class="sxs-lookup"><span data-stu-id="f7a40-102">Authorization Methods</span></span>
  <span data-ttu-id="f7a40-103">Puede utilizar estos métodos para administrar tareas, roles y directivas en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f7a40-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="f7a40-104">Método</span><span class="sxs-lookup"><span data-stu-id="f7a40-104">Method</span></span>|<span data-ttu-id="f7a40-105">Acción</span><span class="sxs-lookup"><span data-stu-id="f7a40-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="f7a40-106">Agrega un nuevo rol a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f7a40-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="f7a40-107">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="f7a40-108">Elimina un rol de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f7a40-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="f7a40-109">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="f7a40-110">Devuelve los permisos de usuario que están asociados a un elemento determinado en la base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7a40-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="f7a40-111">Devuelve las directivas que están asociados a un elemento determinado en la base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7a40-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="f7a40-112">Devuelve las propiedades de metadatos de rol y una colección de tareas asociadas.</span><span class="sxs-lookup"><span data-stu-id="f7a40-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="f7a40-113">Devuelve los permisos de sistema del usuario.</span><span class="sxs-lookup"><span data-stu-id="f7a40-113">Returns the user's system permissions.</span></span> <span data-ttu-id="f7a40-114">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="f7a40-115">Devuelve las directivas del sistema, incluidos los grupos y roles a los que están asociados.</span><span class="sxs-lookup"><span data-stu-id="f7a40-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="f7a40-116">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="f7a40-117">Elimina las directivas asociadas a un elemento determinado en la base de datos del servidor de informes y establece las directivas de seguridad para el elemento en las de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="f7a40-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="f7a40-118">Devuelve un valor booleano que indica si el protocolo Capa de sockets seguros (SSL) se requiere para utilizar el extremo de <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="f7a40-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="f7a40-119">Devuelve los nombres y descripciones de los roles que administra el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f7a40-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="f7a40-120">Devuelve una lista de los métodos del Protocolo simple de acceso a objetos (SOAP) en el extremo de <xref:ReportExecution2005> que requieren una conexión segura cuando se invocan.</span><span class="sxs-lookup"><span data-stu-id="f7a40-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="f7a40-121">El valor `SecureConnectionLevel` del servidor de informes se utiliza para determinar qué métodos se devuelven.</span><span class="sxs-lookup"><span data-stu-id="f7a40-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="f7a40-122">Devuelve las tareas que son administradas por el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f7a40-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="f7a40-123">Establece las directivas que están asociadas a un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="f7a40-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="f7a40-124">Establece las propiedades de los metadatos de rol y asocia un conjunto de tareas a un rol.</span><span class="sxs-lookup"><span data-stu-id="f7a40-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="f7a40-125">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="f7a40-126">Establece la directiva del sistema que define los grupos y sus roles asociados.</span><span class="sxs-lookup"><span data-stu-id="f7a40-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="f7a40-127">Este método se aplica solo al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="f7a40-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7a40-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7a40-128">See Also</span></span>  
 <span data-ttu-id="f7a40-129">[Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f7a40-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="f7a40-130">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="f7a40-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="f7a40-131">[Métodos del servicio web del servidor de informes](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f7a40-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="f7a40-132">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f7a40-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
