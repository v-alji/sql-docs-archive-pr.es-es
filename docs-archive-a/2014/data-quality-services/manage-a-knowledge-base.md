---
title: Administrar una base de conocimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676681"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="a5093-102">Administrar una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="a5093-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="a5093-103">En este tema se describe cómo realizar funciones de administración en una base de conocimiento de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a5093-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="a5093-104">Puede eliminar una base de conocimiento, desbloquearla, descartar los cambios realizados en ella, cambiarle el nombre y mostrar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="a5093-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5093-105">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a5093-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a5093-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a5093-106">Prerequisites</span></span>  
 <span data-ttu-id="a5093-107">Para administrar una base de conocimiento, previamente esta debe haberse creado y estar publicada (si la ha creado otra persona) o cerrada (si la ha creado usted).</span><span class="sxs-lookup"><span data-stu-id="a5093-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5093-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a5093-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a5093-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="a5093-109">Permissions</span></span>  
 <span data-ttu-id="a5093-110">Para abrir una base de conocimiento, debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a5093-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="a5093-111">Administrar una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="a5093-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a5093-112">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5093-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a5093-113">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="a5093-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="a5093-114">Haga clic con el botón secundario en una base de conocimiento de la tabla de bases de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="a5093-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="a5093-115">En el menú contextual, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5093-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="a5093-116">**Abrir**: haga clic aquí para abrir la base de conocimiento de la actividad seleccionada en el panel **Seleccione la actividad** .</span><span class="sxs-lookup"><span data-stu-id="a5093-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="a5093-117">**Desbloquear**: puede desbloquear la base de conocimiento si es el usuario que estaba trabajando con ella en uno de los pasos de la actividad de administración de dominios, de detección de conocimiento y de directiva de coincidencia, y la cerró.</span><span class="sxs-lookup"><span data-stu-id="a5093-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="a5093-118">Si desbloquea la base de conocimiento, otra persona podrá abrirla y trabajar con ella.</span><span class="sxs-lookup"><span data-stu-id="a5093-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="a5093-119">Este comando no está disponible si la base de conocimiento no se encuentra en un estado de una actividad.</span><span class="sxs-lookup"><span data-stu-id="a5093-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="a5093-120">Para obtener más información, vea [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="a5093-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="a5093-121">**Descartar trabajo**: haga clic aquí si se está trabajando actualmente en la base de conocimiento, lo que se indica con una entrada en el campo Estado de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a5093-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="a5093-122">Este comando no está disponible si la base de conocimiento no se encuentra en un estado de una actividad, ni tampoco si está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="a5093-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="a5093-123">Para obtener más información, vea [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="a5093-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="a5093-124">**Cambiar nombre**: haga clic aquí para editar el campo Base de conocimiento de la tabla de la base de conocimiento en la que hizo clic con el botón secundario.</span><span class="sxs-lookup"><span data-stu-id="a5093-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="a5093-125">Cambie el nombre y, a continuación, haga clic en esa base de conocimiento y haga clic de nuevo en el campo para aceptar el cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="a5093-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="a5093-126">**Eliminar**: haga clic aquí para quitar la base de conocimiento de la base de datos DQS_MAIN de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5093-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="a5093-127">**Propiedades**: haga clic aquí para mostrar las propiedades de la base de datos en una presentación de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a5093-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="a5093-128">**Base de conocimiento de origen**: la base de conocimiento en la que está basada esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="a5093-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="a5093-129">De uso opcional.</span><span class="sxs-lookup"><span data-stu-id="a5093-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="a5093-130">**Estado**: indica si la base de conocimiento se encuentra en el estado **Trabajando** y si está en una actividad específica de administración de conocimiento, según se determinó cuando se cerró por última vez.</span><span class="sxs-lookup"><span data-stu-id="a5093-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="a5093-131">El estado puede ser **Trabajando**, en el que la base de conocimiento se abre en una sesión de administración de conocimiento, pero no en una actividad específica, o **Trabajando** más una actividad de administración de conocimiento, en el que la base de conocimiento se abre en una sesión de administración de conocimiento y en una actividad específica.</span><span class="sxs-lookup"><span data-stu-id="a5093-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="a5093-132">**Está bloqueada**: **True** si la base de conocimiento está bloqueada, **False** en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a5093-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="a5093-133">**Incluye contenido sin publicar**: True si la base de conocimiento incluye contenido que no se ha guardado mediante la publicación, False en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a5093-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="a5093-134">**Bloqueada por**: el nombre del usuario que cerró la base de conocimiento, bloqueándola.</span><span class="sxs-lookup"><span data-stu-id="a5093-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="a5093-135">**Fecha de bloqueo**: la fecha en la que se bloqueó.</span><span class="sxs-lookup"><span data-stu-id="a5093-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="a5093-136">**Creada por**: el nombre del usuario que creó la base de conocimiento, junto con la red a la que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="a5093-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="a5093-137">**Fecha de creación**: la fecha en la que se creó.</span><span class="sxs-lookup"><span data-stu-id="a5093-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="a5093-138">Seguimiento: después de administrar una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="a5093-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="a5093-139">Después de administrar una base de conocimiento, el paso siguiente dependerá de la acción que haya realizado en ella:</span><span class="sxs-lookup"><span data-stu-id="a5093-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="a5093-140">Si abrió la base de conocimiento, continuará en la actividad que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="a5093-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="a5093-141">Si la desbloqueó, otras personas podrán abrirla y trabajar en ella, en el estado indicado.</span><span class="sxs-lookup"><span data-stu-id="a5093-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="a5093-142">Si descartó los cambios realizados en ella, la base de conocimiento estará disponible en el estado publicado por última vez.</span><span class="sxs-lookup"><span data-stu-id="a5093-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="a5093-143">Si la cambió de nombre, tendrá que abrirla de nuevo para poder trabajar en ella.</span><span class="sxs-lookup"><span data-stu-id="a5093-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="a5093-144">Si la eliminó, deberá seleccionar otra base de conocimiento en la que trabajar, o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="a5093-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
