---
title: Administrador de conexiones ADO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676141"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="4b6ae-102">Administrador de conexiones ADO</span><span class="sxs-lookup"><span data-stu-id="4b6ae-102">ADO Connection Manager</span></span>
  <span data-ttu-id="4b6ae-103">Un administrador de conexiones ADO permite a un paquete conectarse con Objetos de datos ActiveX (ADO), como un conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="4b6ae-104">Este administrador de conexiones se usa normalmente en tareas personalizadas escritas en una versión anterior de un lenguaje, como por ejemplo, Microsoft Visual Basic 6.0 o en tareas personalizadas que forman parte de una aplicación existente que usa ADO para conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="4b6ae-105">Cuando se agrega un administrador de conexiones ADO a un paquete, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve en una conexión ADO en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la `Connections` colección del paquete.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="4b6ae-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `ADO`.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="4b6ae-107">Solución de problemas del administrador de conexiones ADO</span><span class="sxs-lookup"><span data-stu-id="4b6ae-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="4b6ae-108">Al ser leídos por un administrador de conexiones ADO, los datos de determinados tipos de datos de fecha de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generarán los resultados que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="4b6ae-109">Tipo de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b6ae-109">SQL Server Data type</span></span>|<span data-ttu-id="4b6ae-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="4b6ae-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="4b6ae-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="4b6ae-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="4b6ae-112">Se produce un error en el paquete a menos que el paquete utilice comandos SQL parametrizados.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="4b6ae-113">Para utilizar comandos SQL parametrizados, utilice la tarea Ejecute SQL en el paquete.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="4b6ae-114">Para más información, vea [Tarea Ejecutar SQL](../control-flow/execute-sql-task.md) y [Parámetros y códigos de retorno en la tarea Ejecutar SQL](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="4b6ae-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="4b6ae-115">El administrador de conexiones ADO trunca el valor de milisegundos.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="4b6ae-116">Para más información sobre los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cómo se asignan a los tipos de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vea [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) y [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4b6ae-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="4b6ae-117">Configurar el Administrador de conexiones ADO</span><span class="sxs-lookup"><span data-stu-id="4b6ae-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="4b6ae-118">Puede configurar el administrador de conexiones ADO de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b6ae-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4b6ae-119">Proporcionar una cadena de conexión específica configurada para cumplir con los requisitos del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="4b6ae-120">Según el proveedor, incluir el nombre del origen de datos al cual conectarse.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="4b6ae-121">Proporcionar credenciales de seguridad según resulte apropiado para el proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="4b6ae-122">Indicar si la conexión creada desde el administrador de conexiones se conserva en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="4b6ae-123">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4b6ae-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4b6ae-124">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b6ae-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="4b6ae-125">Configurar el administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="4b6ae-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="4b6ae-126">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4b6ae-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6ae-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b6ae-127">See Also</span></span>  
 [<span data-ttu-id="4b6ae-128">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4b6ae-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
