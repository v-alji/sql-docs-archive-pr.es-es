---
title: Página nuevo informe vinculado (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675233"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="3bd92-102">Nuevo informe vinculado (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="3bd92-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="3bd92-103">Use la página Nuevo informe vinculado para crear un informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="3bd92-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="3bd92-104">Un informe vinculado es un informe con una configuración y propiedades propias pero que está vinculado a la definición de otro informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="3bd92-105">Los informes vinculados son de gran utilidad cuando se dispone de un informe base que se desea modificar para determinados grupos o usuarios; por ejemplo, un informe regional que devuelva datos diferentes en función del código de región que especifique como parámetro.</span><span class="sxs-lookup"><span data-stu-id="3bd92-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="3bd92-106">Normalmente, un informe vinculado se crea a partir de un informe parametrizado cuando se desea modificar y después guardar distintos valores de parámetro con cada instancia del informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="3bd92-107">No obstante, se puede crear un informe vinculado a partir de cualquier informe al que se tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="3bd92-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="3bd92-108">Un informe vinculado puede tener su propio nombre, descripción, ubicación, propiedades de parámetros, propiedades de ejecución de informes, propiedades del historial de informes, permisos y suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3bd92-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="3bd92-109">Sin embargo, los informes vinculados deben usar las propiedades del origen de datos y el diseño del informe base que proporciona la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="3bd92-110">Navegación</span><span class="sxs-lookup"><span data-stu-id="3bd92-110">Navigation</span></span>  
 <span data-ttu-id="3bd92-111">Utilice los procedimientos siguientes para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="3bd92-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="3bd92-112">Para abrir la página Nuevo informe vinculado desde la página Contenido</span><span class="sxs-lookup"><span data-stu-id="3bd92-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="3bd92-113">Abra el Administrador de informes y busque un informe para el que desee crear un informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="3bd92-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="3bd92-114">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3bd92-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="3bd92-115">En el menú desplegable, haga clic en **Crear informe vinculado**.</span><span class="sxs-lookup"><span data-stu-id="3bd92-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="3bd92-116">Para abrir la página Nuevo informe vinculado desde la página de propiedades General de un informe</span><span class="sxs-lookup"><span data-stu-id="3bd92-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="3bd92-117">Abra el Administrador de informes y busque un informe para el que desee crear un informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="3bd92-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="3bd92-118">Mantenga el mouse sobre el informe y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3bd92-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="3bd92-119">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="3bd92-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="3bd92-120">Se abrirá la página de propiedades General correspondiente al informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="3bd92-121">En la barra de herramientas del elemento, haga clic en **Crear informe vinculado**.</span><span class="sxs-lookup"><span data-stu-id="3bd92-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3bd92-122">Opciones</span><span class="sxs-lookup"><span data-stu-id="3bd92-122">Options</span></span>  
 <span data-ttu-id="3bd92-123">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3bd92-123">**Name**</span></span>  
 <span data-ttu-id="3bd92-124">Especifique el nombre del informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="3bd92-124">Specify the name of the linked report.</span></span> <span data-ttu-id="3bd92-125">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="3bd92-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="3bd92-126">También puede incluir espacios en blanco y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="3bd92-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="3bd92-127">Sin embargo, no deben utilizarse los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="3bd92-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="3bd92-128">: \@ & = +, $/\* \< > | "o/al especificar un nombre.</span><span class="sxs-lookup"><span data-stu-id="3bd92-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="3bd92-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3bd92-129">**Description**</span></span>  
 <span data-ttu-id="3bd92-130">Escriba una descripción del contenido del informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-130">Type a description of the report contents.</span></span> <span data-ttu-id="3bd92-131">Esta descripción se mostrará en la página Contenido a los usuarios que tengan permisos de acceso al informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="3bd92-132">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="3bd92-132">**Location**</span></span>  
 <span data-ttu-id="3bd92-133">Especifique la ruta de acceso a la carpeta que contiene el informe.</span><span class="sxs-lookup"><span data-stu-id="3bd92-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="3bd92-134">De manera predeterminada, los informes vinculados se crean como hermanos del informe base.</span><span class="sxs-lookup"><span data-stu-id="3bd92-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="3bd92-135">Haga clic en **Cambiar ubicación** para colocar el informe vinculado en una carpeta diferente.</span><span class="sxs-lookup"><span data-stu-id="3bd92-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="3bd92-136">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="3bd92-136">**OK**</span></span>  
 <span data-ttu-id="3bd92-137">Haga clic en **Aceptar** para guardar los cambios y volver a la página de propiedades General del informe base.</span><span class="sxs-lookup"><span data-stu-id="3bd92-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd92-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bd92-138">See Also</span></span>  
 <span data-ttu-id="3bd92-139">[Crear un informe vinculado](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="3bd92-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="3bd92-140">[Página de propiedades generales, informes &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3bd92-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="3bd92-141">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="3bd92-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
