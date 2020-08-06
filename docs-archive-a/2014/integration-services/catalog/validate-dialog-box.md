---
title: Cuadro de diálogo Validar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663639"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="27c94-102">Validar, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="27c94-102">Validate Dialog Box</span></span>
  <span data-ttu-id="27c94-103">Use el cuadro de diálogo **Validar** para comprobar si hay problemas comunes en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , un proyecto o paquete.</span><span class="sxs-lookup"><span data-stu-id="27c94-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="27c94-104">Si hay un problema, aparecerá un mensaje en la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="27c94-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="27c94-105">De lo contrario, aparecerá el término Preparado en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="27c94-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="27c94-106">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="27c94-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="27c94-107">Abrir el cuadro de diálogo Validar</span><span class="sxs-lookup"><span data-stu-id="27c94-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="27c94-108">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="27c94-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="27c94-109">Abrir el cuadro de diálogo Validar</span><span class="sxs-lookup"><span data-stu-id="27c94-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="27c94-110">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27c94-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="27c94-111">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.</span><span class="sxs-lookup"><span data-stu-id="27c94-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="27c94-112">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="27c94-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="27c94-113">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="27c94-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="27c94-114">Expanda la carpeta que contiene el proyecto o paquete que desee validar.</span><span class="sxs-lookup"><span data-stu-id="27c94-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="27c94-115">Haga clic con el botón derecho en el paquete o proyecto y, después, haga clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="27c94-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="27c94-116">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="27c94-116">Set the options on the General page</span></span>  
 <span data-ttu-id="27c94-117">**Entorno**</span><span class="sxs-lookup"><span data-stu-id="27c94-117">**Environment**</span></span>  
 <span data-ttu-id="27c94-118">Seleccione el entorno que desea usar para validar el proyecto o el paquete.</span><span class="sxs-lookup"><span data-stu-id="27c94-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="27c94-119">**Tiempo de ejecución de 32 bits**</span><span class="sxs-lookup"><span data-stu-id="27c94-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="27c94-120">Seleccione esta opción para usar un motor en tiempo de ejecución de 32 bits para ejecutar un paquete.</span><span class="sxs-lookup"><span data-stu-id="27c94-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="27c94-121">La pestaña **Parámetros** enumera los valores de parámetro que usa para validar el proyecto o el paquete.</span><span class="sxs-lookup"><span data-stu-id="27c94-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="27c94-122">A continuación se exponen las opciones de la pestaña Parámetros.</span><span class="sxs-lookup"><span data-stu-id="27c94-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="27c94-123">**Contenedor**</span><span class="sxs-lookup"><span data-stu-id="27c94-123">**Container**</span></span>  
 <span data-ttu-id="27c94-124">Muestra el objeto que contiene el parámetro.</span><span class="sxs-lookup"><span data-stu-id="27c94-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="27c94-125">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="27c94-125">**Parameter**</span></span>  
 <span data-ttu-id="27c94-126">Muestra el nombre de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="27c94-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="27c94-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="27c94-127">**Value**</span></span>  
 <span data-ttu-id="27c94-128">Muestra el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="27c94-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="27c94-129">La pestaña **Administradores de conexiones** enumera los valores de propiedad del administrador de conexión que usa para validar el proyecto o el paquete.</span><span class="sxs-lookup"><span data-stu-id="27c94-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="27c94-130">A continuación se exponen las opciones de la pestaña **Administradores de conexiones** .</span><span class="sxs-lookup"><span data-stu-id="27c94-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="27c94-131">**Contenedor**</span><span class="sxs-lookup"><span data-stu-id="27c94-131">**Container**</span></span>  
 <span data-ttu-id="27c94-132">Muestra el objeto que contiene el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="27c94-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="27c94-133">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="27c94-133">**Name**</span></span>  
 <span data-ttu-id="27c94-134">Muestra el nombre del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="27c94-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="27c94-135">**Nombre de propiedad**</span><span class="sxs-lookup"><span data-stu-id="27c94-135">**Property name**</span></span>  
 <span data-ttu-id="27c94-136">Muestra el nombre de la propiedad del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="27c94-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="27c94-137">**Valor**</span><span class="sxs-lookup"><span data-stu-id="27c94-137">**Value**</span></span>  
 <span data-ttu-id="27c94-138">Muestra el valor asignado a la propiedad del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="27c94-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
