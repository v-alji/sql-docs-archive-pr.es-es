---
title: Administrar (abrir, desbloquear, cambiar el nombre y eliminar) un proyecto de calidad de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676668"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="fe5ee-102">Administrar (abrir, desbloquear, cambiar nombre y eliminar) un proyecto de calidad de los datos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="fe5ee-103">En este tema se describe cómo administrar un proyecto de calidad de datos mediante [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , realizando acciones tales como abrirlo, desbloquearlo, cambiarle el nombre y eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe5ee-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fe5ee-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="fe5ee-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fe5ee-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fe5ee-106">No es posible abrir un proyecto bloqueado creado por otro usuario.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="fe5ee-107">No se puede desbloquear ni eliminar un proyecto de calidad de datos creado por otro usuario, ni tampoco cambiarle el nombre.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="fe5ee-108">No es posible eliminar un proyecto de calidad de datos bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="fe5ee-109">Para poder eliminarlo, primero debe desbloquearlo.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="fe5ee-110">Solo se podrán desbloquear los proyectos de calidad de datos creados por uno mismo.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fe5ee-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-111">Prerequisites</span></span>  
 <span data-ttu-id="fe5ee-112">Debe disponer al menos de un proyecto de calidad de datos que administrar.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe5ee-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fe5ee-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe5ee-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-114">Permissions</span></span>  
 <span data-ttu-id="fe5ee-115">Debe disponer del rol dqs_kb_editor o dqs_kb_operator en la base de datos DQS_MAIN para administrar un proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="fe5ee-116">Abrir un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fe5ee-117">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe5ee-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fe5ee-118">En la [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] pantalla principal, haga clic en **Abrir proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="fe5ee-119">Aparece la pantalla **Abrir proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fe5ee-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="fe5ee-120">O bien, puede abrir directamente uno de los proyectos de calidad de datos mostrados en el área **Proyecto de calidad de datos reciente** haciendo clic en él.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="fe5ee-121">En la pantalla **Abrir proyecto** , haga clic para seleccionar el proyecto de calidad de datos que desea abrir y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="fe5ee-122">El proyecto de calidad de datos se abre en el mismo estado de la actividad en que se cerró por última vez.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="fe5ee-123">Un proyecto de calidad de datos tiene los estados siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe5ee-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="fe5ee-124">En la actividad **limpieza** , un proyecto de calidad de datos puede tener los Estados siguientes: **limpieza: asignar**, **limpieza: limpiar**, **limpieza: administrar y ver resultados**y **limpieza-exportar**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="fe5ee-125">En el caso de la actividad de **búsqueda de coincidencias** , un proyecto de calidad de datos puede tener los siguientes Estados: **coincidencia de asignación** **, coincidencia de coincidencia**, **permanencia de coincidencia**y **búsqueda de coincidencias**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="fe5ee-126">Desbloquear un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="fe5ee-127">Cuando se crea un proyecto de calidad de datos, queda bloqueado para evitar su uso o modificación por parte de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="fe5ee-128">Si desea que otros usuarios puedan trabajar en el proyecto de calidad de datos, deberá desbloquearlo después de finalizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="fe5ee-129">Para los proyectos que están bloqueados se muestra un símbolo con un candado.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fe5ee-130">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe5ee-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fe5ee-131">En la [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] pantalla principal, haga clic en **Abrir proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="fe5ee-132">Aparece la pantalla **Abrir proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fe5ee-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="fe5ee-133">En la pantalla **Abrir proyecto** , haga clic con el botón secundario en un proyecto de calidad de datos bloqueado que haya creado y, a continuación, haga clic en **Desbloquear** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="fe5ee-134">Se muestra una marca de verificación verde que indicará que el proyecto está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> <span data-ttu-id="fe5ee-135">Cambiar el nombre de un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fe5ee-136">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe5ee-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fe5ee-137">En la [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] pantalla principal, haga clic en **Abrir proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="fe5ee-138">Aparece la pantalla **Abrir proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fe5ee-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="fe5ee-139">En la pantalla **Abrir proyecto** , haga clic con el botón secundario en un proyecto de calidad de datos que haya creado y, a continuación, haga clic en **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="fe5ee-140">Podrá editar el nombre del proyecto de calidad de datos en la columna **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="fe5ee-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="fe5ee-141">Escriba un nuevo nombre y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> <span data-ttu-id="fe5ee-142">Eliminar un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="fe5ee-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fe5ee-143">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe5ee-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fe5ee-144">En la [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] pantalla principal, haga clic en **Abrir proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="fe5ee-145">Aparece la pantalla **Abrir proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fe5ee-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="fe5ee-146">En la pantalla **Abrir proyecto** , haga clic con el botón secundario en un proyecto de calidad de datos desbloqueado que haya creado y, a continuación, haga clic en **Eliminar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="fe5ee-147">Aparece un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-147">A confirmation message appears.</span></span> <span data-ttu-id="fe5ee-148">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fe5ee-148">Click **Yes**.</span></span>  
  
  
