---
title: Tipo de conexión de Oracle (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9db86dd2-beda-42d8-8af7-2629d58a8e3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bf19953c5d2dc2f818eddcacf445e641972d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672768"
---
# <a name="oracle-connection-type-ssrs"></a><span data-ttu-id="eb506-102">Tipo de conexión de Oracle (SSRS)</span><span class="sxs-lookup"><span data-stu-id="eb506-102">Oracle Connection Type (SSRS)</span></span>
  <span data-ttu-id="eb506-103">Para utilizar en el informe los datos de una base de datos de Oracle, debe tener un conjunto de datos basado en un origen de datos de informe de tipo Oracle.</span><span class="sxs-lookup"><span data-stu-id="eb506-103">To use data from an Oracle database in your report, you must you must have a dataset that is based on a report data source of type Oracle.</span></span> <span data-ttu-id="eb506-104">Este tipo de origen de datos integrado está basado en el proveedor administrado de .NET Framework para Oracle y requiere un componente de software del cliente Oracle.</span><span class="sxs-lookup"><span data-stu-id="eb506-104">This built-in data source type is based on the .NET Framework Managed Provider for Oracle and requires an Oracle client software component.</span></span>  
  
 <span data-ttu-id="eb506-105">Utilice la información de este tema para crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="eb506-106">Para obtener instrucciones paso a paso, vea [Agregar y comprobar una conexión de datos o un origen de datos &#40;generador de informes y SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="eb506-107">Cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="eb506-107">Connection String</span></span>  
 <span data-ttu-id="eb506-108">Póngase en contacto con el administrador de bases de datos y solicite la información de conexión y las credenciales que debe usar para conectar con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="eb506-109">En el siguiente ejemplo de cadena de conexión, se especifica una base de datos de Oracle en el servidor denominado "Oracle9" mediante Unicode.</span><span class="sxs-lookup"><span data-stu-id="eb506-109">The following connection string example specifies an Oracle database on the server named "Oracle9" using Unicode.</span></span> <span data-ttu-id="eb506-110">El nombre del servidor debe coincidir con el nombre de instancia del servidor de Oracle definido en el archivo de configuración Tnsnames.ora.</span><span class="sxs-lookup"><span data-stu-id="eb506-110">The server name must match what is defined in the Tnsnames.ora configuration file as the Oracle server instance name.</span></span>  
  
```  
Data Source="Oracle9"; Unicode="True"  
```  
  
 <span data-ttu-id="eb506-111">Para más información sobre ejemplos de cadenas de conexión, vea [Conexiones de datos, orígenes de datos y cadenas de conexión en el Generador de informes](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-111">For more information about connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="eb506-112">Sus</span><span class="sxs-lookup"><span data-stu-id="eb506-112">Credentials</span></span>  
 <span data-ttu-id="eb506-113">Se necesitan credenciales para ejecutar consultas y obtener una vista previa del informe localmente y desde el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eb506-113">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="eb506-114">Después de publicar el informe, es posible que necesite cambiar las credenciales para el origen de datos de tal forma que, cuando el informe se ejecute en el servidor de informes, los permisos para recuperar los datos sean válidos.</span><span class="sxs-lookup"><span data-stu-id="eb506-114">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="eb506-115">Para obtener más información, vea [conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) o [Especifique las credenciales en generador de informes](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-115">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  

  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="eb506-116">Queri</span><span class="sxs-lookup"><span data-stu-id="eb506-116">Queries</span></span>  
 <span data-ttu-id="eb506-117">Para crear un conjunto de datos, se puede seleccionar un procedimiento almacenado en una lista desplegable o se puede crear una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="eb506-117">To create a dataset, you can either select a stored procedure from a drop-down list or create an SQL query.</span></span> <span data-ttu-id="eb506-118">Para generar una consulta, debe usar el diseñador de consultas basado en texto.</span><span class="sxs-lookup"><span data-stu-id="eb506-118">To build a query, you must use the text-based query designer.</span></span> <span data-ttu-id="eb506-119">Para más información, vea [Interfaz de usuario del Diseñador de consultas basado en texto &#40;Generador de informes&#41;](text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-119">For more information, see [Text-based Query Designer User Interface &#40;Report Builder&#41;](text-based-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="eb506-120">Puede especificar los procedimientos almacenados que solo devuelven un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="eb506-120">You can specify stored procedures that return only one result set.</span></span> <span data-ttu-id="eb506-121">No se admiten las consultas basadas en cursor.</span><span class="sxs-lookup"><span data-stu-id="eb506-121">Using cursor-based queries are not supported.</span></span>  
  
##  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="eb506-122">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb506-122">Parameters</span></span>  
 <span data-ttu-id="eb506-123">Si la consulta incluye las variables de consulta, se generan automáticamente los parámetros de informe correspondientes.</span><span class="sxs-lookup"><span data-stu-id="eb506-123">If the query includes query variables, corresponding report parameters are automatically generated.</span></span> <span data-ttu-id="eb506-124">Esta extensión admite los parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="eb506-124">Named parameters are supported by this extension.</span></span> <span data-ttu-id="eb506-125">En Oracle versión 9 o posterior, se admiten los parámetros de varios valores.</span><span class="sxs-lookup"><span data-stu-id="eb506-125">For Oracle version 9 or later, multivalue parameters are supported.</span></span>  
  
 <span data-ttu-id="eb506-126">Los parámetros de informe se crean con valores de propiedad predeterminados que quizá necesite modificar.</span><span class="sxs-lookup"><span data-stu-id="eb506-126">Report parameters are created with default property values that you might need to modify.</span></span> <span data-ttu-id="eb506-127">Por ejemplo, los parámetro de informe son un tipo de datos **Texto**.</span><span class="sxs-lookup"><span data-stu-id="eb506-127">For example, each report parameter is data type **Text**.</span></span> <span data-ttu-id="eb506-128">Una vez creados los parámetros de informe, podría suceder que tenga que cambiar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="eb506-128">After the report parameters are created, you might have to change default values.</span></span> <span data-ttu-id="eb506-129">Para más información, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-129">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  

  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="eb506-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb506-130">Remarks</span></span>  
 <span data-ttu-id="eb506-131">Antes de que pueda conectar con un origen de datos de Oracle, el administrador del sistema debe tener instalada la versión del proveedor de datos .NET para Oracle que permite la recuperación de datos desde la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="eb506-131">Before you can connect an Oracle data source, the system administrator must have installed the version of the .NET Data Provider for Oracle that supports retrieving data from the Oracle database.</span></span> <span data-ttu-id="eb506-132">Este proveedor de datos debe estar instalado en el mismo equipo que el Generador de informes, además de en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="eb506-132">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="eb506-133">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb506-133">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="eb506-134">Para obtener más información, vea[Uso del proveedor de datos de .NET Framework para Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) en msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eb506-134">[Using the .NET Framework Data Provider for Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) on msdn.microsoft.com</span></span>  
  
-   [<span data-ttu-id="eb506-135">Cómo usar Reporting Services para tener acceso a un origen de datos de Oracle y configurarlo</span><span class="sxs-lookup"><span data-stu-id="eb506-135">How to use Reporting Services to configure and to access an Oracle data source</span></span>](https://support.microsoft.com/kb/834305)  
  
-   [<span data-ttu-id="eb506-136">Cómo agregar permisos para la entidad de seguridad NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="eb506-136">How to add permissions for the NETWORK SERVICE security principal</span></span>](https://support.microsoft.com/kb/870668)  
  
###### <a name="alternate-data-extensions"></a><span data-ttu-id="eb506-137">Extensiones de datos alternativas</span><span class="sxs-lookup"><span data-stu-id="eb506-137">Alternate Data Extensions</span></span>  
 <span data-ttu-id="eb506-138">También puede recuperar los datos de una base de datos de Oracle utilizando un tipo de origen de datos OLE DB.</span><span class="sxs-lookup"><span data-stu-id="eb506-138">You can also retrieve data from an Oracle database by using an OLE DB data source type.</span></span> <span data-ttu-id="eb506-139">Para obtener más información, vea [Tipo de conexión OLE DB &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eb506-139">For more information, see [OLE DB Connection Type &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span></span>  
  
###### <a name="report-models"></a><span data-ttu-id="eb506-140">Modelos de informe</span><span class="sxs-lookup"><span data-stu-id="eb506-140">Report Models</span></span>  
 <span data-ttu-id="eb506-141">También se pueden crear modelos basados en una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="eb506-141">You can also create models based on an Oracle database.</span></span>  
  
###### <a name="platform-and-version-information"></a><span data-ttu-id="eb506-142">Información de plataforma y de versión</span><span class="sxs-lookup"><span data-stu-id="eb506-142">Platform and Version Information</span></span>  
 <span data-ttu-id="eb506-143">Para obtener más información sobre la compatibilidad de plataformas y de versiones, vea [Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) en la documentación relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en los [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Libros en pantalla](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="eb506-143">For more information about platform and version support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="eb506-144">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="eb506-144">How-To Topics</span></span>  
 <span data-ttu-id="eb506-145">Esta sección contiene instrucciones paso a paso para trabajar con conexiones de datos, orígenes de datos y conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-145">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="eb506-146">Agregar y comprobar una conexión de datos o un origen de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-146">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="eb506-147">Crear un conjunto de datos compartido o un conjunto de datos incrustado &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-147">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="eb506-148">Agregar un filtro a un conjunto de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-148">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 
  
##  <a name="related-sections"></a><a name="Related"></a> <span data-ttu-id="eb506-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="eb506-149">Related Sections</span></span>  
 <span data-ttu-id="eb506-150">Estas secciones de la documentación proporcionan información conceptual detallada sobre los datos de informe, así como información de procedimientos acerca de cómo definir, personalizar y usar las partes de un informe que están relacionadas con datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-150">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="eb506-151">Agregar datos a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-151">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="eb506-152">Proporciona información general sobre cómo obtener acceso a los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="eb506-152">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="eb506-153">Conexiones de datos, orígenes de datos y cadenas de conexión en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="eb506-153">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="eb506-154">Proporciona información sobre las conexiones de datos y los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-154">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="eb506-155">Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-155">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="eb506-156">Proporciona información sobre conjuntos de datos compartidos e incrustados.</span><span class="sxs-lookup"><span data-stu-id="eb506-156">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="eb506-157">Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-157">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="eb506-158">Proporciona información sobre la colección de campos de conjunto de datos que genera la consulta.</span><span class="sxs-lookup"><span data-stu-id="eb506-158">Provides information about the dataset field collection generated by the query.</span></span>  
  
 <span data-ttu-id="eb506-159">[Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) en la documentación relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en los [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Libros en pantalla](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="eb506-159">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="eb506-160">Proporciona información detallada sobre la compatibilidad de versiones y plataformas para cada extensión de datos.</span><span class="sxs-lookup"><span data-stu-id="eb506-160">Provides in-depth information about platform and version support for each data extension.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="eb506-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb506-161">See Also</span></span>  
 <span data-ttu-id="eb506-162">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="eb506-162">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="eb506-163">[Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="eb506-163">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="eb506-164">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb506-164">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
