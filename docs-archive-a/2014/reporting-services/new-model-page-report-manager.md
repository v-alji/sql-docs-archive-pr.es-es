---
title: Página nuevo modelo (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675232"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="74bd3-102">Página Nuevo modelo (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="74bd3-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="74bd3-103">Use esta página para generar un modelo de informe predeterminado desde un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="74bd3-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="74bd3-104">Solo puede generar modelos de informe desde orígenes de datos multidimensionales de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , orígenes de datos relacionales de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y orígenes de datos relacionales de Oracle.</span><span class="sxs-lookup"><span data-stu-id="74bd3-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="74bd3-105">Los modelos que se generan en el Administrador de informes se basan en el esquema del origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="74bd3-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="74bd3-106">Las entidades, las carpetas y los campos se crean para todas las tablas y columnas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="74bd3-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="74bd3-107">No puede excluir elementos ni puede establecer opciones que determinen la manera en la que se genera el modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="74bd3-108">Si desea personalizar o perfeccionar un modelo, debe usar el Diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="74bd3-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="74bd3-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="74bd3-109">Navigation</span></span>  
 <span data-ttu-id="74bd3-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="74bd3-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="74bd3-111">Para abrir la página Nuevo modelo</span><span class="sxs-lookup"><span data-stu-id="74bd3-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="74bd3-112">Abra el Administrador de informes y busque el origen de datos compartido a partir del cual desea generar un modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="74bd3-113">Mantenga el mouse sobre el origen de datos y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="74bd3-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="74bd3-114">En el menú desplegable, efectúe uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="74bd3-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="74bd3-115">Haga clic en **Generar modelo de informe** para abrir la página Nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="74bd3-116">Haga clic en **Administrar** para abrir la página de propiedades General del informe.</span><span class="sxs-lookup"><span data-stu-id="74bd3-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="74bd3-117">A continuación, haga clic en **Generar modelo** para abrir la página Nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74bd3-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="74bd3-118">Options</span></span>  
 <span data-ttu-id="74bd3-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="74bd3-119">**Name**</span></span>  
 <span data-ttu-id="74bd3-120">Especifica el nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-120">Specifies the name of the model.</span></span> <span data-ttu-id="74bd3-121">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="74bd3-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="74bd3-122">También puede incluir espacios y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="74bd3-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="74bd3-123">No utilice los caracteres siguientes al especificar un nombre:</span><span class="sxs-lookup"><span data-stu-id="74bd3-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="74bd3-124">; ?</span><span class="sxs-lookup"><span data-stu-id="74bd3-124">; ?</span></span> <span data-ttu-id="74bd3-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="74bd3-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="74bd3-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="74bd3-126">**Description**</span></span>  
 <span data-ttu-id="74bd3-127">Muestra una descripción del modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-127">Shows a description of the model.</span></span> <span data-ttu-id="74bd3-128">Los usuarios que ven este elemento a través del Administrador de informes ven esta descripción al examinar la jerarquía de carpetas.</span><span class="sxs-lookup"><span data-stu-id="74bd3-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="74bd3-129">**Cambiar ubicación**</span><span class="sxs-lookup"><span data-stu-id="74bd3-129">**Change Location**</span></span>  
 <span data-ttu-id="74bd3-130">Muestra la ubicación de la carpeta del nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="74bd3-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="74bd3-131">Puede hacer clic en el botón **Cambiar ubicación** para seleccionar una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="74bd3-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
