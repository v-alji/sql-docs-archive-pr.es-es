---
title: Importar una base de conocimiento desde un archivo .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746559"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="a17d0-102">Importar una base de conocimiento desde un archivo .dqs</span><span class="sxs-lookup"><span data-stu-id="a17d0-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="a17d0-103">En este tema se describe cómo importar una base de conocimiento completa desde un archivo de datos .dqs en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a17d0-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="a17d0-104">Para crear el archivo de datos, debe exportar una base de conocimiento existente desde la aplicación [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (vea [exportar una Base de conocimiento a un archivo .dqs](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="a17d0-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="a17d0-105">El uso de un archivo de datos .dqs para exportar el contenido de una base de conocimiento e importarlo a continuación en otra base de conocimiento del mismo [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] o de otro [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifica el proceso de generación del conocimiento, lo que permite ahorrar tiempo y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="a17d0-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="a17d0-106">Le permite compartir con los demás una base de conocimiento y su conocimiento, lo que se traduce en un ahorro de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a17d0-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="a17d0-107">El archivo .dqs contendrá toda la información de la base de conocimiento, incluido los dominios y la directiva de coincidencia, salvo la información de datos de referencia adjunta.</span><span class="sxs-lookup"><span data-stu-id="a17d0-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="a17d0-108">Se importarán tanto los datos publicados como los no publicados.</span><span class="sxs-lookup"><span data-stu-id="a17d0-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="a17d0-109">El archivo de datos .dqs está cifrado, por lo que no se puede ver.</span><span class="sxs-lookup"><span data-stu-id="a17d0-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="a17d0-110">Al importar una base de conocimiento, puede utilizar el mismo nombre, a menos que este exista ya en la aplicación cliente, en cuyo caso deberá cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="a17d0-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a17d0-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a17d0-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a17d0-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a17d0-112">Prerequisites</span></span>  
 <span data-ttu-id="a17d0-113">Para importar una base de conocimiento desde un archivo de .dqs, antes debe haberla exportado al archivo .dqs.</span><span class="sxs-lookup"><span data-stu-id="a17d0-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a17d0-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a17d0-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a17d0-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="a17d0-115">Permissions</span></span>  
 <span data-ttu-id="a17d0-116">Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para importar una base de conocimiento desde un archivo de datos .dqs.</span><span class="sxs-lookup"><span data-stu-id="a17d0-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="a17d0-117">Importar una base de conocimiento desde un archivo. DQS</span><span class="sxs-lookup"><span data-stu-id="a17d0-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a17d0-118">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a17d0-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a17d0-119">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Nueva base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="a17d0-120">Escriba un nombre para la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="a17d0-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="a17d0-121">Haga clic en la flecha abajo de **Crear base de conocimiento a partir de**y, a continuación, seleccione **Importar desde el archivo DQS**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="a17d0-122">En **Seleccionar archivo de datos**, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="a17d0-123">En el cuadro de diálogo **Importar de archivo de datos** , desplácese a la carpeta que contiene el archivo .dqs que desea importar y, a continuación, haga clic en el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="a17d0-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="a17d0-124">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="a17d0-125">Compruebe que en la lista **Dominios** aparecen la base de conocimiento y los dominios correctos.</span><span class="sxs-lookup"><span data-stu-id="a17d0-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="a17d0-126">Seleccione la actividad que desea realizar y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="a17d0-127">En el cuadro de diálogo **Importar base de conocimiento** , compruebe que la línea de estado indica que se ha completado la importación.</span><span class="sxs-lookup"><span data-stu-id="a17d0-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="a17d0-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="a17d0-129">Finalice las tareas de detección de conocimiento, administración de dominios o directiva de coincidencia que necesita realizar y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="a17d0-130">Haga clic en **Publicar** para publicar el conocimiento en la base de conocimiento, o en **No** si prefiere no hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a17d0-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="a17d0-131">Si opta por publicar la base de conocimiento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="a17d0-132">En la página de inicio de Data Quality Services, compruebe que la base de conocimiento aparece debajo de **Base de conocimiento reciente**.</span><span class="sxs-lookup"><span data-stu-id="a17d0-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="a17d0-133">Seguimiento: después de importar una base de conocimiento desde un archivo .dqs</span><span class="sxs-lookup"><span data-stu-id="a17d0-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="a17d0-134">Después de importar una base de conocimiento desde un archivo .dqs, puede agregar conocimiento a la base de conocimiento o utilizarla en un proyecto de limpieza o de búsqueda de coincidencias, dependiendo de su contenido.</span><span class="sxs-lookup"><span data-stu-id="a17d0-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="a17d0-135">Para más información, vea [Realizar la detección de conocimiento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md), [Administrar un dominio compuesto](../../2014/data-quality-services/managing-a-composite-domain.md), [Crear una directiva de coincidencia](../../2014/data-quality-services/create-a-matching-policy.md), [Limpieza de datos](../../2014/data-quality-services/data-cleansing.md) o [Coincidencia de datos](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="a17d0-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
