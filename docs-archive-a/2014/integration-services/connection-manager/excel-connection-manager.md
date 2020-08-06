---
title: Administrador de conexiones con Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672234"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="e8f90-102">Administrador de conexiones con Excel</span><span class="sxs-lookup"><span data-stu-id="e8f90-102">Excel Connection Manager</span></span>
  <span data-ttu-id="e8f90-103">Un Administrador de conexiones con Excel permite a un paquete conectarse con un archivo de libro de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel existente.</span><span class="sxs-lookup"><span data-stu-id="e8f90-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="e8f90-104">El origen de Excel y el destino de Excel que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluye usan el administrador de conexiones con Excel.</span><span class="sxs-lookup"><span data-stu-id="e8f90-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="e8f90-105">Cuando agrega un Administrador de conexiones con Excel a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un Administrador de conexiones que se resuelve como una conexión Excel en el tiempo de ejecución, establece las propiedades del Administrador de conexiones y agrega el Administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="e8f90-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="e8f90-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `EXCEL`.</span><span class="sxs-lookup"><span data-stu-id="e8f90-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8f90-107">No puede conectar con un archivo de Excel protegido mediante contraseña.</span><span class="sxs-lookup"><span data-stu-id="e8f90-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="e8f90-108">Configuración del administrador de conexiones de Excel</span><span class="sxs-lookup"><span data-stu-id="e8f90-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="e8f90-109">Puede configurar el Administrador de conexiones con Excel de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8f90-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="e8f90-110">Especificar la ruta del archivo de libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="e8f90-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="e8f90-111">Especificar la versión de Excel que se usó para crear el archivo.</span><span class="sxs-lookup"><span data-stu-id="e8f90-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="e8f90-112">Indicar si la primera fila de datos a los que se tuvo acceso en las hojas de cálculo o los rangos seleccionados contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="e8f90-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="e8f90-113">Si un origen de Excel utiliza el Administrador de conexiones con Excel, los nombres de las columnas se incluyen con los datos extraídos.</span><span class="sxs-lookup"><span data-stu-id="e8f90-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="e8f90-114">Si un destino de Excel utiliza el Administrador de conexiones con Excel, los nombres de las columnas se incluyen con los datos escritos.</span><span class="sxs-lookup"><span data-stu-id="e8f90-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="e8f90-115">El administrador de conexiones con Excel usa el [!INCLUDE[msCoName](../../includes/msconame-md.md)] proveedor de OLE DB para Jet 4,0 y el controlador ISAM (método de acceso secuencial indizado) de Excel compatible para conectar y leer y escribir datos en orígenes de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="e8f90-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="e8f90-116">Para obtener más información sobre el comportamiento de este proveedor y controlador cuando se usa con orígenes de Excel y destinos de Excel, vea [Excel Source](../data-flow/excel-source.md) y [Excel Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e8f90-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="e8f90-117">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e8f90-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e8f90-118">Para más información sobre las propiedades que puede configurar en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor de Administrador de conexiones con Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e8f90-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="e8f90-119">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="e8f90-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="e8f90-120">Para más información sobre cómo crear bucles entre un grupo de archivos de Excel, vea [Crear bucles entre archivos y tablas de Excel usando un contenedor de bucles Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="e8f90-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e8f90-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e8f90-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e8f90-122">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="e8f90-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="e8f90-123">Importación de datos desde Excel o exportación de datos a Excel con SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="e8f90-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
