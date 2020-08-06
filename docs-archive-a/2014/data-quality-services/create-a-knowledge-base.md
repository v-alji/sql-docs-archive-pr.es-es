---
title: Crear una base de conocimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663732"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="cae92-102">Crear una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="cae92-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="cae92-103">En este tema se describe cómo crear una base de conocimiento en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) y cómo prepararla para la administración de dominios, la detección de conocimiento o la adición de una directiva de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="cae92-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cae92-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cae92-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cae92-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cae92-105">Prerequisites</span></span>  
 <span data-ttu-id="cae92-106">Para crear una base de conocimiento, debe tener instalado [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] y [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae92-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cae92-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cae92-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cae92-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="cae92-108">Permissions</span></span>  
 <span data-ttu-id="cae92-109">Para crear una base de conocimiento, debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="cae92-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="cae92-110">Crear una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="cae92-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="cae92-111">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="cae92-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="cae92-112">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Nueva base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="cae92-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="cae92-113">Escriba un nombre y una descripción para la nueva base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="cae92-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="cae92-114">En **Crear base de conocimiento a partir de**, seleccione en qué desea basar la base de conocimiento:</span><span class="sxs-lookup"><span data-stu-id="cae92-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="cae92-115">Seleccione **Ninguno** si no desea basar la nueva base de conocimiento en una base de conocimiento o un archivo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="cae92-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="cae92-116">Seleccione **Base de conocimiento existente** para basar la nueva base de conocimiento en una base de conocimiento ya existente en [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], o en la base de conocimiento predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cae92-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="cae92-117">Seleccione la base de conocimiento en la lista desplegable **Seleccionar la base de conocimiento** , o haga clic en **Examinar** para mostrar el cuadro de diálogo **Seleccione una base de conocimiento** , seleccione la base de conocimiento existente en la que desea basar la nueva y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cae92-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="cae92-118">Al seleccionar una base de conocimiento en la tabla, los dominios y las reglas de coincidencia de la base de conocimiento se mostrarán en el panel derecho del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cae92-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="cae92-119">También puede seleccionar la base de conocimiento **Datos de DQS** , la base de conocimiento predeterminada que contiene dominios e información habituales relacionados con datos de empresas, direcciones y partidos de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="cae92-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="cae92-120">Seleccione **Importar desde el archivo DQS** para basar la nueva base de conocimiento en un archivo DQS de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae92-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="cae92-121">Haga clic en **Examinar**, seleccione un archivo de datos DQS con la extensión .dqs y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cae92-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cae92-122">En **Seleccione la actividad**, seleccione la actividad que desea realizar en la nueva base de conocimiento:</span><span class="sxs-lookup"><span data-stu-id="cae92-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="cae92-123">Seleccione **Administración de dominios** para crear la base de conocimiento y pasar a las pantallas que se utilizan para modificar los dominios de esta.</span><span class="sxs-lookup"><span data-stu-id="cae92-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="cae92-124">Seleccione **Detección de conocimiento** para crear la base de conocimiento e iniciar el asistente que se usa para analizar una muestra de datos y rellenar los dominios de la base de conocimiento con los resultados.</span><span class="sxs-lookup"><span data-stu-id="cae92-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="cae92-125">Seleccione **Directiva de coincidencia** para crear una directiva de coincidencia y agregarla a la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="cae92-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="cae92-126">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="cae92-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="cae92-127">Seguimiento: después de crear una base de conocimiento</span><span class="sxs-lookup"><span data-stu-id="cae92-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="cae92-128">Una vez creada la base de conocimiento, aparecerá un asistente que podrá utilizar para realizar la detección de conocimiento, un asistente para crear una directiva de coincidencia o varias páginas que le permitirán realizar la administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="cae92-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="cae92-129">Para más información sobre la detección de conocimiento, la administración de dominios o la directiva de coincidencia, vea [Realizar la detección de conocimiento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md) o [Crear una directiva de coincidencia](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="cae92-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
