---
title: Crear un proyecto de calidad de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744311"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="9e389-102">Crear un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="9e389-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="9e389-103">En este tema se describe cómo crear un proyecto de calidad de datos mediante [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e389-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="9e389-104">Un proyecto de calidad de datos se utiliza para ejecutar la actividad de limpieza o de búsqueda de coincidencias en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="9e389-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9e389-105">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9e389-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9e389-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e389-106">Prerequisites</span></span>  
 <span data-ttu-id="9e389-107">Debe disponer de una base de conocimiento apropiada para su uso en el proyecto de calidad de datos para la actividad de limpieza o de búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="9e389-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9e389-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9e389-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9e389-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="9e389-109">Permissions</span></span>  
 <span data-ttu-id="9e389-110">Debe disponer del rol dqs_kb_editor o dqs_kb_operator en la base de datos DQS_MAIN para crear un proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="9e389-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="9e389-111">Crear un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="9e389-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9e389-112">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="9e389-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9e389-113">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Nuevo proyecto de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="9e389-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="9e389-114">En la pantalla **Nuevo proyecto de calidad de datos** :</span><span class="sxs-lookup"><span data-stu-id="9e389-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="9e389-115">En el cuadro **Nombre** , escriba el nombre del nuevo proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="9e389-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="9e389-116">(Opcional) En el cuadro **Descripción** , escriba una descripción para el nuevo proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="9e389-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="9e389-117">Haga clic en la lista **Usar base de conocimiento** para seleccionar la base de conocimiento que se utilizará para el proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="9e389-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="9e389-118">El área **Detalles de la base de conocimiento: <nombre_base_conocimiento>** situada en el lado derecho muestra los nombres de dominio disponibles en la base de conocimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9e389-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="9e389-119">En el área **Seleccione la actividad** , haga clic en la actividad que desea realizar utilizando este proyecto de calidad de datos:</span><span class="sxs-lookup"><span data-stu-id="9e389-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="9e389-120">**Limpieza**: seleccione esta actividad para limpiar los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9e389-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="9e389-121">**Coincidencia**: seleccione esta actividad para realizar la búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="9e389-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="9e389-122">Esta actividad solo está disponible si la base de conocimiento seleccionada para el proyecto de calidad de datos contiene una directiva de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="9e389-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="9e389-123">Haga clic en **Crear** para crear un proyecto de calidad de datos.</span><span class="sxs-lookup"><span data-stu-id="9e389-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a><span data-ttu-id="9e389-124">Seguimiento: después de crear un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="9e389-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="9e389-125">Una vez creado el proyecto de calidad de datos, aparecerá un asistente que podrá utilizar para realizar la actividad seleccionada: limpieza o búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="9e389-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="9e389-126">Para más información sobre las actividades de limpieza y de búsqueda de coincidencias, vea [Limpieza de datos](../../2014/data-quality-services/data-cleansing.md) y [Coincidencia de datos](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="9e389-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
