---
title: Administrador de conexiones de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], Analysis Services
- connection managers [Integration Services], Analysis Services
- Analysis Services connection manager
ms.assetid: 9f9cadad-a1d0-4db5-98f5-df5dbbec1be4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5da84acd131b75ef9ea174986836265934fb44b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673224"
---
# <a name="analysis-services-connection-manager"></a><span data-ttu-id="1d864-102">administrador de conexiones de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d864-102">Analysis Services Connection Manager</span></span>
  <span data-ttu-id="1d864-103">Un administrador de conexiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] permite que un paquete se conecte con un servidor que se ejecuta en una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o con un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que proporciona acceso a datos de cubo y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="1d864-103">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager enables a package to connect to a server that runs an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that provides access to cube and dimension data.</span></span> <span data-ttu-id="1d864-104">Solo puede conectarse a un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mientras desarrolla paquetes en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d864-104">You can only connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project while developing packages in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1d864-105">Durante el tiempo de ejecución, los paquetes se conectan al servidor y la base de datos en la que se implementó el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d864-105">At run time, packages connect to the server and the database to which you deployed the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
 <span data-ttu-id="1d864-106">Ambas tareas, como la tarea Ejecutar DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y la tarea Procesamiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , y los destinos como el destino de Entrenamiento del modelo de minería de datos, usan un administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d864-106">Both tasks, such as the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task and the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task, and destinations, such as the Data Mining Model Training destination, use an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="1d864-107">Para obtener más información sobre las bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Bases de datos de modelos multidimensionales &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span><span class="sxs-lookup"><span data-stu-id="1d864-107">For more information about [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, see [Multidimensional Model Databases &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span></span>  
  
## <a name="configuration-of-the-analysis-services-connection-manager"></a><span data-ttu-id="1d864-108">Configuración del administrador de conexiones de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d864-108">Configuration of the Analysis Services Connection Manager</span></span>  
 <span data-ttu-id="1d864-109">Cuando se agrega un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Administrador de conexiones a un paquete, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] conexión en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la `Connections` colección del paquete.</span><span class="sxs-lookup"><span data-stu-id="1d864-109">When you add an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to a package, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="1d864-110">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `MSOLAP100`.</span><span class="sxs-lookup"><span data-stu-id="1d864-110">The `ConnectionManagerType` property of the connection manager is set to `MSOLAP100`.</span></span>  
  
 <span data-ttu-id="1d864-111">Puede configurar el administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d864-111">You can configure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="1d864-112">Proporcionar una cadena de conexión configurada para cumplir con los requisitos del Proveedor Microsoft OLE DB para Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1d864-112">Provide a connection string configured to meet the requirements of the Microsoft OLE Provider for Analysis Services provider.</span></span>  
  
-   <span data-ttu-id="1d864-113">Especificar la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] con el que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="1d864-113">Specify the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to connect to.</span></span>  
  
-   <span data-ttu-id="1d864-114">Si se está conectando a una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], especifique el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="1d864-114">If you are connecting to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], specify the authentication mode.</span></span>  
  
-   <span data-ttu-id="1d864-115">Indicar si la conexión creada desde el administrador de conexiones se conserva en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d864-115">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="1d864-116">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1d864-116">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1d864-117">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d864-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="1d864-118">Referencia de la interfaz de usuario del cuadro de diálogo Agregar administrador de conexiones con Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d864-118">Add Analysis Services Connection Manager Dialog Box UI Reference</span></span>](add-analysis-services-connection-manager-dialog-box-ui-reference.md)  
  
 <span data-ttu-id="1d864-119">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="1d864-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
