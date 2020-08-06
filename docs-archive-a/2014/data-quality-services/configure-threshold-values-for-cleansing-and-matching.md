---
title: Configurar los valores de umbral para la limpieza y la coincidencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744319"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="e92a7-102">Configurar los valores de umbral para la limpieza y coincidencia</span><span class="sxs-lookup"><span data-stu-id="e92a7-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="e92a7-103">En este tema se describe cómo configurar los valores de umbral que se utilizarán durante las actividades de limpieza y búsqueda de coincidencias asistidas por PC en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="e92a7-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e92a7-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e92a7-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e92a7-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e92a7-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e92a7-106">Permisos</span><span class="sxs-lookup"><span data-stu-id="e92a7-106">Permissions</span></span>  
 <span data-ttu-id="e92a7-107">Para configurar estos valores de umbral, debe disponer del rol dqs_administrator en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="e92a7-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="e92a7-108">Configurar los valores de umbral</span><span class="sxs-lookup"><span data-stu-id="e92a7-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="e92a7-109">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="e92a7-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="e92a7-110">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="e92a7-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="e92a7-111">A continuación, haga clic en la pestaña **Configuración general** . Esta pestaña le permite especificar los valores de umbral para la limpieza y las actividades coincidentes.</span><span class="sxs-lookup"><span data-stu-id="e92a7-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="e92a7-112">Para establecer los valores de umbral para la actividad de limpieza, especifique los valores adecuados en los cuadros siguientes del área **Limpieza interactiva** :</span><span class="sxs-lookup"><span data-stu-id="e92a7-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="e92a7-113">**Puntuación mínima para sugerencias**: la puntuación mínima o el nivel de confianza que utilizará DQS para sugerir reemplazos para un valor durante el proceso de limpieza asistida por PC.</span><span class="sxs-lookup"><span data-stu-id="e92a7-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="e92a7-114">Escriba un valor en la notación decimal del valor de porcentaje correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e92a7-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="e92a7-115">Por ejemplo, escriba 0,75 para un porcentaje del 75%.</span><span class="sxs-lookup"><span data-stu-id="e92a7-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="e92a7-116">Este valor debe ser menor o igual que el valor especificado en el cuadro **Puntuación mínima de correcciones automáticas** .</span><span class="sxs-lookup"><span data-stu-id="e92a7-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="e92a7-117">El valor predeterminado es 0,7.</span><span class="sxs-lookup"><span data-stu-id="e92a7-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="e92a7-118">**Puntuación mínima de correcciones automáticas**: la puntuación mínima o el nivel de confianza que utilizará DQS para corregir automáticamente un valor durante el proceso de limpieza asistida por PC.</span><span class="sxs-lookup"><span data-stu-id="e92a7-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="e92a7-119">Escriba un valor en la notación decimal del valor de porcentaje correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e92a7-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="e92a7-120">Por ejemplo, escriba 0,9 para un porcentaje del 90%.</span><span class="sxs-lookup"><span data-stu-id="e92a7-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="e92a7-121">El valor predeterminado es 0,8.</span><span class="sxs-lookup"><span data-stu-id="e92a7-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="e92a7-122">Para establecer el valor de umbral para la actividad de búsqueda de coincidencias, especifique un valor en el cuadro **Puntuación de registro mínima** en el área **Coincidencia** .</span><span class="sxs-lookup"><span data-stu-id="e92a7-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="e92a7-123">Este valor indica la puntuación mínima necesaria para que un registro se considere como una coincidencia de otro.</span><span class="sxs-lookup"><span data-stu-id="e92a7-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="e92a7-124">El valor predeterminado es 80 %.</span><span class="sxs-lookup"><span data-stu-id="e92a7-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="e92a7-125">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e92a7-125">Click **Close**.</span></span>  
  
  
