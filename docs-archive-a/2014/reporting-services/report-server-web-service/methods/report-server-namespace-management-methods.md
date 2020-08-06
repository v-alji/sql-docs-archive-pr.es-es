---
title: Métodos de administración de los espacios de nombres del servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- reports [Reporting Services], managing
- management methods [Reporting Services]
- methods [Reporting Services], about methods
- methods [Reporting Services]
ms.assetid: 2aa43ce9-f51e-408a-8ce0-b40d3dd62561
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b2dc38976406aaa0fa799e7a58ee340e5449d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745030"
---
# <a name="report-server-namespace-management-methods"></a><span data-ttu-id="5aff7-102">Métodos de administración de los espacios de nombres del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="5aff7-102">Report Server Namespace Management Methods</span></span>
  <span data-ttu-id="5aff7-103">El servicio web de administración del servidor de informes contiene métodos que puede utilizar para administrar los informes, carpetas y recursos en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5aff7-103">The Report Server Management Web service contains methods that you can use to manage reports, folders, and resources in the report server database.</span></span>  
  
|<span data-ttu-id="5aff7-104">Método</span><span class="sxs-lookup"><span data-stu-id="5aff7-104">Method</span></span>|<span data-ttu-id="5aff7-105">Acción</span><span class="sxs-lookup"><span data-stu-id="5aff7-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CancelJob%2A>|<span data-ttu-id="5aff7-106">Cancela la ejecución de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="5aff7-106">Cancels execution of a job.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateFolder%2A>|<span data-ttu-id="5aff7-107">Agrega una carpeta a la base de datos del servidor de informes o a la biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5aff7-107">Adds a folder to the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A>|<span data-ttu-id="5aff7-108">Agrega un nuevo elemento a una base de datos del servidor de informes o a la biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5aff7-108">Adds a new item to a report server database or SharePoint library.</span></span> <span data-ttu-id="5aff7-109">Este método se aplica a los tipos de elementos `Report`, `Model`, `Dataset`, `Component`, `Resource` y `DataSource`.</span><span class="sxs-lookup"><span data-stu-id="5aff7-109">This method applies to the `Report`, `Model`, `Dataset`, `Component`, `Resource`, and `DataSource` item types.</span></span>|  
|<span data-ttu-id="5aff7-110">M:ReportService2010.ReportingService2010.CreateReportEditSession(System.String,System.String,System.Byte[],ReportService2010.Warning[]@)</span><span class="sxs-lookup"><span data-stu-id="5aff7-110">M:ReportService2010.ReportingService2010.CreateReportEditSession(System.String,System.String,System.Byte[],ReportService2010.Warning[]@)</span></span>|<span data-ttu-id="5aff7-111">Crea una nueva sesión de edición de informes.</span><span class="sxs-lookup"><span data-stu-id="5aff7-111">Creates a new report edit session.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteItem%2A>|<span data-ttu-id="5aff7-112">Quita un elemento de la base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5aff7-112">Removes an item from the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.FindItems%2A>|<span data-ttu-id="5aff7-113">Devuelve los elementos de la base de datos del servidor de informes o biblioteca de SharePoint que coinciden con el criterio de búsqueda especificado.</span><span class="sxs-lookup"><span data-stu-id="5aff7-113">Returns the items in the report server database or SharePoint library that match the specified search criteria.</span></span>|  
|<xref:ReportService2010.ReportingService2010.FireEvent%2A>|<span data-ttu-id="5aff7-114">Desencadena un evento basado en los parámetros proporcionados.</span><span class="sxs-lookup"><span data-stu-id="5aff7-114">Triggers an event based on the supplied parameters.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExtensionSettings%2A>|<span data-ttu-id="5aff7-115">Devuelve una lista de valores para una extensión determinada.</span><span class="sxs-lookup"><span data-stu-id="5aff7-115">Returns a list of settings for a given extension.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemType%2A>|<span data-ttu-id="5aff7-116">Recupera el tipo de un elemento de la base de datos del servidor de informes o biblioteca de SharePoint, si el elemento existe.</span><span class="sxs-lookup"><span data-stu-id="5aff7-116">Retrieves the type of an item in the report server database or SharePoint library, if the item exists.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="5aff7-117">Devuelve los valores de una o más propiedades en un elemento de la base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5aff7-117">Returns the values of one or more properties on an item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDefinition%2A>|<span data-ttu-id="5aff7-118">Recupera la definición o contenido para un elemento.</span><span class="sxs-lookup"><span data-stu-id="5aff7-118">Retrieves the definition or content for an item.</span></span> <span data-ttu-id="5aff7-119">Este método se aplica a los tipos de elementos `Report`, `Model`, `Dataset`, `Component`, `Resource` y `DataSource`.</span><span class="sxs-lookup"><span data-stu-id="5aff7-119">This method applies to the `Report`, `Model`, `Dataset`, `Component`, `Resource`, and `DataSource` item types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemReferences%2A>|<span data-ttu-id="5aff7-120">Devuelve una lista de referencias de elemento de catálogo asociadas a un elemento.</span><span class="sxs-lookup"><span data-stu-id="5aff7-120">Returns a list of catalog item references associated with an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetReportServerConfigInfo%2A>|<span data-ttu-id="5aff7-121">Devuelve información de la instancia del servidor de informes conectada o de todas las instancias del servidor de informes de una implementación escalada.</span><span class="sxs-lookup"><span data-stu-id="5aff7-121">Returns information on the connected report server instance or all the report server instances in a scale-out deployment.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="5aff7-122">Devuelve una o más propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="5aff7-122">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListChildren%2A>|<span data-ttu-id="5aff7-123">Obtiene una lista de elementos secundarios de una carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="5aff7-123">Gets a list of children of a specified folder.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDatabaseCredentialRetrievalOptions%2A>|<span data-ttu-id="5aff7-124">Devuelve una lista de opciones de recuperación de credenciales admitidas.</span><span class="sxs-lookup"><span data-stu-id="5aff7-124">Returns a list of supported credential retrieval options.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListEvents%2A>|<span data-ttu-id="5aff7-125">Devuelve una lista de extensiones de evento como aparecen en el archivo de configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5aff7-125">Returns a list of event extensions as they appear in the report server configuration file.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListJobs%2A>|<span data-ttu-id="5aff7-126">Devuelve una lista de los trabajos que se ejecutan en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5aff7-126">Returns a list of jobs running on the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExtensions%2A>|<span data-ttu-id="5aff7-127">Devuelve una lista de las extensiones que están configuradas para un tipo de extensión determinado.</span><span class="sxs-lookup"><span data-stu-id="5aff7-127">Returns a list of extensions that are configured for a given extension type.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExtensionTypes%2A>|<span data-ttu-id="5aff7-128">Devuelve una lista de tipos de extensión admitidos.</span><span class="sxs-lookup"><span data-stu-id="5aff7-128">Returns a list of supported extension types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListItemTypes%2A>|<span data-ttu-id="5aff7-129">Devuelve una lista de los tipos de elemento del catálogo admitidos.</span><span class="sxs-lookup"><span data-stu-id="5aff7-129">Returns a list of supported catalog item types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListJobActions%2A>|<span data-ttu-id="5aff7-130">Devuelve una lista de acciones de trabajo admitidas.</span><span class="sxs-lookup"><span data-stu-id="5aff7-130">Returns a list of supported job actions.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListJobStates%2A>|<span data-ttu-id="5aff7-131">Devuelve una lista de estados de trabajo admitidos.</span><span class="sxs-lookup"><span data-stu-id="5aff7-131">Returns a list of supported job states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListJobTypes%2A>|<span data-ttu-id="5aff7-132">Devuelve una lista de tipos de trabajo admitidos.</span><span class="sxs-lookup"><span data-stu-id="5aff7-132">Returns a list of supported job types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListParents%2A>|<span data-ttu-id="5aff7-133">Recupera los elementos primarios para el elemento determinado.</span><span class="sxs-lookup"><span data-stu-id="5aff7-133">Retrieves parent items for the given item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSecurityScopes%2A>|<span data-ttu-id="5aff7-134">Devuelve una lista de los ámbitos de seguridad admitidos.</span><span class="sxs-lookup"><span data-stu-id="5aff7-134">Returns a list of supported security scopes.</span></span>|  
|<xref:ReportService2010.ReportingService2010.Logoff%2A>|<span data-ttu-id="5aff7-135">Cierra la sesión del usuario actual que realiza solicitudes de servicio web.</span><span class="sxs-lookup"><span data-stu-id="5aff7-135">Logs out the current user making Web service requests.</span></span> <span data-ttu-id="5aff7-136">Este método solo se aplica al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="5aff7-136">This method only applies to native mode.</span></span>|  
|<xref:ReportService2010.ReportingService2010.LogonUser%2A>|<span data-ttu-id="5aff7-137">Inicia la sesión de un usuario y autentica una solicitud de usuario en el servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5aff7-137">Logs on a user and authenticates a user request to the Report Server Web service.</span></span> <span data-ttu-id="5aff7-138">Este método solo se aplica al modo nativo.</span><span class="sxs-lookup"><span data-stu-id="5aff7-138">This method only applies to native mode.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemReferences%2A>|<span data-ttu-id="5aff7-139">Establece los elementos de catálogo asociados a un elemento.</span><span class="sxs-lookup"><span data-stu-id="5aff7-139">Sets the catalog items associated with an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.MoveItem%2A>|<span data-ttu-id="5aff7-140">Mueve y/o cambia el nombre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5aff7-140">Moves and/or renames an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="5aff7-141">Establece una o más propiedades de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5aff7-141">Sets one or more properties of an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDefinition%2A>|<span data-ttu-id="5aff7-142">Establece la definición o el contenido para un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="5aff7-142">Sets the definition or content for a specified item.</span></span> <span data-ttu-id="5aff7-143">Este método se aplica a los tipos de elementos `Report`, `Model`, `Dataset`, `Component`, `Resource` y `DataSource`.</span><span class="sxs-lookup"><span data-stu-id="5aff7-143">This method applies to the `Report`, `Model`, `Dataset`, `Component`, `Resource`, and `DataSource` item types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="5aff7-144">Establece una o varias propiedades del sistema en el servidor de informes o la granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5aff7-144">Sets one or more system properties in the report server or SharePoint farm.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ValidateExtensionSettings%2A>|<span data-ttu-id="5aff7-145">Valida la configuración de la extensión de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aff7-145">Validates [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extension settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5aff7-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5aff7-146">See Also</span></span>  
 <span data-ttu-id="5aff7-147">[Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="5aff7-147">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="5aff7-148">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="5aff7-148">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="5aff7-149">[Métodos del servicio web del servidor de informes](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="5aff7-149">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="5aff7-150">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5aff7-150">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  