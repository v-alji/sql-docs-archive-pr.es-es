---
title: Administrar modelos (complementos de minería de datos de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675627"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="189db-102">Administrar modelos (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="189db-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="189db-103">![Botón Administrar modelos, cinta de opciones Minería de datos](media/dmc-manage.gif "Botón Administrar modelos, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="189db-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="189db-104">El cuadro de diálogo **administrar modelos** le permite interactuar con modelos de minería de datos y estructuras de minería de datos existentes almacenados en el [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor al que está conectado actualmente.</span><span class="sxs-lookup"><span data-stu-id="189db-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="189db-105">También puede ver y administrar estructuras y modelos temporales que se han creado durante la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="189db-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="189db-106">Si ha usado tanto modelos de sesión como modelos almacenados en un servidor, todos ellos estarán visibles en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="189db-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="189db-107">Usar el Asistente para administrar modelos</span><span class="sxs-lookup"><span data-stu-id="189db-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="189db-108">Al hacer clic en **administrar modelos**, se abre el cuadro de diálogo **administrar estructuras y modelos de minería** de datos, que proporciona acceso a la siguiente funcionalidad para administrar estructuras y modelos de minería de datos existentes:</span><span class="sxs-lookup"><span data-stu-id="189db-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="189db-109">Cambiar el nombre de un modelo o una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="189db-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="189db-110">Eliminar un modelo o una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="189db-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="189db-111">Borrar un modelo o una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="189db-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="189db-112">Procesar una estructura de minería de datos con datos nuevos o existentes</span><span class="sxs-lookup"><span data-stu-id="189db-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="189db-113">Exportar o importar un modelo o una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="189db-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="189db-114">En este cuadro de diálogo no se pueden crear consultas o modelos.</span><span class="sxs-lookup"><span data-stu-id="189db-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="189db-115">Para crear una nueva estructura de minería de datos, use uno de los asistentes proporcionados en el cliente de minería de datos para Excel o utilice la **editor avanzado de consulta de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="189db-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="189db-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="189db-116">Requirements</span></span>  
 <span data-ttu-id="189db-117">Para administrar modelos de minería de datos, primero debe crear una conexión a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="189db-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="189db-118">La conexión es necesaria incluso aunque se trabaje con modelos de sesión almacenados en un archivo temporal.</span><span class="sxs-lookup"><span data-stu-id="189db-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="189db-119">Para obtener más información acerca de cómo crear o cambiar una conexión, vea [conectarse a los datos de origen &#40;cliente de minería de datos para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="189db-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="189db-120">Si la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la que se conecta no contiene estructuras ni modelos de minería de datos, puede crearlos usando los asistentes y demás herramientas que le proporciona este complemento.</span><span class="sxs-lookup"><span data-stu-id="189db-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="189db-121">También puede crear nuevos modelos mediante el Editor avanzado del **modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="189db-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189db-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="189db-122">See Also</span></span>  
 <span data-ttu-id="189db-123">[Documentar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="189db-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="189db-124">Implementar y escalar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="189db-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  
